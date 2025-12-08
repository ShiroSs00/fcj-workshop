---
title: "Nhật ký công việc - Tuần 3"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu Tuần 3:

- Tìm hiểu về S3 (Simple Storage Service) để lưu trữ objects.
- Hiểu về DynamoDB (cơ sở dữ liệu NoSQL) và các khái niệm cốt lõi.
- Thực hành các hoạt động S3 và DynamoDB.

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ                                                                                    | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| ---- | ------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1    | Tìm hiểu nền tảng S3: buckets, objects, storage classes, versioning, lifecycle policies     | 09/22/2025   | 09/22/2025      | <https://docs.aws.amazon.com/s3/>         |
| 2    | Thực hành S3: Tạo bucket, upload objects, kích hoạt versioning, cấu hình lifecycle policies | 09/23/2025   | 09/23/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 3    | Tìm hiểu bảo mật S3: bucket policies, ACLs, pre-signed URLs, encryption                     | 09/24/2025   | 09/24/2025      | <https://000057.awsstudygroup.com/>       |
| 4    | Tìm hiểu nền tảng DynamoDB: tables, items, partition key, sort key, capacity modes          | 09/25/2025   | 09/25/2025      | <https://docs.aws.amazon.com/dynamodb/>   |
| 5    | Thực hành DynamoDB: Tạo table, insert items, query và scan operations, auto-scaling         | 09/26/2025   | 09/26/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6    | Thực hành DynamoDB (tiếp theo): Update items, delete items, cấu hình indexes, TTL settings  | 09/27/2025   | 09/27/2025      | <https://cloudjourney.awsstudygroup.com/> |

### Thành tựu Tuần 3:

Thành công tìm hiểu và thực hành nền tảng S3:

- Tạo S3 buckets và upload/download objects
- Kích hoạt versioning để bảo vệ dữ liệu
- Cấu hình lifecycle policies để tối ưu hóa chi phí
- Triển khai bảo mật S3 với bucket policies và ACLs
- Tạo pre-signed URLs để cấp quyền truy cập tạm thời
- Kích hoạt server-side encryption cho dữ liệu nhạy cảm

Thành công tìm hiểu và thực hành nền tảng DynamoDB:

- Tạo DynamoDB tables với partition keys và sort keys
- Insert, update, và delete items
- Thực hiện Query và Scan operations với filters
- Cấu hình provisioned capacity và auto-scaling
- Tạo Global Secondary Indexes để truy vấn linh hoạt
- Thiết lập TTL để hết hạn items tự động
- Giám sát table metrics sử dụng CloudWatch

Đạt được kỹ năng quản lý lưu trữ objects và cơ sở dữ liệu NoSQL cho các ứng dụng sản xuất.

Tích hợp kiến thức S3 và DynamoDB với các dịch vụ AWS trước đó (EC2, IAM, VPC) để có hiểu biết toàn diện về cơ sở hạ tầng.
