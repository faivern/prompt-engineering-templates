# Architecture Review Template

## Purpose
Review software architecture, design patterns, and system structure for scalability and maintainability.

## Template

```
I need you to review the architecture of the following system:

**System Type**: [web application/microservices/mobile app/etc.]
**Purpose**: [what the system does]
**Current Scale**: [users, requests, data volume]
**Expected Growth**: [growth projections]

**Architecture Overview**:
[Provide description or diagram of current architecture]

**Components**:
- [Component 1]: [description]
- [Component 2]: [description]
- [Component 3]: [description]

**Technology Stack**:
- Frontend: [technologies]
- Backend: [technologies]
- Database: [technologies]
- Infrastructure: [cloud/on-prem, services used]

**Current Issues**:
- [issue 1]
- [issue 2]

**Review Focus**:
- Scalability
- Maintainability
- Security architecture
- Data flow and consistency
- Service boundaries
- Design patterns used
- Deployment strategy
- Monitoring and observability
- [specific architectural concerns]

Please provide:
1. Overall architecture assessment
2. Strengths of current design
3. Identified issues and anti-patterns
4. Scalability concerns
5. Security architecture review
6. Recommendations for improvement
7. Alternative approaches to consider
8. Migration path if redesign is needed
```

## Example

```
I need you to review the architecture of the following system:

**System Type**: E-commerce web application
**Purpose**: Online store with product catalog, shopping cart, and order processing
**Current Scale**: 10,000 daily active users, 1,000 orders per day
**Expected Growth**: 10x growth over next 2 years

**Architecture Overview**:
Monolithic application with the following structure:
- Single Node.js/Express server handling all requests
- PostgreSQL database for all data
- Redis for session storage
- All services in a single codebase
- Deployed on single EC2 instance
- No load balancer
- Manual deployments

**Components**:
- User Service: Authentication, profiles, preferences
- Product Service: Catalog, inventory, search
- Cart Service: Shopping cart management
- Order Service: Order processing, payment, fulfillment
- Notification Service: Email and SMS notifications

**Technology Stack**:
- Frontend: React SPA
- Backend: Node.js/Express (monolith)
- Database: PostgreSQL (single instance)
- Cache: Redis
- Infrastructure: AWS EC2, S3 for images

**Current Issues**:
- Slow response times during peak traffic
- Deployments require downtime
- Difficult to scale specific services
- One service failure brings down entire app
- Growing codebase becoming hard to maintain

**Review Focus**:
- Scalability for 10x growth
- Service decomposition strategy
- Database scaling approach
- Fault tolerance and resilience
- Deployment and CI/CD improvements
- Monitoring and observability
- Cost optimization

Please provide:
1. Overall architecture assessment
2. Strengths of current design (simplicity, etc.)
3. Identified issues (single point of failure, no horizontal scaling)
4. Scalability concerns for projected growth
5. Security architecture review (API gateway, service mesh)
6. Recommendations (microservices, load balancing, database replication)
7. Alternative approaches (serverless, event-driven)
8. Phased migration path to improved architecture
```

## Tips

1. **Provide complete system context** including scale and growth
2. **Describe current architecture** with components and relationships
3. **List specific problems** you're experiencing
4. **Mention growth expectations** to inform scaling recommendations
5. **Include technology stack** for context-appropriate suggestions
6. **Specify review focus areas** most important to you
7. **Ask for migration path** if redesign is recommended
8. **Request trade-off analysis** for different approaches
