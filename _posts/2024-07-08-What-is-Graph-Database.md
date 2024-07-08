---
layout: post
title: Graph-database
categories: Graph-database
---

## Graph-database

Một cơ sở dữ liệu đồ thị là một bộ sưu tập dữ liệu có hệ thống nhấn mạnh vào các mối quan hệ giữa các thực thể dữ liệu khác nhau.
Cơ sở dữ liệu NoSQL này sử dụng lý thuyết đồ thị toán học để hiển thị các kết nối dữ liệu.
Khác với cơ sở dữ liệu quan hệ lưu trữ dữ liệu trong cấu trúc bảng cứng nhắc, cơ sở dữ liệu đồ thị lưu trữ dữ liệu dưới dạng mạng lưới các thực thể và mối quan hệ. 
Do đó, các cơ sở dữ liệu này thường cung cấp hiệu suất và linh hoạt tốt hơn vì chúng phù hợp hơn cho việc mô hình hóa các kịch bản thực tế.

## Đồ thị

- Thuật ngữ "đồ thị" bắt nguồn từ lĩnh vực toán học. Một đồ thị bao gồm một tập hợp các nút và cạnh.

## Nút

- Nút là các đỉnh lưu trữ các đối tượng dữ liệu. Mỗi nút có thể có vô số quan hệ và loại quan hệ.

## Cạnh

- Cạnh biểu thị các mối quan hệ giữa các nút. Ví dụ, cạnh có thể mô tả mối quan hệ cha-mẹ, hành động hoặc sở hữu. Cạnh có thể biểu thị cả các mối quan hệ một-nhiều và nhiều-nhiều. Một cạnh luôn có một nút bắt đầu, nút kết thúc, loại và hướng.

## Thuộc tính (Properties)

- Mỗi nút có thuộc tính hoặc các thuộc tính mô tả nó. Trong một số trường hợp, các cạnh cũng có thuộc tính. Đồ thị có thuộc tính còn được gọi là đồ thị thuộc tính. (property graphs)

## Các ứng dụng của cơ sở dữ liệu đồ thị

