# Code Optimization Template

## Purpose
Optimize code for better performance, resource usage, or efficiency.

## Template

```
I need help optimizing the following code:

**Programming Language**: [language]
**Current Performance**:
- [metric 1: e.g., execution time]
- [metric 2: e.g., memory usage]
- [metric 3: e.g., database queries]

**Performance Goal**:
[Specific target: e.g., "reduce execution time by 50%" or "handle 10x more data"]

**Code to Optimize**:
```[language]
[paste code here]
```

**Context**:
- Dataset size: [size of data being processed]
- Frequency: [how often this runs]
- Environment: [hardware/infrastructure constraints]

**Current Bottlenecks** (if known):
- [bottleneck 1]
- [bottleneck 2]

**Optimization Focus**:
- [ ] Time complexity
- [ ] Space complexity
- [ ] Database queries
- [ ] Network calls
- [ ] Algorithm efficiency
- [ ] Caching
- [ ] Parallelization
- [other specific areas]

**Constraints**:
- Must maintain exact same output
- [any other functional constraints]
- [budget/resource limits]

Please provide:
1. Analysis of current performance bottlenecks
2. Optimized code with improvements
3. Explanation of optimization techniques used
4. Expected performance improvement (with metrics)
5. Trade-offs made (if any)
6. Benchmarking recommendations
```

## Example

```
I need help optimizing the following code:

**Programming Language**: JavaScript (Node.js)
**Current Performance**:
- Execution time: 5-8 seconds for 1,000 items
- Memory usage: Spikes to 500MB
- Multiple redundant database queries

**Performance Goal**:
Reduce execution time to under 1 second and memory usage below 100MB for 1,000 items. Must scale to 10,000 items.

**Code to Optimize**:
```javascript
async function generateUserReports(userIds) {
  const reports = [];
  
  for (const userId of userIds) {
    const user = await db.users.findOne({ id: userId });
    const orders = await db.orders.find({ userId: userId });
    
    let totalSpent = 0;
    for (const order of orders) {
      const items = await db.orderItems.find({ orderId: order.id });
      for (const item of items) {
        const product = await db.products.findOne({ id: item.productId });
        totalSpent += product.price * item.quantity;
      }
    }
    
    reports.push({
      userId: user.id,
      userName: user.name,
      totalOrders: orders.length,
      totalSpent: totalSpent
    });
  }
  
  return reports;
}
```

**Context**:
- Dataset size: 1,000-10,000 users, each with 5-20 orders
- Frequency: Runs on-demand when admin requests batch reports
- Environment: AWS Lambda with 1GB memory, PostgreSQL database

**Current Bottlenecks**:
- N+1 query problem (multiple DB calls per user)
- Sequential processing (no parallelization)
- No caching of product data
- Loading entire order history into memory

**Optimization Focus**:
- [x] Database queries (biggest issue)
- [x] Parallelization potential
- [x] Caching opportunities
- [x] Algorithm efficiency

**Constraints**:
- Must return same report data
- Cannot modify database schema
- Lambda timeout is 30 seconds max

Please provide:
1. Analysis of N+1 query problem and memory issues
2. Optimized code using batch queries and aggregation
3. Explanation of database query optimization
4. Expected performance improvement (target: 10x faster)
5. Trade-offs (if any, e.g., memory vs speed)
6. Suggestions for monitoring and profiling
```

## Tips

1. **Provide current metrics** with specific numbers
2. **Set clear performance goals** with measurable targets
3. **Include context** about data volume and frequency
4. **Identify known bottlenecks** if you've profiled the code
5. **Specify optimization priorities** (speed vs memory vs cost)
6. **Mention environment constraints** (hardware, timeouts, etc.)
7. **Request metrics** for before/after comparison
8. **Ask about trade-offs** to understand compromises
9. **Include profiling data** if you have it
