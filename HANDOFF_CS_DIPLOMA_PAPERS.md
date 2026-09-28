# Handoff: solve NPSC CTSE Computer Science (Diploma) papers

Paste everything below this line into a local Claude Code session.

---

I'm preparing for the NPSC (Nagaland Public Service Commission) Combined Technical Services Examination (CTSE). I need solved versions of the **Computer Science (Diploma)** past papers only.

## Inputs
- Zip files of CTSE past papers are in `C:\Users\areax\Documents\ctse`. They cover many streams and years.
- Extract them into a scratch folder. Keep only the **Computer Science (Diploma)** papers (Paper-I and Paper-II, every year available) and ignore the other streams. Some zips may hold scanned images instead of text PDFs. If so, read the page images directly and transcribe them.
- List what you found (year, paper, page count) before you start solving.

## Output repo
- The repo is `prep` (GitHub `zkiel013/prep`). Work on branch `claude/ctse-exam-question-banks-tbfxbg`: pull it first, since it holds an earlier session's work.
- **Format to copy exactly:** `Materials/General/08_CTSE_2026_GK_PAPER_SOLVED.md` (a solved GK paper) and its PDF in `PDFs/Materials/General/`.
- Save the new files as `Materials/ComputerScience_Diploma/PYQ_<YEAR>_PAPER_<I|II>_SOLVED.md`, with a matching PDF in `PDFs/Materials/ComputerScience_Diploma/`.
- For context on the syllabus and the Diploma topics (MS Office, MS-DOS, hardware, systems analysis, viruses), see `Materials/ComputerScience_Diploma/CSDip_00_OVERVIEW.md` through `CSDip_04_MCQ_and_QuestionBank.md` and `Materials/_Shared/OFFICIAL_SYLLABUS.md`.

## Format for each paper
1. A header naming the paper, year, booklet code (if printed), marks/duration, and marking scheme as printed on the cover. The technical MCQ papers have used +2 per correct answer and −1/3 of that per wrong answer, but take the scheme from each paper's own instructions.
2. **Every question typed out in full, with its options.** Transcribe exactly, keeping statement lists (i/ii/iii) and match-the-following tables.
3. The answer directly under each question as a blockquote: `> **Ans: C) …** ✓ one-line reason`.
4. Descriptive questions (5/10/15 marks) get a model answer sized to the marks: a 5-mark answer is ~5–6 solid points, and 10/15-mark answers get headings, a diagram described in text or ASCII, and a worked example where relevant.
5. Mark confidence on every answer:
   - ✅ confirmed by a web source (cite the URL in a Sources list at the end)
   - ✓ standard textbook fact
   - ⚠️ ambiguous or sources disagree. Give the best answer, name the alternative, and say why.

## Accuracy rules (strict)
- **No assumptions.** If a question can't be answered with certainty, mark it ⚠️ and explain. Don't present a guess as fact.
- Work out numerical, code-output and logic questions step by step, and show the working in the reason. Where you can, run code snippets to confirm outputs.
- If a scan is unreadable, write `[illegible in source]` rather than guess the wording.

## PDF generation
Convert each `.md` to a phone-readable A4 PDF with the answer blockquotes styled: a green left border and light green background. The questions must keep their line breaks, i.e. the options on a new line under the stem (the earlier session used Python `markdown` with the `tables` + `nl2br` extensions, then headless Chromium via Playwright). Any equivalent tool is fine. Check one rendered page visually before finishing.

## Finish
- Commit with a clear message and push to `claude/ctse-exam-question-banks-tbfxbg`.
- Tell me which papers were solved, how many questions each, and the ⚠️ list with reasons.
