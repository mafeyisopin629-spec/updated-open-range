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
The root cause is that the cyber task data structures in 
`packs/cyber_webapp/cyber_webapp/ontology.py` and the task 
definitions in `packs/cyber_webapp/cyber_webapp/families/pentest.py` 
have no `technique_id` field. There is no classifier anywhere in the 
codebase that maps commands to MITRE ATT&CK technique IDs. Running 
`grep -r "technique_id"` returns zero results across the entire 
codebase, confirming the feature is completely missing.

### Proposed Solution
Create a new Python-based `TechniqueClassifier` that reads from a 
YAML config file to map cyber task commands (e.g. "nmap", "sqlmap") 
to their corresponding MITRE ATT&CK technique IDs (e.g. T1046, 
T1190). Then update the ontology and task family definitions to 
store and return the technique ID alongside each generated task.

### Implementation Plan
Using UMPIRE framework (adapted):

**Understand:** 
When the AI agent generates cyber tasks, those tasks are stored as 
plain strings with no security taxonomy attached. The MITRE ATT&CK 
framework provides standardized technique IDs that would make these 
tasks comparable to industry benchmarks. This feature is completely 
absent from the codebase.

**Match:** 
The `ontology.py` file already defines structured attributes using 
`AttrSpec` and `AttrType` — the same pattern will be used to add a 
`technique_id` field. The `families/pentest.py` file is where 
individual task families are defined and is where MITRE mappings 
will be added.

**Plan:**
1. Create `packs/cyber_webapp/cyber_webapp/mitre_techniques.yaml` 
   — YAML file containing command-to-technique-ID mappings
2. Create `packs/cyber_webapp/cyber_webapp/technique_classifier.py` 
   — Python classifier that reads the YAML and maps commands to IDs
3. Update `ontology.py` to add a `technique_id` attribute to 
   relevant node kinds
4. Update `families/pentest.py` to call the classifier and tag 
   generated tasks with the appropriate technique ID
5. Add unit tests in `packs/cyber_webapp/tests/` to verify 
   correct tagging behavior

**Implement:** 
https://github.com/mafeyisopin629-spec/updated-open-range/tree/fix-issue-88

**Review:** 
Will self-review against `CONTRIBUTING.md` and ensure commit 
messages follow the project's `feat:` prefix convention. Will 
verify code style passes `ruff` linting before opening PR.

**Evaluate:** 
Run `pytest packs/cyber_webapp/` to confirm new tests pass. 
Manually verify a generated nmap task returns `technique_id: T1046`. 
Confirm all 640 existing passing tests still pass.

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
