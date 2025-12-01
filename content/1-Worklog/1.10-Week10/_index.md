---
title: "Week 10 Worklog"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

- Learn advanced ASP.NET Core features: authentication, authorization, API security.
- Integrate ASP.NET Core API with AWS services.
- Practic

### Tasks to be carried out this week:

| Day | Task                                                                                   | Start Date | Completion Date | Reference Material                                                        |
| --- | -------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------------------------------------- |
| 1   | Learn about JWT authentication and Bearer tokens in ASP.NET Core                       | 11/10/2025 | 11/10/2025      | https://learn.microsoft.com/en-us/aspnet/core/security/authentication/jwt |
| 2   | Learn about authorization and role-based access control (RBAC)                         | 11/11/2025 | 11/11/2025      | https://learn.microsoft.com/en-us/aspnet/core/security/authorization/     |
| 3   | Practice: Implement JWT authentication in API, create login endpoint                   | 11/12/2025 | 11/12/2025      | https://learn.microsoft.com/en-us/aspnet/core/security/                   |
| 4   | Learn about integrating ASP.NET Core with AWS services (Cognito, S3, DynamoDB)         | 11/13/2025 | 11/13/2025      | https://docs.aws.amazon.com/sdk-for-net/                                  |
| 5   | Practice: Integrate API with AWS Cognito for user management                           | 11/14/2025 | 11/14/2025      | https://docs.aws.amazon.com/cognito/latest/developerguide/                |
| 6   | Practice: Integrate API with S3 for file upload/download and DynamoDB for data storage | 11/15/2025 | 11/15/2025      | https://docs.aws.amazon.com/sdk-for-net/                                  |

### Week 10 Achievements:

- Successfully learned JWT (JSON Web Token) authentication:

  - JWT structure and claims
  - Token generation and validation
  - Bearer token authorization
  - Token expiration and refresh tokens

- Successfully implemented authentication in ASP.NET Core API:

  - Created login endpoint that generates JWT tokens
  - Configured JWT validation middleware
  - Protected endpoints with [Authorize] attribute
  - Implemented secure password handling

- Successfully learned authorization and access control:

  - Role-based access control (RBAC)
  - Claims-based authorization
  - Authorization policies and requirements
  - Implementing role checks in endpoints

- Successfully implemented role-based authorization:

  - Created different user roles (Admin, User, etc.)
  - Protected endpoints with role requirements
  - Implemented authorization policies
  - Tested access control with different roles

- Successfully integrated ASP.NET Core API with AWS Cognito:

  - Configured Cognito user pool in API
  - Implemented user registration using Cognito SDK
  - Implemented user login and JWT token generation
  - Integrated Cognito for user management and authentication

- Successfully integrated ASP.NET Core API with AWS S3:

  - Uploaded files to S3 from API endpoints
  - Downloaded files from S3 through API
  - Managed S3 bucket operations from application
  - Implemented proper error handling for S3 operations

- Successfully integrated ASP.NET Core API with AWS DynamoDB:

  - Created DynamoDB client in ASP.NET Core
  - Implemented CRUD operations for DynamoDB
  - Stored and retrieved data from DynamoDB tables
  - Integrated database operations with API endpoints

- Successfully built complete application combining:

  - ASP.NET Core API for business logic
  - JWT authentication with Cognito
  - S3 integration for file storage
  - DynamoDB integration for data persistence
  - Proper error handling and validation
  - CloudWatch logging for monitoring

- Gained ability to build enterprise-grade, secure APIs integrated with AWS services.
