---
layout: post
title: Exmaple ACID và BASE database
categories: Database
---

## Example

*link: https://daynhauhoc.com/t/tim-vi-du-thuc-te-ve-tinh-acid-va-base-cua-database/125618/8*

## Atomic
- Giao dịch chuyển tiền là 1 transaction gồm nhiều giao tác (check số dư, trừ tiền A, cộng tiền B, gửi thông báo, …). Transaction này hoặc thành công nếu tất cả giao tác đó thành công hoặc thất bại nếu chỉ một giao tác bất kỳ thất bại. Nếu trường hợp thất bại xảy ra thì CSDL phải có cơ chế rollback để khôi phục về trạng thái ban đầu xem như chưa có chuyện gì xảy ra (tiền của A vẫn còn nguyên)

## Durability

- Về Durability, cậu hiểu cơ bản khái niệm rồi. Tuy nhiên, tớ không nghĩ NoSQL durable đâu :smile:

NoSQL như cậu đã biết, thiết kế theo BASE. Vì lẽ đó, khi cậu gửi một request thay đổi/thêm/xóa dữ liệu tới NoSQL, cho dù NoSQL có trả lời cậu “OK”, nhưng nó không đồng nghĩa với việc dữ liệu của cậu đã được persist trên đĩa (nó sẽ được, nhưng ở một thời điểm nào đó trong tương lai).
Thiết kế này sẽ cho cậu một vài hệ quả:

    + NoSQL nhanh hơn SQL trong thời gian phản hồi.Đó là selling point của NoSQL, khi cậu không tốn cost persist dữ liệu vào disk (vốn đắt đỏ), mà thực hiện nó một cách bất đồng bộ về sau.Cậu có thể đã nhận thấy, có 1 khoảng thời gian từ lúc NoSQL trả về “OK”, tới lúc NoSQL thực sự persist dữ liệu vào disk.
    
    + Chuyện gì sẽ xảy ra nếu như server của cậu gặp vấn đề, như crash NoSQL, mất điện, etc? :smile: Dữ liệu chưa kịp persist vào disk sẽ bị mất ở trường hợp này, trong khi dữ liệu của SQL vẫn sẽ còn. Đấy là khả năng durability.

+ Vì vậy, trong TH thiết kế của cậu yêu cầu cao với tính nhất quán dữ liệu, cậu buộc phải cân nhắc SQL hơn là NoSQL. Sếp nào chịu được việc khi cậu gọi tới database để trừ tiền khách hàng, DB trả lời hoàn thành, nhưng cuối cùng, tiền thực ra chưa chắc sẽ bị trừ trong một số TH chứ? :smile:
    
- Vậy nên, MongoDB hay các NoSQL khác đều không thể đảm bảo durability trong mọi TH đâu.

## Consistency

Tính nhất quán, thật không may, cậu không hiểu đúng rồi.

Để hiểu về tính nhất quán, cậu cần hiểu 1 khái niệm, đó là data integrity - tính toàn vẹn dữ liệu. Tớ sẽ giải thích bằng ví dụ nhé! :smile:
Thử tưởng tượng cậu có một model mô phỏng dữ liệu thuộc về 1 giao dịch ngân hàng trong app của cậu. Model đó bao gồm:

    + Thông tin tài khoản gửi (số tài khoản, các ràng buộc như hạn mức, khả năng thực hiện giao dịch, số dư hiện tại, đơn vị tiền tệ…)
    + Thông tin tài khoản nhận (tương tự như tk gửi).
    + Số tiền (khoản tiền, đơn vị tiền tệ, tỷ giá tại thời điểm gửi…)

Cậu hẳn nhiên cần thiết kế database schema để lưu thông tin trên. Nó thường được lưu trữ ở các bảng/collection/khái niệm tương tự nào đó ở CSDL.
Giờ, nếu cậu cần chuyển 1 khoản tiền từ tài khoản người gửi sang tài khoản người nhận, cậu cần:

    + Kiểm tra số dư ở tài khoản gửi
    + Trừ tiền ở tài khoản gửi
    + Cộng tiền ở tài khoản nhận

Chuyện gì sẽ xảy ra nếu như sau khi cậu trừ tiền ở tài khoản gửi, nhưng gặp lỗi khi đang cố cộng tiền ở tài khoản nhận?

    + Nếu cậu không rollback lại trạng thái cũ, cậu sẽ có một model không toàn vẹn: số tiền gửi đã trừ, nhưng bên còn lại chưa nhận được.
    + Nếu cậu không dùng SQL transaction, khoảng thời gian giữa thời điểm trừ tiền ở tk gửi và cộng tiền ở tk nhận, model của cậu cũng không toàn vẹn về mặt logic.

