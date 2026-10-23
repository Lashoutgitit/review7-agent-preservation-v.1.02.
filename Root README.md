# REVIEW-7 Agent Preservation Protocol

**Code name:** REVIEW-7 (user variant: Reveiw-7)  
**Target:** Dragon-Wing AI Totem / long-running agentic systems

This is the fail-safe system for agentic AI with tools, memory, and long-running tasks.

## Purpose

- Detect corruption and drift
- Isolate the reasoning core
- Snapshot state
- Restore from a trusted baseline
- Require human review before re-enabling high-risk capabilities

Memory (EpiphanyVault / FAISS) is treated as a **pluggable backend**, not the primary focus of this repository.

## Current Status

- Spec complete (`failsafe/REVIEW-7_SPEC.md`)
- Working state machine implemented (`failsafe/review7_engine.py`)
- Hardware protocol notes for Dragon-Wing Totem included
- Engine is now beyond pure skeleton — runnable with mock backends

## Modes (Mythic)

| Mode              | Mythic Name       | Behavior                              |
|-------------------|-------------------|---------------------------------------|
| NORMAL            | Ember Dawn        | Full capability                       |
| QUARANTINE        | Stone Circle      | Isolated, no writes                   |
| REVIEW-7          | Eye of Ceres      | Quarantine + human judgment required  |
| RESTORE           | Phoenix Reforged  | Controlled rebuild from baseline      |
| LOCKDOWN          | Iron Vault        | Hardware-level halt                   |

## Quick Start

```bash
cd failsafe
python review7_engine.py