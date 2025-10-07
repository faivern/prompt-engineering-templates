# Code Review Template

## Purpose
Get comprehensive code reviews focusing on quality, best practices, and potential improvements.

## Template

```
I need you to perform a thorough code review of the following code:

**Programming Language**: [language]
**Context**: [what this code is supposed to do]
**Code**:
```[language]
[paste code here]
```

**Review Focus Areas**:
- Code quality and readability
- Best practices and design patterns
- Performance considerations
- Security vulnerabilities
- Error handling
- Testing coverage
- Documentation
- Maintainability
- [any specific concerns]

**Coding Standards**: [style guide or standards to check against]

Please provide:
1. Overall assessment (rate 1-10)
2. Strengths of the code
3. Issues found (categorized by severity: Critical, Major, Minor)
4. Specific suggestions for improvement with code examples
5. Security concerns if any
6. Performance bottlenecks if any
7. Questions or clarifications needed
```

## Example

```
I need you to perform a thorough code review of the following code:

**Programming Language**: JavaScript (Node.js)
**Context**: Express.js middleware for user authentication and authorization
**Code**:
```javascript
const authenticate = (req, res, next) => {
  const token = req.headers.authorization;
  
  if (!token) {
    return res.status(401).json({ error: 'No token' });
  }
  
  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    req.user = decoded;
    next();
  } catch (err) {
    res.status(401).json({ error: 'Invalid token' });
  }
};

const authorize = (roles) => {
  return (req, res, next) => {
    if (!roles.includes(req.user.role)) {
      return res.status(403).json({ error: 'Forbidden' });
    }
    next();
  };
};

module.exports = { authenticate, authorize };
```

**Review Focus Areas**:
- Code quality and readability
- Best practices for JWT authentication
- Security vulnerabilities
- Error handling completeness
- Token format handling
- Performance considerations
- Missing validation
- Logging for security events

**Coding Standards**: Airbnb JavaScript Style Guide

Please provide:
1. Overall assessment (rate 1-10)
2. Strengths of the code
3. Issues found (categorized by severity: Critical, Major, Minor)
4. Specific suggestions for improvement with code examples
5. Security concerns (token storage, timing attacks, etc.)
6. Missing edge cases
7. Questions or clarifications needed
```

## Tips

1. **Provide context** about what the code does
2. **Specify focus areas** if you have particular concerns
3. **Mention coding standards** to check against
4. **Include surrounding code** if context is needed
5. **Ask for severity levels** to prioritize issues
6. **Request specific examples** for suggested improvements
7. **Mention security concerns** explicitly if that's important