Đó là consistency :smile: Về cơ bản, DB đảm bảo tính chất này sẽ đảm bảo cậu luôn có model toàn vẹn về mặt logic. Không thời điểm nào model của cậu bị sai về mặt logic cả :smile:

Database theo nguyên tắc BASE sẽ không thể đảm bảo tính toàn vẹn dữ liệu tại mọi thời điểm. Vậy nên, nếu cậu cần bảo vệ data integrity nghiêm ngặt (chẳng hạn, các thao tác liên quan tới tiền), cậu buộc phải cân nhắc DB có tính chất ACID, hoặc sử dụng NoSQL mà hi sinh availability (see CAP theorem 9).

## Isolation

- Tính chất này đảm bảo cho cậu các transaction khác nhau chạy độc lập với nhau. Điều đó có nghĩa là, việc đọc dữ liệu từ DB ở transaction này không bị ảnh hưởng bởi việc ghi dữ liệu ở transaction khác khi việc ghi này chưa được commit.

Với ví dụ ở phần “Consistency”, cậu có thể thấy nếu có 2 transaction cùng thực hiện chuyển khoản, 2 transaction này không nên ảnh hưởng lẫn nhau ở bất cứ thao tác đọc/ghi nào.

Liên quan tới tính chất này, cậu nên tìm hiểu thêm về **transaction isolation level** . Kiến thức này có thể hơi advance chút, nhưng nếu được, cậu nên biết nó có tồn tại, cho công việc của cậu ở tương lai :smile:

Tớ nghĩ qua ví dụ trên, cậu có thể hiểu hơn về ACID, thậm chí cả BASE. Nếu cậu có vấn đề gì về việc hiểu 2 tính chất này, cho tớ biết nhé!

# Câu hỏi 2: 

Dạ anh ơi cho em hỏi về trường hợp này có bị vi phạm tính nhất quán của dữ liệu không? Nếu không thì gọi là gì?
Ví dụ có một trường đại học, thầy hiệu trưởng muốn query database trường report chính xác số lượng sinh viên hiện tại đang theo học tại trường. Mà mỗi bộ phận lại đưa ra số liệu khác nhau. VD:

Hỏi phòng tài chính hiện tại trường có bao nhiêu sinh viên?

==> Phòng tài chính dựa vào số lượng sinh viên đã đóng tiền học phí để trả lời là 1000 sinh viên đã đóng học phí nên hiện tại có 1000 sinh viên.

Nếu hỏi phòng đào tạo trường có bao nhiêu sinh viên?

==> Phòng đào tạo kiểm tra thấy hệ thống có 1500 sinh có thời khóa biểu, được xếp lớp nên trả lời là 1500.

Cũng câu hỏi đó mà với ban tuyển sinh.

==> Ban tuyển sinh sẽ trả lời là 2000 sinh viên, vì đầu năm học đã duyệt 2000 hồ sơ ứng tuyển hợp lệ.

Nếu hỏi các thầy chủ nhiệm.

===> Sau khi cộng danh sách điểm danh mỗi buổi thì thống kê lại chỉ có 800 sinh viên điểm danh đầy đủ (những em còn lại mặc dù có tên trong danh sách nhưng vắng nên không biết còn đi học hay đã nghỉ luôn).

Nếu lấy dữ liệu từ máy quẹt thẻ trước cổng bảo vệ

===> Bác bảo vệ kiểm tra máy chấm công thì xuất report: “chỉ có 500 sinh viên ra vào cổng trường thường xuyên thôi, những em còn lại từ đầu năm tới giờ chưa thấy bước vào cổng trường”

Giả sử những số liệu đó là thật, không có ai gian dối hết. Vậy cuối cùng ngôi trường này hiện tại có bao nhiêu sinh viên? Thầy hiệu trưởng biết tin vào số liệu nào khi cấp dưới mỗi người thống kê ra một kiểu? Vậy thông tin tổng số sinh viên đang còn học hiện tại là chưa nhất quán đúng không anh?

## trả lời câu 2: 

Như @qloved nói, mỗi hệ thống có một concern khác nhau, nên số liệu của mỗi hệ thống cũng có ý nghĩa khác nhau. Các hệ thống cậu đề cập đều không chính xác trong việc trả lời câu hỏi “có bao nhiêu sinh viên trong trường?”.
Về cơ bản, ví dụ của cậu có lẽ không chính xác lắm về TH thực tế của việc số liệu không nhất quán đâu. Nếu cậu có ví dụ nào về 2 hệ thống cùng một concern, nhưng thiếu sự đồng bộ giữa 2 hệ thống, thì sẽ chính xác hơn.

## Cho ví dụ:

