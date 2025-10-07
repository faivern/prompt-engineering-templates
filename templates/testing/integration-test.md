# Integration Test Template

## Purpose
Generate integration tests that verify components work correctly together.

## Template

```
I need you to create integration tests for the following system:

**Testing Framework**: [framework]
**Components to Test**:
- [Component 1]
- [Component 2]
- [Component 3]

**Integration Points**:
- [Integration 1: e.g., API → Database]
- [Integration 2: e.g., Service → External API]
- [Integration 3: e.g., Frontend → Backend]

**System Description**:
[Brief description of how components interact]

**Code/Endpoints to Test**:
```[language]
[paste relevant code or list endpoints]
```

**Test Scenarios**:
1. [Scenario 1: e.g., successful data flow]
2. [Scenario 2: e.g., error handling between components]
3. [Scenario 3: e.g., transaction rollback]

**Test Environment**:
- Database: [type and setup approach]
- External Services: [how to handle - mock/stub/real]
- Authentication: [how to handle]

**Test Data**:
- [describe test data needs]
- Fixtures/Seed data: [yes/no]

**Setup Requirements**:
- Database migrations: [yes/no]
- Initial data: [describe]
- Environment variables: [list]

Please provide:
1. Complete integration test suite
2. Setup and teardown procedures
3. Test data fixtures
4. Mock/stub implementations if needed
5. Clear test scenarios with assertions
6. Error case testing
7. Cleanup procedures
```

## Example

```
I need you to create integration tests for the following system:

**Testing Framework**: Jest with Supertest (Node.js/Express)
**Components to Test**:
- Express API endpoints
- PostgreSQL database (via Sequelize ORM)
- Authentication middleware
- External payment service

**Integration Points**:
- API endpoints → Database operations
- API → Authentication middleware → Protected routes
- Order processing → Payment service API
- Error handling → Database transactions

**System Description**:
E-commerce API with user authentication, product catalog, and order processing. Tests should verify the complete flow from HTTP request through business logic to database persistence.

**Code/Endpoints to Test**:
```javascript
// POST /api/orders - Create new order
// Requires authentication
// Validates products exist
// Processes payment via external service
// Saves order to database
// Returns order confirmation

// GET /api/orders/:id - Get order details
// Requires authentication
// User can only access their own orders
```

**Test Scenarios**:
1. Successfully create order with valid products and payment
2. Reject order with non-existent products
3. Reject order with invalid payment details
4. Verify transaction rollback on payment failure
5. Verify authorization (users can't access others' orders)
6. Handle concurrent order creation
7. Validate order totals calculated correctly

**Test Environment**:
- Database: PostgreSQL test database (isolated for each test)
- External Services: Mock payment service (stub API calls)
- Authentication: Generate test JWT tokens

**Test Data**:
- Seed database with test users and products before tests
- Create fixtures for valid/invalid payment scenarios
- Use unique data per test to avoid conflicts

**Setup Requirements**:
- Database migrations: Yes, run before test suite
- Initial data: Seed users and products
- Environment variables: TEST_DATABASE_URL, JWT_SECRET

Please provide:
1. Complete test suite with all scenarios
2. beforeAll/afterAll hooks for database setup/teardown
3. beforeEach/afterEach for test isolation
4. Test data seeding functions
5. Mock payment service implementation
6. Helper functions for authentication tokens
7. Transaction rollback tests
8. Clear assertions for each scenario
```

## Tips

1. **Describe the integration points** clearly
2. **Specify how to handle external services** (mock, stub, or real)
3. **Define test data strategy** (fixtures, factories, seeds)
4. **Request setup and teardown** procedures
5. **List all scenarios** including error cases
6. **Mention isolation requirements** between tests
7. **Specify authentication handling** if needed
8. **Request transaction testing** for data consistency
9. **Ask for helper functions** to reduce test code duplication
