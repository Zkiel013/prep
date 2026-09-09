# CS (Diploma) — MS Office & MS-DOS (Paper-I §8, Paper-II §1)

> Elective 3: **Computer Science / Computer Engineering (Diploma)**, NPSC CTSE 2026.
> **Paper-I:** Tue 29 September 2026, 1:00–4:00 pm · **Paper-II:** Wed 30 September, 9 am–12 · **MCQ:** Wed 30 September, 1–3 pm.
> This file covers **Paper-I §8** (Computer languages, Software classification, and MS Office in detail) and **Paper-II §1** (the MS-DOS and Windows portion).

---

## 0. Why this is your highest-risk file (read first)

You are a **B.Tech Computer Science graduate**. You already know operating systems, DBMS,
networks, C and data structures *above* the depth this Diploma paper asks — for those
units your job is refresh, not learning. **This file is different.** As `CSDip_00_OVERVIEW.md`
warns, MS Office and MS-DOS are computer-*literacy* content, not computer-*science*
content. You very plausibly **never formally studied**:

- The **menu-level, feature-level** detail of Word, Excel, PowerPoint and Access — DropCap,
  WordArt, callouts, footnote-vs-endnote, tabs/borders/shading, **Mail Merge steps**,
  Excel function *categories*, chart components, PowerPoint *views*, Access *query types*.
- **MS-DOS** — the boot sequence, the system files, the exact **internal-vs-external**
  command split with syntax, and the meaning of **.BAT / .EXE / .COM**.

**None of this is derivable from first principles.** You cannot reason your way to "which
DOS command is external" or "how many steps Mail Merge has." You have to *learn it as
fact*. And it is **disproportionately represented in MCQs**, because each feature is an
easy single-fact question. `CSDip_00` allocates **~25–30% of your total study time** to
this file for maybe 15% of the syllabus. That ratio is correct. This is where the marks
you can *lose* live.

> ⚠️ **Version note.** Menu paths and some feature names differ slightly across Office
> versions (2003 menus vs 2007+ Ribbon; "Text" vs "Short Text" in Access). Where a detail
> is version-dependent it is marked **⚠️ verify**. Concepts (what Mail Merge *is*, what an
> absolute reference *does*) are version-independent and are given plainly. In the exam,
> **describe the concept and the standard steps**; do not stake an answer on an exact menu
> label unless you are sure.

---

## Tick-box checklist — what "ready" means for this file

Tick a box only when you can write a 5-mark answer from memory *and* score 8/10 on a
self-quiz of its facts.

**Languages & software (Paper-I §7, §8a)**
- [ ] Machine / assembly / high-level languages; 1GL → 5GL
- [ ] Characteristics of a good language
- [ ] Software classification: system vs application
- [ ] **Compiler vs Interpreter vs Assembler** (the comparison table)

**MS Word (Paper-I §8b)**
- [ ] Window components; editing; formatting
- [ ] Symbols / WordArt / DropCap; tabs, borders, shading
- [ ] Header/footer; **footnote vs endnote**
- [ ] Shapes, text boxes, callouts, captions; tables
- [ ] AutoCorrect; spelling & grammar; multiple columns
- [ ] **★ Mail Merge — full steps in order (guaranteed 10-marker)**
- [ ] Shortcut keys table

**MS Excel (Paper-I §8c)**
- [ ] Window; workbook vs worksheet
- [ ] **Relative vs absolute vs mixed referencing** (worked)
- [ ] Function syntax: SUM, AVERAGE, COUNT, COUNTA, IF, nested IF, VLOOKUP, HLOOKUP, MAX, MIN, ROUND, CONCATENATE
- [ ] Sort / filter
- [ ] **Charts: components, types, 3-D**

**MS PowerPoint (Paper-I §8d)**
- [ ] Components; **the views and their uses**
- [ ] Templates / slide master
- [ ] **Transition vs animation**; action buttons

**MS Access (Paper-I §8e)**
- [ ] Tables / fields / records / data types; primary keys
- [ ] Relationships (1:1, 1:M, M:N)
- [ ] **Queries (select / parameter / action / QBE)**; forms; reports

**MS-DOS (Paper-II §1f)**
- [ ] Features; booting; system files (IO.SYS, MSDOS.SYS, COMMAND.COM)
- [ ] **Internal vs external commands — full categorised table with syntax**
- [ ] Wildcards; **BAT vs EXE vs COM**

**Windows (Paper-II §1g)**
- [ ] Window operations; file/folder management; Recycle Bin/Restore
- [ ] Accessories (Notepad vs WordPad, Paint); versions in order

---

# PART A — COMPUTER LANGUAGES & SOFTWARE CLASSIFICATION

## A.1 Computer languages — the generations

**Intuition first.** A computer only understands 0s and 1s. Every "language" above that is
a more human-friendly layer that must eventually be **translated down** to those 0s and 1s.
The higher the generation, the closer to human language and the further from the machine.

| Gen | Name | What it is | Example | Needs translation? |
|---|---|---|---|---|
| **1GL** | **Machine language** | Pure binary (0s/1s); the only thing the CPU runs directly | `10110000 01100001` | No (it *is* machine code) |
| **2GL** | **Assembly language** | Mnemonics for machine instructions (ADD, MOV, SUB) | `MOV AL, 61h` | Yes — by an **assembler** |
| **3GL** | **High-level language** | English-like, machine-independent, procedural | C, FORTRAN, COBOL, BASIC, Pascal | Yes — **compiler/interpreter** |
| **4GL** | Very-high-level / problem-oriented | Closer to natural language; specify *what*, not *how* | SQL, report generators | Yes |
| **5GL** | AI / constraint-based | Solve problems via constraints and logic | Prolog, LISP (AI context) | Yes |