Lấy ví dụ ở một trường đại học, cậu có một hệ thống quản lý sinh viên, với khả năng tra cứu thông tin sinh viên, điểm số qua các kỳ, v.v.
Một ngày nọ, trường đó muốn xây dựng hệ thống đăng ký sách ở @library. Tất nhiên, họ muốn có thông tin toàn bộ sinh viên trong trường, đặc biệt là địa chỉ nhà, để trong TH cần họ có thể gửi thư tới tận nhà để lấy sách.

Tuy vậy, hệ thống quản lý được thiết kế tương đối kém, nên không có cách nào dễ dàng để lấy được thông tin sinh viên thông qua API, cũng như việc xây dựng lại hệ thống thông tin sinh viên lại từ đâu cũng sẽ tốn kém nguồn lực. Việc tích hợp hệ thống book sách vào hệ thống thông tin sinh viên cũng không ổn, vì 2 vấn đề đó không liên quan lắm tới nhau, và không ai muốn việc book trả sách có thể khiến cho cả trường không đăng ký nổi môn học :sweat_smile:
Một kỹ sư thông minh nào đó đã đưa ra giải pháp đơn giản, đấy là dump database ở bên hệ thống thông tin sinh viên, lọc dữ liệu, và insert nó vào database ở bên hệ thống book sách. Mỗi năm, họ chỉ cần làm việc đó 1 lần, do đặc thù của trường đại học.

Cơ mà, trong TH một sinh viên nào đó chuyển địa chỉ nhà, và khai báo với nhà trường, hệ thống thông tin của trường sẽ có thông tin mới nhất, nhưng hệ thống book sách lại vẫn còn dữ liệu cũ, và chỉ có thể được update lại ở đầu năm học. Điều đó dẫn tới sự thiếu nhất quán về dữ liệu giữa 2 hệ thống.

Đó là ví dụ cho sự thiếu nhất quán dữ liệu giữa 2 hệ thống :smile: 2 hệ thống trên đều quan tâm tới model sinh viên, nhưng có khả năng trả về 2 kết quả khác nhau cho 1 sinh viên.

# Câu hỏi 3:

Không biết có thể tạo transaction cho client khi connect với server qua REST API giống như cách mà web server tạo transaction với DBMS không ạ? Ví dụ client là web SPA hoặc mobile app thực hiện giao dịch là mua hàng, để tạo đơn cần phải gọi rất nhiều API phía server mới hoàn tất một giao dịch.

Theo cá nhân em nghĩ nếu để cho client call quá nhiều API cho một task nào đó thì lỗi do ông thiết kế backend sai đúng không ạ? Backend phải tối ưu enpoint làm sao để cho client chỉ cần tạo một HTTP request POST duy nhất là tạo được đơn hàng.

Em có tham khảo cuộc thảo luận ở đây nhưng chẳng hiểu gì cả https://stackoverflow.com/questions/147207/transactions-in-rest 4

Mong được khai sáng và chia sẻ kinh nghiệm. Em cảm ơn.

## Trả lời câu 3:

Cậu đúng về việc nên chỉ có 1 endpoint cho một việc nào đó, để front end/app gọi tới. Cơ mà, tớ không nghĩ có thể quy trách nhiệm đó ở backend :sweat_smile:
Backend thường sẽ expose cho cậu các endpoint để các app/client/front-end có thể tùy biến sử dụng. Thường các endpoint đó được thiết kế làm một việc cụ thể, và thường một business flow sẽ cần phải làm nhiều việc khác nhau.

Thường, việc tạo ra 1 endpoint duy nhất như cậu mong muốn sẽ thường được đặt ở các tầng aggregate service (tầng này tổng hợp dữ liệu từ nhiều service để đưa ra 1 model), hoặc được đặt ở BFF (Backend For Front-end). Owner của aggregate service có thể là của backend team (nếu các client đều sử dụng dữ liệu đó), và BFF thường thuộc về front-end (nơi họ có thể tự tùy biến các thao tác theo nghiệp vụ của họ).

Ngoài ra, gần như không thể optimize các endpoint sao cho chỉ có 1 endpoint cho một công việc :sweat_smile: Ngay ở ví dụ trên về việc tạo order, logic tớ kể trên là ví dụ cơ bản, trong thực tế, có rất nhiều payment method ở domain EC. Có payment method phải được thực hiện:

    + Trước khi tạo order (credit card chẳng hạn, vì cậu sẽ buộc phải authorize payment transaction thông qua một hệ thống nào đó)

    + Trong lúc tạo order (ví Momo, Paypal chẳng hạn).

    + Sau khi tạo order (Cash On Delivery).

Điều này khiến cho việc có 1 endpoint duy nhất để phục vụ tất cả mọi business scenario gần như bất khả thi ở các domain phức tạp.

Hi vọng tớ đã trả lời được các thắc mắc của c