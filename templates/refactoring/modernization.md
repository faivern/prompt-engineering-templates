# Code Modernization Template

## Purpose
Update legacy code to use modern language features, patterns, and best practices.

## Template

```
I need help modernizing the following code:

**Programming Language**: [language]
**Current Version**: [version]
**Target Version**: [version]

**Legacy Code**:
```[language]
[paste legacy code here]
```

**Modernization Goals**:
- Update to modern syntax and features
- Use current best practices
- Improve type safety (if applicable)
- Adopt modern patterns
- Update deprecated APIs
- [other specific goals]

**New Features to Adopt**:
- [feature 1: e.g., async/await]
- [feature 2: e.g., arrow functions]
- [feature 3: e.g., destructuring]
- [feature 4: e.g., optional chaining]

**Constraints**:
- Maintain backward compatibility: [yes/no]
- Target environment: [browsers/Node.js version/etc.]
- Dependencies that can be updated: [list]

**Context**:
[What this code does and why you're modernizing it]

Please provide:
1. Analysis of outdated patterns and practices
2. Modernized code using current best practices
3. Explanation of each modernization
4. List of new features/patterns applied
5. Any breaking changes and migration notes
6. Updated dependencies (if applicable)
```

## Example

```
I need help modernizing the following code:

**Programming Language**: JavaScript
**Current Version**: ES5 (circa 2015)
**Target Version**: ES2022 (modern JavaScript)

**Legacy Code**:
```javascript
var UserManager = function(apiUrl) {
  this.apiUrl = apiUrl;
  this.users = [];
};

UserManager.prototype.fetchUsers = function(callback) {
  var self = this;
  var xhr = new XMLHttpRequest();
  
  xhr.onreadystatechange = function() {
    if (xhr.readyState === 4) {
      if (xhr.status === 200) {
        var data = JSON.parse(xhr.responseText);
        self.users = data;
        callback(null, data);
      } else {
        callback(new Error('Failed to fetch users'));
      }
    }
  };
  
  xhr.open('GET', this.apiUrl + '/users');
  xhr.send();
};

UserManager.prototype.findUser = function(id) {
  for (var i = 0; i < this.users.length; i++) {
    if (this.users[i].id === id) {
      return this.users[i];
    }
  }
  return null;
};

UserManager.prototype.getUserNames = function() {
  var names = [];
  for (var i = 0; i < this.users.length; i++) {
    names.push(this.users[i].name);
  }
  return names;
};
```

**Modernization Goals**:
- Convert to ES6+ class syntax
- Use async/await instead of callbacks
- Replace XMLHttpRequest with fetch API
- Use modern array methods
- Add type checking with JSDoc or TypeScript
- Use const/let instead of var
- Apply modern patterns (optional chaining, nullish coalescing)

**New Features to Adopt**:
- ES6 classes
- async/await
- fetch API
- Arrow functions
- Array methods (find, map, filter)
- Template literals
- Destructuring
- Optional chaining (?.)

**Constraints**:
- Maintain backward compatibility: No (fresh rewrite allowed)
- Target environment: Modern browsers (last 2 versions) and Node.js 18+
- Can add new dependencies: Yes

**Context**:
This is a utility class for managing user data in a web application. It's being modernized as part of a larger application upgrade from jQuery-era code to modern React.

Please provide:
1. Analysis of outdated patterns (prototypes, xhr, callbacks, var)
2. Modernized code with ES6+ features and async/await
3. Explanation of each modernization and why it's better
4. List of new language features used
5. Optional: TypeScript version if it would add value
6. Error handling improvements
7. Suggestions for testing the modernized code
```

## Tips

1. **Specify source and target versions** clearly
2. **List features you want to adopt** to guide the modernization
3. **Mention compatibility requirements** (browser support, etc.)
4. **Provide full context** of the code's purpose
5. **State if breaking changes are okay** or if compatibility is needed
6. **Request TypeScript** if you want static typing
7. **Ask for explanations** to understand the improvements
8. **Request migration notes** if it affects other code
