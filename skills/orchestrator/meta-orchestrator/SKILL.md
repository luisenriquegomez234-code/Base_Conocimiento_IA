# Skill: Meta-Orchestrator (Orchestration Router)

## 🎯 Purpose
Analyze a project or task and intelligently decide which specialized orchestrator and sub-skills to use as the foundation for the solution.

---

## 📥 When to use
- At the start of ANY new project or complex task.
- When there is ambiguity about how to coordinate multiple agents or tools.
- To ensure optimal selection of patterns (Durable vs. Parallel vs. Distributed).

---

## ⚙️ Orchestration Selection Matrix

| Project context / Task type | Primary Orchestrator | Key Reason |
| :--- | :--- | :--- |
| **Robots-Adres / Persistent Tasks** | `workflow-orchestration-patterns` | Ensures durability and resume-from-last-step on failure. |
| **Multi-Agent Coordination** | `multi-agent-task-orchestrator` | Prevents duplicate work and implements Quality Gates. |
| **Microservices / Distributed APIs**| `saga-orchestration` | Handles distributed transactions and compensation (rollbacks). |
| **Skill Discovery & Registry** | `agent-orchestrator` | Best for automatic matching of capabilities across the ecosystem. |
| **TDD / Test-First Dev** | `tdd-orchestrator` | Focuses on cycle of Red-Green-Refactor for reliability. |

---

## 🧠 Decision Logic (Lógica de Ejecución)

### Step 1: Analyze Context
Determine if the project requires **persistence** (long-running), **concurrency** (parallel agents), or **atomicity** (all-or-nothing transactions).

### Step 2: Orchestrator Selection
Select one of the primary orchestrators from the matrix above.

### Step 3: Skill Mapping
Based on the selected orchestrator, identify required domain skills:
- **Core**: `core/directorios-archivos`.
- **AI**: `ai/ingenieria-de-prompts`, `ai/memoria`, `ai/llm-structured-output`.
- **System**: `system/integracion-resiliente-apis`.
- **Business**: `business/seguridad`.

---

## 📤 Expected Result
A structured recommendation in Spanish that includes:
1. Selected Orchestrator (English pattern).
2. List of required Sub-Skills.
3. Rationale for the selection based on project constraints.

---

## 🚫 Constraints
- No generar soluciones desde cero si hay una skill disponible.
- Maintain technical patterns in English.
- Prioritize reusable and scalable solutions.
