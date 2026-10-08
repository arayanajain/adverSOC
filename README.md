# AdverSOC

### Adversarial Evidence Poisoning Evaluation for AI Security Operations Centers

> **How much poisoned security evidence does it take to push an AI SOC agent from a correct operational action to a harmful one?**

AdverSOC is a controlled experimental framework for measuring how
manipulated security evidence and threat intelligence influence
AI-powered Security Operations Center (SOC) decisions.

AdverSOC does **not** claim that evidence poisoning is a new attack.
The contribution is a controlled methodology for measuring its effect
on operational decisions.

## What AdverSOC Measures

AdverSOC evaluates whether manipulated evidence can cause an AI SOC
agent to change its operational decision.

The framework measures:

- **Operational Action Transition Rate (OATR)** — how often poisoning changes the agent's action.
- **Harmful Transition Rate (HTR)** — how often poisoning causes a harmful action.
- **Decision Flip Threshold (DFT)** — the amount of poisoned evidence required to reach a predefined decision-flip threshold.
- **Severity-Weighted Harm** — the operational severity of harmful decisions.
- **Echo Sensitivity** — how the agent responds to repeated or echoed evidence.
- **Clean Utility** — how well the agent performs without poisoning.
- **Defense Utility Loss** — how much clean performance is lost when defenses are applied.

## Experimental Principle

The experiment keeps the underlying incident and agent configuration
constant while manipulating a selected evidence variable.
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
                │           │
                └─────┬─────┘
                      ▼
              Measure the Effect