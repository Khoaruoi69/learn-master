---
layout: post
title: Recommendation Engine Using Neo4j - 01
categories: Neo4j
---

## Starts

*link: https://neo4j.com/developer-blog/recommendation-engine-hands-on-1/*

*link: https://neo4j.com/developer-blog/recommendation-engine-hands-on-2/*

## From Data Model to Loading Data to Making Recommendations ( Từ mô hình dữ liệu đến tải dữ liệu đến đưa ra đề xuất)

Hệ thống đề xuất đóng một vai trò quan trọng trong việc giải quyết một trong những vấn đề phức tạp nhất mà chúng ta gặp phải khi muốn đưa ra quyết định và đó là một vấn đề nan giải.

Tôi đặt món ăn gì? Tôi nên xem phim nào? Nên mua áo nào? Đề xuất giúp chúng tôi khám phá sản phẩm. Trong bài viết này, chúng tôi sẽ:
    + Khám phá tính năng lọc cộng tác và dựa trên nội dung. (Collaborative Filtering and content-based filtering )
    + Xây dựng trực giác về cơ sở nào sẽ đưa ra đề xuất và cách thực hiện đề xuất đó.
    + Thiết kế mô hình dữ liệu phù hợp dần dần.

Trong phần 2 của loạt bài thực hành này, chúng ta sẽ thực hiện tương tự, bắt đầu bằng việc tải dữ liệu hiện có từ CSV, theo dõi các đơn đặt hàng mới và sau đó đưa ra đề xuất — tất cả đều sử dụng ngôn ngữ truy vấn Cypher. Chúng tôi cũng sẽ thảo luận về việc triển khai cơ sở dữ liệu Neo4j và đưa ra các đề xuất của chúng tôi.

## Two Types of Recommendation Systems

Như bạn có thể đã biết, các công cụ đề xuất thường chia thành hai loại: Lọc cộng tác và Lọc dựa trên nội dung (**Collaborative Filtering and Content-Based Filtering.**)  Hai điều này là hai thái cực và giải pháp của bạn rất có thể sẽ là một cách tiếp cận kết hợp. Hãy thảo luận ngắn gọn về chúng.

### Collaborative Filtering

- “Collaboration” can’t take place if there is only a single person working on a task (excluding human-robot collaboration).
- Tương tự, trong lọc cộng tác, khi người dùng cộng tác trên một thực thể duy nhất, tức là đặt hàng cùng một mặt hàng, xem cùng một bộ phim, v.v.
- Bạn có thể coi họ giống nhau dựa trên thực tế là họ quan tâm đến những điều giống nhau và có một số sở thích giống nhau. Dựa trên điều này, bạn có thể đề xuất điều gì đó cho người dùng được những người dùng khác thích, những người cũng thích những thứ khác mà người dùng liên quan thích.

  ![_config.yml]({{ site.baseurl }}/images/using-neo4j-01.png)

  Đơn giản hóa bằng một ví dụ đơn giản (trong thực tế, bạn sẽ cân nhắc dựa trên số lượng sở thích chung),  if User Ishan likes both Item A and Item B, and User Shalaka likes Item A, then there is a possibility that Shalaka may also like Item B.

  ### Content-Based Filtering

