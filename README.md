# claude-skills

Skills I use with Claude, one folder each. Take what helps you.

*Le skill che uso con Claude. Se vi aiutano, mettetele nel vostro flow.*

## Install

1. Download the folder of the skill you want, or clone the repo.
2. In Claude, open Customize > Skills > Add and upload the folder (or a zip of it).
3. Toggle it on. It triggers on the phrases listed in its description.

Each skill is a single `SKILL.md` file with a `name`, a `description` that says when it fires, the instructions, and one complete example of the output. The instructions are in English and the output follows the language of the conversation.

## Skills

These skills are built for claude.ai Projects, where work is split across many chats that share the same knowledge.


| Skill | What it does |
|---|---|
| [recap](recap/) | Closes a chat in a claude.ai Project with a standard handoff: chat name, what was done, next chat, actions for you, and a hook to paste into it. |
| [project-knowledge-check](project-knowledge-check/) | Keeps a Project's knowledge and instructions aligned with what was decided, so the next chat does not start from stale files. `recap` calls it before writing. |

## License

MIT. See [LICENSE](LICENSE).
