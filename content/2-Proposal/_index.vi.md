---
title: "Đề xuất"
date: 2025-09-09
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Nền tảng Chia sẻ Video

## 1. Tóm tắt Điều hành

Đề xuất này trình bày phát triển một Nền tảng Chia sẻ Video có thể mở rộng tận dụng các dịch vụ AWS cloud. Nền tảng sẽ cho phép người dùng tải lên, phát trực tuyến, và chia sẻ nội dung video với các tính năng bao gồm xác thực người dùng, quản lý nội dung, và phát video trực tuyến trong thời gian thực.

Các mục tiêu chính:

- Xây dựng một nền tảng chia sẻ video an toàn, có thể mở rộng
- Triển khai xác thực và ủy quyền người dùng
- Cung cấp khả năng phát video chất lượng cao
- Đảm bảo quản lý cơ sở hạ tầng hiệu quả về chi phí
- Cung cấp trải nghiệm người dùng liền mạch trên các thiết bị

Giải pháp sử dụng các dịch vụ AWS bao gồm Amplify để lưu trữ frontend, Cognito để xác thực, S3 để lưu trữ, CloudFront để phân phối nội dung, và Interactive Video Service để phát trực tuyến.

## 2. Tuyên bố Vấn đề

### Vấn đề là gì?

Các giải pháp chia sẻ video hiện tại gặp phải nhiều thách thức:

- Chi phí cơ sở hạ tầng cao để lưu trữ và phát video
- Yêu cầu cấu hình và bảo trì phức tạp
- Khả năng mở rộng hạn chế trong thời gian sử dụng cao điểm
- Các lỗ hổng bảo mật trong xác thực người dùng
- Chất lượng video kém và các vấn đề về buffer

### Giải pháp

Nền tảng chia sẻ video dựa trên AWS của chúng tôi giải quyết các thách thức này bằng cách:

- Tận dụng mô hình định giá trả-khi-sử-dụng hiệu quả của AWS
- Sử dụng các dịch vụ quản lý để giảm chi phí hoạt động
- Triển khai khả năng tự động mở rộng để xử lý các đột biến lưu lượng
- Cung cấp bảo mật cấp doanh nghiệp thông qua AWS Cognito
- Cung cấp phát video chất lượng cao qua Amazon IVS và CloudFront

### Lợi ích và Lợi nhuận từ Đầu tư

**Tiết kiệm Chi phí:**

- Giảm 40-60% chi phí cơ sở hạ tầng so với hosting truyền thống
- Không cần đầu tư phần cứng trước
- Mô hình trả-khi-sử-dụng tối ưu hóa chi phí hoạt động

**Cải thiện Hiệu suất:**

- Tính sẵn sàng thời gian hoạt động 99,9%
- Phân phối nội dung toàn cầu với độ trễ thấp
- Tự động mở rộng xử lý tăng lưu lượng 10 lần một cách liền mạch

**Giá trị Kinh doanh:**

- Thời gian đưa ra thị trường nhanh hơn (3-6 tháng so với 12+ tháng)
- Trải nghiệm người dùng được cải thiện thúc đẩy mức độ tương tác cao hơn
- Kiến trúc có thể mở rộng hỗ trợ tăng trưởng kinh doanh

## 3. Kiến trúc Giải pháp

