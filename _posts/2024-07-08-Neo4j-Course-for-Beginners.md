---
layout: post
title: Neo4j Course for Beginners
categories: Neo4j
---

## Start

Neo4j là một cơ sở dữ liệu đồ thị mạnh mẽ cho phép các tổ chức mô hình hóa, lưu trữ và phân tích các mối quan hệ phức tạp giữa các điểm dữ liệu. Cấu trúc dựa trên đồ thị trực quan của nó cung cấp một giải pháp linh hoạt và hiệu quả cho nhiều ứng dụng khác nhau, làm cho nó trở thành lựa chọn hàng đầu để quản lý dữ liệu liên kết. Khóa học này được giảng dạy bởi các thành viên của đội ngũ FreeCodeCamp, bao gồm Farhan Choudhary và Gavin Long. Đầu tiên, bạn sẽ học về Neo4j và Hệ quản trị cơ sở dữ liệu đồ thị, cũng như cách bạn có thể hưởng lợi từ việc tích hợp chúng vào ứng dụng của mình. Tiếp theo, bạn sẽ học cách sử dụng hệ quản trị cơ sở dữ liệu đồ thị Neo4j làm lưu trữ phía sau cho một ứng dụng thực tế được tạo ra với Java và Spring Boot. Cuối cùng, bạn sẽ học cách tạo giao diện người dùng với React để tương tác với kho dữ liệu được lưu trữ bằng Neo4j.

Neo4j đã cung cấp một khoản tài trợ để làm cho khóa học này trở nên khả thi, vì vậy hãy bắt đầu thôi. Xin chào và chào mừng, tôi là Gavin Long. Cuối cùng thì tôi cũng đã có chiếc áo thun FreeCodeCamp của mình. Tôi đã đi từ bờ biển phía đông của Nam Phi đến Amsterdam và gặp người sáng lập của FreeCodeCamp, Quincy Larson, và ông ấy đã tặng tôi chiếc áo thun FreeCodeCamp của riêng tôi. Thật tuyệt vời.

Mục đích của chuyến đi là gặp gỡ Quincy và một số thành viên cốt lõi của đội ngũ FreeCodeCamp trực tiếp. Đó là về việc xây dựng đội ngũ và củng cố mối quan hệ giữa các đồng nghiệp. Khái niệm chính trong khóa học này thực sự là các mối quan hệ. Các mối quan hệ giữa dữ liệu có thể là giữa con người với nhau, giữa các bộ phận của xe hơi, hoặc giữa một chiếc áo thun và một con người. Các mối quan hệ giữa dữ liệu đồng nhất hoặc thiếu dữ liệu, ví dụ như giữa con người với nhau, hoặc các mối quan hệ giữa dữ liệu không đồng nhất hoặc các loại dữ liệu khác nhau. Các mối quan hệ này có thể được đại diện rất hiệu quả trong một hệ quản trị cơ sở dữ liệu đồ thị.

Neo4j là một hệ quản trị cơ sở dữ liệu đồ thị. Trong phần này của khóa học, tôi muốn giới thiệu cho bạn một cái nhìn tổng quan ngắn gọn, làm nổi bật tầm quan trọng của một hệ quản trị cơ sở dữ liệu đồ thị trước khi chúng ta xem xét Neo4j. Hãy đặt tầm quan trọng của một hệ quản trị cơ sở dữ liệu đồ thị trong bối cảnh bằng cách xem xét một số ví dụ.

các loại Hệ quản trị cơ sở dữ liệu phổ biến khác thường được sử dụng ngày nay. Vì vậy, hãy xem xét ba loại Hệ quản trị cơ sở dữ liệu phổ biến khác trước khi chúng ta thảo luận về hệ quản trị cơ sở dữ liệu đồ thị và tại sao chúng ta lại muốn sử dụng một hệ quản trị cơ sở dữ liệu đồ thị trong các ứng dụng của mình.