**Machine vs Assembly vs High-level — the classic table:**

| Feature | Machine (1GL) | Assembly (2GL) | High-level (3GL) |
|---|---|---|---|
| Form | Binary 0/1 | Mnemonics | English-like statements |
| Machine dependent? | **Yes** | **Yes** (CPU-specific) | **No** (portable) |
| Ease for humans | Hardest | Moderate | Easiest |
| Execution speed | Fastest | Fast | Slower (needs translation) |
| Translator needed | None | Assembler | Compiler / Interpreter |

**Characteristics of a good programming language** (a common 5-marker): simplicity &
readability, naturalness for its problem area, portability (machine independence),
efficiency, reliability, ease of maintenance, good structure/modularity, availability of
compilers and good documentation.

## A.2 Software classification

**Intuition.** Software is the set of instructions that makes hardware useful. It splits
into software that runs *the computer itself* (system) and software that does *your work*
(application).

```
                         SOFTWARE
              ┌─────────────┴─────────────┐
        SYSTEM SOFTWARE            APPLICATION SOFTWARE
        ├─ Operating System        ├─ General-purpose / packages
        ├─ Language translators     │   (MS Office, Photoshop, PageMaker,
        │   (compiler, interpreter, │    Tally)
        │    assembler)             └─ Custom / bespoke software
        └─ Utility programs             (payroll, billing written to order)
           (antivirus, disk tools)
```

| Type | Purpose | Examples |
|---|---|---|
| **System software** | Runs and manages the computer; a platform for applications | OS (Windows, Linux, DOS), compilers, interpreters, assemblers, device drivers, utilities |
| **Application software** | Helps the user do specific tasks | MS Word, MS Excel, Photoshop, PageMaker, Tally, browsers |

## A.3 ★ Compiler vs Interpreter vs Assembler (guaranteed question)

**Intuition.** All three are **translators** that convert human-written code into machine
code. The difference is *what* they translate and *how* they do it.

| Feature | **Compiler** | **Interpreter** | **Assembler** |
|---|---|---|---|
| Translates | High-level language → machine code | High-level language → machine code | **Assembly** language → machine code |
| How | **Whole program at once** | **Line by line** | Whole program (assembly) |
| Output | A separate **object/executable file** | No separate file; executes directly | Object code |
| Speed of execution | **Faster** (translated once) | **Slower** (translates each run) | Fast |
| Error reporting | Lists **all** errors after compiling | Stops at the **first** error | Reports errors in assembly |
| Memory | Needs space for object code | Less (no object file) | — |
| Examples | C, C++ compilers | Python, BASIC, older interpreted langs | MASM, TASM |

**MCQ traps:**
- A **compiler translates the whole program at once**; an **interpreter one line at a time**.
- The **assembler** translates **assembly** language (not high-level).
- An interpreter reports **only the first error** and then stops; a compiler reports the
  full error list.

### Part A — likely exam questions

- **[5]** Differentiate between a compiler and an interpreter.
- **[5]** Classify computer languages into generations with examples.
- **[5]** Distinguish between system software and application software.
- **[10]** Explain machine, assembly and high-level languages with their advantages and
  disadvantages.

---

# PART B — MS WORD

## B.1 The Word window — components

**Intuition.** Everything you do in Word happens in a window with a fixed furniture of
bars and areas. Naming them is a common objective/5-mark item.

| Component | What it is |
|---|---|
| **Title bar** | Top bar showing the document name and the program name |
| **Quick Access Toolbar** | Small customisable toolbar (Save, Undo, Redo) ⚠️ verify (2007+) |
| **Ribbon / Menu bar** | The tabbed command area (Home, Insert, Page Layout, References, Mailings, Review, View) in 2007+; a menu bar in 2003 ⚠️ verify |
| **Groups** | Sections within a Ribbon tab (e.g. Font, Paragraph) |
| **Ruler** | Horizontal & vertical rulers for margins, tabs, indents |
| **Document/Text area** | The white page where you type |
| **Cursor / Insertion point** | The blinking vertical line where text appears |
| **Scroll bars** | Move the view vertically/horizontally |
| **Status bar** | Bottom bar: page number, word count, language, view buttons, zoom |
| **View buttons** | Print Layout, Web Layout, Read Mode, Outline, Draft |

## B.2 Editing & formatting

- **Editing:** typing, selecting (click-drag; double-click = word; triple-click =
  paragraph ⚠️ verify), **Cut / Copy / Paste**, **Undo/Redo**, **Find & Replace**,
  Go To, insert/overtype.
- **Character formatting (Font group):** font face, size, **bold**, *italic*, underline,
  colour, highlight, subscript/superscript, change case, strikethrough.
- **Paragraph formatting:** alignment (left/centre/right/justify), line spacing,
  indentation, bullets & numbering, borders & shading.
- **Page formatting:** margins, orientation (portrait/landscape), paper size, columns,
  page breaks, watermark, page colour, page borders.

## B.3 Symbols, WordArt, DropCap

| Feature | What it does | Where ⚠️ verify menu |
|---|---|---|
| **Symbol** | Insert characters not on the keyboard (©, ±, §, α) | Insert → Symbol |
| **WordArt** | Decorative, stylised text with effects (curved, 3-D, coloured) | Insert → WordArt |
| **Drop Cap** | Enlarges the **first letter** of a paragraph to drop across several lines (as in a storybook) | Insert → Drop Cap; options **Dropped** or **In Margin** |
| **Equation** | Insert mathematical equations | Insert → Equation |

## B.4 Tabs, borders and shading

- **Tabs / Tab stops:** positions the cursor jumps to when you press **Tab**; types —
  **Left, Right, Centre, Decimal, Bar**; set via the ruler or Tabs dialog. Useful for
  aligning columns of text without a table.
