---
title: "Event 2"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: "DevOps on AWS"

### Event Information

- **Date**: Monday, November 17, 2025
- **Time**: 8:30 AM – 5:00 PM
- **Location**: AWS Vietnam Office

### Event Objectives

- Understand DevOps culture, principles, and key metrics
- Master AWS CI/CD services (CodeCommit, CodeBuild, CodeDeploy, CodePipeline)
- Learn Infrastructure as Code with CloudFormation and AWS CDK
- Explore containerization with Docker, ECR, ECS, and EKS
- Implement monitoring and observability solutions
- Discover DevOps best practices and real-world case studies

### Event Agenda

#### Morning Session (8:30 AM – 12:00 PM)

##### 8:30 – 9:00 AM | Welcome & DevOps Mindset

- Recap of AI/ML session
- DevOps culture and principles
- Benefits and key metrics (DORA, MTTR, deployment frequency)

##### 9:00 – 10:30 AM | AWS DevOps Services – CI/CD Pipeline

- **Source Control**: AWS CodeCommit, Git strategies (GitFlow, Trunk-based)
- **Build & Test**: CodeBuild configuration, testing pipelines
- **Deployment**: CodeDeploy with Blue/Green, Canary, and Rolling updates
- **Orchestration**: CodePipeline automation
- **Live Demo**: Full CI/CD pipeline walkthrough

##### 10:30 – 10:45 AM | Break

##### 10:45 AM – 12:00 PM | Infrastructure as Code (IaC)

- **AWS CloudFormation**: Templates, stacks, and drift detection
- **AWS CDK (Cloud Development Kit)**: Constructs, reusable patterns, and language support
- **Demo**: Deploying with CloudFormation and CDK
- **Discussion**: Choosing between IaC tools

#### Lunch Break (12:00 – 1:00 PM)

_Self-arranged lunch break_

#### Afternoon Session (1:00 – 5:00 PM)

##### 1:00 – 2:30 PM | Container Services on AWS

- **Docker Fundamentals**: Microservices and containerization
- **Amazon ECR**: Image storage, scanning, lifecycle policies
- **Amazon ECS & EKS**: Deployment strategies, scaling, and orchestration
- **AWS App Runner**: Simplified container deployment
- **Demo & Case Study**: Microservices deployment comparison

##### 2:30 – 2:45 PM | Break

##### 2:45 – 4:00 PM | Monitoring & Observability

- **CloudWatch**: Metrics, logs, alarms, and dashboards
- **AWS X-Ray**: Distributed tracing and performance insights
- **Demo**: Full-stack observability setup
- **Best Practices**: Alerting, dashboards, and on-call processes

##### 4:00 – 4:45 PM | DevOps Best Practices & Case Studies

- **Deployment strategies**: Feature flags, A/B testing
- **Automated testing** and CI/CD integration
- **Incident management** and postmortems
- **Case Studies**: Startups and enterprise DevOps transformations

##### 4:45 – 5:00 PM | Q&A & Wrap-up

- DevOps career pathways
- AWS certification roadmap

### Key Highlights

#### DevOps Culture & Metrics

- **DORA Metrics**: Deployment frequency, lead time, mean time to recovery (MTTR), change failure rate
- **Key Benefits**: Faster time-to-market, improved reliability, enhanced team collaboration
- **Cultural shift**: Breaking silos between development and operations teams
- **Continuous improvement**: Iterative processes and feedback loops

#### AWS CI/CD Pipeline Services

- **CodeCommit**: Fully managed Git repository with branch protection and pull request reviews
- **CodeBuild**: Fully managed build service supporting multiple languages and frameworks
- **CodeDeploy**: Automated deployments with multiple strategies (Blue/Green, Canary, Rolling)
- **CodePipeline**: Orchestrate workflows across build, test, and deployment stages
- **Git Strategies**: GitFlow for feature branches, Trunk-based for continuous deployment

#### Infrastructure as Code (IaC)

##### CloudFormation

- **Templates**: JSON/YAML format defining AWS resources
- **Stacks**: Collections of resources managed as a single unit
- **Change Sets**: Preview changes before applying
- **Drift Detection**: Identify manual changes to stack resources
- **Stack Policies**: Control who can modify resources

##### AWS CDK

- **Language Support**: Python, JavaScript, Java, C#, Go
- **Constructs**: Pre-built components for common AWS patterns
- **Reusability**: Share constructs across teams and projects
- **Type Safety**: Catch errors at development time
- **Synthesis**: Generate CloudFormation templates from code

#### Container Services

##### Docker & Containerization

- **Microservices**: Breaking monolithic applications into smaller, manageable services
- **Portability**: Consistent behavior across different environments
- **Resource Efficiency**: Lightweight compared to virtual machines
- **Isolation**: Each container runs independently with its dependencies

##### Amazon ECR (Elastic Container Registry)

- **Image Storage**: Centralized repository for Docker images
- **Scanning**: Automatic vulnerability detection
- **Lifecycle Policies**: Automate image retention and cleanup
- **Integration**: Seamless integration with ECS, EKS, and other AWS services

##### ECS & EKS

- **ECS (Elastic Container Service)**: AWS-native orchestration, simpler setup
- **EKS (Elastic Kubernetes Service)**: Kubernetes-based, more complex but powerful
- **Deployment Strategies**: Blue/Green, rolling updates, canary deployments
- **Auto Scaling**: Scale based on metrics (CPU, memory, custom metrics)
- **Service Discovery**: Automatic load balancing and DNS

