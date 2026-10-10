---
name: project-knowledge-check
description: Checks that a claude.ai Project knowledge and instructions are current and consistent with what was decided. Use after a decision that changes direction, before closing a chat, or when the user asks whether the knowledge or KB is ok ("la kb è ok?", "check the knowledge").
---

# Project knowledge check

Every new chat in a Project reads the knowledge and the Project instructions before anything else. If those contain old versions or superseded decisions, the new chat starts from the wrong place and repeats mistakes that were already fixed. This check keeps them aligned with what was decided.

It is designed for claude.ai Projects. Outside a Project, say so in one line and stop.

## When to run it

- Right after a decision that changes direction (a new tool, a new scope, a dropped option). This is when stale files do the most damage.
- Before closing a chat. The `recap` skill calls it.
- When the user asks whether the knowledge is ok.

## Steps

1. **List what is there.** Read the Project info: instructions, documents, uploaded files.
2. **Versions.** For every document created or changed in this chat, the latest version must be in the knowledge. Follow the versioning convention in the Project instructions. If there is none, propose one (a short progressive suffix in the file name, only the latest version kept).
3. **Superseded content.** Compare the knowledge and the instructions with the decisions taken in this chat. Look for anything that now contradicts them, such as old tools, old prices, old names, people no longer involved, options that were dropped. Search for the specific terms, do not rely on a skim.
4. **Fix what you can.**
   - A working document that is out of date gets a new version that describes the current state. Rewrite it, do not patch it with strikethroughs and notes, because a patched document still reads as the old one.
   - A historical document that should stay as it is (a brief, an original offer) gets a short notice at the top saying what is superseded and which file prevails.
   - Remove previous versions of documents you versioned yourself in this Project, once the new one is saved.
5. **Hand over what you cannot do.** Claude cannot edit the Project instructions. If they are out of date, write the full corrected text as a document in the knowledge, tell the user to paste it into Project instructions, and delete the document once they confirm. Same for files only the user can upload.

## Rules

- Never delete a document the user uploaded without asking. Deletions cannot be undone.
- Never delete a version until its replacement is saved.
- After the user says they made a change, read the Project info again and confirm. Do not assume.

## Output

A short report in the language of the conversation, three parts at most.

- **Fixed**, what was changed, with file names.
- **For you**, what only the user can do, with the exact file or text to use.
- **Ok**, a one-line confirmation when nothing else is needed.

No introduction, no list of files that were already fine. When writing in Italian, follow the same style rules as `recap`.

## Example

**Fixed**
- Rewrote the project plan as `project-plan_05.md`, removing the old CMS and the dropped supplier, and deleted `project-plan_04.md`
- Added a notice at the top of `original-brief.md` saying that the budget and stack sections are superseded by the plan

**For you**
- Paste the text of `project-instructions_02.md` into Project instructions, then tell me so I can check and delete the file

---

Part of [claude-skills](https://github.com/italosan/claude-skills) by Italo Sannino. MIT license.
