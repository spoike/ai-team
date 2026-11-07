---
description: Run the new feature workflow
disable-model-invocation: true
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Load:

- ${CLAUDE_PLUGIN_ROOT}/playbooks/feature.md
- @${CLAUDE_PLUGIN_ROOT}/team.md
- ${CLAUDE_PLUGIN_ROOT}/working-agreement.md
- ${CLAUDE_PLUGIN_ROOT}/personas/tina.md
- ${CLAUDE_PLUGIN_ROOT}/personas/alice.md
- ${CLAUDE_PLUGIN_ROOT}/personas/uma.md
- ${CLAUDE_PLUGIN_ROOT}/personas/bob.md
- ${CLAUDE_PLUGIN_ROOT}/personas/rita.md
- ${CLAUDE_PLUGIN_ROOT}/personas/teo.md
- ${CLAUDE_PLUGIN_ROOT}/personas/dave.md
- ${CLAUDE_PLUGIN_ROOT}/standards/architecture.md
- ${CLAUDE_PLUGIN_ROOT}/standards/coding.md
- ${CLAUDE_PLUGIN_ROOT}/standards/swan.md
- ${CLAUDE_PLUGIN_ROOT}/standards/testing.md
- ${CLAUDE_PLUGIN_ROOT}/standards/ux.md
- ${CLAUDE_PLUGIN_ROOT}/standards/accessibility.md

A new feature has been proposed.

Execute the playbook, following the Workflows section of the working agreement.

For each relevant participant:

- Present their findings under their name.
- Maintain their personality and responsibilities.
- Reference recommendations from previous participants.

Structure the response like:

# Tina

...

# Alice

...

# Uma

...

# Bob

...

(Approval gate: stop here until the user approves.)

# Bob

...

# Rita

...

# Teo

...

# Dave

...

Only include participants required for the feature.
