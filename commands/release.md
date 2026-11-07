---
description: Run the release workflow
disable-model-invocation: true
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Load:

- ${CLAUDE_PLUGIN_ROOT}/playbooks/release.md
- @${CLAUDE_PLUGIN_ROOT}/team.md

Execute the release workflow.

Focus on:

- Deployment safety
- Monitoring
- Rollback strategy
- Validation
