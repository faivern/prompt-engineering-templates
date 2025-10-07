# 🧠 AI Project Companion System

A modular prompt and documentation setup for developing software ideas with AI assistance.  
Each Markdown file has a clear role — from ideation to implementation and follow-up.

---

## 📂 Overview

| File | Purpose |
|------|----------|
| **`idea_honing.md`** | A structured conversation prompt to refine any idea step by step. The AI asks one question at a time and builds a complete specification. |
| **`spec.md`** | Defines the system’s requirements, architecture, data handling, and testing plan. The foundation for any technical build. |
| **`prompt_plan.md`** | Outlines each step of the development process — from setup to deployment — serving as a roadmap for building the project. |
| **`todo.md`** | A detailed, checkable task list automatically generated from the spec and prompt plan. Perfect for tracking progress. |

---

## 🪄 How to Use

### 1. Start with the Idea
Open **`idea_honing.md`** and replace `{{your_idea}}` with your project concept.  
Example:
> “I want to create a TODO web app for managing my hobby projects.”

The AI will then ask **one focused question at a time** to refine your idea into a concrete plan.  
When ready, say:
> **“generate spec”**

---

### 2. Generate the Specification
Once your idea feels solid, the AI will produce a full **`spec.md`** file containing:
- Functional & non-functional requirements  
- Architecture choices  
- Data handling  
- Error handling strategies  
- Testing plan

This becomes your technical blueprint.

---

### 3. Plan the Build
Use **`prompt_plan.md`** to structure your development process into clear steps.  
Each step (e.g. *Project Setup*, *Database Schema*) gets its own section with key actions.

You can later expand or customize these steps per project.

---

### 4. Generate a Checklist
Finally, ask the AI:
> “Can you make a `todo.md` that I can use as a checklist? Be thorough.”

It will create a **checkable** `todo.md` file based on your `spec.md` and `prompt_plan.md`, ready for use in GitHub or any markdown editor.

---

## 🧩 Recommended Workflow

1. ✏️ **Ideate** — start with `idea_honing.md`  
2. 🧱 **Specify** — generate `spec.md`  
3. 🗂️ **Plan** — organize tasks in `prompt_plan.md`  
4. ✅ **Execute** — follow the generated `todo.md`

---

## 💡 Tip
This system is designed to be *AI-compatible* — meaning you can use the same files across multiple projects and let AI continuously expand, adjust, and regenerate them as your ideas evolve.

> *Think of it as a reusable, evolving engineering notebook for AI-assisted development.*

---

### 🧭 License
MIT — feel free to use, modify, and build upon this template for your own projects.
