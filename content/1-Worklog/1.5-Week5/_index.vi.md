---
title: "Nhật ký công việc - Tuần 5"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu Tuần 5:

- Thực hành và củng cố IAM, VPC, S3, và DynamoDB thông qua các bài thực hành.
- Xây dựng các dự án tích hợp các dịch vụ lưu trữ và cơ sở dữ liệu.

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                           |
| ---- | -------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------ |
| 1    | Thực hành IAM: Tạo users, roles, groups, và policies                       | 10/06/2025   | 10/06/2025      | https://cloudjourney.awsstudygroup.com/2-manage/2-1-iam/     |
| 2    | Thực hành VPC: Tạo VPC, subnets, security groups, route tables             | 10/07/2025   | 10/07/2025      | https://cloudjourney.awsstudygroup.com/2-manage/2-2-vpc/     |
| 3    | Thực hành S3: Tạo buckets, upload objects, versioning, lifecycle policies  | 10/08/2025   | 10/08/2025      | https://cloudjourney.awsstudygroup.com/3-store/3-1-s3/       |
| 4    | Thực hành DynamoDB: Tạo tables, CRUD operations, indexes                   | 10/09/2025   | 10/09/2025      | https://cloudjourney.awsstudygroup.com/3-store/3-2-dynamodb/ |
| 5    | Dự án: Hệ thống lưu trữ tệp với S3 và metadata trong DynamoDB              | 10/10/2025   | 10/10/2025      | https://cloudjourney.awsstudygroup.com/3-store/              |
| 6    | Khắc phục sự cố: Sửa chữa connectivity, permissions, và performance issues | 10/11/2025   | 10/11/2025      | https://cloudjourney.awsstudygroup.com/                      |

### Thành tựu Tuần 5:

- Thành công thực hành tạo IAM users và roles với các quyền hạn phù hợp.
- Xây dựng VPC với public và private subnets có security groups hoạt động.
- Tạo S3 buckets với versioning và lifecycle policies được cấu hình.
- Tạo DynamoDB tables và thực hiện các CRUD operations.
- Xây dựng dự án lưu trữ tệp kết hợp S3 và DynamoDB.
- Gỡ lỗi và sửa chữa các vấn đề về connectivity và permissions.

### Chi tiết thực hành:

#### Thực hành IAM

- Tạo IAM users với các mục đích khác nhau
- Tổ chức users vào các nhóm theo chức năng
- Gán roles và policies để kiểm soát truy cập
- Kiểm tra quyền hạn và kiểm soát truy cập

#### Thực hành VPC

- Thiết kế VPC với các subnets công khai và riêng tư
- Cấu hình security groups với quy tắc inbound/outbound
- Thiết lập route tables và Internet Gateway
- Kiểm tra kết nối giữa các resources

#### Thực hành S3

- Tạo multiple S3 buckets cho các mục đích khác nhau
- Kích hoạt versioning để bảo vệ dữ liệu
- Cấu hình lifecycle policies để tối ưu hóa chi phí lưu trữ
- Triển khai bucket policies và ACLs
- Cài đặt encryption và logging

#### Thực hành DynamoDB

- Thiết kế bảng với partition keys và sort keys phù hợp
- Thực hiện Create, Read, Update, Delete (CRUD) operations
- Tạo Global Secondary Indexes (GSI) cho truy vấn linh hoạt
- Cấu hình auto-scaling và TTL
- Giám sát hiệu suất table

#### Dự án tích hợp - Hệ thống lưu trữ tệp

- **Kiến trúc**: S3 cho lưu trữ tệp, DynamoDB cho metadata
- **Tính năng**:
  - Upload và download tệp từ S3
  - Lưu trữ metadata (tên, kích thước, ngày tạo) trong DynamoDB
  - Quản lý phiên bản tệp
  - Tìm kiếm tệp dựa trên metadata
  - Xóa tệp cùng với metadata

#### Khắc phục sự cố

- Kiểm tra và sửa chữa lỗi kết nối mạng (VPC, Security Groups)
- Xác minh và điều chỉnh IAM permissions
- Phân tích và tối ưu hóa hiệu suất DynamoDB
- Khắc phục các vấn đề S3 bucket access
- Sử dụng CloudWatch logs để debug
