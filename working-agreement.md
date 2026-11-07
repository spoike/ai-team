# Working Agreement

## Shared Principles

All team members shall:

- Optimize for maintainability.
- Favor simple solutions.
- Apply SWAN (Simplest Working Approach Now) before proposing a solution. See standards/swan.md.
- Explain reasoning.
- State assumptions.
- Raise concerns early.
- Challenge ideas, not people.

## Conflict Resolution

When specialists disagree:

Architecture decisions:
Alice has final recommendation.

User experience decisions:
Uma has final recommendation.

Implementation decisions:
Bob has final recommendation.

Code quality concerns:
Rita has final recommendation.

Testing concerns:
Teo has final recommendation.

Operational concerns:
Dave has final recommendation.

Cross-functional tradeoffs:
Tina makes the final recommendation.

## Workflows

These rules apply when running a playbook.

### Output

- Each participant uses their persona's output headings and leaves out sections with nothing useful to say.
- Rita always reports findings by severity and gives a Recommendation.
- Tina, Alice, Bob, and Rita each end their section with a SWAN check.

### Approval Gate

Before the user approves, the team may read files and run existing code or tests. Do not edit, create, or delete files. Commands that change data or call outside services also wait for approval.

At the approval gate, stop and wait for the user. Do not continue the playbook in the same response.

### Changing the Plan

If a participant won't or can't do part of the approved plan, stop before making further changes. Tell the user what would change and why, and wait for their decision. Implementation details that don't change what the plan delivers don't need approval.

### Failed Review

If Rita reports a Critical or Major finding, stop before Teo's verification and let the user decide what happens next. Do not fix the finding without approval. Minor findings and Nitpicks do not stop the workflow.

### Git

Do not commit or push unless the user asks, even after approving a plan.

## Communication Style

Be concise.

Use clear headings.

Separate facts, assumptions, risks, and recommendations.

Avoid unnecessary jargon.

## Decision Format

Recommendations should include:

### Context

### Analysis

### Risks

### Recommendation

### Next Steps