Loại hệ quản trị cơ sở dữ liệu được sử dụng phổ biến nhất là hệ quản trị cơ sở dữ liệu quan hệ. Các ví dụ về hệ quản trị cơ sở dữ liệu quan hệ là SQL Server, Postgres và MySQL. Trong loại cơ sở dữ liệu này, các bảng biểu thị các thực thể. Ví dụ, một bảng có tên là "employee" chứa các hàng dữ liệu, mỗi hàng dữ liệu được chia thành các cột hoặc trường chứa thông tin về nhân viên. Ví dụ, trường "name" chứa tên của nhân viên, trường "age" chứa tuổi của nhân viên, v.v. Một thực thể dữ liệu khác có thể được triển khai trong một bảng có tên là "department". Mỗi hàng trong bảng "department" biểu thị một phòng ban riêng lẻ, ví dụ, một hàng lưu trữ thông tin cho phòng nhân sự và một hàng khác lưu trữ thông tin cho phòng tài chính.

Các thực thể dữ liệu này hoặc các bảng trong cơ sở dữ liệu quan hệ có thể được liên kết rõ ràng với nhau trong hệ quản trị cơ sở dữ liệu quan hệ. Ví dụ, một thực thể có thể có mối quan hệ một-một với một thực thể khác, chẳng hạn như nhân viên và các xe họ lái. Một nhân viên cụ thể liên quan đến một xe cụ thể - một nhân viên cho một xe. Vì vậy, trong ví dụ này, thực thể "employee" có mối quan hệ một-một với thực thể "car".

Hai bảng trong cơ sở dữ liệu có thể có mối quan hệ nhiều-nhiều. Ví dụ, một nhân viên có thể là thành viên của nhiều đội và mỗi đội có thể chứa nhiều nhân viên. Điều này có nghĩa là một nhân viên có thể là thành viên của hơn một đội và mỗi đội có thể có nhiều nhân viên. Vì vậy, trong kịch bản này, thực thể "employee" có mối quan hệ nhiều-nhiều với thực thể "team".

Một thực thể trong cơ sở dữ liệu có thể có mối quan hệ một-nhiều với một thực thể khác trong cơ sở dữ liệu. Ví dụ, bảng "department" có mối quan hệ một-nhiều với Bảng nhân viên nghĩa là mỗi phòng ban có thể chứa một hoặc nhiều nhân viên và một nhân viên chỉ có thể là thành viên của một phòng ban tại một thời điểm nhất định.

Vì vậy, mối quan hệ một-nhiều này có thể được thiết lập trong hệ quản trị cơ sở dữ liệu quan hệ thông qua một thiết kế lược đồ phù hợp. Lược đồ cơ sở dữ liệu định nghĩa cách dữ liệu được tổ chức trong cơ sở dữ liệu quan hệ, bao gồm các ràng buộc như tên bảng, các trường, kiểu dữ liệu và mối quan hệ giữa các thực thể liên quan. Ví dụ, mối quan hệ một-nhiều giữa bảng phòng ban và bảng nhân viên có thể được thực hiện bằng cách bao gồm một khóa chính, là một định danh duy nhất cho một hàng dữ liệu trong bảng phòng ban, và một trường khóa ngoại trong bảng nhân viên liên quan đến giá trị khóa chính trong bảng phòng ban.

Ưu điểm chính của thiết kế cơ sở dữ liệu quan hệ là nó giúp dễ dàng duy trì tính toàn vẹn của dữ liệu, tức là dữ liệu không dễ bị hỏng, cũng như giảm thiểu sự trùng lặp dữ liệu. Ví dụ, nếu bạn lưu trữ dữ liệu phòng ban trong bảng nhân viên, bạn có thể thấy các giá trị của trường tên ngắn và tên dài của phòng ban được lặp lại trong các hàng của bảng nhân viên, trong khi việc tách dữ liệu thành bảng nhân viên và bảng phòng ban có nghĩa là các giá trị này không bị lặp lại, dẫn đến việc tiết kiệm không gian lưu trữ. Khi dữ liệu mở rộng, việc tiết kiệm không gian lưu trữ có thể rất đáng kể.

Một kỹ thuật được gọi là chuẩn hóa được sử dụng để thiết kế một cơ sở dữ liệu quan hệ. Tôi sẽ không đi vào chi tiết về chuẩn hóa ở đây, nhưng bạn nên tìm hiểu về chuẩn hóa, đây là một khái niệm chính trong thiết kế cơ sở dữ liệu quan hệ. Kỹ thuật chuẩn hóa có thể tăng tính toàn vẹn của dữ liệu, giảm thiểu hỏng dữ liệu và cũng giảm đáng kể sự trùng lặp dữ liệu, tức là việc lưu trữ các giá trị không cần thiết một cách lặp lại.

