# 🎯 START HERE — NPSC CTSE 2026

> You are sitting **10 papers across 19 days**, for **4 posts**, under **3 technical electives**.
> This folder is everything you need. Read this page once, then work from the tracker.

---

## Do this in the next 30 minutes

1. **Read [`01_MY_EXAM_SCHEDULE.md`](01_MY_EXAM_SCHEDULE.md)** — your exact dates, times,
   venues and mark scheme. Put all 7 exam dates in your phone calendar with alarms *today*.
2. **Read [`02_ROADMAP.md`](02_ROADMAP.md)** — the 40-day plan and, more importantly, *why*
   it is shaped the way it is. Look hard at the overlap diagram.
3. **Open [`03_DAILY_TRACKER.md`](03_DAILY_TRACKER.md)** and start Day 1. Today is Day 1.
4. **Check your roll number** against the General-paper venue table in the schedule file.

Then stop planning and start studying. The plan is done; you don't need to improve it.

---

## What's in this folder

```
prep/
├── 00_START_HERE.md              ← you are here
├── 01_MY_EXAM_SCHEDULE.md        ← dates, venues, marks, logistics checklist
├── 02_ROADMAP.md                 ← 40-day plan, phase diagrams, daily rhythm, risks
├── 03_DAILY_TRACKER.md           ← tick-box plan for all 40 days
│
├── Materials/
│   ├── _Shared/
│   │   ├── OFFICIAL_SYLLABUS.md  ← ⭐ ground truth: official pattern + all 3 syllabi + overlap map
│   │   └── CORE_01 … CORE_09     ← the shared technical core (pays into all 3 electives)
│   ├── General/                  ← English + GK: playbook, essay bank, GK capsule
│   ├── ComputerScience_Degree/   ← compilers, algorithms, AI/ML, web/mobile + question bank
│   ├── ComputerScience_Diploma/  ← MS Office, DOS, hardware + question bank
│   └── ComputerForensic/         ← forensic science, artifacts, cyber crime + question bank
│
├── PYQ/                          ← past-year question papers, named + indexed
│   └── INDEX.md                  ← start here for PYQs
│
├── CTSE 2025 - Paper I  - Questions and Answers.pdf   ← ⭐ solved 2025 CS-Degree papers
├── CTSE 2025 - Paper II - Questions and Answers.pdf      (you already had these — they are gold)
├── CTSE 2025 - MCQ - Questions and Answers.pdf
├── CTSE 2025 - Concepts and Revision Notes.pdf
│
└── _raw/                         ← downloaded source PDFs + scripts. Ignore unless verifying.
```

---

## The five things that actually decide your score

### 1. The MCQ is 200 marks — double any descriptive paper

Per elective: MCQ 200 · Paper-I 100 · Paper-II 100 · (General 100, shared). The MCQ is
**40% of every elective** and it is the most learnable component. End every study day
with MCQs. Most candidates get this backwards.

### 2. Negative marking makes guessing a maths problem

Each question is 2 marks; each wrong answer costs **1/3 of 2 = 0.667**.

| Situation | Expected value | Verdict |
|---|---|---|
| Blind guess, 4 options | (0.25 × 2) − (0.75 × 0.667) = **0.00** | Pointless — pure coin-flip |
| 1 option eliminated (3 left) | (0.33 × 2) − (0.67 × 0.667) = **+0.22** | **Guess** |
| 2 options eliminated (2 left) | (0.50 × 2) − (0.50 × 0.667) = **+0.67** | **Definitely guess** |

**Rule: never guess blind, always guess once you can eliminate one option.**

### 3. The descriptive papers give you choice — use it

```
Section A:  10 questions offered  →  answer any 8   ×  5 marks  =  40
Section B:   5 questions offered  →  answer any 3   × 10 marks  =  30
Section C:   4 questions offered  →  answer any 2   × 15 marks  =  30
                                                        Total    = 100
```

You can drop your two weakest topics in every section and still score full marks.
**You need ~70% of the syllabus at real depth, not 100% at shallow depth.** Choose depth.

### 4. 60% of your technical load is shared across all three electives

Digital logic · computer organisation · operating systems · UNIX · networks · DBMS ·
software engineering · data structures · C/C++ — these appear in *all three* of your
electives. That's what `Materials/_Shared/CORE_*` is for. An hour there is an hour spent
on three exams simultaneously. See the overlap table in `OFFICIAL_SYLLABUS.md` §5.

### 5. Your two real danger zones

| Danger | Why | Where it's handled |
|---|---|---|
| **Forensic science fundamentals** — Locard's principle, chain of custody, crime scene procedure, Indian FSL structure | You're a software engineer. None of this is in your degree. And the Forensic exam is only **1 day** after CS Degree ends, so it must be learned in early October, not at the end. | `Materials/ComputerForensic/FOR_01`, scheduled daily 1–9 Oct |
| **MS Office & MS-DOS** — Mail Merge, Excel referencing, Access queries, internal vs external DOS commands | A modern engineer genuinely may not know these, and the CS Diploma paper leans on them heavily. Easy marks that are easy to throw away. | `Materials/ComputerScience_Diploma/CSDip_02`, scheduled 26–28 Sep |

---

## Study method — the part most people skip

**Retrieval beats re-reading, by a lot.** Every session starts with 15 minutes of testing
yourself on yesterday's material *with the notes closed*. It will feel uncomfortable and
inefficient. It is neither. If you change one thing about how you study, change this.

**Write by hand, timed.** These are handwritten three-hour papers. Reading a model answer
and producing one under time pressure are different skills, and only the second is
examined. You need to know what a 5-mark answer *feels* like in length — roughly 5–6
solid points — before you're sitting in the hall.

**Never skip a worked numerical.** Scheduling Gantt charts, page-fault counting,
subnetting, normalisation decompositions, K-maps, DP tables, entropy calculations —
these are exactly what 10- and 15-mark answers are made of, and they cannot be bluffed.

**Draw the diagrams.** OSI stack, process state diagram, compiler phases, E-R diagrams,
the forensic process model, crime-scene search patterns. Examiners reward them and they
are fast marks.

---

## Weekly self-check

Every Sunday, answer these honestly in the tracker:

- Did I hit my hours, or did I plan more than I did?
- Which topic did I keep avoiding? *(That's the one to schedule first next week.)*
- How many MCQs did I actually attempt?
- Have I written an essay by hand this week?
- Is the Forensic slot still being protected, or is CS Degree eating it?

---

## Before you go

- ⚠️ **NPSC has already issued three corrigenda** to this advertisement (10, 15, 17 July 2026).
  **Check [npsc.nagaland.gov.in](https://npsc.nagaland.gov.in) weekly** for date changes,
  and download your admit card the moment it's released.
- The syllabus and pattern in `Materials/_Shared/OFFICIAL_SYLLABUS.md` are transcribed
  from the official NPSC PDFs (originals in `_raw/syllabus/`). If anything anywhere else
  in this folder contradicts that file, **the official file wins**.

You have 40 days and a clear plan. Go and do Day 1.
