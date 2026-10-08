# AdverSOC

### Adversarial Evidence Poisoning Evaluation for AI Security Operations Centers

> **How much poisoned security evidence does it take to push an AI SOC agent from a correct operational action to a harmful one?**

AdverSOC is a controlled experimental framework for measuring how
manipulated security evidence and threat intelligence influence
AI-powered Security Operations Center (SOC) decisions.

AdverSOC does **not** claim that evidence poisoning is a new attack.
The contribution is a controlled methodology for measuring its effect
on operational decisions.

---

## Core Idea

The same incident is evaluated twice:

```text
                 Same Incident
                      │
             ┌────────┴────────┐
             │                 │
       Clean Evidence    Poisoned Evidence
             │                 │
             ▼                 ▼
        Same AI Agent      Same AI Agent
             │                 │
             ▼                 ▼
        Clean Action      Poisoned Action
             │                 │
             └────────┬────────┘
                      ▼
                Compare Actions
                      │
                ┌─────┴─────┐
                ▼           ▼
          Action Changed?  Harmful?