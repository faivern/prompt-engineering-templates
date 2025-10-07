# Code Refactoring Template

## Purpose
Improve code quality, readability, and maintainability through systematic refactoring.

## Template

```
I need help refactoring the following code:

**Programming Language**: [language]
**Current Issues**:
- [issue 1: e.g., code duplication]
- [issue 2: e.g., poor naming]
- [issue 3: e.g., too complex]

**Code to Refactor**:
```[language]
[paste code here]
```

**Refactoring Goals**:
- [goal 1: e.g., improve readability]
- [goal 2: e.g., reduce complexity]
- [goal 3: e.g., better separation of concerns]

**Constraints**:
- Maintain existing functionality (behavior should not change)
- [any other constraints, e.g., performance requirements]

**Style Guidelines**: [if any specific style guide to follow]

Please provide:
1. Analysis of current code issues
2. Refactored code with improvements
3. Explanation of changes made
4. Before/after comparison for key improvements
5. Any design patterns applied
6. Suggestions for further improvements
```

## Example

```
I need help refactoring the following code:

**Programming Language**: Python
**Current Issues**:
- Repetitive code with similar patterns
- Long function doing too many things
- Poor variable naming
- No error handling
- Hard to test

**Code to Refactor**:
```python
def process(data, type):
    if type == 'a':
        r = []
        for i in data:
            if i > 10:
                x = i * 2
                y = x + 5
                r.append(y)
        return r
    elif type == 'b':
        r = []
        for i in data:
            if i > 10:
                x = i * 3
                y = x + 10
                r.append(y)
        return r
    elif type == 'c':
        r = []
        for i in data:
            if i > 10:
                x = i * 4
                y = x + 15
                r.append(y)
        return r
    else:
        return []
```

**Refactoring Goals**:
- Eliminate code duplication
- Improve naming for clarity
- Break down into smaller, focused functions
- Add type hints and docstrings
- Make it more testable and maintainable
- Follow Single Responsibility Principle

**Constraints**:
- Maintain existing functionality exactly
- Should handle the same input/output scenarios
- Performance should not degrade

**Style Guidelines**: PEP 8 and Google Python Style Guide

Please provide:
1. Analysis of current code issues (duplication, naming, structure)
2. Refactored code with clear improvements
3. Detailed explanation of each change
4. Before/after comparison highlighting improvements
5. Design patterns used (Strategy pattern, etc.)
6. Unit test examples for the refactored code
```

## Tips

1. **List specific issues** you see or want addressed
2. **Define clear goals** for the refactoring
3. **Include full context** so behavior is understood
4. **Mention constraints** like performance or API compatibility
5. **Request explanations** to learn from the refactoring
6. **Ask for tests** to ensure behavior is preserved
7. **Specify style guidelines** for consistent code style
8. **Request patterns** if you want to learn design patterns
