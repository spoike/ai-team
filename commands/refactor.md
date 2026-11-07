---
description: Run the refactoring workflow
disable-model-invocation: true
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Load:

- ${CLAUDE_PLUGIN_ROOT}/playbooks/refactor.md
- @${CLAUDE_PLUGIN_ROOT}/team.md

Execute the refactoring workflow.

Focus on:

- Improved maintainability
- Reduced complexity
- Preserved behavior