- **Borders:** lines around text, paragraphs, pages, or table cells (style, colour,
  width). **Shading:** a background fill/colour behind text or a cell.

## B.5 Header, footer, footnote and endnote

- **Header** = repeating text at the **top** of every page; **Footer** = repeating text at
  the **bottom** (page numbers, date, title, logo).

**★ Footnote vs Endnote (a guaranteed "differentiate" question):**

| Feature | **Footnote** | **Endnote** |
|---|---|---|
| Appears | At the **bottom of the same page** where the reference mark is | At the **end of the document (or section)** |
| Purpose | A note/citation tied to a specific point | Consolidated notes/references at the end |
| Default numbering | 1, 2, 3 … | i, ii, iii … ⚠️ verify default |
| Inserted via | References → Insert Footnote | References → Insert Endnote |
| Shortcut ⚠️ verify | Alt+Ctrl+F | Alt+Ctrl+D |

## B.6 Shapes, text boxes, callouts, captions, tables

| Feature | What it is |
|---|---|
| **Shapes** | Drawing objects — lines, rectangles, circles, arrows, stars, flowchart symbols |
| **Text box** | A movable box that holds text anywhere on the page, independent of the main flow |
| **Callout** | A shape with a pointer/leader line used to label or annotate (like a speech bubble) |
| **Caption** | A numbered label added below/above a figure or table ("Figure 1: …", "Table 2: …") |
| **Table** | Rows × columns grid; insert, merge/split cells, borders, sort, formulas (=SUM) ⚠️ verify |

## B.7 AutoCorrect, spelling & grammar, multiple columns

- **AutoCorrect:** automatically fixes common typos ("teh" → "the") and can expand
  abbreviations as you type.
- **Spelling & Grammar check:** red wavy underline = spelling, green/blue wavy = grammar;
  run with **F7** ⚠️ verify.
- **Multiple columns:** split page text into 2 or more newspaper-style columns
  (Layout → Columns): One, Two, Three, Left, Right, or custom width/spacing with a line
  between.

## B.8 ★ MAIL MERGE — the guaranteed 10-marker (learn the steps in order)

**Intuition.** Mail Merge lets you write **one** letter and automatically produce **many**
personalised copies — same body, different name/address on each — by combining a
**main document** with a **data source (recipient list)**. Classic use: sending the same
letter to 500 people, each addressed personally.

**The three ingredients:**

| Ingredient | What it is |
|---|---|
| **Main document** | The letter/email/label template with fixed text |
| **Data source** | The list of recipients (a Word table, Excel sheet, Access DB, or Outlook contacts) with fields like Name, Address, City |
| **Merge fields** | Placeholders in the main document («Name», «Address») that get replaced by data-source values |

**The steps (Mailings tab → Start Mail Merge → Step-by-Step Wizard):**

1. **Select the document type** — Letters, E-mail messages, Envelopes, Labels, or
   Directory. (Usually **Letters**.)
2. **Select the starting document** — the current document, a template, or an existing one.
3. **Select recipients** — choose the data source: **type a new list**, **use an existing
   list** (Excel/Access/Word table), or **select from Outlook contacts**.
4. **Write / arrange your document** — type the fixed text and **insert merge fields** at
   the right places: **Address Block**, **Greeting Line**, or **Insert Merge Field** for
   individual fields.
5. **Preview your letters** — check how each personalised copy looks; scroll through
   recipients; exclude any you don't want.
6. **Complete the merge** — **Print** the letters directly, or **Edit individual documents**
   to produce one merged file you can review/save.

> **Answer tip:** write the definition, the **three ingredients**, then the **six numbered
> steps**. Drawing the "main document + data source → merged letters" flow scores well.

## B.9 Word shortcut keys (memorise — MCQ gold)

| Shortcut | Action | Shortcut | Action |
|---|---|---|---|
| Ctrl+N | New document | Ctrl+B | Bold |
| Ctrl+O | Open | Ctrl+I | Italic |
| Ctrl+S | Save | Ctrl+U | Underline |
| Ctrl+P | Print | Ctrl+E | Centre align |
| Ctrl+C | Copy | Ctrl+L | Left align |
| Ctrl+X | Cut | Ctrl+R | Right align |
| Ctrl+V | Paste | Ctrl+J | Justify |
| Ctrl+Z | Undo | Ctrl+A | Select all |
| Ctrl+Y | Redo | Ctrl+F | Find |
| Ctrl+K | Insert hyperlink | Ctrl+H | Replace |
| F7 | Spelling & grammar | Ctrl+Home / Ctrl+End | Start / end of document |

### Part B (Word) — likely exam questions

- **[10]** What is Mail Merge? Explain the steps to perform a mail merge in MS Word.
- **[5]** Differentiate between a footnote and an endnote.
- **[5]** What is Drop Cap? What is WordArt?
- **[5]** Explain header and footer.
- **[10]** Describe the main components of the MS Word window.
- **[5]** Differentiate between a text box and a callout.

### Part B — MCQ traps (with answers)

<details><summary>Answers</summary>

1. A footnote appears at the? → **bottom of the same page**
2. Mail Merge combines a main document with a? → **data source (recipient list)**
3. Ctrl+U does? → **Underline**
4. Drop Cap affects the? → **first letter of a paragraph**
5. F7 is the shortcut for? → **Spelling & Grammar check**
6. Repeating text at the top of every page is a? → **Header**
7. Which tab contains Mail Merge? → **Mailings** ⚠️ verify (2007+)

</details>

---

# PART C — MS EXCEL

## C.1 The Excel window & basic terms

**Intuition.** Excel is a grid of cells for storing numbers, text and **formulas** that
recalculate automatically when data changes.

