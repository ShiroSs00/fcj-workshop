---
title: "Worklog Tuần 1"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu Tuần 1:

- Kết nối và làm quen với các thành viên của First Cloud Journey.
- Hiểu về các dịch vụ AWS cơ bản, cách sử dụng Console & CLI.

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ                                                                                                                                                                                               | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                  |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | --------------------------------------------------- |
| 2    | - Làm quen với các thành viên FCJ <br> - Đọc và ghi chú các quy tắc và quy định của đơn vị thực tập                                                                                                    | 09/08/2025   | 09/08/2025      |
| 3    | - Tìm hiểu về AWS và các loại dịch vụ <br>&emsp; + Compute (Tính toán) <br>&emsp; + Storage (Lưu trữ) <br>&emsp; + Networking (Mạng) <br>&emsp; + Database (Cơ sở dữ liệu) <br>&emsp; + ... <br>       | 09/09/2025   | 09/09/2025      | <https://cloudjourney.awsstudygroup.com/1-explore/> |
| 4    | - Tạo tài khoản AWS Free Tier <br> - Tìm hiểu về AWS Console & AWS CLI <br> - **Thực hành:** <br>&emsp; + Tạo tài khoản AWS <br>&emsp; + Cài đặt & cấu hình AWS CLI <br> &emsp; + Cách sử dụng AWS CLI | 09/10/2025   | 09/10/2025      | <https://000001.awsstudygroup.com/>                 |
| 5    | - Quản lý chi phí với AWS Budgets: <br>&emsp; + Ngân sách Chi phí <br>&emsp; + Ngân sách Sử dụng <br>&emsp; + Ngân sách Reservation <br>&emsp; + Ngân sách Savings Plans <br><br>                      | 09/11/2025   | 09/11/2025      | <https://000007.awsstudygroup.com/>                 |
| 6    | - **Thực hành:** <br>&emsp; + Khởi chạy EC2 instance <br>&emsp; + Kết nối qua SSH <br>&emsp; + Gắn một volume EBS                                                                                      | 09/12/2025   | 09/12/2025      | <https://docs.aws.amazon.com/ec2/>                  |

### Thành tựu Tuần 1:

- Hiểu rõ nền tảng AWS và các danh mục dịch vụ cơ bản:

  - Dịch vụ Compute: EC2, Lambda, Lightsail
  - Dịch vụ Storage: S3, EBS, Glacier
  - Dịch vụ Database: DynamoDB, RDS, Aurora
  - Dịch vụ Networking: VPC, CloudFront, Route 53
  - Công cụ Developer: CodePipeline, CodeBuild, CodeDeploy

- Thành công tạo và cấu hình tài khoản AWS Free Tier.

- Làm quen với AWS Management Console và học cách tìm kiếm, truy cập và sử dụng các dịch vụ qua giao diện web.

- Cài đặt và cấu hình AWS CLI trên máy tính, bao gồm:

  - Access Key
  - Secret Key
  - Default Region

- Sử dụng AWS CLI để thực hiện các hoạt động cơ bản như:

  - Kiểm tra thông tin tài khoản & cấu hình
  - Lấy danh sách các region
  - Xem dịch vụ EC2
  - Tạo và quản lý key pairs
  - Kiểm tra thông tin về các dịch vụ đang chạy
  - ...

- Hoàn thành thành công bài thực hành EC2:
  - Khởi chạy EC2 t2.micro instance (đủ điều kiện Free Tier)
  - Tạo và cấu hình Security Groups cho SSH, HTTP, HTTPS
  - Tạo và tải xuống EC2 key pair
  - Kết nối đến EC2 instance qua SSH
  - Gắn volume EBS và mount filesystem
  - Cài đặt và cấu hình web server
