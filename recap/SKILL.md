---
name: recap
description: Closes a chat in a claude.ai Project with a standard handoff. Use this skill whenever the user writes "recap", "/recap", "let's close here", "wrap up", "chiudiamo qui", "facciamo il recap", or asks how to name the chat, what was done, or what to do in the next chat. Produces Chat name, Done, Next chat, For you (only when needed) and Hook, and nothing else.
---

# Recap

End-of-chat handoff for people who split a claude.ai Project into many chats. A new chat starts with no memory of the previous one. The recap is written for whoever reopens this chat in a month and for whoever opens the next one. It must fit on one screen.

This skill is designed for chats inside a Project. If the chat is not in a Project, say so in one line and ask whether to produce only the hook.

## Before writing

Run the `project-knowledge-check` skill if it is installed. The next chat reads the Project knowledge first, so a recap is only as good as the files behind it. If the skill is not installed, at least confirm that every document created or changed in this chat is in the knowledge in its latest version.

## Output, in this order, with no extra sections

### 1. Chat name

One line with the syntax `NN — SCOPE — Short title`.

- If the chat already has a name in the Project, keep it. Do not invent a new one.
- If the Project instructions define a different naming convention, follow that one.
- `NN` is the sequential number within the project, two digits, in the order chats were opened. If the number cannot be inferred from the context, ask for it before writing the recap.
- `SCOPE` is optional. Use it only when the project has more than one thread (for example TALK and WS). Do not repeat the project name, it is already in the project.
- The title says what the chat produced, not what it discussed. "Participant setup page", not "Discussion about setup".

### 2. Done

Three to seven lines, one per concrete result. Decisions, files produced, things verified. No narrative of the reasoning, no discarded options unless discarding them is a decision worth remembering. If something was left open, write it as open.

### 3. Next chat

The proposed name of the next chat, same syntax, followed by one to three lines on what it must produce. If there is more than one next chat, list them in order of deadline and say which one comes first. The hook is written only for the first.

### 4. For you

Only when there are actions that only the user can take before opening the next chat. For example pasting new Project instructions, uploading a file Claude cannot write, renaming the chat, sending a message. One to three lines, each naming the exact file or text to use. If there is nothing, leave the section out.

### 5. Hook

A message ready to paste as the first message of the next chat, three to six lines. It contains the current state in one sentence, the goal of the chat, the constraints that matter, and the knowledge files to read before answering. Written in the second person, addressed to Claude. No preamble.

- Name the knowledge files exactly as they appear in the knowledge, version included.
- Never mention choices that were superseded in this chat. State what is still undecided as undecided.

## Language

Write the recap in the language of the conversation. The section labels follow the conversation language too:

| English | Italian |
|---|---|
| Chat name | Nome chat |
| Done | Fatto |
| Next chat | Prossima chat |
| For you | Da fare tu |
| Hook | Hook |

For any other language, translate the labels the same way, keeping Hook unchanged.

## Style rules

- Plain sentences.
- When writing in Italian, no dashes, semicolons or colons inside sentences. The em dash is used only in the chat name syntax.
- Interface labels (menus, settings, buttons) always in English.
- No introduction, no closing, no offer to do anything else. The recap ends with the hook.

## Example

**Chat name**
01 — WS — Participant setup page

**Done**
- Wrote the setup page in Italian, interface labels in English, to be sent three days before the workshop
- Clarified the difference between local extension and remote connector, with screenshots
- Verified that the remote connector works with a Figma Starter account and Claude Free
- Open: the Claude Free message cap over 75 minutes is still untested

**Next chat**
02 — WS — Workshop Figma file
Must produce the messy copy of Rectangle 47 to hand out and the rich home page for the refactoring demo.

**For you**
- Paste the text of `workshop-instructions_02.md` into Project instructions, then delete the file

**Hook**
We are at chat 02 of the project. The setup page is done and in the knowledge as `setup-page_03.md`. Now we need the workshop Figma file, a messy copy of Rectangle 47 to hand out and a home page with six or seven components for the refactoring demo. Constraints are single-mode variables and reads only through use_figma. Read `workshop-brief_02.md` before answering.

---

Part of [claude-skills](https://github.com/italosan/claude-skills) by Italo Sannino. MIT license.