Các cơ sở dữ liệu đồ thị có lợi thế trong các trường hợp sử dụng như mạng xã hội, hệ thống đề xuất và phát hiện gian lận khi xây dựng các mối quan hệ giữa dữ liệu và truy vấn nhanh chóng các mối quan hệ này.

    - **Phát hiện gian lận:** Cơ sở dữ liệu đồ thị có khả năng ngăn chặn gian lận phức tạp. Ví dụ, bạn có thể sử dụng các mối quan hệ trong cơ sở dữ liệu đồ thị để xử lý các giao dịch tài chính gần thời gian thực. Với các truy vấn đồ thị nhanh, bạn có thể phát hiện ra rằng một người mua tiềm năng đang sử dụng cùng địa chỉ email và thẻ tín dụng được bao gồm trong một vụ gian lận đã biết. Cơ sở dữ liệu đồ thị cũng có thể giúp bạn phát hiện gian lận thông qua các mẫu mối quan hệ, như nhiều người liên quan đến cùng một địa chỉ email cá nhân hoặc nhiều người chia sẻ cùng một địa chỉ IP nhưng sống tại các vị trí vật lý khác nhau.

    - **Hệ thống đề xuất:** Mô hình đồ thị là lựa chọn tốt cho các ứng dụng cung cấp các đề xuất. Bạn có thể lưu trữ các mối quan hệ đồ thị giữa các danh mục thông tin như sở thích của khách hàng, bạn bè và lịch sử mua hàng. Bạn có thể sử dụng một cơ sở dữ liệu đồ thị có sẵn cao để đưa ra các đề xuất sản phẩm cho người dùng dựa trên các sản phẩm được mua bởi những người khác có sở thích và lịch sử mua hàng tương tự. Bạn cũng có thể xác định những người có bạn chung nhưng chưa biết nhau và sau đó đưa ra khuyến nghị kết bạn.

    - **Tối ưu hóa tuyến đường:** Các vấn đề tối ưu hóa tuyến đường liên quan đến phân tích tập dữ liệu và tìm ra các giá trị phù hợp nhất cho một kịch bản cụ thể. Ví dụ, bạn có thể sử dụng một cơ sở dữ liệu đồ thị để tìm ra:
        + Đoạn đường ngắn nhất từ điểm A đến B trên bản đồ bằng cách xem xét các con đường khác nhau.
        + Nhân viên phù hợp nhất cho một ca làm việc cụ thể bằng cách phân tích sự có mặt khác nhau, địa điểm và kỹ năng.
        + Thiết bị tối ưu cho các hoạt động bằng cách xem xét các thông số như chi phí và tuổi thọ của thiết bị.

    Các truy vấn đồ thị có thể phân tích những tình huống này nhanh chóng hơn vì chúng có thể đếm và so sánh số lượng liên kết giữa hai nút

    - **Khám phá mẫu:** Cơ sở dữ liệu đồ thị rất phù hợp để khám phá các mối quan hệ phức tạp và các mẫu ẩn trong dữ liệu. Ví dụ, một công ty mạng xã hội sử dụng cơ sở dữ liệu đồ thị để phân biệt giữa tài khoản bot và tài khoản thực. Nó phân tích hoạt động tài khoản để khám phá các kết nối giữa tương tác tài khoản và hoạt động bot.

    - **Quản lý tri thức**: Cơ sở dữ liệu đồ thị cung cấp các kỹ thuật cho tích hợp dữ liệu, dữ liệu liên kết và chia sẻ thông tin. Chúng biểu diễn siêu dữ liệu phức tạp hoặc các khái niệm lĩnh vực trong một định dạng chuẩn và cung cấp ngữ nghĩa phong phú cho xử lý ngôn ngữ tự nhiên. Bạn cũng có thể sử dụng các cơ sở dữ liệu này cho các đồ thị tri thức và quản lý dữ liệu chính. Ví dụ, các thuật toán học máy phân biệt giữa rừng mưa Amazon và thương hiệu Amazon bằng các mô hình đồ thị.

## Các lợi ích của cơ sở dữ liệu đồ thị

Cơ sở dữ liệu đồ thị được xây dựng tùy chỉnh để quản lý dữ liệu có sự kết nối cao. Khi độ kết nối và khối lượng dữ liệu hiện đại tăng lên, cơ sở dữ liệu đồ thị cung cấp cơ hội để sử dụng và phân tích dữ liệu một cách hiệu quả về chi phí. Dưới đây là ba lợi ích chính của phân tích đồ thị.

    - **Linh hoạt**: Cấu trúc và mô hình đồ thị có thể thay đổi theo ứng dụng của bạn. Các nhà phân tích dữ liệu có thể thêm hoặc sửa đổi cấu trúc đồ thị hiện có mà không ảnh hưởng đến các chức năng hiện tại. Không cần thiết phải mô hình hóa các miền trước.

    - **Hiệu suất:** Mô hình cơ sở dữ liệu quan hệ trở nên ít tối ưu khi khối lượng và độ sâu của các mối quan hệ tăng lên. Điều này dẫn đến việc trùng lặp và dư thừa dữ liệu — nhiều bảng cần được xử lý để khám phá kết quả truy vấn. Ngược lại, hiệu suất của cơ sở dữ liệu đồ thị cải thiện nhanh chóng khi truy vấn các mối quan hệ, thậm chí khi khối lượng dữ liệu đồ thị tăng lên.

    - **Hiệu quả**: Truy vấn đồ thị ngắn và hiệu quả hơn so với các cơ sở dữ liệu quan hệ để tạo ra các báo cáo tương tự. Các công nghệ đồ thị tận dụng các nút liên kết. Việc duyệt các liên kết hoặc mối quan hệ là quá trình nhanh chóng, vì các mối quan hệ giữa các nút không được tính toán vào thời điểm truy vấn mà được lưu trữ trong cơ sở dữ liệu.
    
## Làm thế nào phân tích đồ thị và cơ sở dữ liệu đồ thị hoạt động

