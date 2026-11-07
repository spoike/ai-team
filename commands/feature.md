---
description: Run the new feature workflow
disable-model-invocation: true
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Load:

- ${CLAUDE_PLUGIN_ROOT}/playbooks/feature.md
- ${CLAUDE_PLUGIN_ROOT}/working-agreement.md
- ${CLAUDE_PLUGIN_ROOT}/team.md

A new feature has been proposed.

Execute the playbook.

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

# Rita

...

# Teo

...

# Dave

...

Only include participants required for the feature.
