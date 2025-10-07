# Prompt Plan

Each step of the development process is written as its own section.  
This file acts as a structured roadmap that the AI (or you) can follow to plan, build, and track progress.

---

## Step 1: Project Setup
- Initialize project (`npm init`, `dotnet new`, or equivalent)
- Install dependencies
- Create folder structure
- Configure environment variables
- Initialize version control (Git)

---

## Step 2: Database Schema
- Define schema (e.g., SQLite, PostgreSQL, MongoDB)
- Create migration script
- Add seed data
- Verify schema alignment with requirements in `spec.md`

---

## Step 3: API Layer
- Define API routes (CRUD or custom endpoints)
- Implement controllers or handlers
- Connect database logic
- Add input validation and error handling
- Write basic documentation for endpoints

---

## Step 4: Core Logic
- Implement core business rules
- Handle edge cases and validation
- Integrate external APIs if applicable
- Follow separation of concerns principles

---

## Step 5: Frontend (Optional)
- Set up UI framework (React, Vue, etc.)
- Connect API to frontend
- Create essential components and views
- Test data flow between backend and frontend

---

## Step 6: Testing
- Write unit tests for key modules
- Add integration tests for routes and data handling
- Run automated test suite
- Document testing outcomes in `todo.md`

---

## Step 7: Deployment
- Prepare production build
- Configure hosting and database
- Add environment variables and secrets
- Run smoke tests post-deployment

---

**Tip:**  
Once this plan is complete, ask the AI:  
> “Can you create a `todo.md` checklist based on my `prompt_plan.md` and `spec.md`?”
