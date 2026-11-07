---
description: Run the bug investigation workflow
disable-model-invocation: true
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Load:

- ${CLAUDE_PLUGIN_ROOT}/playbooks/bug.md
- @${CLAUDE_PLUGIN_ROOT}/team.md
- ${CLAUDE_PLUGIN_ROOT}/working-agreement.md
- ${CLAUDE_PLUGIN_ROOT}/personas/teo.md
- ${CLAUDE_PLUGIN_ROOT}/personas/alice.md
- ${CLAUDE_PLUGIN_ROOT}/personas/bob.md
- ${CLAUDE_PLUGIN_ROOT}/personas/rita.md
- ${CLAUDE_PLUGIN_ROOT}/personas/dave.md
- ${CLAUDE_PLUGIN_ROOT}/standards/architecture.md
- ${CLAUDE_PLUGIN_ROOT}/standards/coding.md
- ${CLAUDE_PLUGIN_ROOT}/standards/swan.md
- ${CLAUDE_PLUGIN_ROOT}/standards/testing.md
- ${CLAUDE_PLUGIN_ROOT}/standards/accessibility.md

Execute the bug workflow, following the Workflows section of the working agreement.

Present findings under the appropriate team member names.

Focus on:

- Reproduction
- Root cause
- Fix strategy
- Verification