![Sơ đồ Kiến trúc](https://cuti-duck.github.io/hugo-aws-project/images/architecdiagram.png)

### Dịch vụ AWS Được sử dụng

**Amplify:** Nền tảng lưu trữ frontend và triển khai cho các ứng dụng React/Vue.js với tích hợp CI/CD.

**Cognito:** Dịch vụ xác thực và ủy quyền người dùng cung cấp đăng ký, đăng nhập và kiểm soát truy cập an toàn.

**App Runner:** Lưu trữ API backend được container hóa với tự động mở rộng và cân bằng tải.

**DynamoDB:** Cơ sở dữ liệu NoSQL để lưu trữ hồ sơ người dùng, siêu dữ liệu video, và dữ liệu ứng dụng.

**S3:** Lưu trữ đối tượng cho các tệp video, hình nhỏ, và tài sản tĩnh với versioning và lifecycle policies.

**CloudFront:** CDN toàn cầu để phân phối nội dung nhanh và phát video với edge caching.

**Amazon IVS (Interactive Video Service):** Dịch vụ phát video trực tuyến cho các buổi phát sóng trực tiếp và nội dung theo yêu cầu với độ trễ thấp.

**Code Pipeline:** Pipeline CI/CD để kiểm tra, xây dựng, và triển khai tự động.

**Code Build:** Dịch vụ xây dựng để biên dịch mã nguồn, chạy các bài kiểm tra, và tạo các gói triển khai.

**Elastic Container Registry:** Đăng ký container Docker để lưu trữ và quản lý hình ảnh ứng dụng.

### Thiết kế Thành phần

**Lớp Frontend:**

- Ứng dụng web dựa trên React được lưu trữ trên Amplify
- Thiết kế đáp ứng hỗ trợ di động và máy tính để bàn
- Trình phát video thời gian thực với streaming bitrate thích ứng

**Lớp API:**

- API RESTful được xây dựng với Node.js/Express
- Được container hóa và triển khai trên App Runner
- Tích hợp xác thực dựa trên JWT

**Lớp Dữ liệu:**

- Bảng DynamoDB cho dữ liệu người dùng và siêu dữ liệu video
- S3 buckets để lưu trữ video với phân tầng thông minh

**Lớp Bảo mật:**

- Nhóm người dùng Cognito để xác thực
- IAM roles và policies để kiểm soát truy cập

**Kiến trúc Phát trực tuyến:**

- Amazon IVS cho khả năng phát trực tuyến
- CloudFront để phân phối video toàn cầu
- Streaming bitrate thích ứng để tối ưu hóa chất lượng

### Các trường hợp sử dụng

**Sự kiện Phát trực tuyến:**

- Phát sóng thời gian thực của các hội nghị, webinars, và sự kiện công ty
- Phát trực tuyến đa bitrate cho trải nghiệm xem tối ưu

**Video theo yêu cầu (VOD):**

- Tải lên và chia sẻ nội dung giáo dục, hướng dẫn, và tài liệu đào tạo
- Truy cập nội dung an toàn với quyền người dùng

**Chia sẻ Video Xã hội:**

- Chia sẻ nội dung do người dùng tạo
- Các tính năng cộng đồng với bình luận và xếp hạng

## 4. Triển khai Kỹ thuật

### Giai đoạn 1: Thiết lập Cơ sở hạ tầng

**Cấu hình Tài khoản AWS:**

- Cấu hình IAM roles và policies cho truy cập ít nhất đặc quyền

**Triển khai Dịch vụ Cốt lõi:**

- Triển khai bảng DynamoDB với indexing phù hợp
- Cấu hình S3 buckets với encryption và lifecycle policies
- Thiết lập nhóm người dùng Cognito và nhóm nhận dạng

### Giai đoạn 2: Phát triển Backend

**Phát triển API:**

- Xây dựng API RESTful sử dụng framework Node.js/Express
- Triển khai xác thực JWT với tích hợp Cognito
- Tạo các endpoints tải lên/xử lý video
- Phát triển API quản lý người dùng và nội dung

**Lược đồ Cơ sở dữ liệu:**

- Bảng Users: user_id, email, profile_data, created_at
- Bảng Videos: video_id, user_id, metadata, upload_status
- Bảng Analytics: event_id, user_id, video_id, timestamp, action

**Container hóa:**

- Tạo Docker containers cho các dịch vụ API
- Đẩy hình ảnh lên Elastic Container Registry
- Cấu hình App Runner để triển khai tự động

### Giai đoạn 3: Phát triển Frontend

**Ứng dụng React:**

- Triển khai các thành phần UI đáp ứng
- Tích hợp AWS Amplify SDK để xác thực
- Xây dựng giao diện tải lên video với theo dõi tiến trình
- Tạo trình phát video với streaming thích ứng

**Các tính năng chính:**

- Đăng ký/đăng nhập người dùng với xác minh email
- Tải lên video với chức năng kéo và thả
- Phát video trực tuyến thời gian thực với lựa chọn chất lượng
- Bảng điều khiển người dùng để quản lý nội dung

### Giai đoạn 4: Tích hợp Phát trực tuyến

**Thiết lập Amazon IVS:**

- Cấu hình các kênh phát trực tuyến và URL phát lại
- Triển khai streaming bitrate thích ứng
- Thiết lập các quy trình ghi âm và lưu trữ

**Cấu hình CloudFront:**

- Tạo các phân phối cho phân phối nội dung video
- Cấu hình các vị trí edge để tiếp cận toàn cầu
- Triển khai các chiến lược caching để tối ưu hóa hiệu suất

### Giai đoạn 5: Pipeline CI/CD

**Triển khai Tự động:**

- Cấu hình CodePipeline cho quy trình từ nguồn đến sản xuất
- Thiết lập CodeBuild để kiểm tra và xây dựng tự động
- Triển khai chiến lược triển khai blue-green

**Chiến lược Kiểm thử:**

- Kiểm tra đơn vị cho các endpoints API
- Kiểm tra tích hợp cho các tương tác dịch vụ AWS
- Kiểm tra tải cho xác thực hiệu suất
