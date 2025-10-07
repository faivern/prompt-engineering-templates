# 🧠 AI Project Companion System  
*A lightweight documentation and prompting framework for AI-assisted software development.*

This system helps you move seamlessly from an idea → to a specification → to a roadmap → to a working implementation — all in Markdown.

---

## 📘 Overview

This repository provides a reusable system for developing, planning, and executing projects alongside an AI assistant such as ChatGPT, Copilot, or OpenAI’s Build environment.  

Each file serves a specific role in the project lifecycle:

| File | Purpose |
|------|----------|
| **`idea_honing.md`** | A structured dialogue prompt where the AI asks one question at a time to refine and deepen your idea until it becomes a solid project concept. |
| **`spec.md`** | Defines functional and non-functional requirements, architecture, data handling, error strategies, and testing plans — your project’s technical blueprint. |
| **`prompt_plan.md`** | Outlines step-by-step actions (setup, schema, API, testing, deployment) that turn your specification into a concrete build roadmap. |
| **`todo.md`** | A generated, checkable task list derived from both `spec.md` and `prompt_plan.md`, allowing easy progress tracking. |

---

## 🪄 How It Works — The AI Workflow

1. ✏️ **Start an Idea** — Open `idea_honing.md` and replace `{{your_idea}}` with your concept.  
   The AI will ask one question at a time to explore and refine your idea.  
   When ready, say:  
   > **"generate spec"**

2. 🧱 **Generate a Specification** — The AI creates `spec.md` describing what the system does, how it’s built, and how it’s tested.

3. 🗂️ **Plan the Project** — Use `prompt_plan.md` to break your implementation into logical steps (setup, schema, API, tests, etc.).

4. ✅ **Generate a Checklist** — Ask:  
   > “Can you make a `todo.md` that I can use as a checklist? Be thorough.”  
   The AI will produce a complete, checkable `todo.md` for development tracking.

5. 💻 **Implement** — Use these Markdown files as live context for Copilot or GPT to generate or improve your code.

6. 🔁 **Iterate** — Update `spec.md` or `todo.md` as your project evolves; regenerate files as needed.

---

## 📁 Recommended Project Structure

You can include the files directly in your project or within a `/docs/` folder for organization.

my-project/
│
├── src/ # Source code
├── docs/ # Optional: store AI companion files here
│ ├── idea_honing.md
│ ├── spec.md
│ ├── prompt_plan.md
│ └── todo.md
├── README.md
└── .gitignore

yaml
Copy code

If simplicity is preferred, you can also keep them in the project root.

---

## 🤖 How to Use Inside a Live Project

### 🧭 1. With **GitHub Copilot / Copilot Workspace**
You can reference these files as **context documents** for Copilot’s project understanding.

- Keep them under `/docs/` or root level.
- Use clear names like `spec.md`, `todo.md`, `prompt_plan.md`.
- In prompts or commit messages, reference them explicitly:
  > “Refer to `/docs/spec.md` and `/docs/prompt_plan.md` for context.  
  > Help me implement Step 3: API Layer as described there.”

💡 **Tip:** Copilot Workspace automatically reads Markdown files in your repository. Keeping these names consistent makes Copilot more effective.

---

### 🧱 2. With **OpenAI GPTs / Build Mode**
When using a GPT with **File Context**:
- Upload your `idea_honing.md` and `spec.md` before starting a session.
- Tell the model:
  > “Use these files as project context for all design and code generation tasks.”
- Then prompt:
  > “Generate code for Step 2 in `prompt_plan.md` following the architecture in `spec.md`.”

This allows the GPT to reason across your idea, spec, and plan simultaneously.

---

### 🧠 3. With **Manual AI Sessions**
When chatting manually (e.g., ChatGPT web or terminal tools):
- Paste relevant sections from `spec.md` or `prompt_plan.md` into the chat.
- Then ask:
  > “Based on this spec, generate the backend logic for Step 4.”

This approach works even without integrated AI features — you just provide context explicitly.

---

## ⚙️ Integration Tips for Copilot and GPT

- Keep your `.md` files in predictable locations (e.g., `/docs/spec.md`).
- Use clear section headers like `## Step 3: API Layer` or `## Functional Requirements`.
- Update Markdown content before each coding session — AI tools read the latest committed version.
- Avoid vague text; AI models perform best with specific, well-structured content.

---

## 🧩 Why This System Works

Modern AI assistants perform best when given structured, readable, and context-rich input.  
By using this companion system:

- 🧠 You provide AI with consistent reference documents.  
- 🧰 You maintain clear, human-readable project documentation.  
- 🔁 You can regenerate or extend sections automatically as your project grows.  

This bridges the gap between **AI reasoning** and **real software engineering workflow**.

---

## 🧭 Summary Table

| Purpose | File | Tool Integration |
|----------|------|------------------|
| Idea refinement | `idea_honing.md` | GPT / ChatGPT |
| Specification | `spec.md` | GPT / Copilot Workspace |
| Development roadmap | `prompt_plan.md` | GPT / Copilot |
| Task checklist | `todo.md` | Copilot / GitHub Issues |

---

## 💡 License
MIT — free to use, adapt, and evolve.  

> “The goal is not just to use AI to code — but to **think and build with structure.**”
