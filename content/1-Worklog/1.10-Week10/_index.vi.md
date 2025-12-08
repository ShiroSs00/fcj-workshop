---
title: "Nhật ký công việc - Tuần 10"
date: "`r Sys.Date()`"
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu Tuần 10:

- Tìm hiểu các tính năng nâng cao của ASP.NET Core: authentication, authorization, API security.
- Tích hợp ASP.NET Core API với các dịch vụ AWS.
- Thực hành xây dựng API an toàn tích hợp AWS.

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ                                                                               | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                        |
| ---- | -------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------------------- |
| 1    | Tìm hiểu JWT authentication và Bearer tokens trong ASP.NET Core                        | 11/10/2025   | 11/10/2025      | https://learn.microsoft.com/en-us/aspnet/core/security/authentication/jwt |
| 2    | Tìm hiểu authorization và role-based access control (RBAC)                             | 11/11/2025   | 11/11/2025      | https://learn.microsoft.com/en-us/aspnet/core/security/authorization/     |
| 3    | Thực hành: Triển khai JWT authentication trong API, tạo login endpoint                 | 11/12/2025   | 11/12/2025      | https://learn.microsoft.com/en-us/aspnet/core/security/                   |
| 4    | Tìm hiểu tích hợp ASP.NET Core với các dịch vụ AWS (Cognito, S3, DynamoDB)             | 11/13/2025   | 11/13/2025      | https://docs.aws.amazon.com/sdk-for-net/                                  |
| 5    | Thực hành: Tích hợp API với AWS Cognito để quản lý users                               | 11/14/2025   | 11/14/2025      | https://docs.aws.amazon.com/cognito/latest/developerguide/                |
| 6    | Thực hành: Tích hợp API với S3 để upload/download files và DynamoDB để lưu trữ dữ liệu | 11/15/2025   | 11/15/2025      | https://docs.aws.amazon.com/sdk-for-net/                                  |

### Thành tựu Tuần 10:

- Thành công tìm hiểu JWT (JSON Web Token) authentication:

  - Cấu trúc JWT và claims
  - Tạo và xác thực tokens
  - Bearer token authorization
  - Token expiration và refresh tokens

- Thành công triển khai authentication trong ASP.NET Core API:

  - Tạo login endpoint để tạo JWT tokens
  - Cấu hình JWT validation middleware
  - Bảo vệ endpoints với [Authorize] attribute
  - Triển khai xử lý password an toàn

- Thành công tìm hiểu authorization và access control:

  - Role-based access control (RBAC)
  - Claims-based authorization
  - Authorization policies và requirements
  - Triển khai role checks trong endpoints

- Thành công triển khai role-based authorization:

  - Tạo các user roles khác nhau (Admin, User, v.v.)
  - Bảo vệ endpoints với role requirements
  - Triển khai authorization policies
  - Kiểm thử access control với các roles khác nhau

- Thành công tích hợp ASP.NET Core API với AWS Cognito:

  - Cấu hình Cognito user pool trong API
  - Triển khai user registration sử dụng Cognito SDK
  - Triển khai user login và JWT token generation
  - Tích hợp Cognito để quản lý users và authentication

- Thành công tích hợp ASP.NET Core API với AWS S3:

  - Upload files lên S3 từ API endpoints
  - Download files từ S3 qua API
  - Quản lý S3 bucket operations từ ứng dụng
  - Triển khai error handling cho S3 operations

- Thành công tích hợp ASP.NET Core API với AWS DynamoDB:

  - Tạo DynamoDB client trong ASP.NET Core
  - Triển khai CRUD operations cho DynamoDB
  - Lưu trữ và lấy dữ liệu từ DynamoDB tables
  - Tích hợp database operations với API endpoints

- Thành công xây dựng ứng dụng hoàn chỉnh kết hợp:

  - ASP.NET Core API cho business logic
  - JWT authentication với Cognito
  - S3 integration để lưu trữ files
  - DynamoDB integration để lưu trữ dữ liệu
  - Error handling và validation phù hợp
  - CloudWatch logging để giám sát

- Đạt được khả năng xây dựng enterprise-grade, secure APIs tích hợp với AWS services.