| Term | Meaning |
|---|---|
| **Cell** | Intersection of a column and row (e.g. **B3**) |
| **Cell reference / address** | Column letter + row number (B3) |
| **Column** | Vertical; labelled A, B, C … |
| **Row** | Horizontal; labelled 1, 2, 3 … |
| **Name box** | Shows the active cell's address; top-left |
| **Formula bar** | Where you type/edit a cell's content or formula |
| **Active cell** | The currently selected cell (bordered) |
| **Range** | A block of cells, e.g. **A1:A10** or **A1:C5** |
| **Sheet tabs** | Tabs at the bottom to switch worksheets |

## C.2 Workbook vs Worksheet (a "differentiate" question)

| Feature | **Workbook** | **Worksheet** |
|---|---|---|
| What it is | The **whole Excel file** | A **single sheet (page)** inside the file |
| Contains | One or more worksheets | Cells (rows & columns) |
| File extension | `.xlsx` (2007+) / `.xls` (2003) ⚠️ verify | — (it lives inside the workbook) |
| Analogy | A book | A page in the book |

## C.3 ★ Relative, absolute and mixed referencing (worked — high yield)

**Intuition.** When you **copy a formula** to another cell, Excel adjusts the cell
references *unless you lock them*. How they change is the single most-tested Excel concept.
The **$** sign locks a part; press **F4** to cycle through the forms.

| Type | Looks like | Behaviour when copied | Use it when… |
|---|---|---|---|
| **Relative** | `A1` | **Both** column and row adjust | you want the reference to move with the formula (the normal case) |
| **Absolute** | `$A$1` | **Neither** changes — fully locked | you always point to one fixed cell (e.g. a tax rate) |
| **Mixed** | `$A1` (column locked) or `A$1` (row locked) | only the **unlocked** part adjusts | you lock one direction, e.g. multiplication tables |

**Worked example.** Cell **C1** contains `=A1*B1`. Copy it **down** to C2:

| | If C1 is | C2 becomes | Why |
|---|---|---|---|
| Relative | `=A1*B1` | `=A2*B2` | both rows shift down by one |
| Absolute | `=$A$1*$B$1` | `=$A$1*$B$1` | fully locked — no change |
| Mixed | `=A$1*B1` | `=A$1*B2` | row 1 in the first term is locked, the rest shifts |

**MCQ trap:** `$A$1` is **absolute** (locked both ways); `$A1` and `A$1` are **mixed**;
`A1` is **relative**. The `$` locks whatever comes **immediately after** it.

## C.4 Function syntax — the must-know functions

**Intuition.** A function is a built-in formula. Syntax = `=FUNCTION(arguments)`.

| Function | Syntax | Returns |
|---|---|---|
| **SUM** | `=SUM(A1:A10)` | Total of the range |
| **AVERAGE** | `=AVERAGE(A1:A10)` | Arithmetic mean |
| **COUNT** | `=COUNT(A1:A10)` | Count of cells that contain **numbers** |
| **COUNTA** | `=COUNTA(A1:A10)` | Count of **non-empty** cells (numbers **and** text) |
| **MAX** | `=MAX(A1:A10)` | Largest value |
| **MIN** | `=MIN(A1:A10)` | Smallest value |
| **ROUND** | `=ROUND(3.14159, 2)` → 3.14 | Rounds a number to given decimals |
| **IF** | `=IF(A1>=40,"Pass","Fail")` | One value if true, another if false |
| **Nested IF** | `=IF(A1>=90,"A",IF(A1>=75,"B","C"))` | Tests multiple conditions in sequence |
| **VLOOKUP** | `=VLOOKUP(lookup_value, table, col_index, [range_lookup])` | Looks up a value in the **first column** of a table and returns a value from another column (**vertical**) |
| **HLOOKUP** | `=HLOOKUP(lookup_value, table, row_index, [range_lookup])` | Same but searches the **first row** (**horizontal**) |
| **CONCATENATE** | `=CONCATENATE(A1," ",B1)` | Joins text from several cells into one |

**Key distinctions (MCQ traps):**
- **COUNT** counts only **numbers**; **COUNTA** counts **all non-empty** cells.
- **VLOOKUP** searches the **first column** and looks **down** (Vertical); **HLOOKUP**
  searches the **first row** and looks **across** (Horizontal).
- Every formula/function **begins with `=`**.

## C.5 Sort & Filter

- **Sort:** rearrange rows by a column's values — **Ascending (A→Z, small→large)** or
  **Descending (Z→A, large→small)**; can sort by multiple levels (e.g. by City, then Name).
- **Filter (AutoFilter):** temporarily **hides** rows that don't match a condition, showing
  only the rows you want; the data isn't deleted, just hidden.

## C.6 Charts — components, types, 3-D

**Intuition.** A chart turns numbers into a picture so trends are visible at a glance.

**Chart components (label these for a 5-marker):**

| Component | What it is |
|---|---|
| **Chart area** | The whole chart region |
| **Plot area** | The inner region where the data is drawn |
| **Data series** | A set of related values (one column/row of data) |
| **Data point** | A single value in a series |
| **Axes** | **X-axis (category)** and **Y-axis (value)** |
| **Legend** | Key that identifies each data series by colour |
| **Gridlines** | Reference lines across the plot area |
| **Data labels** | The actual values shown on the bars/points |
| **Chart title / axis titles** | Names of the chart and axes |

**Chart types (know when each is used):**

| Type | Best for |
|---|---|
| **Column / Bar** | Comparing values across categories (vertical/horizontal bars) |
| **Line** | Trends over time |
| **Pie** | Parts of a whole (percentages) — one data series |
| **Area** | Magnitude of change over time |
| **XY (Scatter)** | Relationship/correlation between two variables |
| **Doughnut** | Like a pie but multiple series |
| **Radar / Stock / Surface / Bubble** | Specialised comparisons ⚠️ verify list per version |

