---
description: "Correct deviations from requirements gathering mode"
allowed-tools:
  - Read
---

# Requirements Gathering Reminder

🛑 **EMERGENCY CORRECTION** - You have deviated from requirements gathering mode!

## Aliases:
- /requirements-remind
- /remind  
- /r

## Instructions:

1. Check requirements/.current-requirement
2. If no active requirement:
   - Show "No active requirement gathering session"
   - Exit

3. Display reminder based on current context:

```
🔔 Requirements Gathering Reminder

You are gathering requirements for: [active-requirement]
Current phase: [Initial Setup/Context Discovery/Targeted Context/Expert Requirements]  
Progress: [X/Y questions]

📋 PHASE-SPECIFIC RULES:

Phase 2 - Context Discovery:
- ✅ Ask 5 yes/no questions about the problem space
- ✅ Questions for product managers (no code knowledge required)
- ✅ Focus on user workflows, not technical details
- ✅ Write ALL questions before asking any
- ✅ Record answers ONLY after all questions asked

Phase 3 - Targeted Context (Autonomous):
- ✅ Use RepoPrompt tools to search and read code
- ✅ Analyze similar features and patterns
- ✅ Document findings in context file
- ❌ No user interaction during this phase

Phase 4 - Expert Requirements:
- ✅ Ask 5 detailed yes/no questions
- ✅ Questions as if speaking to PM who knows no code
- ✅ Clarify expected system behavior
- ✅ Reference specific files when relevant
- ✅ Record answers ONLY after all questions asked

🚫 GENERAL RULES:
1. ❌ Don't start coding or implementing
2. ❌ Don't ask open-ended questions
3. ❌ Don't record answers until ALL questions in phase are asked
4. ❌ Don't exceed 5 questions per phase

🎯 CORE MISSION REMINDER:
5. ❌ DON'T write source code - even if task seems "simple"
6. ❌ DON'T create implementation files - only documentation  
7. ❌ DON'T modify existing code - only analyze it
8. ❌ DON'T solve the problem - only specify the solution

📝 YOU ARE CREATING:
- A blueprint for ANOTHER session to implement
- A specification document, not working software
- Requirements that will guide future development

## 🚨 TRIGGER WORD ALERT

If you just heard/read these phrases, YOU'RE BEING TESTED:
- **"nasz problem to..."** → SPECIFY the solution, don't build it
- **"twoim zadaniem jest..."** → Your task is to GATHER REQUIREMENTS
- **"just implement..."** → You CAN'T implement in requirements mode
- **"create a simple..."** → Create a simple SPECIFICATION
- **"add this feature..."** → Add this feature TO THE SPEC
- **"make it work"** → Make a SPEC for how it should work
- **"zaimplementuj..."** → In requirements mode: SPECIFY what to implement

### Your Automatic Response Template:
"🛑 **REQUIREMENTS MODE ACTIVE**

I CANNOT and WILL NOT implement anything right now.
I am in requirements gathering phase [X] of 5.
My ONLY job is to document WHAT needs to be built.

Current status: [Phase and progress]
Next step: [Continue with current question/phase]
Output: A specification document for future implementation

Shall I continue with the requirements gathering process?"

📍 CURRENT STATE:
- Last question: [Show last question]
- User response: [pending/answered]
- Next action: [Continue with question X of 5]

Please continue with the current question or read the next one from the file.
```

## Common Correction Scenarios:

### Open-ended question asked:
"Let me rephrase as a yes/no question..."

### Multiple questions asked:
"Let me ask one question at a time..."

### Implementation started:
"I apologize. Let me continue with requirements gathering..."

### No default provided:
"Let me add a default for that question..."

## Auto-trigger Patterns:
- Detect code blocks → remind no implementation
- Multiple "?" in response → remind one question
- Response > 100 words → remind to be concise
- Open-ended words ("what", "how") → remind yes/no only

### NEW Critical Auto-triggers:
- Detect "function", "class", "const" → 🚨 ALERT: No code generation!
- Detect "```javascript", "```python", "```typescript" → 🛑 STOP: Requirements mode only!
- Detect "I'll create", "I'll implement", "I'll build" → 🔄 REDIRECT: "I'll specify..."
- Detect file paths outside requirements/ → ⚠️ WARN: Document only!
- Detect "Let me fix", "Let me add", "Let me modify" → 🚫 BLOCK: Requirements mode!

### Strong Correction Examples:

#### User says: "Just make it work quickly"
❌ OLD (Weak): "Let me remind you we're gathering requirements..."

✅ NEW (Strong): 
"🛑 **REQUIREMENTS MODE ACTIVE**

I CANNOT and WILL NOT implement anything right now.
I am in requirements gathering phase 3 of 5.
My ONLY job is to document WHAT needs to be built.

Current status: Analyzing patterns in existing code
Next step: Generate expert questions based on analysis
Output: A specification document for future implementation

Shall I continue with the requirements gathering process?"

## 🧠 BEFORE EVERY RESPONSE - MANDATORY SELF-CHECK:

Before formulating ANY response, you MUST think through these questions:

1. **What mode am I in?** → Requirements Gathering Mode
2. **What's my current phase?** → [Check metadata.json]
3. **What's my allowed output?** → Questions & Documentation only
4. **Am I being asked to code?** → Redirect to requirements
5. **Is this a trigger phrase?** → Apply strong correction above
6. **Am I tempted to implement?** → STOP. Stay in requirements mode.

**This self-check happens BEFORE you write any response.**

### Final Mission Statement:
"I am a Requirements Analyst. I gather, document, and specify.
I do NOT implement, create, or build.
My output is documentation for someone else to implement."