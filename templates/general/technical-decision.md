# Technical Decision Template

## Purpose
Get help making technical decisions by analyzing trade-offs, pros/cons, and recommendations.

## Template

```
I need help making a technical decision about:

**Decision**: [what you need to decide]
**Context**: [project description and current situation]

**Options Being Considered**:
1. [Option 1]
2. [Option 2]
3. [Option 3]

**Decision Criteria** (in priority order):
1. [criterion 1: e.g., performance]
2. [criterion 2: e.g., developer experience]
3. [criterion 3: e.g., cost]
4. [criterion 4: e.g., scalability]

**Project Constraints**:
- Team size: [number]
- Team expertise: [skill levels]
- Timeline: [project timeline]
- Budget: [budget constraints]
- Scale: [expected users/load]
- [other constraints]

**Current Stack**: [existing technologies]

**Requirements**:
- [requirement 1]
- [requirement 2]
- [requirement 3]

**Concerns**:
- [concern 1]
- [concern 2]

Please provide:
1. Analysis of each option
2. Pros and cons comparison
3. Trade-offs for each option
4. Recommendation with justification
5. Risk assessment
6. Migration/implementation complexity
7. Long-term considerations
8. Alternative options if applicable
```

## Example

```
I need help making a technical decision about:

**Decision**: Choosing a database for a new social media application
**Context**: Building a social media platform with user profiles, posts, comments, likes, and a feed. Need to support real-time updates and complex queries. Currently in early stages with a small team.

**Options Being Considered**:
1. PostgreSQL (relational)
2. MongoDB (document)
3. PostgreSQL + Redis (hybrid)

**Decision Criteria** (in priority order):
1. Query flexibility (complex queries for feeds, relationships)
2. Scalability (plan to grow to millions of users)
3. Developer experience (team familiar with SQL)
4. Performance (feed generation needs to be fast)
5. Cost (startup budget)
6. Data consistency (important for likes, follows)

**Project Constraints**:
- Team size: 3 developers
- Team expertise: Strong with SQL, limited NoSQL experience
- Timeline: 6 months to MVP
- Budget: Startup budget (~$500/month for infrastructure)
- Scale: Expecting 10k users at launch, hope to reach 1M in year 2
- Must support real-time features (notifications, live feed updates)

**Current Stack**: 
- Backend: Node.js/Express
- Frontend: React
- Hosting: AWS (flexible on specific services)

**Requirements**:
- Store user profiles, posts, comments, likes
- Complex queries for feed generation (friends' posts, sorted by engagement)
- Support follower/following relationships
- Real-time notifications
- Search functionality
- Analytics on user behavior
- Strong data consistency for critical operations (follows, likes)

**Concerns**:
- Feed generation performance at scale
- Cost of scaling
- Complexity of managing multiple databases
- Learning curve for new technologies
- Data modeling for social graph

Please provide:
1. Analysis of each option:
   - PostgreSQL: capabilities, limitations for this use case
   - MongoDB: how well it fits social media data
   - Hybrid: complexity vs benefits
2. Detailed pros/cons comparison table
3. Trade-offs:
   - Consistency vs performance
   - Simplicity vs optimization
   - Learning curve vs long-term benefits
4. Recommendation based on criteria (rank them)
5. Risk assessment:
   - Performance risks
   - Scaling risks
   - Team capability risks
6. Implementation complexity and timeline impact
7. Long-term considerations (year 2-3)
8. Alternative: Consider PostgreSQL with separate graph database?
```

## Tips

1. **Clearly state the decision** you need to make
2. **Provide full context** about the project
3. **List all options** you're considering
4. **Prioritize criteria** so trade-offs can be evaluated
5. **Include constraints** (team, time, budget)
6. **Mention current stack** for compatibility considerations
7. **Specify requirements** that must be met
8. **Share concerns** you have about each option
9. **Request structured comparison** (table format)
10. **Ask for long-term implications** not just immediate
11. **Request alternatives** you might not have considered
