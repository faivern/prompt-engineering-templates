# Test Strategy Template

## Purpose
Develop a comprehensive testing strategy for a project or feature.

## Template

```
I need help creating a test strategy for the following project:

**Project Description**:
[Brief description of the project/feature]

**Project Type**: [web app/API/mobile app/library/etc.]
**Technology Stack**:
- [technology 1]
- [technology 2]
- [technology 3]

**Components/Features**:
1. [Component 1]
2. [Component 2]
3. [Component 3]

**Testing Objectives**:
- [objective 1: e.g., ensure reliability]
- [objective 2: e.g., prevent regressions]
- [objective 3: e.g., validate security]

**Current State**:
- Existing tests: [yes/no - describe]
- Coverage: [current coverage if known]
- CI/CD: [yes/no]

**Constraints**:
- Timeline: [available time]
- Resources: [team size, budget]
- [other constraints]

**Specific Concerns**:
- [concern 1: e.g., critical payment flow]
- [concern 2: e.g., performance under load]
- [concern 3: e.g., data integrity]

Please provide:
1. Testing pyramid strategy (unit/integration/e2e ratios)
2. Recommended testing frameworks and tools
3. Test coverage goals for each layer
4. Priority areas to test first
5. Testing types needed (unit, integration, e2e, performance, security)
6. CI/CD integration recommendations
7. Test data management strategy
8. Timeline and implementation plan
9. Success metrics
```

## Example

```
I need help creating a test strategy for the following project:

**Project Description**:
A financial transaction processing API that handles user accounts, transfers, and transaction history. Critical requirements include data accuracy, security, and high availability.

**Project Type**: RESTful API with microservices architecture
**Technology Stack**:
- Node.js/Express backend
- PostgreSQL database
- Redis for caching
- Docker/Kubernetes deployment
- External payment gateway integration

**Components/Features**:
1. User authentication and authorization (JWT)
2. Account management (create, update, view balances)
3. Money transfers (internal and external)
4. Transaction history and reporting
5. Payment gateway integration
6. Audit logging
7. Rate limiting and fraud detection

**Testing Objectives**:
- Ensure 100% accuracy for financial calculations
- Prevent security vulnerabilities (auth, injection, etc.)
- Validate data consistency across microservices
- Ensure system handles expected load (1000 req/sec)
- Prevent regressions in critical flows
- Maintain 99.9% uptime

**Current State**:
- Existing tests: Basic unit tests (~40% coverage)
- No integration or e2e tests
- Manual testing for releases
- No CI/CD pipeline yet

**Constraints**:
- Timeline: 8 weeks to improve testing
- Resources: 2 developers, limited budget for tools
- Must maintain development velocity

**Specific Concerns**:
- Money transfers must be atomic and accurate
- Concurrent transactions and race conditions
- External payment gateway failures and retries
- Security: authentication, authorization, data protection
- Performance under peak load
- Database transaction integrity

Please provide:
1. Testing pyramid strategy (unit/integration/e2e distribution)
2. Recommended frameworks (Jest, Supertest, etc.)
3. Coverage goals (unit: 80%, integration: 60%, e2e: critical paths)
4. Priority: Start with transaction integrity tests
5. Testing types:
   - Unit tests for business logic
   - Integration tests for API endpoints
   - Contract tests for payment gateway
   - Load tests for performance
   - Security tests for vulnerabilities
6. CI/CD integration (GitHub Actions with test stages)
7. Test data strategy (fixtures, factories, isolated test DB)
8. 8-week phased implementation plan
9. Metrics (coverage %, regression count, deployment confidence)
```

## Tips

1. **Describe the project completely** including its criticality
2. **List all components** that need testing
3. **Specify testing objectives** and why you're testing
4. **Mention current state** to understand starting point
5. **Define constraints** (time, resources, budget)
6. **Highlight critical areas** that need special attention
7. **Request specific recommendations** (tools, frameworks)
8. **Ask for implementation timeline** if starting from scratch
9. **Request metrics** to track progress and success
10. **Mention compliance needs** if applicable (SOC2, HIPAA, etc.)
