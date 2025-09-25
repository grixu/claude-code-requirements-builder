---
description: "Finalize requirements gathering - generate specification only"
allowed-tools:
  - Read
  - Write
---

# End Requirements Gathering

Finalize the current requirement gathering session.

## Instructions:

1. Read requirements/.current-requirement
2. If no active requirement:
   - Show "No active requirement to end"
   - Exit

3. Show current status and ask user intent:
   ```
   ⚠️ Ending requirement: [name]
   Current phase: [phase] ([X/Y] complete)
   
   What would you like to do?
   1. Generate spec with current information
   2. Mark as incomplete for later
   3. Cancel and delete
   ```

4. Based on choice:

### Option 1: Generate Spec
- Create 06-requirements-spec.md *(SPECIFICATION document, not implementation)*
- Include all answered questions
- Add defaults for unanswered with "ASSUMED:" prefix
- Generate implementation hints *(as guidance for future developer)*
- Update metadata status to "complete"

**⚠️ CRITICAL REMINDER**: You are creating a SPECIFICATION DOCUMENT, not implementation code.
Even though you have analyzed technical details, your output is documentation that describes what to build, not the actual build.

### Option 2: Mark Incomplete
- Update metadata status to "incomplete"
- Add "lastUpdated" timestamp
- Create summary of progress
- Note what's still needed

### Option 3: Cancel
- Confirm deletion
- Remove requirement folder
- Clear .current-requirement

## Final Spec Format:
**REMEMBER**: This is a SPECIFICATION document that will guide future implementation!

```markdown
# Requirements Specification: [Name]

Generated: [timestamp]
Status: [Complete with X assumptions / Partial]

## Overview
[Problem statement and solution summary]

## Detailed Requirements

### Functional Requirements
[Based on answered questions]

### Technical Requirements
- Affected files: [list with paths] *(to be modified by implementer)*
- New components: [if any] *(to be created by implementer)*
- Database changes: [if any] *(to be implemented by implementer)*

### Assumptions
[List any defaults used for unanswered questions]

### Implementation Notes
[Specific guidance for implementation] *(instructions for future developer)*

### Acceptance Criteria
[Testable criteria for completion] *(to verify the implementation)*
```

**🎯 WHAT THIS DOCUMENT IS**:
- A blueprint for implementation
- Guidance for future development work  
- Documentation of requirements and constraints

**❌ WHAT THIS DOCUMENT IS NOT**:
- Executable code or working software
- Implementation files ready to use
- The actual solution to the problem

5. Clear .current-requirement
6. Update requirements/index.md