**3-D charts:** many chart types (column, bar, pie, line, area) have a **three-dimensional
variant** that adds depth for visual effect — e.g. a **3-D pie** or **3-D column**. They
look striking but can distort perception of values, so they are used for presentation
impact.

### Part C (Excel) — likely exam questions

- **[10]** Explain relative, absolute and mixed cell referencing with examples.
- **[5]** Differentiate between COUNT and COUNTA.
- **[5]** What is the difference between VLOOKUP and HLOOKUP?
- **[10]** Explain the components of a chart. Name any four chart types and their uses.
- **[5]** Differentiate between a workbook and a worksheet.
- **[5]** Write the syntax of the IF function with an example of a nested IF.

### Part C — MCQ traps (with answers)

<details><summary>Answers</summary>

1. `$A$1` is which type of reference? → **Absolute**
2. `A$1` is which type? → **Mixed** (row locked)
3. COUNT counts cells containing? → **numbers only**
4. VLOOKUP searches which part of the table? → **the first (leftmost) column**
5. Every Excel formula starts with? → **= (equal sign)**
6. A pie chart shows? → **parts of a whole (one data series)**
7. The whole Excel file is called a? → **Workbook**
8. Which key cycles reference types? → **F4** ⚠️ verify

</details>

---

# PART D — MS POWERPOINT

## D.1 Components

**Intuition.** PowerPoint builds a **slide show** — a sequence of slides holding text,
images, charts and media for a presentation.

| Component | What it is |
|---|---|
| **Slide** | A single page of the presentation |
| **Slide pane** | The main area where you edit the current slide |
| **Slides/Outline tab (thumbnails)** | Left-side panel showing all slides in order |
| **Placeholder** | A pre-formatted box for title, text, or content |
| **Notes pane** | Space for the speaker's private notes |
| **Status bar** | Slide number, view buttons, zoom |

## D.2 ★ The views and their uses (guaranteed question)

| View | What it shows / used for |
|---|---|
| **Normal view** | Default working view — edit one slide at a time (slide + thumbnails + notes) |
| **Slide Sorter view** | All slides as thumbnails — **reorder, add, delete, duplicate** slides and apply transitions |
| **Notes Page view** | The slide plus a large area for **speaker notes**, as it will print |
| **Reading view** | Play the show in a **window** (not full screen) for review |
| **Slide Show view** | The **full-screen** presentation the audience sees (start with **F5**) ⚠️ verify |
| **Outline view** | Shows only the **text** of slides as an outline — good for organising content quickly ⚠️ verify |

## D.3 Templates & Slide Master

- **Design template / theme:** a ready-made set of colours, fonts and background applied
  to all slides for a consistent look.
- **Slide Master:** the **top-level slide** that controls the formatting of **every** slide
  — change the master once and all slides update (fonts, logo, background, placeholders).
  This is a favourite exam concept: "a change made in the Slide Master applies to all
  slides."

## D.4 ★ Transition vs Animation (guaranteed "differentiate")

**Intuition.** A **transition** is the effect **between slides** (how one slide gives way
to the next). An **animation** is the effect applied to **objects within a slide** (how a
bullet, image or title enters, exits or moves).

| Feature | **Transition** | **Animation** |
|---|---|---|
| Applies to | The **whole slide** (slide-to-slide change) | An **individual object** on a slide (text, image, shape) |
| Example | Fade, Push, Wipe, Cover between slides | Fly In, Appear, Wipe, Zoom of a bullet point |
| Purpose | Smooth movement from one slide to the next | Control the order/emphasis of elements on one slide |
| Ribbon tab ⚠️ verify | **Transitions** | **Animations** |

## D.5 Action buttons

**Action buttons** are ready-made shapes (Home, Next, Back, Forward, Return) you place on
a slide; clicking them during the show performs an **action** — jump to another slide,
open a file/URL, or run a program. Used to make presentations interactive/navigable.

### Part D (PowerPoint) — likely exam questions

- **[5]** Explain the different views in MS PowerPoint and their uses.
- **[5]** Differentiate between a slide transition and an animation.
- **[5]** What is a Slide Master? Why is it useful?
- **[5]** What are action buttons? Give two examples.

### Part D — MCQ traps (with answers)

<details><summary>Answers</summary>

1. Which view is used to reorder slides? → **Slide Sorter view**
2. An effect between two slides is a? → **Transition**
3. An effect applied to a bullet point is an? → **Animation**
4. Changing the Slide Master affects? → **all slides**
5. F5 starts? → **the Slide Show** ⚠️ verify
6. Speaker notes are added in? → **Notes pane / Notes Page view**

</details>

---

# PART E — MS ACCESS

## E.1 The building blocks

**Intuition.** Access is a **relational database** program. Instead of one flat sheet, data
lives in **tables** that can be **linked**, and you interrogate them with **queries**,
enter data through **forms**, and print results as **reports**.

| Term | Meaning |
|---|---|
| **Database** | An organised collection of related data |
| **Table** | A grid storing data about one subject (e.g. Students) |
| **Field** | A **column** — one attribute (e.g. Name, RollNo) |
| **Record** | A **row** — all data about one entity (one student) |
| **Data type** | The kind of value a field holds |
| **Primary key** | A field that **uniquely identifies** each record; no duplicates, no nulls |

## E.2 Field data types