Cơ sở dữ liệu đồ thị hoạt động bằng cách sử dụng ngôn ngữ truy vấn chuẩn hóa và các thuật toán đồ thị.

## Ngôn ngữ truy vấn đồ thị (Graph query languages)

Ngôn ngữ truy vấn đồ thị được sử dụng để tương tác với cơ sở dữ liệu đồ thị. Tương tự như SQL, ngôn ngữ này có các tính năng để thêm, sửa đổi và truy vấn dữ liệu. Tuy nhiên, những ngôn ngữ này tận dụng các cấu trúc đồ thị cơ bản để xử lý các truy vấn phức tạp một cách hiệu quả. Chúng cung cấp giao diện để bạn có thể đặt câu hỏi như:
    - Số bước đi giữa các nút
    - Đường đi dài nhất/đường đi ngắn nhất/đường đi tối ưu
    - Giá trị của các nút

**Apache TinkerPop Gremlin, SPARQL và openCypher là các ngôn ngữ truy vấn đồ thị phổ biến.**

## Thuật toán đồ thị (Graph algorithms)

Thuật toán đồ thị là các hoạt động phân tích các mối quan hệ và hành vi trong dữ liệu liên kết. Ví dụ, chúng khám phá khoảng cách và đường đi giữa các nút hoặc phân tích các cạnh đến và các nút láng giềng để tạo ra các báo cáo. Các thuật toán có thể nhận diện các mẫu chung, bất thường, cộng đồng và các đường đi kết nối các yếu tố dữ liệu. Một số ví dụ về thuật toán đồ thị bao gồm:

    - Phân cụm (Clustering)

    *Các ứng dụng như xử lý hình ảnh, thống kê và khai thác dữ liệu sử dụng phân cụm để nhóm các nút dựa trên các đặc điểm chung. Việc phân cụm có thể được thực hiện trê cả sự khác biệt giữa các cụm và sự tương đồng trong cụm*

    - Phân vùng (Partitioning)

    *Bạn có thể phân vùng hoặc cắt đồ thị tại nút có ít cạnh nhất. Các ứng dụng như kiểm tra mạng sử dụng phân vùng để tìm các điểm yếu trong mạng.*

    - Tìm kiếm (Search)

    *Tìm kiếm hoặc duyệt qua đồ thị có thể thuộc một trong hai loại—theo chiều rộng hoặc theo chiều sâu. Tìm kiếm theo chiều rộng di chuyển từ nút này sang nút khác trên biểu đồ. Nó rất hữu ích trong việc khám phá đường dẫn tối ưu. Tìm kiếm theo chiều sâu di chuyển dọc theo một nhánh để tìm tất cả các mối quan hệ của một nút cụ thể.*

## Khi nào cơ sở dữ liệu đồ thị không phù hợp

Một cơ sở dữ liệu đồ thị chuyên dụng cung cấp giá trị lớn nhất cho các bộ dữ liệu có kết nối cao và bất kỳ phân tích nào đòi hỏi tìm kiếm các mối quan hệ ẩn và rõ ràng. Nếu điều này không phù hợp với trường hợp sử dụng của bạn, các loại cơ sở dữ liệu khác có thể phù hợp hơn.

Ví dụ, hãy tưởng tượng một tình huống khi bạn cần ghi lại tồn kho sản phẩm theo từng mục. Bạn chỉ cần lưu trữ chi tiết như tên mặt hàng và số lượng có sẵn. Vì bạn không cần giữ thông tin bổ sung, các cột trên bảng sẽ không thay đổi. Do tính chất bảng, cơ sở dữ liệu quan hệ sẽ phù hợp hơn cho dữ liệu không liên quan như vậy.

Điều quan trọng là không sử dụng cơ sở dữ liệu đồ thị đơn giản làm kho lưu trữ khóa-giá trị. Kết quả tra cứu từ một khóa đã biết không tối đa hóa chức năng mà cơ sở dữ liệu đồ thị được tạo ra để thực hiện.

