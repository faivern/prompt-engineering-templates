# Function Generation Template

## Purpose
Generate well-structured, documented functions with proper error handling and type hints.

## Template

```
I need you to create a function with the following specifications:

**Function Name**: [function_name]
**Programming Language**: [language]
**Purpose**: [clear description of what the function should do]

**Parameters**:
- [param1_name]: [type] - [description]
- [param2_name]: [type] - [description]

**Return Type**: [return_type]
**Return Value**: [description of what it returns]

**Requirements**:
- [requirement 1]
- [requirement 2]
- Include proper error handling
- Add comprehensive docstrings/comments
- Follow [style_guide] conventions

**Edge Cases to Handle**:
- [edge_case_1]
- [edge_case_2]

**Example Usage**:
```[language]
[show example of how the function should be called]
```
```

## Example

```
I need you to create a function with the following specifications:

**Function Name**: calculate_discount
**Programming Language**: Python
**Purpose**: Calculate the final price after applying a discount percentage

**Parameters**:
- original_price: float - The original price before discount
- discount_percent: float - The discount percentage (0-100)

**Return Type**: float
**Return Value**: The final price after applying the discount

**Requirements**:
- Validate that original_price is positive
- Validate that discount_percent is between 0 and 100
- Include proper error handling for invalid inputs
- Add comprehensive docstrings
- Follow PEP 8 conventions

**Edge Cases to Handle**:
- Zero or negative prices
- Discount percentages outside valid range
- None or invalid input types

**Example Usage**:
```python
final_price = calculate_discount(100.0, 20.0)  # Should return 80.0
```
```

## Tips

1. **Be specific** about the function's purpose and behavior
2. **Define all parameters** clearly with types and descriptions
3. **Specify edge cases** that need handling
4. **Include example usage** to clarify expected behavior
5. **Mention style guides** or coding standards to follow
6. **Request error handling** explicitly if needed
