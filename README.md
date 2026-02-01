# Duncan: AI Infrastructure & Context Engineering Project

This repository is a hands-on laboratory for building AI-native infrastructure, focusing on the intersection of **Harnessing** and **Context Engineering**.

## 🎯 Purpose

1.  **Learn AI Infrastructure:** Deep dive into building the "plumbing" (Harness) and the "strategy" (Context Engineering) required to make LLMs useful in real-world environments.
2.  **Build a Useful Tool:** Develop a personal/work assistant (`duncan`) where Google Drive and Cursor Cloud Agent can all **share context with one another**.

## 📐 End-State Architecture

```
                         [ API Gateway ]
                               |
                               v
                    +---------------------+
                    |    ORCHESTRATOR     |
                    | (Context Engineer)  |
                    +---------------------+
                            /     \
                           v       v
                    +---------+  +------------------+
                    | GDRIVE  |  | CURSOR CLOUD     |
                    |         |<->|     AGENT        |
                    +---------+  +------------------+
                           \       /
                            \     /
                             v   v
                    +---------------------+
                    |   SHARED CONTEXT    |
                    +---------------------+
```

The **Orchestrator** sits in the middle, using **Context Engineering** to:
- Read and write to **GDrive**.
- Delegate code tasks to the **Cursor Cloud Agent**.
- Share context between both, enabling flows like: *"Read GDrive spec → Implement in Code → Update GDrive docs."*

## 🚀 Roadmap: The Three Milestones

### Milestone 1: Individual Capabilities (Read-Only)
**Goal:** Establish the "Hands" for each source and the "Brain" for execution.
- [ ] **GDrive Connector (Read):** List files and read content from Google Docs.
- [ ] **Cursor Cloud Agent:** Programmatically trigger the agent to perform repo tasks.
- [ ] **Context Engineering (V1):** Basic formatting of GDrive data for LLM consumption.
- *Constraint: No data sharing between sources.*

### Milestone 2: Advanced Interaction & UI Feedback
**Goal:** Move from reading to writing and enhance the observation harness.
- [ ] **GDrive (Write):** Create docs, update content, and append to files.
- [ ] **Cursor Tool Upgrades:**
    - **Visual Feedback:** Capture screenshots of code-driven UI changes.
    - **Execution:** Run the project and capture terminal/UI output.
- [ ] **Observability Harness:** Custom logging for all write operations and tool calls.
- *Constraint: Still no cross-pollination of context.*

### Milestone 3: The Unified Orchestrator (Cross-Source Intelligence)
**Goal:** Full context sharing and autonomous cross-platform execution.
- [ ] **Cross-Source Context:** GDrive documentation can drive code implementation, and code changes can update GDrive docs.
- [ ] **Unified Search:** A single query that finds relevant info across Code and GDocs.
- [ ] **Autonomous Loop:** The agent can read a GDrive spec, check the codebase, and then instruct Cursor to implement the feature, updating GDrive with results.
- [ ] **Evaluation Harness:** Test the system's ability to handle complex, multi-step, multi-platform tasks.


