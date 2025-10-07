# Security Analysis Template

## Purpose
Perform security-focused analysis to identify vulnerabilities and security best practice violations.

## Template

```
I need you to perform a security analysis of the following code:

**Programming Language**: [language]
**Application Type**: [web app/API/CLI/etc.]
**Context**: [what this code does and where it's used]

**Code**:
```[language]
[paste code here]
```

**Security Focus Areas**:
- Input validation and sanitization
- Authentication and authorization
- SQL injection vulnerabilities
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Injection attacks
- Sensitive data exposure
- Cryptography issues
- Access control
- [any specific security concerns]

**Environment**:
- Framework: [framework]
- Database: [database type]
- External APIs: [list if applicable]

Please provide:
1. Security risk assessment (High/Medium/Low)
2. Identified vulnerabilities with OWASP category
3. Potential attack vectors
4. Specific code fixes with examples
5. Security best practices to implement
6. Recommended security libraries/tools
7. Testing recommendations for security
```

## Example

```
I need you to perform a security analysis of the following code:

**Programming Language**: Python (Flask)
**Application Type**: Web API
**Context**: User login endpoint that authenticates users and returns session tokens

**Code**:
```python
from flask import Flask, request, jsonify
import sqlite3

app = Flask(__name__)

@app.route('/login', methods=['POST'])
def login():
    username = request.json.get('username')
    password = request.json.get('password')
    
    conn = sqlite3.connect('users.db')
    cursor = conn.cursor()
    
    query = f"SELECT * FROM users WHERE username='{username}' AND password='{password}'"
    cursor.execute(query)
    user = cursor.fetchone()
    
    conn.close()
    
    if user:
        token = username + '_' + str(hash(password))
        return jsonify({'token': token})
    else:
        return jsonify({'error': 'Invalid credentials'}), 401
```

**Security Focus Areas**:
- SQL injection vulnerabilities
- Password handling (hashing, storage)
- Token generation security
- Input validation
- Error message information leakage
- HTTPS enforcement
- Rate limiting
- Session management

**Environment**:
- Framework: Flask 2.x
- Database: SQLite
- No external APIs

Please provide:
1. Security risk assessment (High/Medium/Low)
2. Identified vulnerabilities with OWASP Top 10 categories
3. Potential attack vectors and exploitation scenarios
4. Specific code fixes with secure examples
5. Security best practices (password hashing, parameterized queries, etc.)
6. Recommended security libraries (bcrypt, Flask-Limiter, etc.)
7. Testing recommendations (penetration testing tools)
```

## Tips

1. **Provide full context** about the application and its environment
2. **Specify the framework** for framework-specific vulnerabilities
3. **List specific security concerns** you're worried about
4. **Include data flow** if the code handles sensitive data
5. **Mention compliance requirements** (GDPR, PCI-DSS, HIPAA)
6. **Request OWASP categorization** for standard vulnerability classification
7. **Ask for attack scenarios** to understand real-world risks
8. **Request tool recommendations** for ongoing security testing
