# Unit Test Generation Template

## Purpose
Generate comprehensive unit tests for functions, classes, and methods.

## Template

```
I need you to create unit tests for the following code:

**Programming Language**: [language]
**Testing Framework**: [Jest/Mocha/PyTest/JUnit/etc.]
**Code to Test**:
```[language]
[paste the code to be tested]
```

**Test Coverage Requirements**:
- Test all public methods/functions
- Cover edge cases
- Test error conditions
- Test boundary values
- [specific scenarios to test]

**Test Organization**:
- Group related tests in describe/context blocks
- Use clear, descriptive test names
- Follow [AAA pattern / Given-When-Then]

**Mocking Requirements**:
- Mock external dependencies: [list dependencies]
- Mock database calls: [yes/no]
- Mock API calls: [yes/no]

**Coverage Goal**: [percentage, e.g., 80%+]

Please provide:
1. Complete test suite with all test cases
2. Setup and teardown if needed
3. Mock implementations for dependencies
4. Test data fixtures
5. Comments explaining complex test scenarios
6. Coverage report interpretation (which cases are covered)
```

## Example

```
I need you to create unit tests for the following code:

**Programming Language**: TypeScript
**Testing Framework**: Jest with React Testing Library
**Code to Test**:
```typescript
export class ShoppingCart {
  private items: Map<string, CartItem> = new Map();
  private discountCode: string | null = null;

  addItem(productId: string, name: string, price: number, quantity: number): void {
    if (price < 0) {
      throw new Error('Price cannot be negative');
    }
    if (quantity <= 0) {
      throw new Error('Quantity must be positive');
    }

    const existing = this.items.get(productId);
    if (existing) {
      existing.quantity += quantity;
    } else {
      this.items.set(productId, { productId, name, price, quantity });
    }
  }

  removeItem(productId: string): boolean {
    return this.items.delete(productId);
  }

  getTotal(): number {
    let total = 0;
    for (const item of this.items.values()) {
      total += item.price * item.quantity;
    }

    if (this.discountCode === 'SAVE10') {
      total *= 0.9;
    } else if (this.discountCode === 'SAVE20') {
      total *= 0.8;
    }

    return Math.round(total * 100) / 100;
  }

  applyDiscount(code: string): boolean {
    const validCodes = ['SAVE10', 'SAVE20'];
    if (validCodes.includes(code)) {
      this.discountCode = code;
      return true;
    }
    return false;
  }

  clear(): void {
    this.items.clear();
    this.discountCode = null;
  }
}

interface CartItem {
  productId: string;
  name: string;
  price: number;
  quantity: number;
}
```

**Test Coverage Requirements**:
- Test all public methods (addItem, removeItem, getTotal, applyDiscount, clear)
- Cover edge cases (negative prices, zero quantity, duplicate items)
- Test error conditions (invalid inputs)
- Test boundary values (empty cart, single item, many items)
- Test discount logic thoroughly
- Test quantity accumulation when adding existing items

**Test Organization**:
- Group tests by method in describe blocks
- Use clear, descriptive test names
- Follow AAA (Arrange-Act-Assert) pattern

**Mocking Requirements**:
- No external dependencies to mock (pure class)

**Coverage Goal**: 100% (all methods, all branches)

Please provide:
1. Complete test suite covering all methods and scenarios
2. Setup for creating fresh cart instance before each test
3. Test cases for all edge cases and error conditions
4. Clear test names that describe what's being tested
5. Comments for complex assertions
6. Verification that all branches are covered
```

## Tips

1. **Specify the testing framework** for correct syntax
2. **List all scenarios to cover** including edge cases
3. **Identify dependencies** that need mocking
4. **Request specific patterns** (AAA, Given-When-Then)
5. **Mention coverage goals** to ensure thoroughness
6. **Include the full code** so tests match implementation
7. **Ask for test data** fixtures if needed
8. **Request organized structure** with describe blocks
