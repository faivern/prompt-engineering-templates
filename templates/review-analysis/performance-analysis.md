# Performance Analysis Template

## Purpose
Analyze code for performance issues, bottlenecks, and optimization opportunities.

## Template

```
I need you to perform a performance analysis of the following code:

**Programming Language**: [language]
**Context**: [what this code does and expected scale]
**Current Performance Issue**: [description of the problem]

**Code**:
```[language]
[paste code here]
```

**Performance Criteria**:
- Expected load: [number of requests/operations per second]
- Dataset size: [data volume]
- Response time requirement: [target time]
- Resource constraints: [memory/CPU limits]

**Analysis Focus**:
- Time complexity (Big O)
- Space complexity
- Database query optimization
- Algorithmic efficiency
- Caching opportunities
- Concurrency/parallelization
- Memory leaks
- [specific performance concerns]

Please provide:
1. Current performance bottlenecks
2. Time and space complexity analysis
3. Profiling recommendations
4. Specific optimization suggestions with code examples
5. Alternative algorithms or approaches
6. Caching strategies
7. Database optimization (if applicable)
8. Expected performance improvement
```

## Example

```
I need you to perform a performance analysis of the following code:

**Programming Language**: Python
**Context**: Function that processes customer orders to find patterns, runs nightly on all orders
**Current Performance Issue**: Taking 2+ hours to process 100,000 orders

**Code**:
```python
def analyze_orders(orders):
    results = []
    
    for order in orders:
        customer_orders = []
        for other_order in orders:
            if other_order['customer_id'] == order['customer_id']:
                customer_orders.append(other_order)
        
        total_spent = 0
        for customer_order in customer_orders:
            for item in customer_order['items']:
                total_spent += item['price'] * item['quantity']
        
        if total_spent > 1000:
            results.append({
                'customer_id': order['customer_id'],
                'total_spent': total_spent,
                'order_count': len(customer_orders)
            })
    
    return results
```

**Performance Criteria**:
- Expected load: 100,000-500,000 orders per run
- Dataset size: Growing 20% annually
- Response time requirement: Should complete within 30 minutes
- Resource constraints: 4GB RAM, 2 CPU cores

**Analysis Focus**:
- Time complexity - nested loops concern
- Algorithmic efficiency
- Data structure optimization
- Caching/memoization opportunities
- Parallel processing potential
- Memory usage
- Database query alternative (if orders come from DB)

Please provide:
1. Current performance bottlenecks (identify the nested loops issue)
2. Time complexity analysis (O(n²) or worse?)
3. Profiling recommendations (tools to use)
4. Specific optimization with code examples (use dictionaries, groupby, etc.)
5. Alternative approaches (DataFrame operations, SQL aggregation)
6. Caching strategies (memoize customer lookups)
7. Parallel processing options (multiprocessing, concurrent.futures)
8. Expected performance improvement (target: 10x faster)
```

## Tips

1. **Describe the performance problem** with specific metrics
2. **Include scale information** (data size, request volume)
3. **Specify constraints** (time, memory, CPU limits)
4. **Provide the full algorithm** including data structures used
5. **Mention expected improvements** to set goals
6. **Request Big O analysis** for complexity understanding
7. **Ask for profiling tools** appropriate for the language
8. **Include database schema** if queries are involved
