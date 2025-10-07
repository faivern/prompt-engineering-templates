# Bug Diagnosis Template

## Purpose
Systematically diagnose bugs by providing context, symptoms, and relevant code.

## Template

```
I need help diagnosing a bug in my code:

**Programming Language**: [language]
**Framework/Library**: [if applicable]
**Environment**: [development/staging/production]

**Bug Description**:
[Clear description of what's going wrong]

**Expected Behavior**:
[What should happen]

**Actual Behavior**:
[What is actually happening]

**Steps to Reproduce**:
1. [step 1]
2. [step 2]
3. [step 3]

**Error Messages** (if any):
```
[paste error messages or stack traces]
```

**Relevant Code**:
```[language]
[paste the relevant code sections]
```

**Recent Changes**:
[Any recent code changes that might be related]

**What I've Tried**:
- [attempt 1]
- [attempt 2]

**Environment Details**:
- OS: [operating system]
- Version: [language/framework version]
- Dependencies: [relevant dependency versions]

Please help me:
1. Identify the root cause of the bug
2. Explain why it's happening
3. Suggest specific fixes with code examples
4. Recommend preventive measures
```

## Example

```
I need help diagnosing a bug in my code:

**Programming Language**: Python
**Framework/Library**: Flask + SQLAlchemy
**Environment**: Development (local)

**Bug Description**:
Database records are not updating when I try to modify user information through the API endpoint. The endpoint returns success but the database remains unchanged.

**Expected Behavior**:
When I send a PUT request to /api/users/{id} with updated data, the user record in the database should be modified and return the updated user data.

**Actual Behavior**:
The endpoint returns 200 OK with what appears to be the updated data, but when I check the database or fetch the user again, the old values are still there.

**Steps to Reproduce**:
1. Create a user with POST /api/users (works fine)
2. Send PUT /api/users/1 with {"name": "New Name"}
3. Endpoint returns 200 with the new name
4. GET /api/users/1 still returns the old name

**Error Messages** (if any):
No error messages - endpoint completes successfully

**Relevant Code**:
```python
@app.route('/api/users/<int:user_id>', methods=['PUT'])
def update_user(user_id):
    user = User.query.get_or_404(user_id)
    data = request.get_json()
    
    if 'name' in data:
        user.name = data['name']
    if 'email' in data:
        user.email = data['email']
    
    return jsonify(user.to_dict()), 200
```

**Recent Changes**:
Recently switched from Flask-SQLAlchemy 2.x to 3.x

**What I've Tried**:
- Added print statements to verify user object is being modified (it is)
- Checked that data is coming through in the request (it is)
- Verified database connection is working (it is for reads)

**Environment Details**:
- OS: macOS 13.0
- Python: 3.11
- Flask: 2.3.0
- SQLAlchemy: 2.0.0
- Database: PostgreSQL 14

Please help me:
1. Identify why changes aren't persisting
2. Explain the root cause
3. Provide the correct code to fix this
4. Suggest best practices for database updates in Flask
```

## Tips

1. **Be very specific** about what's wrong and what you expected
2. **Include error messages** in full, including stack traces
3. **Provide reproducible steps** so the issue is clear
4. **Show relevant code** including surrounding context
5. **Mention recent changes** that might have introduced the bug
6. **List what you've tried** to avoid duplicate suggestions
7. **Include environment details** as version differences matter
8. **Use code blocks** with proper syntax highlighting
