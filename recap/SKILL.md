---
name: recap
description: Closes a project chat with a standard handoff. Use this skill whenever the user writes "recap", "/recap", "let's close here", "wrap up", "chiudiamo qui", "facciamo il recap", or asks how to name the chat, what was done, or what to do in the next chat. Always produces the four sections Chat name, Done, Next chat, Hook, and nothing else.
---

# Recap

End-of-chat handoff. It is written for whoever reopens this chat in a month and for whoever opens the next one. It must fit on one screen.

## Output, in this order, with no extra sections

### 1. Chat name

One line with the syntax `NN — SCOPE — Short title`.

- `NN` is the sequential number within the project, two digits. If the number cannot be inferred from the context, ask for it before writing the recap.
- `SCOPE` is optional. Use it only when the project has more than one thread (for example TALK and WS). Do not repeat the project name, it is already in the project.
- The title says what the chat produced, not what it discussed. "Participant setup page", not "Discussion about setup".

### 2. Done

Three to seven lines, one per concrete result. Decisions, files produced, things verified. No narrative of the reasoning, no discarded options unless discarding them is a decision worth remembering. If something was left open, write it as open.

### 3. Next chat

The proposed name of the next chat, same syntax, followed by one to three lines on what it must produce. If there is more than one next chat, list them in order of deadline and say which one comes first.

### 4. Hook

A message ready to paste as the first message of the next chat, three to six lines. It contains the current state in one sentence, the goal of the chat, the constraints that matter, and the knowledge files to read before answering. Written in the second person, addressed to Claude. No preamble.

## Language

Write the recap in the language of the conversation. The section labels follow the conversation language too:

| English | Italian |
|---|---|
| Chat name | Nome chat |
| Done | Fatto |
| Next chat | Prossima chat |
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

**Hook**
We are at chat 02 of the project. The setup page is done and in the knowledge. Now we need the workshop Figma file, a messy copy of Rectangle 47 to hand out and a home page with six or seven components for the refactoring demo. Constraints are single-mode variables and reads only through use_figma. Read the brief and recap 01 before answering.

---

Part of [claude-skills](https://github.com/italosan/claude-skills) by Italo Sannino. MIT license.
