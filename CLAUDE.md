# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **documentation-only** repository containing **learner-facing companion materials** (guides, templates, checklists) for [NaoKeys](https://naokeys.com/courses) e-learning courses. There is no application code, build system, or test suite.

Resources here are referenced from specific course lessons — students download or follow along with these materials during the course. Each resource ties to a lesson in the courses repo.

## NaoKeys Ecosystem

NaoKeys is a purpose-driven e-learning organization operating under the **AngoraSix** governance framework (cooperative, transparent, contribution-based). Three repos form the ecosystem:

| Repo | Path | Purpose |
|---|---|---|
| **branding** | `../../../branding` | Brand identity: logo, fonts (Lato + Fira Code), color palette, visual specs |
| **courses** | `../courses` | Course content: lesson scripts, video notes, production tools (slides, recording) |
| **resources** (this repo) | `.` | Learner-facing companion materials that complement specific lessons |

**Current course:** "Level Up to Modern Web Building — In the Age of AI" (WDLUP) — teaching practical web development with AI tools (v0, Next.js, Tailwind, MUI).

### How resources map to lessons

Resources are created as companions to specific lessons in the courses repo. For example:
- `01- Reference Guide` → used in WDLUP Module 1, Lesson 2 (defining website goal & scope)
- `02- Initial Prompt Template for v0` → used in WDLUP Module 1, Lesson 3 (generating initial website draft)

### Brand reference (from branding repo)

When creating or styling resources, follow NaoKeys brand guidelines:
- **Colors:** Key Yellow `#F7EC59`, Ink Black `#000000`, Warm Cream `#FAF6E3`
- **Fonts:** Lato (headings/body), Fira Code (code/technical content)
- **Contrast rule:** Never pair Warm Cream + Key Yellow as text/background (fails accessibility). Key Yellow + Ink Black and Warm Cream + Ink Black are both AAA compliant.

## Structure

- `README.md` — landing page listing available courses and platform links
- Course folders contain numbered resource files (one folder per course, named to match the course title)

## Conventions

- Resources are Markdown files organized by course folder.
- Files are numbered with a prefix (`01-`, `02-`) to indicate order and match the lesson sequence.
- Course folder names match the course title exactly.
- Content is written in English; templates may include i18n-ready structures (en/es dictionaries).
- **Tone:** Clear, practical, human — matching the course tone. No vague terminology; didactic correctness matters.
- Branch naming follows `rozagerardo/Trello-<ID>_<summary>` pattern.
- PRs are merged into `main` via GitHub pull requests.
