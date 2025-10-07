# Class Creation Template

## Purpose
Generate well-designed classes with proper encapsulation, methods, and documentation.

## Template

```
I need you to create a class with the following specifications:

**Class Name**: [ClassName]
**Programming Language**: [language]
**Purpose**: [clear description of what the class represents]

**Properties/Attributes**:
- [property1]: [type] - [description]
- [property2]: [type] - [description]

**Methods**:
1. **[method1_name]**
   - Purpose: [description]
   - Parameters: [parameters]
   - Returns: [return_type]

2. **[method2_name]**
   - Purpose: [description]
   - Parameters: [parameters]
   - Returns: [return_type]

**Requirements**:
- [requirement 1]
- Include constructor/initializer
- Add property validation where appropriate
- Include docstrings for class and all methods
- Follow [style_guide] conventions
- Implement [design_pattern] if applicable

**Additional Features**:
- [feature 1]
- [feature 2]
```

## Example

```
I need you to create a class with the following specifications:

**Class Name**: ShoppingCart
**Programming Language**: Python
**Purpose**: Represent a shopping cart that can hold items and calculate totals

**Properties/Attributes**:
- items: list - List of items in the cart
- customer_id: str - ID of the customer who owns the cart
- discount_code: str (optional) - Applied discount code

**Methods**:
1. **add_item**
   - Purpose: Add an item to the cart
   - Parameters: item_name (str), price (float), quantity (int)
   - Returns: None

2. **remove_item**
   - Purpose: Remove an item from the cart
   - Parameters: item_name (str)
   - Returns: bool (True if removed, False if not found)

3. **calculate_total**
   - Purpose: Calculate the total price of all items
   - Parameters: None
   - Returns: float

4. **apply_discount**
   - Purpose: Apply a discount code
   - Parameters: discount_code (str)
   - Returns: bool (True if valid, False otherwise)

**Requirements**:
- Include constructor that accepts customer_id
- Validate that prices are positive
- Validate that quantities are positive integers
- Include comprehensive docstrings
- Follow PEP 8 conventions
- Prevent duplicate items (update quantity instead)

**Additional Features**:
- Implement __str__ method for readable output
- Add method to clear the cart
- Track total number of items
```

## Tips

1. **Define clear responsibilities** for the class
2. **Specify all properties** with types and purposes
3. **Detail each method** including parameters and return values
4. **Request validation** for data integrity
5. **Mention design patterns** if a specific pattern is needed
6. **Include special methods** like constructors, __str__, __repr__, etc.
