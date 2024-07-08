---
layout: post
title: Graph database
categories: CSDL_NC Neo4j Graph-database
---

## Graph database là gì?

*link: https://giaiphapso.com/graph-database-la-gi-va-hoat-dong-the-nao/*

- Cơ sở dữ liệu đồ thị (graph database) là cơ sở dữ liệu được thiết kế để coi các mối quan hệ giữa các dữ liệu là quan trọng như nhau đối với bản thân dữ liệu.
- Nó được thiết kế để lưu giữ dữ liệu mà không cần biến nó thành một mô hình được xác định trước.
- Thay vào đó, dữ liệu được lưu trữ giống như lần đầu tiên chúng ta vẽ ra – cho biết cách mỗi thực thể riêng lẻ kết nối với hoặc có liên quan với những thực thể khác.

## Tại sao lại cần cơ sở dữ liệu đồ thị?

- Chúng ta đang sống trong một thế giới kết nối! Không có phần thông tin riêng biệt, mà là các miền phong phú, được kết nối xung quanh chúng ta
- Chỉ một cơ sở dữ liệu bao gồm các mối quan hệ nguyên bản mới có thể lưu trữ, xử lý và truy vấn các kết nối một cách hiệu quả.
- Trong khi các cơ sở dữ liệu khác tính toán các mối quan hệ tại thời điểm truy vấn thông qua các hoạt động JOIN tốn kém, thì cơ sở dữ liệu đồ thị lưu trữ các kết nối cùng với dữ liệu trong mô hình.

- Truy cập các nút và mối quan hệ trong cơ sở dữ liệu đồ thị gốc là một hoạt động hiệu quả, thời gian liên tục và cho phép bạn nhanh chóng duyệt qua hàng triệu kết nối mỗi giây trên mỗi lõi.
- **Không phụ thuộc vào tổng kích thước của tập dữ liệu của bạn**, cơ sở dữ liệu biểu đồ **vượt trội trong việc quản lý dữ liệu được kết nối cao và các truy vấn phức tạp**.
- Chỉ với một mẫu và một tập hợp các điểm bắt đầu, cơ sở dữ liệu biểu đồ khám phá dữ liệu lân cận xung quanh các điểm xuất phát ban đầu đó – thu thập và tổng hợp thông tin từ hàng triệu nút và mối quan hệ – và để lại bất kỳ dữ liệu nào bên ngoài chu vi tìm kiếm không bị ảnh hưởng.

## Graph database hoạt động thế nào?

- Cơ sở dữ liệu đồ thị thường đơn giản về cách chúng được cấu trúc. Chúng chủ yếu bao gồm hai thành phần:

    + Nút (node): Đây là phần dữ liệu thực tế của chính nó. Đó có thể là số người xem video trên youtube, số người đã đọc tweet hoặc thậm chí có thể là thông tin cơ bản như tên, địa chỉ của mọi người, v.v.
    + Cạnh (Edge): Điều này giải thích mối quan hệ thực tế giữa hai nút. Điều thú vị là các cạnh cũng có thể có các phần thông tin riêng của chúng, chẳng hạn như bản chất của mối quan hệ giữa hai nút. Tương tự, các cạnh cũng có thể có các hướng mô tả luồng dữ liệu đã nói.

  ![_config.yml]({{ site.baseurl }}/images/graph-DB.png)

- Thông tin được sử dụng trong cơ sở dữ liệu đồ thị về cơ bản có thể là bất cứ thứ gì, và như bạn có thể thấy từ cấu trúc ở trên, khá đơn giản để vẽ ra và hiểu ở mức cơ bản.
-  Trên thực tế, rất nhiều cơ sở dữ liệu đồ thị hiện đại đang bắt đầu bao gồm loại hình ảnh trực quan nhanh này không yêu cầu kiến thức ngôn ngữ cơ sở dữ liệu phức tạp, với một ví dụ điển hình gần đây là MongoDB.
-

## Một số Graph database tiêu biểu

Mặc dù cơ sở dữ liệu đồ thị không quá phổ biến như một số cơ sở dữ liệu NoSQL khác, nhưng có một số cơ sở dữ liệu đã trở thành tiêu chuẩn khá tốt khi nói về graph database:

- **Neo4j:** Một trong những cơ sở dữ liệu biểu đồ hàng đầu trên thế giới, nó vừa là nguồn mở vừa được xây dựng thú vị trên Java. Nó cũng có ngôn ngữ riêng, được gọi là Cypher, tương tự như ngôn ngữ SQL khai báo, nhưng được tạo ra để phù hợp với đồ thị. Nó cũng hỗ trợ các ngôn ngữ phổ biến bên cạnh Java, chẳng hạn như Python, .NET, JavaScript và một số ngôn ngữ khác. Neo4j lý tưởng cho những việc như quản lý trung tâm dữ liệu và phát hiện gian lận. 

- **RedisGraph:** RedisGraph thực sự là một mô-đun đồ thị được tích hợp sẵn trong Redis, bản thân nó là một cơ sở dữ liệu NoSQL có khóa-giá trị. Vì bản thân Redis được xây dựng trên cấu trúc dữ liệu trong bộ nhớ, nên RedisGraph được tạo ra để có dữ liệu được lưu trữ trong Ram. Điều này dẫn đến một cơ sở dữ liệu đồ thị hiệu suất cao, với khả năng truy vấn và lập chỉ mục nhanh chóng. RedisGraph cũng sử dụng Cypher, điều này rất tuyệt nếu bạn muốn có được sự linh hoạt hơn cho cơ sở dữ liệu với tư cách là một lập trình viên hoặc nhà khoa học dữ liệu. Mục đích sử dụng chính là bất kỳ ứng dụng nào yêu cầu hiệu suất thực sự nhanh như chớp.

- **OrientDB:** Khá thú vị, OrientDB là sự kết hợp của nhiều loại mô hình dữ liệu khác nhau và hỗ trợ đồ thị, kho lưu trữ tài liệu, lưu trữ khóa-giá trị và dựa trên đối tượng. Điều đó đang được nói, tất cả các mối quan hệ được lưu trữ bằng cách sử dụng mô hình đồ thị sử dụng kết nối trực tiếp giữa các cơ sở dữ liệu. Giống như hai cơ sở dữ liệu đồ thị trước đó, OrientDB cũng là nguồn mở và giống như Neo4j, nó được viết bằng Java (mặc dù rất tiếc, nó không sử dụng Cypher). Ý tưởng đằng sau OrientDB là để sử dụng khi yêu cầu nhiều mô hình dữ liệu và do đó được tối ưu hóa để đảm bảo tính nhất quán của dữ liệu, cũng như giảm độ phức tạp của dữ liệu.

