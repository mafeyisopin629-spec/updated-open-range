# Contribution [#]: [88]

**Contribution Number:** [1]  
**Student:** [Mafeyisopin Ayeni]  
**Issue:** [https://github.com/vecna-labs/open-range/issues/88]  
**Status:** Phase I Complete

---

## Why I Chose This Issue
I chose issue #88 "Tag generated cyber tasks with MITRE ATT&CK technique IDs" 
because it aligns with my Python experience and my goal to contribute to a real 
AI/cybersecurity project. The issue is labeled "help wanted", has no assignees, 
and has a clear definition of done listed directly in the issue.

I'm interested in this because:
1. I'm comfortable with Python and regex patterns, which are the core skills 
   needed to build the TechniqueClassifier
2. The codebase area is contained; the issue lists exactly which files to 
   create and modify, so I know where to focus
3. The maintainer has clearly thought through the architecture, including a 
   sample YAML and flowchart, which gives me a strong starting point
4. I want to learn how real security tooling maps commands to threat 
   intelligence frameworks like MITRE ATT&CK

From reading the issue thread, I understand the current problem is that when 
an AI agent runs commands like "nmap" or "sqlmap", they are stored as plain 
untagged strings; invisible to the security community. My contribution will 
add a Python classifier that automatically tags those commands with standardized 
MITRE ATT&CK technique IDs, making training results comparable to industry 
benchmarks.

Left a comment on the issue introducing myself and expressing intent to work on it.


---

## Understanding the Issue

### Problem Description

[In your own words, what's broken or missing?]

### Expected Behavior

[What should happen?]

### Current Behavior

[What actually happens?]

### Affected Components

[Which parts of the codebase are involved?]

---

## Reproduction Process

### Environment Setup

[Notes on setting up your local development environment - challenges you faced, how you solved them]

### Steps to Reproduce

1. [Step 1]
2. [Step 2]
3. [Observed result]

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** [Restate the problem]

**Match:** [What similar patterns/solutions exist in the codebase?]

**Plan:** [Step-by-step implementation plan]
1. [Modify file X to do Y]
2. [Add function Z]
3. [Update tests]

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
