---
layout: post
title: So sanh Graph DB vs Relational DB
categories: Graph-database
---

## Điểm khác biệt

*link: https://aws.amazon.com/vi/compare/the-difference-between-graph-and-relational-database/*

- Cả cơ sở dữ liệu đồ thị và cơ sở dữ liệu quan hệ đều lưu trữ các mục dữ liệu có mối quan hệ định sẵn giữa chúng.
- Tuy nhiên, các mục dữ liệu đó biểu thị các mối quan hệ dữ liệu theo cách rất khác nhau. 
- **Cơ sở dữ liệu quan hệ lưu trữ dữ liệu ở định dạng bảng gồm các hàng và cột.**
-  Dữ liệu liên quan cũng được lưu trữ trong bảng và các điểm dữ liệu liên kết trở lại bảng gốc. Các hoạt động liên quan đến mối quan hệ dữ liệu trở nên kém hiệu quả vì cần phải tra cứu nhiều bảng dữ liệu.
- Ngược lại, **cơ sở dữ liệu đồ thị lưu trữ dữ liệu dưới dạng mạng lưới gồm các thực thể và mối quan hệ.**
- Cơ sở dữ liệu đồ thị sử dụng **lý thuyết đồ thị toán học** để **lưu trữ và thực hiện** các thao tác trên mối quan hệ dữ liệu.
- Cơ sở dữ liệu đồ thị lập mô hình mối quan hệ hiệu quả hơn nhiều. Chúng cải thiện đáng kể hiệu năng ứng dụng trong các trường hợp sử dụng có các kết nối dữ liệu phức tạp.


