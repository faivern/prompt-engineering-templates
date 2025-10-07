# Code Comments Template

## Purpose
Generate clear, helpful comments and docstrings for code that explain purpose, parameters, and behavior.

## Template

```
I need you to add comprehensive comments and documentation to the following code:

**Programming Language**: [language]
**Code**:
```[language]
[paste your code here]
```

**Documentation Requirements**:
- Add file/module header comment with purpose and author
- Add docstrings/comments for all [functions/classes/methods]
- Explain complex logic or algorithms
- Document parameters with types and descriptions
- Document return values
- Include usage examples in docstrings
- Note any side effects or important behaviors
- Follow [style_guide] conventions

**Documentation Style**: [JSDoc/Sphinx/Javadoc/etc.]

**Focus Areas**:
- [specific functions or sections that need explanation]
- [complex algorithms that need clarification]

Please maintain the original code logic while adding clear, professional documentation.
```

## Example

```
I need you to add comprehensive comments and documentation to the following code:

**Programming Language**: Python
**Code**:
```python
def process_data(data, threshold=0.5, normalize=True):
    if normalize:
        max_val = max(data)
        min_val = min(data)
        data = [(x - min_val) / (max_val - min_val) for x in data]
    
    result = []
    for val in data:
        if val > threshold:
            result.append(val)
    
    return result

class DataProcessor:
    def __init__(self, config):
        self.config = config
        self.cache = {}
    
    def process(self, input_data):
        key = str(input_data)
        if key in self.cache:
            return self.cache[key]
        
        processed = self._transform(input_data)
        self.cache[key] = processed
        return processed
    
    def _transform(self, data):
        return [x * self.config.get('multiplier', 1) for x in data]
```

**Documentation Requirements**:
- Add module header comment with purpose
- Add docstrings for all functions and classes following PEP 257
- Explain the normalization algorithm
- Document parameters with types using type hints
- Document return values
- Include usage examples in docstrings
- Note the caching behavior and its implications
- Follow Google Python Style Guide conventions

**Documentation Style**: Google-style docstrings

**Focus Areas**:
- The normalization logic in process_data
- The caching mechanism in DataProcessor
- The purpose of the _transform method

Please maintain the original code logic while adding clear, professional documentation.
```

## Tips

1. **Specify the documentation style** (Google, NumPy, JSDoc, etc.)
2. **Indicate which parts need explanation** if certain sections are complex
3. **Request type hints** if the language supports them
4. **Ask for usage examples** in docstrings when helpful
5. **Mention style guides** to follow established conventions
6. **Include the full code** so context is clear
7. **Note any domain-specific terms** that should be explained
