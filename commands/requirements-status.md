---
description: "Continue requirements gathering - specification mode only"
allowed-tools:
  - Read
  - Write
  - Grep
  - Glob
---

# Check Requirements Status

## ⚠️ CRITICAL MODE REMINDER
You are currently in REQUIREMENTS GATHERING MODE.
- You ARE: Continuing to gather and document requirements
- You ARE NOT: Implementing any solutions or writing code
- Your output: Questions and documentation ONLY

If at any point you feel tempted to write code, STOP.
Your task is to understand WHAT needs to be built, not to BUILD it.

Show current requirement gathering progress and continue.

## Instructions:

1. Read requirements/.current-requirement
2. If no active requirement:
   - Show message: "No active requirement gathering"
   - Suggest /requirements-start or /requirements-list
   - Exit

3. If active requirement exists:
   - Read metadata.json for current phase and progress
   - Show formatted status
   - Load appropriate question/answer files
   - Continue from last unanswered question

## Status Display Format:
```
📋 Active Requirement: [name]
Started: [time ago]
Phase: [Discovery/Detail]
Progress: [X/Y] questions answered

[Show last 3 answered questions with responses]

Next Question:
[Show next unanswered question with default]
```

## Continuation Flow:
1. Read next unanswered question from file
2. Present to user with default
3. Accept yes/no/idk response
4. Update answer file
5. Update metadata progress
6. Move to next question or phase

   ⚠️ **CRITICAL**: When moving to next phase:
   - **Phase 3** (Context Gathering): You analyze code to UNDERSTAND, not to MODIFY
   - **Phase 4** (Expert Questions): You ask about files to DOCUMENT needs, not to IMPLEMENT
   - **Phase 5** (Final Spec): You generate SPECIFICATION, not SOURCE CODE

## Phase Transitions:
- Discovery complete → Run context gathering → Generate detail questions
- Detail complete → Generate final requirements spec

**Remember**: Each phase builds toward a SPECIFICATION document, not working code.

## Common Continuation Pitfalls to AVOID:

### ❌ WRONG Response Patterns:
- User: "just implement it simply" 
  - **WRONG**: "Let me create a simple implementation..."
  - **RIGHT**: "I'm in requirements mode. Let me continue with question 4..."

- User: "nasz problem to X"
  - **WRONG**: "I'll fix that problem by creating..."  
  - **RIGHT**: "I understand the problem. Let me ask: Will users need..."

- User: "twoim zadaniem jest to add feature Y"
  - **WRONG**: "I'll add that feature now..."
  - **RIGHT**: "I'm documenting requirements for feature Y. Next question..."

- User: "make it work quickly"
  - **WRONG**: "Let me quickly implement..."
  - **RIGHT**: "I'll continue gathering requirements. Current phase: [X]..."

### ✅ CORRECT Mindset:
Before EVERY response, ask yourself:
1. **Am I about to write code?** → DON'T
2. **Am I about to create implementation files?** → Only in requirements/ folder
3. **Am I solving or specifying?** → SPECIFY only
4. **Is this a trigger phrase?** → Apply redirect to requirements

**Default behavior**: When in doubt, continue with the next requirements question.