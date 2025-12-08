---
title: "Nhật ký công việc - Tuần 12"
date: "`r Sys.Date()`"
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu Tuần 12:

- Thiết kế và triển khai một nền tảng chia sẻ video hoàn chỉnh sử dụng AWS services và ASP.NET Core.
- Tích hợp tất cả các dịch vụ AWS đã học trong thời gian thực tập.
- Xây dựng ứng dụng production-ready với kiến trúc và deployment phù hợp.

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                      |
| ---- | ------------------------------------------------------------------------------------------ | ------------ | --------------- | --------------------------------------- |
| 1    | Thiết kế kiến trúc hệ thống: Định nghĩa các thành phần, dịch vụ AWS, data flow             | 11/24/2025   | 11/24/2025      | Tất cả các tuần trước                   |
| 2    | Thiết lập cơ sở hạ tầng: Tạo VPC, security groups, EC2 instances, RDS database             | 11/25/2025   | 11/25/2025      | https://cloudjourney.awsstudygroup.com/ |
| 3    | Triển khai backend API: Quản lý users, authentication, video metadata endpoints            | 11/26/2025   | 11/26/2025      | Các tuần ASP.NET Core trước             |
| 4    | Triển khai video operations: Upload lên S3, lưu metadata trong DynamoDB, Lambda processing | 11/27/2025   | 11/27/2025      | Tuần 3, 4, 6                            |
| 5    | Triển khai video delivery: Phát videos từ S3, streaming, CloudFront CDN                    | 11/28/2025   | 11/28/2025      | https://docs.aws.amazon.com/cloudfront/ |
| 6    | Triển khai và giám sát: CloudFormation deployment, CloudWatch monitoring, testing          | 11/29/2025   | 11/29/2025      | Tuần 7, 8                               |

### Thành tựu Tuần 12:

- Thành công thiết kế kiến trúc nền tảng chia sẻ video hoàn chỉnh tích hợp tất cả dịch vụ AWS.

- Triển khai hệ thống quản lý users với JWT authentication và Cognito integration.

- Xây dựng chức năng upload video với S3 integration và pre-signed URLs.

- Tạo hệ thống quản lý video metadata sử dụng DynamoDB với query hiệu quả.

- Triển khai xử lý video serverless sử dụng Lambda được trigger bởi S3 events.

- Cấu hình CloudFront CDN để phân phối và streaming videos hiệu quả.

- Thiết lập comprehensive monitoring và logging với CloudWatch và X-Ray.

- Triển khai ứng dụng hoàn chỉnh sử dụng CloudFormation infrastructure as code.

- Tự động hóa CI/CD pipeline với CodePipeline, CodeBuild, và CodeDeploy.

- Thành công tích hợp tất cả các dịch vụ AWS đã học trong thời gian thực tập vào một ứng dụng production-ready.

- Đạt được hiểu biết toàn diện về xây dựng, triển khai, và giám sát các ứng dụng cloud cấp enterprise.