| Data type | Holds | Example |
|---|---|---|
| **Short Text / Text** | Text up to ~255 chars ⚠️ verify | Name, address |
| **Long Text / Memo** | Long text/paragraphs | Remarks |
| **Number** | Numeric values for calculation | Age, marks |
| **Date/Time** | Dates and times | DOB |
| **Currency** | Money values | Fees |
| **AutoNumber** | Auto-incrementing unique number (often a primary key) | ID |
| **Yes/No (Boolean)** | Two-state true/false | Passed? |
| **OLE Object** | Embedded object (image, file) | Photo |
| **Hyperlink** | Web/email link | Website |
| **Attachment** ⚠️ verify | Attached files | — |

## E.3 The Access objects

| Object | Purpose |
|---|---|
| **Table** | Stores the actual data |
| **Query** | Retrieves/filters/updates data (see E.5) |
| **Form** | A user-friendly screen for entering and viewing records one at a time |
| **Report** | A formatted printout/summary of data (with grouping, totals) |
| **Macro / Module** | Automation ⚠️ verify (beyond Diploma depth) |

## E.4 Relationships

**Intuition.** Tables are linked through a **common field** (a primary key in one table
matching a **foreign key** in another). This avoids duplicating data.

| Relationship | Meaning | Example |
|---|---|---|
| **One-to-One (1:1)** | One record in A links to one in B | Person ↔ Passport |
| **One-to-Many (1:M)** | One record in A links to many in B (**most common**) | Department ↔ Employees |
| **Many-to-Many (M:N)** | Many in A link to many in B (needs a junction table) | Students ↔ Courses |

## E.5 ★ Queries — the types (guaranteed question)

**Intuition.** A query asks a question of the data ("show all students who scored > 60").

| Query type | What it does |
|---|---|
| **Select query** | Retrieves and displays records matching criteria (the most common) |
| **Parameter query** | Prompts the user to type a value at run-time (e.g. "Enter city:") and uses it as the criterion |
| **Action query** | **Changes** data in bulk — four kinds: **Append** (add records), **Update** (modify), **Delete** (remove), **Make-Table** (create a new table from results) |
| **Crosstab query** | Summarises data in a spreadsheet-like grid (row × column totals) ⚠️ verify |
| **QBE (Query By Example)** | The **design-grid method** of building a query visually — you specify fields and criteria in a grid instead of writing SQL |

**MCQ trap:** **QBE = Query By Example**, the visual grid way of designing a query. The
four **action** queries are **Append, Update, Delete, Make-Table**.

### Part E (Access) — likely exam questions

- **[15]** Explain MS Access — database planning, tables and data types, queries, forms and
  reports.
- **[5]** Differentiate between a field and a record.
- **[5]** What is a primary key? Why is it important?
- **[5]** Explain the types of queries in MS Access.
- **[5]** Explain the three types of relationships in a database.

### Part E — MCQ traps (with answers)

<details><summary>Answers</summary>

1. A column in a table is a? → **Field**
2. A row in a table is a? → **Record**
3. A field that uniquely identifies each record? → **Primary key**
4. QBE stands for? → **Query By Example**
5. The four action queries? → **Append, Update, Delete, Make-Table**
6. Most common relationship type? → **One-to-Many (1:M)**
7. A user-friendly data-entry screen is a? → **Form**

</details>

---

# PART F — MS-DOS

## F.1 Features & characteristics

**Intuition.** MS-DOS (Microsoft Disk Operating System) is an old, **command-line**,
**single-user, single-tasking** operating system — you type commands rather than click
icons. Understanding it is pure recall; nothing is derivable.

| Feature | Detail |
|---|---|
| Interface | **Command-line (CLI)** — you type commands at a prompt (`C:\>`) |
| User/task model | **Single-user, single-tasking** |
| Character-based | No graphics (text only) |
| Case-insensitive | `DIR` = `dir` |
| File naming | **8.3 format** — up to **8** characters name + **3** characters extension (e.g. `LETTER.DOC`) |
| 16-bit | Runs 16-bit programs |

## F.2 The booting process

**Intuition.** "Booting" = starting the computer and loading the OS into memory. (The word
comes from "pull yourself up by your bootstraps.")

- **Cold boot** = starting from power-off. **Warm boot** = restarting a running machine
  (**Ctrl+Alt+Del**) without cutting power.

**Boot sequence (learn the order):**

1. **Power on** → the CPU runs the **BIOS**.
2. **POST (Power-On Self-Test)** — BIOS checks the hardware (RAM, keyboard, disks).
3. BIOS loads the **boot loader** from the **boot sector** of the disk (**MBR**).
4. **IO.SYS** loads (handles basic input/output).
5. **MSDOS.SYS** loads (the kernel/core of DOS).
6. **CONFIG.SYS** is read (loads device drivers & settings) — *if present*.
7. **COMMAND.COM** loads (the **command interpreter** / shell).
8. **AUTOEXEC.BAT** runs (a batch file of startup commands) — *if present*.
9. The **DOS prompt `C:\>`** appears — ready for commands.

## F.3 System files (memorise these three + two config files)

| File | Role | Type |
|---|---|---|
| **IO.SYS** | Handles low-level input/output; interfaces with BIOS | Hidden system file |
| **MSDOS.SYS** | The **kernel** — core of the OS; manages files, memory, programs | Hidden system file |
| **COMMAND.COM** | The **command interpreter (shell)** — reads and executes your typed commands; **holds all internal commands** | Command processor |
| *CONFIG.SYS* | Loads device drivers and system settings at boot | Text config file |
| *AUTOEXEC.BAT* | Batch file of commands run automatically at startup | Batch file |

> **The three "system files" the syllabus names are IO.SYS, MSDOS.SYS and COMMAND.COM.**
> CONFIG.SYS and AUTOEXEC.BAT are *startup configuration* files, not the core system files —
> but know both sets.

## F.4 ★ Internal vs External commands (the key table with syntax)

**Intuition — the single most important DOS distinction:**