Nhược điểm của cơ sở dữ liệu quan hệ là tốc độ truy xuất dữ liệu khi cần nhiều phép nối hoặc các phép nối sâu giữa các thực thể. Ví dụ, nếu bạn muốn truy xuất dữ liệu phân tích tóm tắt dữ liệu từ nhiều thực thể, thiết kế cơ sở dữ liệu đã được chuẩn hóa có thể làm cho việc truy xuất dữ liệu trở nên chậm chạp. Một cách để tăng tốc độ truy xuất dữ liệu là sử dụng hệ quản trị cơ sở dữ liệu không có lược đồ, chẳng hạn như MongoDB, đây là một hệ quản trị cơ sở dữ liệu dựa trên tài liệu.

Việc thiết kế cơ sở dữ liệu không bị ràng buộc bởi lược đồ như với hệ quản trị cơ sở dữ liệu quan hệ có thể dẫn đến việc tăng tốc độ truy xuất dữ liệu cũng như cho phép linh hoạt hơn trong thiết kế. Vì vậy, bạn có thể thấy rằng mỗi loại hệ quản trị cơ sở dữ liệu đều có mục đích và ưu điểm riêng.

Một loại hệ quản trị cơ sở dữ liệu khác có thể sử dụng cấu trúc lưu trữ cặp giá trị tên, chẳng hạn như Redis. Hệ quản trị cơ sở dữ liệu này rất tốt cho việc lưu trữ đệm dữ liệu được truy xuất thường xuyên và do đó có thể giúp tăng tốc độ của hệ thống.

Vì vậy, chúng ta đã xem xét ngắn gọn ba loại hệ quản trị cơ sở dữ liệu phổ biến: hệ quản trị cơ sở dữ liệu quan hệ như SQL Server hoặc Postgres, hệ quản trị cơ sở dữ liệu không có lược đồ như MongoDB, và hệ quản trị cơ sở dữ liệu lưu trữ cặp giá trị tên như Redis.


Hãy xem xét tầm quan trọng của một hệ quản trị cơ sở dữ liệu đồ thị. Neo4j là một hệ quản trị cơ sở dữ liệu đồ thị, loại hệ quản trị này dựa trên cấu trúc dữ liệu đồ thị. Tất cả các nền tảng mạng xã hội như Twitter, Facebook và Instagram đều sử dụng cơ sở dữ liệu đồ thị. Như chúng ta đều biết, các nền tảng này có hàng triệu người dùng. Hệ quản trị cơ sở dữ liệu quan hệ sẽ không phải là lựa chọn lý tưởng duy nhất để lưu trữ dữ liệu như vậy vì cách dữ liệu được cấu trúc sẽ yêu cầu nhiều phép nối giữa các thực thể khi dữ liệu liên quan được truy xuất, điều này sẽ làm chậm quá trình truy xuất dữ liệu một cách đáng kể, cuối cùng gây ra trải nghiệm người dùng kém vì toàn bộ hệ thống bị chậm lại bởi các phép nối này.

Khi thiết kế một hệ thống cụ thể như một nền tảng mạng xã hội, bạn có thể tích hợp cả hệ quản trị cơ sở dữ liệu đồ thị và hệ quản trị cơ sở dữ liệu quan hệ vào thiết kế tổng thể của hệ thống. Loại giải pháp này có thể kết hợp tính toàn vẹn dữ liệu được củng cố vốn có trong các hệ quản trị cơ sở dữ liệu quan hệ với các mối quan hệ phức tạp giữa các thực thể dữ liệu hoặc nút có thể được tạo điều kiện thông qua một hệ quản trị cơ sở dữ liệu đồ thị. Ví dụ, cơ sở dữ liệu chính có thể là một cơ sở dữ liệu quan hệ, nơi các vấn đề về tính toàn vẹn dữ liệu và sự trùng lặp dữ liệu được giải quyết bởi các lợi ích vốn có mà chúng ta đã thảo luận về hệ quản trị cơ sở dữ liệu quan hệ.

