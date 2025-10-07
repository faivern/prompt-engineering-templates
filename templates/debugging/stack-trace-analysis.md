# Stack Trace Analysis Template

## Purpose
Analyze and interpret complex stack traces to identify the root cause of errors.

## Template

```
I need help analyzing this stack trace:

**Programming Language**: [language]
**Framework**: [framework]
**Error Type**: [Exception/Error class name]

**Full Stack Trace**:
```
[paste the complete stack trace]
```

**Context**:
[What was the application doing when this occurred?]

**Application Flow**:
[Describe the sequence of operations leading to the error]

**Relevant Code Sections**:
```[language]
[paste code for the functions/methods mentioned in the stack trace]
```

**Frequency**:
[How often does this occur? One-time / Intermittent / Every time]

**Recent Changes**:
[Any recent code or configuration changes]

**Environment**:
- [Environment type: dev/staging/prod]
- [Language/Framework versions]
- [Deployment platform]

Please help me:
1. Interpret what this stack trace is telling me
2. Identify the exact line/function causing the issue
3. Explain the sequence of calls that led to the error
4. Determine the root cause
5. Suggest specific fixes
6. Recommend how to add better error handling
```

## Example

```
I need help analyzing this stack trace:

**Programming Language**: Java
**Framework**: Spring Boot
**Error Type**: NullPointerException

**Full Stack Trace**:
```
java.lang.NullPointerException: Cannot invoke "com.example.User.getName()" because "user" is null
    at com.example.service.OrderService.processOrder(OrderService.java:45)
    at com.example.service.OrderService$$FastClassBySpringCGLIB$$a1b2c3d4.invoke(<generated>)
    at org.springframework.cglib.proxy.MethodProxy.invoke(MethodProxy.java:218)
    at org.springframework.aop.framework.CglibAopProxy$CglibMethodInvocation.invokeJoinpoint(CglibAopProxy.java:793)
    at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:163)
    at org.springframework.transaction.interceptor.TransactionInterceptor$1.proceedWithInvocation(TransactionInterceptor.java:123)
    at org.springframework.transaction.interceptor.TransactionAspectSupport.invokeWithinTransaction(TransactionAspectSupport.java:388)
    at org.springframework.transaction.interceptor.TransactionInterceptor.invoke(TransactionInterceptor.java:119)
    at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:186)
    at org.springframework.aop.framework.CglibAopProxy$CglibMethodInvocation.proceed(CglibAopProxy.java:763)
    at org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:708)
    at com.example.service.OrderService$$EnhancerBySpringCGLIB$$5e6f7a8b.processOrder(<generated>)
    at com.example.controller.OrderController.createOrder(OrderController.java:32)
    at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
    at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
    at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
```

**Context**:
The error occurs when a customer tries to place an order through the REST API. The application is supposed to create an order and associate it with the logged-in user.

**Application Flow**:
1. Client sends POST request to /api/orders
2. OrderController.createOrder() receives the request
3. OrderService.processOrder() is called
4. Service tries to access user information to link to the order

**Relevant Code Sections**:
```java
// OrderController.java - line 32
@PostMapping("/orders")
public ResponseEntity<Order> createOrder(@RequestBody OrderRequest request) {
    Order order = orderService.processOrder(request);
    return ResponseEntity.ok(order);
}

// OrderService.java - line 45
@Transactional
public Order processOrder(OrderRequest request) {
    User user = userRepository.findById(request.getUserId()).orElse(null);
    
    Order order = new Order();
    order.setUserName(user.getName());  // LINE 45 - NPE occurs here
    order.setItems(request.getItems());
    order.setTotal(calculateTotal(request.getItems()));
    
    return orderRepository.save(order);
}
```

**Frequency**:
Intermittent - happens for some orders but not all

**Recent Changes**:
Refactored user lookup to use Optional instead of throwing exceptions

**Environment**:
- Production environment
- Java 17
- Spring Boot 3.0.5
- PostgreSQL database

Please help me:
1. Interpret what the Spring CGLIB proxies mean in the stack trace
2. Confirm the exact cause (user lookup returning null)
3. Explain why orElse(null) is problematic
4. Suggest proper error handling with Optional
5. Recommend validation at the controller level
6. Suggest how to add better logging for debugging
```

## Tips

1. **Include the entire stack trace** without truncation
2. **Provide the actual code** at the lines mentioned in the trace
3. **Explain the application flow** that led to the error
4. **Mention if errors are intermittent** vs consistent
5. **Include framework details** as proxy/AOP layers add complexity
6. **Show recent changes** that might have introduced the issue
7. **Specify the environment** as behavior can differ between environments
8. **Ask about framework-specific elements** if the trace includes them
