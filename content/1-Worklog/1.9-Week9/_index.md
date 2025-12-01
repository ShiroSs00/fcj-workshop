---
title: "Week 9 Worklog"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

- Learn ASP.NET Core fundamentals for building REST APIs.
- Understand Model-View-Controller (MVC) and Dependency Injection patterns.
- Practice building and testing RESTful APIs with ASP.NET Core.

### Tasks to be carried out this week:

| Day | Task                                                                    | Start Date | Completion Date | Reference Material                                                              |
| --- | ----------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------------------------------------------- |
| 1   | Learn ASP.NET Core basics: project structure, controllers, routing      | 11/03/2025 | 11/03/2025      | https://learn.microsoft.com/en-us/aspnet/core/                                  |
| 2   | Learn about Dependency Injection and middleware in ASP.NET Core         | 11/04/2025 | 11/04/2025      | https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection |
| 3   | Practice: Create ASP.NET Core project, setup controllers, define routes | 11/05/2025 | 11/05/2025      | https://learn.microsoft.com/en-us/aspnet/core/tutorials/                        |
| 4   | Learn about Entity Framework Core and database operations               | 11/06/2025 | 11/06/2025      | https://learn.microsoft.com/en-us/ef/core/                                      |
| 5   | Practice: Create API endpoints for CRUD operations with EF Core         | 11/07/2025 | 11/07/2025      | https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api           |
| 6   | Practice: Test API endpoints, implement error handling, validation      | 11/08/2025 | 11/08/2025      | https://learn.microsoft.com/en-us/aspnet/core/web-api/                          |

### Week 9 Achievements:

- Understood ASP.NET Core fundamentals and project structure:

  - Startup configuration and middleware pipeline
  - Controller-based and minimal API patterns
  - Routing and endpoint mapping
  - Request/response handling

- Successfully learned Dependency Injection pattern:

  - Service registration in ConfigureServices
  - Constructor injection for loose coupling
  - Singleton, Scoped, Transient lifetimes
  - Dependency Injection container usage

- Successfully created ASP.NET Core REST API project:

  - Set up API controllers with appropriate routing
  - Defined HTTP GET, POST, PUT, DELETE endpoints
  - Implemented action results (Ok, Created, BadRequest, NotFound)
  - Structured code following RESTful conventions

- Successfully learned Entity Framework Core:

  - DbContext configuration and setup
  - Entity models and relationships
  - Migrations for database schema management
  - Query operations with LINQ

- Successfully implemented CRUD API endpoints:

  - GET endpoints for retrieving single and multiple resources
  - POST endpoints for creating new resources
  - PUT endpoints for updating existing resources
  - DELETE endpoints for removing resources
  - Proper HTTP status codes and response formats

- Successfully tested and validated API:

  - Tested endpoints using Postman
  - Implemented input validation with data annotations
  - Added error handling and exception handling middleware
  - Validated request data before processing
  - Implemented proper HTTP status codes for different scenarios

- Gained ability to build production-ready REST APIs with ASP.NET Core.
