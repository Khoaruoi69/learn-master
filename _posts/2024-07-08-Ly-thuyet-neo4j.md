---
layout: post
title: Homework
categories: CSDL_NC Neo4j
---

## Lý thuyết về Neo4j

*link: https://neo4j.com/docs/getting-started/*

- Download sub: https://downsub.com/

Neo4j là cơ sở dữ liệu hàng đầu cho dữ liệu liên kết, được xây dựng từ đầu để tận dụng không chỉ dữ liệu mà còn mối quan hệ giữa các dữ liệu này. 
Neo4j là một cơ sở dữ liệu đồ thị tự nhiên, điều này làm nó khác biệt quan trọng so với các lưu trữ dữ liệu khác. 
"Native" ở đây có nghĩa là Neo4j được thiết kế xung quanh một tối ưu hóa đơn giản nhưng mạnh mẽ: mỗi bản ghi dữ liệu hoặc nút chứa các liên kết trực tiếp đến tất cả các nút mà nó kết nối. 
Những liên kết trực tiếp này được gọi là mối quan hệ. Tất cả thông tin cần thiết để tìm nút tiếp theo trong một chuỗi có sẵn trong nút chính nó. Lớp lưu trữ tự nhiên là một đồ thị liên kết. 
Đây là ý nghĩa của 'Native' vì nguyên tắc này, Neo4j không cần tính toán các mối quan hệ giữa dữ liệu của bạn trong lúc truy vấn. Các kết nối đã có sẵn được lưu trữ ngay trong cơ sở dữ liệu. 
Do đó, các truy vấn dữ liệu mật độ kết nối cao nhanh hơn nhiều lần. Các cơ sở dữ liệu khác không lưu trữ các liên kết trực tiếp giữa các bản ghi, chúng cần tính toán các kết nối bằng cách tìm kiếm qua một cấu trúc dữ liệu riêng gọi là chỉ mục.
 Quá trình tra cứu này, mà phải thực hiện lặp đi lặp lại để tìm mỗi kết nối, rất tốn kém và trở nên chậm hơn một cách mũi nhọn khi kích thước dữ liệu và phức tạp truy vấn tăng lên.
Điều này làm cho chúng chậm hơn Neo4j một cách bẩm sinh đối với các truy vấn tập trung vào mối quan hệ. Trong thập kỷ qua, Neo4j đã biến cơ sở dữ liệu đồ thị thành một công nghệ chủ chốt, động lực cho các ứng dụng hiện đại của hàng trăm công ty trong danh sách Fortune 500, các cơ quan chính phủ và các tổ chức phi chính phủ.
 Neo4j được sử dụng để phát hiện gian lận, nâng cao trí tuệ nhân tạo, quản lý chuỗi cung ứng, đạt được cái nhìn 360 độ về dữ liệu và nhiều hơn thế nữa. Tìm hiểu thêm tại neo4j.com.

