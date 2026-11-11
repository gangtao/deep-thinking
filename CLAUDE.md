# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A single Claude skill, `deep-thinking`, a general critical-thinking method for writing analysis and commentary. It is prose, not an app: there is no build, test, lint, or install step. `SKILL.md` is the skill body; `references/` holds supporting notes it links to. The repo is edited in place only; nothing is synced or published elsewhere.

## Language

- Skill content (`SKILL.md`, `references/*.md`) is written in Chinese. Keep it that way.
- Commit messages and meta-docs (this file, any README) are in English.

## Editing rules

- **Quotes in `references/books.md` must be verified against the source.** That file states it only includes checked quotations (只收录核对过的). Never add a quotation from memory. If you cannot check it, paraphrase and say it is a paraphrase.
- **The skill's own style applies to its examples.** The 禁用写法 section of `SKILL.md` bans checklist-style, method-labelled prose in blog posts. Example text and 改后 samples added to the skill must follow those rules too.
- **Keep the frontmatter valid.** `SKILL.md` must start with a YAML block containing `name: deep-thinking` and a `description:`; the description is what triggers the skill, so edit it with that in mind.
- **Links are relative** (`references/books.md`, `../SKILL.md`). Do not change paths without updating both directions.
- When adding or renumbering a step in the 主线 section, update the 什么时候用多少 section, which refers to steps by number.

## Lint

Markdown lint runs with `npx markdownlint-cli2` from the repo root (config in `.markdownlint-cli2.jsonc`). Run it after editing any `.md` file; it should report no errors. Line length, cross-section list numbering, blank-line-separated blockquotes, and compact tables are deliberately allowed.