##### AWS App Runner

- **Simplified Deployment**: Deploy containers without managing infrastructure
- **Automatic Scaling**: Handles scaling based on demand
- **Built-in Security**: TLS termination, automatic patching
- **Quick Setup**: Deploy from source code or container image

#### Monitoring & Observability

##### CloudWatch

- **Metrics**: Track application and infrastructure performance
- **Logs**: Centralized log aggregation and analysis
- **Alarms**: Set thresholds and trigger automated actions
- **Dashboards**: Visualize metrics and logs in real-time
- **Custom Metrics**: Track application-specific metrics

##### AWS X-Ray

- **Distributed Tracing**: Track requests across multiple services
- **Performance Insights**: Identify bottlenecks and latency issues
- **Service Map**: Visualize service dependencies and interactions
- **Error Analysis**: Trace failures to their root causes
- **Integration**: Works with Lambda, API Gateway, RDS, and more

#### DevOps Best Practices

- **Feature Flags**: Deploy code without releasing features immediately
- **A/B Testing**: Compare different implementations in production
- **Automated Testing**: Unit, integration, and end-to-end tests in pipeline
- **Incident Management**: Documented processes for handling outages
- **Postmortems**: Learn from incidents without blame
- **On-Call Rotation**: Fair distribution of incident response responsibilities
- **Observability First**: Monitor and alert on important metrics

### Key Takeaways

#### Technical Skills

- **CI/CD Mastery**: Build complete automation pipelines with CodePipeline
- **IaC Proficiency**: Choose between CloudFormation and CDK for infrastructure
- **Containerization**: Understand Docker and orchestration platforms (ECS, EKS)
- **Observability**: Implement comprehensive monitoring with CloudWatch and X-Ray
- **Deployment Strategies**: Safely roll out changes with minimal risk

#### Best Practices

- **Automation First**: Automate everything from builds to deployments
- **Infrastructure as Code**: Treat infrastructure like software with versioning
- **Observability Over Monitoring**: Understand system behavior, not just metrics
- **Fail Fast, Recover Quick**: Implement canary and blue/green deployments
- **Shared Responsibility**: Foster collaboration between development and operations

#### Career Insights

- **DevOps Roles**: Site Reliability Engineer, Platform Engineer, Infrastructure Engineer
- **AWS Certifications**: DevOps Engineer – Professional, Solutions Architect
- **Continuous Learning**: DevOps evolves rapidly; stay updated with latest practices
- **Skills in Demand**: Automation, cloud platforms, containerization, observability

### Applying to Work

- **Implement CI/CD**: Migrate existing deployment processes to CodePipeline
- **Adopt IaC**: Convert manual infrastructure setup to CloudFormation or CDK
- **Containerize Applications**: Evaluate which applications benefit from containerization
- **Deploy to ECS/EKS**: Choose appropriate container orchestration platform
- **Setup Observability**: Implement CloudWatch dashboards and X-Ray tracing
- **Define Deployment Strategies**: Implement blue/green or canary deployments
- **Automate Testing**: Integrate automated tests into CI/CD pipeline
- **Establish On-Call Process**: Implement incident response procedures

### Event Experience

Attending the **"DevOps on AWS"** workshop provided comprehensive understanding of modern DevOps practices and AWS services for automation and infrastructure management.

#### Learning from AWS experts

- Gained deep knowledge of AWS DevOps service ecosystem
- Learned proven strategies for CI/CD pipeline design and implementation
- Understood different approaches to infrastructure management
- Discovered best practices for monitoring production systems

#### Hands-on technical exposure

- **CI/CD Pipeline Demo**: Saw complete automation from code commit to production deployment
- **IaC Comparison**: Understood trade-offs between CloudFormation and CDK
- **Container Orchestration**: Learned differences between ECS and EKS
- **Full-stack Observability**: Saw how CloudWatch and X-Ray work together

#### Key insights gained

- DevOps is about culture and process, not just tools
- Automation reduces manual errors and accelerates releases
- Infrastructure as Code enables reproducible, version-controlled environments
- Observability is critical for understanding production system behavior
- Container orchestration simplifies scaling and deployment of microservices

#### Practical applications

- Can implement CodePipeline for automated deployments
- Can use CloudFormation or CDK for infrastructure provisioning
- Can containerize applications and deploy to ECS or EKS
- Can setup comprehensive monitoring with CloudWatch and X-Ray
- Can implement safe deployment strategies (blue/green, canary)

#### Networking opportunities

- Connected with AWS DevOps specialists
- Discussed automation challenges with fellow participants
- Learned about DevOps transformation case studies from enterprise perspective

#### Lessons learned

- Start with CI/CD automation before complex infrastructure
- Choose IaC tool based on team expertise and project needs
- Invest in observability early to reduce troubleshooting time
- Implement safety mechanisms (feature flags, gradual rollouts) for production changes
- Foster collaboration between development and operations teams

### Event Photos

_Add your event photos here_

> Overall, this DevOps workshop significantly enhanced my understanding of production deployment, automation, and infrastructure management. The combination of expert guidance, live demonstrations, and case studies provided actionable insights I can immediately apply to improve development workflows and system reliability.
