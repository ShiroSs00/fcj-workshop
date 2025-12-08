---
title: "Nhật ký công việc - Tuần 4"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu Tuần 4:

- Tìm hiểu về Lambda (serverless computing) và kiến trúc hướng sự kiện.
- Hiểu về API Gateway để tạo REST APIs.
- Thực hành CloudWatch để giám sát và ghi nhật ký.
- Tích hợp nhiều dịch vụ AWS vào một ứng dụng hoàn chỉnh.

### Các nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                      |
| ---- | ------------------------------------------------------------------------------------------------ | ------------ | --------------- | --------------------------------------- |
| 1    | Tìm hiểu nền tảng Lambda: functions, triggers, runtime, execution role, permissions              | 09/29/2025   | 09/29/2025      | https://docs.aws.amazon.com/lambda/     |
| 2    | Thực hành Lambda: Tạo function, kiểm tra invocation, cấu hình trigger, đặt environment variables | 09/30/2025   | 09/30/2025      | https://cloudjourney.awsstudygroup.com/ |
| 3    | Tìm hiểu API Gateway: REST APIs, endpoints, methods, request/response mapping, authorization     | 10/01/2025   | 10/01/2025      | https://docs.aws.amazon.com/apigateway/ |
| 4    | Thực hành API Gateway: Tạo REST API, cấu hình resources và methods, tích hợp với Lambda          | 10/02/2025   | 10/02/2025      | https://cloudjourney.awsstudygroup.com/ |
| 5    | Tìm hiểu CloudWatch: monitoring, logging, metrics, alarms, dashboards                            | 10/03/2025   | 10/03/2025      | https://docs.aws.amazon.com/cloudwatch/ |
| 6    | Thực hành CloudWatch: Tạo logs, đặt metrics, cấu hình alarms, xây dựng dashboards để giám sát    | 10/04/2025   | 10/04/2025      | https://cloudjourney.awsstudygroup.com/ |

### Thành tựu Tuần 4:

- Hiểu rõ serverless computing với Lambda và kiến trúc hướng sự kiện.

- Thành công tạo và kiểm tra Lambda functions với các execution roles và permissions phù hợp.

- Làm quen với API Gateway và học cách tạo REST APIs và tích hợp với Lambda.

- Cài đặt và cấu hình CloudWatch để giám sát, ghi nhật ký và tạo alarms.

- Sử dụng CloudWatch để thực hiện các hoạt động giám sát như:

  - Xem Lambda function logs
  - Tạo custom metrics
  - Thiết lập CloudWatch alarms
  - Xây dựng monitoring dashboards
  - Phân tích logs với CloudWatch Logs Insights

- Thành công hoàn thành dự án tích hợp kết hợp:

  - Lambda cho xử lý serverless
  - API Gateway cho REST API endpoints
  - S3 cho triggers lưu trữ objects
  - DynamoDB cho lưu trữ dữ liệu
  - CloudWatch cho giám sát toàn diện

- Có được khả năng thiết kế các ứng dụng hướng sự kiện và xây dựng các giải pháp serverless có thể mở rộng trên AWS.