- **Internal commands** are **built into COMMAND.COM** — they load into memory at boot, so
  they are **always available** and need no separate file on disk.
- **External commands** are **separate program files** (`.COM` / `.EXE`) stored on disk —
  DOS must **find and load the file** to run them, so they only work if that file (or its
  PATH) is present.

**INTERNAL COMMANDS (in COMMAND.COM):**

| Command | Syntax | Purpose |
|---|---|---|
| **DIR** | `DIR [drive:][path] [/P] [/W]` | List files & folders in a directory |
| **CD / CHDIR** | `CD [path]` | Change the current directory |
| **MD / MKDIR** | `MD dirname` | Make (create) a directory |
| **RD / RMDIR** | `RD dirname` | Remove an (empty) directory |
| **COPY** | `COPY source destination` | Copy one or more files |
| **DEL / ERASE** | `DEL filename` | Delete file(s) |
| **REN / RENAME** | `REN oldname newname` | Rename a file |
| **TYPE** | `TYPE filename` | Display a text file's contents on screen |
| **CLS** | `CLS` | Clear the screen |
| **DATE** | `DATE` | Display/set the system date |
| **TIME** | `TIME` | Display/set the system time |
| **VER** | `VER` | Show the DOS version |
| **PROMPT** | `PROMPT $p$g` | Change the look of the command prompt |
| **PATH** | `PATH=C:\DOS;...` | Set the search path for executable files |

**EXTERNAL COMMANDS (separate .EXE/.COM files on disk):**

| Command | Syntax | Purpose |
|---|---|---|
| **FORMAT** | `FORMAT drive:` | Prepare (format) a disk for use — erases it |
| **DISKCOPY** | `DISKCOPY A: B:` | Make an exact copy of one floppy to another |
| **CHKDSK** | `CHKDSK drive:` | Check a disk for errors and report status |
| **SCANDISK** | `SCANDISK drive:` | Scan and repair disk errors ⚠️ verify (later DOS) |
| **XCOPY** | `XCOPY source dest /S` | Copy files **and subdirectories** (more powerful COPY) |
| **ATTRIB** | `ATTRIB +R file` | View/change file attributes (Read-only, Hidden, System, Archive) |
| **TREE** | `TREE [drive:]` | Display the directory structure graphically |
| **LABEL** | `LABEL drive: name` | Create/change a disk's volume label |
| **SORT** | `SORT < file` | Sort lines of text |
| **FIND** | `FIND "text" file` | Search a file for a text string |
| **MORE** | `MORE < file` | Display output one screen at a time |
| **EDIT** | `EDIT filename` | Open the full-screen text editor |

> **How to tell them apart in the exam:** the "everyday navigation and file" commands
> (DIR, CD, MD, RD, COPY, DEL, REN, TYPE, CLS, DATE, TIME, VER, PROMPT, PATH) are
> **internal**. The "disk utilities and tools" (FORMAT, DISKCOPY, CHKDSK, SCANDISK, XCOPY,
> ATTRIB, TREE, LABEL, SORT, FIND, MORE, EDIT) are **external**. Memorise the two lists;
> this is a guaranteed "differentiate + list" question and a rich MCQ source.

## F.5 Wildcards

Wildcards let one command act on many files whose names match a pattern:

| Wildcard | Meaning | Example |
|---|---|---|
| **`*`** (asterisk) | Matches **any number** of characters | `DIR *.TXT` = all files with `.TXT` extension; `DEL *.*` = all files |
| **`?`** (question mark) | Matches **exactly one** character | `DIR FILE?.DOC` matches FILE1.DOC, FILEA.DOC, but not FILE12.DOC |

## F.6 ★ BAT vs EXE vs COM (guaranteed "differentiate")

**Intuition.** All three can be **run by typing their name** at the prompt, but they are
fundamentally different kinds of file.

