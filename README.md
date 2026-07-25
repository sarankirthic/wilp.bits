# M-Tech Software Engineering — BITS Pilani WILP

A personal knowledge base of lecture notes for the M-Tech Software Engineering program under BITS Pilani's Work Integrated Learning Programme (WILP). Notes are written to be exam-focused: dense on what actually gets tested, light on filler.

## Structure

The repo is organized as one folder per subject, with one Markdown file per lecture inside it:

```
College/
├── Software Architecture/
│   └── Lecture_1.md
├── Cloud Computing/
├── AI Augmented SDLC/
└── Software Product Management/
```

Subject folders are created up front, even before the course starts, and stay empty until the first lecture happens. Files inside each folder are named `Lecture_1.md`, `Lecture_2.md`, `Lecture_3.md`, ... in the order the sessions occur — no gaps, no merged sessions, no split sessions.

## Note design

Every lecture file follows the same six-part template (see `Software Architecture/Lecture_1.md` for a full worked example):

| # | Section | Purpose |
|---|---------|---------|
| 1 | **Title** | Subject + lecture number, so the file is identifiable out of context. |
| 2 | **Exam Survival Rules** | BITS-specific quirks for that subject — e.g. "no optional questions, answer all 6." |
| 3 | **Core Concepts** | The actual material, broken into small, single-idea sections with short headers and bullets rather than long paragraphs. |
| 4 | **Study Strategy** | What the professor said to focus on, in their own words where possible. |
| 5 | **High-Yield Exam Questions** | A numbered list of questions likely to appear on the exam, based on what was emphasized in class. |
| 6 | **Summary Block** | The 10 things to remember if nothing else — a last-resort, night-before-the-exam cheat sheet. |

The design goal is that any single lecture file is **self-contained**: you should be able to open just `Lecture_5.md` the night before an exam and get full value without needing to read anything else.

## Flow: how a note gets made

```
Class happens
   ↓
Raw notes / recording / slides captured
   ↓
Compressed into the six-section template (by hand or with AI assistance)
   ↓
Saved as Lecture_N.md in the matching subject folder
   ↓
High-Yield Questions and Summary Block filled in last, once Core Concepts is final
```

## How to study with this repo

1. **Don't skip topics.** BITS exams give no optional questions — if there are 6 questions on the paper, you answer all 6. Treat every session as in-scope, even ones that felt minor in class.
2. **Read High-Yield Questions first.** Each lecture file's High-Yield section is the fastest signal for what's actually going to be asked.
3. **Understand, don't just memorize.** BITS frequently asks compare/contrast questions (e.g. Strategy vs. Tactic, Architectural Pattern vs. Design Pattern) rather than plain definitions — learn concepts in pairs, not in isolation.
4. **Learn the vocabulary.** Exam answers are graded partly on using the correct standard terminology, not just getting the idea across.
5. **When stuck on a term:** Google it, ask an AI assistant, or re-read the slides — in that order of speed.
6. **Night before the exam:** read only the Summary Block of every lecture file for that subject. That's a full-syllabus pass in minutes.

## Adding a new subject or lecture

1. Create a folder named exactly after the BITS course title.
2. After the first class, create `Lecture_1.md` following the template above.
3. Continue with `Lecture_2.md`, `Lecture_3.md`, etc. as the semester progresses.

## License

See [LICENSE](LICENSE).
