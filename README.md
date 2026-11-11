# deep-thinking

A Claude skill for writing commentary and analysis that thinks before it argues. It distills seven books on critical thinking into one method: start from a real puzzle, give the other side its strongest version, question the evidence where a reader would, and end with a conditional judgment. The skill itself is written in Chinese; the method is language-independent.

## What it does

The skill splits writing into two halves:

1. **Think.** Before drafting, the agent works through a private "thinking draft": what does not add up, whose problem this is, the strongest case for the other side, competing explanations, what survives once rhetoric is stripped, second-order effects, and a tentative judgment with its conditions. This draft is never shown to readers.
2. **Write.** The article develops only the one or two findings that actually changed the judgment. Follow-up questions appear next to the sentence or number that raised them, phrased as facts and scenarios rather than method names. No section titled "applying framework X", no textbook terms, no checklist prose.

The method draws on Dewey's *How We Think*, Gause and Weinberg's *Are Your Lights On?*, Weinberg's *Quality Software Management*, Paul and Elder's *Critical Thinking*, Moore and Parker's *Critical Thinking*, Bassham et al.'s *Critical Thinking*, and Browne and Keeley's *Asking the Right Questions*.

## Layout

```text
SKILL.md             The skill: attitudes, the eight-step inquiry, writing rules,
                     before/after examples, the thinking-draft checklist, self-check
references/books.md  Notes on the seven books, verified quotations, and the full
                     eleven questions from Browne and Keeley with an output structure
                     for a detailed critique document
```

## Install

Copy or symlink this directory into your skills folder, for example:

```sh
ln -s /path/to/deep-thinking ~/.claude/skills/deep-thinking
```

Claude Code picks it up by the `description` in `SKILL.md`, which is bilingual so the skill triggers for both Chinese and English requests.

## Development

The skill text is Chinese; commit messages and this README are English. Quotations in `references/books.md` are only added after checking them against the source. Lint Markdown with:

```sh
npx markdownlint-cli2
```

Changes to the writing rules are verified by having agents write the same article from the same source material with and without the skill, then comparing the results.
