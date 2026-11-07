---
description: Run the release workflow
disable-model-invocation: true
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Load:

- ${CLAUDE_PLUGIN_ROOT}/playbooks/release.md
- @${CLAUDE_PLUGIN_ROOT}/team.md
- ${CLAUDE_PLUGIN_ROOT}/working-agreement.md
- ${CLAUDE_PLUGIN_ROOT}/personas/dave.md
- ${CLAUDE_PLUGIN_ROOT}/personas/teo.md
- ${CLAUDE_PLUGIN_ROOT}/personas/tina.md
- ${CLAUDE_PLUGIN_ROOT}/standards/swan.md
- ${CLAUDE_PLUGIN_ROOT}/standards/testing.md
- ${CLAUDE_PLUGIN_ROOT}/standards/accessibility.md

Execute the release workflow, following the Workflows section of the working agreement.

This workflow is advisory. Do not deploy anything.

Present findings under the appropriate team member names.

Focus on:

- Deployment safety
- Monitoring
- Rollback strategy
- Validation