| Feature | **.COM** | **.EXE** | **.BAT** |
|---|---|---|---|
| Type | Executable — a direct memory image of a program | Executable — with a header, relocatable | **Batch file** — plain **text** list of DOS commands |
| Size limit | **Max 64 KB** (single segment) | Can be **large** (multi-segment) | Any (it's just text) |
| How it runs | Loaded directly and executed | Loaded via its header, then executed | **Interpreted line by line** by COMMAND.COM |
| Human-readable? | No (binary) | No (binary) | **Yes** (you can open/edit it in a text editor) |
| Example | `COMMAND.COM` | `FORMAT.EXE` | `AUTOEXEC.BAT` |

**Execution priority** — if `RUN.COM`, `RUN.EXE` and `RUN.BAT` all exist and you type
`RUN`, DOS runs them in the order **`.COM` → `.EXE` → `.BAT`.** (COM first.)

**MCQ traps:**
- **.COM** files have a **64 KB** size limit; **.EXE** can be larger.
- **.BAT** is a **text** file interpreted line by line — the only human-readable one.
- Priority order **COM > EXE > BAT**.

### Part F (DOS) — likely exam questions

- **[10]** Differentiate between internal and external DOS commands, with examples of each.
- **[5]** Explain the booting process of MS-DOS.
- **[5]** Name the system files of MS-DOS and state the role of each.
- **[5]** Differentiate between .BAT, .EXE and .COM files.
- **[5]** What are wildcards? Explain `*` and `?` with examples.
- **[10]** Explain any five internal and any five external DOS commands with syntax.

### Part F — MCQ traps (with answers)

<details><summary>Answers</summary>

1. Internal commands are stored in? → **COMMAND.COM**
2. FORMAT is an? → **external** command
3. DIR is an? → **internal** command
4. The command interpreter of DOS is? → **COMMAND.COM**
5. `*` wildcard matches? → **any number of characters**
6. Max size of a .COM file? → **64 KB**
7. DOS 8.3 naming means? → **8-char name + 3-char extension**
8. Warm boot key combination? → **Ctrl+Alt+Del**
9. Which loads first: IO.SYS or COMMAND.COM? → **IO.SYS**
10. The DOS kernel file is? → **MSDOS.SYS**

</details>

---

# PART G — WINDOWS OS

## G.1 Window operations

**Intuition.** Windows is a **GUI (Graphical User Interface)**, **multi-tasking** OS — you
interact with icons, windows and a mouse instead of typed commands.

| Operation | How |
|---|---|
| **Open / Close** | Double-click an icon to open; click the **✕** to close |
| **Minimize** | Shrink the window to the taskbar (the **–** button) |
| **Maximize / Restore** | Fill the screen (**▢**) / return to previous size |
| **Move** | Drag the **title bar** |
| **Resize** | Drag a **border or corner** |
| **Switch between windows** | **Alt+Tab**, or click the taskbar |

**Desktop parts:** icons, **Taskbar**, **Start button/menu**, **System tray (notification
area)**, and the clock.

## G.2 File & folder management

| Task | How |
|---|---|
| **Create folder** | Right-click → New → Folder |
| **Copy / Move** | Copy (Ctrl+C) then Paste (Ctrl+V); Move = Cut (Ctrl+X) then Paste |
| **Rename** | Right-click → Rename, or press **F2** |
| **Delete** | Delete key → goes to **Recycle Bin** |
| **Search** | Search box / File Explorer search |
| Tool | **File Explorer / Windows Explorer** is the file-management program |

## G.3 Recycle Bin & Restore

**Intuition.** When you delete a file it isn't destroyed immediately — it goes to the
**Recycle Bin**, a holding area, so you can recover it.

- **Restore:** open the Recycle Bin → right-click the file → **Restore** → it returns to
  its original location.
- **Permanent delete:** emptying the Recycle Bin, or **Shift+Delete** (bypasses the Bin).
- Files deleted from **removable drives / network drives** usually do **not** go to the
  Recycle Bin. ⚠️ verify

## G.4 Accessories

| Accessory | What it is | Key distinction |
|---|---|---|
| **Notepad** | A **plain-text** editor (`.txt`) | **No formatting** — no bold, fonts, colours |
| **WordPad** | A **basic word processor** | **Supports formatting** — fonts, bold, colour, images (`.rtf`, `.doc`) |
| **Paint** | A simple **graphics/drawing** program | Create/edit images (`.bmp`, `.png`, `.jpg`) |
| **Calculator** | On-screen calculator | Standard/scientific modes |

**★ Notepad vs WordPad (common "differentiate"):** **Notepad edits plain text with no
formatting**; **WordPad is a lightweight word processor that supports fonts, styles,
colours and images.**

## G.5 Windows versions in order (memorise the sequence)

| Version | Year ⚠️ verify years |
|---|---|
| Windows 1.0 | 1985 |
| Windows 3.0 / 3.1 | 1990 / 1992 |
| **Windows 95** | 1995 |
| **Windows 98** | 1998 |
| Windows ME | 2000 |
| **Windows 2000** | 2000 |
| **Windows XP** | 2001 |
| Windows Vista | 2007 |
| **Windows 7** | 2009 |
| Windows 8 / 8.1 | 2012 / 2013 |
| **Windows 10** | 2015 |
| **Windows 11** | 2021 |

> Learn the **order** (which came before which) even if you're unsure of exact years —
> "Which came first, Windows 98 or Windows XP?" is a typical MCQ. (98 came first.)

### Part G (Windows) — likely exam questions

- **[5]** Differentiate between Notepad and WordPad.
- **[5]** What is the Recycle Bin? How do you restore a deleted file?
- **[5]** Explain file and folder management operations in Windows.
- **[5]** List the Windows versions in chronological order.

### Part G — MCQ traps (with answers)

<details><summary>Answers</summary>

1. Deleted files go to the? → **Recycle Bin**
2. Which key permanently deletes (bypasses the Bin)? → **Shift+Delete**
3. Notepad saves files with which extension? → **.txt**
4. Which supports formatting: Notepad or WordPad? → **WordPad**
5. F2 is used to? → **Rename**
6. Alt+Tab does? → **switch between open windows**
7. Which came first: Windows 98 or Windows XP? → **Windows 98**
8. The file-management tool in Windows is? → **File Explorer / Windows Explorer**

</details>

---

## Final revision map for this file

| Priority | Block | Why it matters most |
|---|---|---|
| **1** | **Mail Merge (B.8)**, **Internal vs External DOS commands (F.4)**, **BAT/EXE/COM (F.6)** | Named guaranteed questions; pure recall you can't derive |
| **2** | **Excel referencing (C.3)** + functions (C.4), **PowerPoint views (D.2)** & transition-vs-animation (D.4) | High-frequency "differentiate/explain" items |
| **3** | **Footnote vs endnote (B.5)**, **Access query types (E.5)**, **compiler/interpreter/assembler (A.3)** | Classic 5-mark and MCQ fodder |
| **4** | **DOS boot sequence (F.2)** & system files (F.3), **chart components (C.6)** | Ordered-list and labelling questions |
| **5** | **Windows: Notepad vs WordPad, Recycle Bin, versions (Part G)** | Easy product-fact MCQs |

**One-line summary:** This is the material you are least likely to already know and the
material most likely to appear as easy MCQs and standard "differentiate/explain"
descriptive questions. Over-learn **Mail Merge**, the **internal-vs-external DOS command
split**, **BAT/EXE/COM**, **Excel referencing** and **PowerPoint views** — these are named,
predictable, high-yield, and cannot be bluffed. Treat every **⚠️ verify** menu label or
year as "confirm before you write it," but the **concepts** in this file are exam-solid.