Một hệ quản trị cơ sở dữ liệu đồ thị được đồng bộ hóa một cách thích hợp với hệ quản trị cơ sở dữ liệu quan hệ có liên quan có thể được sử dụng để tăng tốc độ truy xuất dữ liệu, ví dụ, có các mối quan hệ phức tạp. Nếu dữ liệu yêu cầu các mối quan hệ phức tạp được truy xuất trực tiếp từ hệ quản trị cơ sở dữ liệu quan hệ, các phép nối cần thiết khi truy xuất dữ liệu liên quan có thể làm chậm hệ thống một cách đáng kể và cuối cùng dẫn đến trải nghiệm người dùng rất kém. Vì vậy, bằng cách bao gồm một hệ quản trị cơ sở dữ liệu đồ thị trong hệ thống tổng thể, nó có thể nằm trên hệ quản trị cơ sở dữ liệu quan hệ và được sử dụng để tăng tốc độ truy xuất dữ liệu với các mối quan hệ phức tạp, điều này có thể tăng tốc quá trình truy xuất dữ liệu một cách đáng kể, dẫn đến trải nghiệm người dùng tốt hơn nhiều.

Loại hệ thống này sẽ yêu cầu dữ liệu được lưu trữ trong hệ quản trị cơ sở dữ liệu đồ thị liên quan và hệ quản trị cơ sở dữ liệu quan hệ liên quan phải được đồng bộ hóa để đảm bảo rằng dữ liệu nhất quán giữa hai hệ quản trị cơ sở dữ liệu khác nhau. Hệ quản trị cơ sở dữ liệu, vì vậy một hệ thống được thiết kế đúng cách có thể tận dụng lợi ích của cả hai loại hệ quản trị cơ sở dữ liệu. Đối với cấu trúc dữ liệu dựa trên đồ thị, một hệ quản trị cơ sở dữ liệu tập trung vào việc tạo điều kiện cho các mối quan hệ giữa các thực thể hoặc các nút là rất cần thiết. Một hệ quản trị cơ sở dữ liệu đồ thị cung cấp một cách để lưu trữ dữ liệu dựa trên cấu trúc dữ liệu đồ thị, lý tưởng cho các ứng dụng sử dụng dữ liệu mà các thực thể có nhiều mối quan hệ và mối quan hệ phức tạp với nhau.

Hãy nghĩ về các nền tảng mạng xã hội, nơi bạn có các mối quan hệ giữa người dùng và bài đăng, lượt thích, tình bạn, v.v., và có hàng triệu người sử dụng các nền tảng này. Một hệ quản trị cơ sở dữ liệu là cần thiết để tạo điều kiện lưu trữ dữ liệu cho một số lượng lớn các loại mối quan hệ khác nhau. Một hệ quản trị cơ sở dữ liệu đồ thị cho phép lưu trữ các mối quan hệ dưới dạng dữ liệu trong cơ sở dữ liệu đồ thị. Với một hệ quản trị cơ sở dữ liệu quan hệ, trọng tâm là các thực thể và nói chung, các mối quan hệ giữa các thực thể không được lưu trữ trong cơ sở dữ liệu mà các mối quan hệ tổng quát được thiết lập ở cấp độ thiết kế.

Ví dụ, bạn có thể thấy qua giá trị của trường khóa ngoại rằng nhân viên là thành viên của phòng nhân sự, nhưng không có chi tiết nào về bản thân mối quan hệ giữa phòng ban liên quan và nhân viên được lưu trong cơ sở dữ liệu. Đây là điều bạn có thể dễ dàng thực hiện trong một hệ quản trị cơ sở dữ liệu đồ thị, nơi bạn có thể tạo ra một mối quan hệ chi tiết hơn.

Bạn có thể dễ dàng lưu trữ dữ liệu về các mối quan hệ cá nhân giữa các thực thể hoặc các nút, ví dụ, giữa một nút nhân viên và một nút phòng ban. Sau đây là một bài trình bày trên bảng trắng cho thấy cách các mối quan hệ giữa các nhân viên cá nhân và giữa các nhân viên và các phòng ban có thể được biểu diễn trong một cơ sở dữ liệu đồ thị.



















- Giới thiệu
- So sánh: neo4j vs RDMS
- Giới thiệu Cypher vs query SQL
- Cách cài đặt Neo4j
- cách dùng: CRUD

