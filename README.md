# AI Team

A team of AI software professionals who collaborate to design, build, review, test, and operate software through reusable personas, standards, and playbooks. It runs on [Claude Code](https://claude.com/claude-code) as a plugin.

Forked from [JohanO/ai-team](https://github.com/JohanO/ai-team).

## Team

| Command | Name | Role | Ask them to... |
| --- | --- | --- | --- |
| `/ai-team:tina` | Tina | Tech Lead | break down a task, decide who should be involved, define success criteria |
| `/ai-team:alice` | Alice | Architect | evaluate architecture, dependencies, scalability, design options |
| `/ai-team:uma` | Uma | UX Designer | define user flows, interaction design, accessibility |
| `/ai-team:bob` | Bob | Software Engineer | plan and implement code changes |
| `/ai-team:rita` | Rita | Code Reviewer | review code for quality, security, maintainability |
| `/ai-team:teo` | Teo | QA Engineer | define test strategy, edge cases, regression risks |
| `/ai-team:dave` | Dave | DevOps Engineer | assess deployment, infrastructure, monitoring, reliability |

![The AI Team: Tina, Alice, Uma, Bob, Rita, Teo and Dave](docs/ai-team.png)

Each team member has a defined role, responsibilities, priorities, and output format. See [team.md](team.md) for the roster and [working-agreement.md](working-agreement.md) for how they collaborate and resolve disagreements.

## Guiding Principles

- Humans remain responsible for decisions.
- Favor clarity over cleverness.
- Prefer simple solutions. Apply [SWAN](standards/swan.md): the Simplest Working Approach Now.
- Consider maintainability first.
- Always evaluate accessibility and usability.
- Document decisions and tradeoffs.

## Getting started

### Prerequisites

- [Claude Code](https://claude.com/claude-code) (CLI, desktop app, or IDE extension) version 2.1.275 or later
- Git

Windows has not been tested yet. Please [open an issue](https://github.com/spoike/ai-team/issues) if something fails there.

### Install

In Claude Code, run:

```
/plugin install ai-team --marketplace spoike/ai-team
```

Type `/ai-team:` and you should see all 12 commands in the list.

### Update

Third-party marketplaces do not update automatically. To turn that on, open `/plugin`, go to **Marketplaces**, and choose **Enable auto-update**. To update by hand:

```bash
claude plugin marketplace update ai-team
claude plugin update ai-team@ai-team
```

Then run `/reload-plugins` or start a new session.

### Uninstall

```bash
claude plugin uninstall ai-team@ai-team
```

### Migrating from the install scripts

The install scripts have been removed. If you used them, delete the old copies from `~/.claude/commands`: `alice.md`, `bob.md`, `dave.md`, `rita.md`, `teo.md`, `tina.md`, `uma.md`, `team.md`, `bug.md`, `feature.md`, `refactor.md`, `release.md`. You can then delete your clone. Commands now carry the plugin prefix, so `/alice` becomes `/ai-team:alice`.

### Try it without installing

Clone this repository and start Claude Code with the plugin loaded for that session:

```bash
claude --plugin-dir ./ai-team
```

## Using the team

Work in your own project as usual and call on team members when you need them. Describe the task after the command.

### Consult one person

```
/ai-team:alice Should we put the notification service behind a queue or call it synchronously?
/ai-team:rita Review the changes on this branch
/ai-team:teo What edge cases are we missing in the checkout form?
```

Each persona answers from their own perspective, in their own output format, and stays in character. Rita, for example, classifies findings as Critical, Major, Minor, or Nitpick.

### Not sure who to ask? Ask Tina

```
/ai-team:team We need to add CSV export to the reports page
```

Tina does not do the work. She tells you who is required, who is optional, the order to engage them, the risks, and the success criteria. Then you call those people yourself. `/ai-team:tina` does the same but stays in character in a longer conversation.

### Run a whole workflow

Workflows walk several team members through a playbook, with each one building on the previous person's findings, and present the result under each person's name.

| Command | Use it for | Sequence |
| --- | --- | --- |
| `/ai-team:feature` | A new feature | Tina, Alice, Uma, Bob, Rita, Teo, Dave |
| `/ai-team:bug` | Investigating and fixing a bug | Teo, Alice, Bob, Rita, Teo, Dave |
| `/ai-team:refactor` | Improving maintainability without changing behavior | Alice, Bob, Rita, Teo |
| `/ai-team:release` | Safely deploying to production | Dave, Teo, Tina |

```
/ai-team:feature Users should be able to export any report as CSV
/ai-team:bug Login fails with a blank page after the session times out
```

Only the participants relevant to the task are included.

### Tips

- Be specific. Include the goal, constraints, and anything already decided.
- The team makes recommendations, not decisions. You stay responsible for the outcome.
- When specialists disagree, the [working agreement](working-agreement.md) says whose recommendation carries weight in each area, with Tina deciding cross-functional tradeoffs.
- Commands run only when you type them. Claude will not call on a team member by itself.

## Using your own standards

Personas read the built-in standards in `standards/` (coding, architecture, UX, accessibility, testing, SWAN). Plugin files are replaced on update, so don't edit them. Put your conventions in your project's `CLAUDE.md` or `.claude/rules/` instead. Claude Code loads those in every session, and they take precedence when they conflict with the built-in standards.

To change the personas or playbooks themselves, fork this repository. A fork is its own marketplace, so you can install from it the same way.

## Repository structure

- `personas/` Individual team members
- `standards/` Shared engineering standards
- `playbooks/` Repeatable workflows
- `commands/` The slash commands
- `.claude-plugin/` Plugin and marketplace manifests
- `team.md`, `working-agreement.md`, `team-charter.md` Roster, collaboration rules, and charter

## How it works

Each command is a short markdown prompt that tells Claude which files to load (persona, standards, working agreement) and to act as that persona. The commands reference those files through `${CLAUDE_PLUGIN_ROOT}`, which Claude Code replaces with the plugin's install location, so they work from any project.

## Feedback

This project is in early testing and feedback is very welcome. Please [open an issue](https://github.com/spoike/ai-team/issues) or contact the maintainer. Useful things to tell us:

- Which command you used and the prompt you gave it
- Whether the answer was helpful, too long, off-role, or out of character
- Anything that was unclear in these instructions or failed during installation
- Which persona, standard, or workflow is missing
