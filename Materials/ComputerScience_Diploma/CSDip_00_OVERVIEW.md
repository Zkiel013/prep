# CS (Diploma) — Overview, Strategy and Navigation

> Elective 3: **Computer Science / Computer Engineering (Diploma)**, NPSC CTSE 2026.
> This file is the map. Read it once fully, then keep it open as your checklist.

---

```
+==============================================================================+
|                                                                              |
|   !!  THIS IS YOUR FIRST TECHNICAL EXAM.  IT IS THE MOST TIME-CRITICAL.  !!  |
|                                                                              |
|   Paper-I    ....... Tue 29 September 2026 ......  1:00 pm - 4:00 pm         |
|   Paper-II   ....... Wed 30 September 2026 ......  9:00 am - 12:00 noon      |
|   Technical MCQ .... Wed 30 September 2026 ......  1:00 pm - 3:00 pm         |
|                                                                              |
|   Today is 5 September 2026.                                                 |
|                                                                              |
|        DAYS TO PAPER-I  :  24                                                |
|        DAYS TO PAPER-II :  25   (and the MCQ the same afternoon)             |
|                                                                              |
|   The CS (Degree) papers are on 10 and 12 October -- ELEVEN DAYS LATER.      |
|   Do NOT let Degree revision eat this month. Diploma comes first, and the    |
|   shared core you build for Diploma pays straight into Degree afterwards.    |
|                                                                              |
|   30 September is a DOUBLE DAY: a 3-hour descriptive paper in the morning    |
|   and a 2-hour, 100-question MCQ in the afternoon with only ~1 hour gap.     |
|   Build stamina for it. Do at least two full-length back-to-back rehearsals. |
|                                                                              |
+==============================================================================+
```

---

## Table of contents

1. [Exam structure and marking](#1-exam-structure-and-marking)
2. [The single most important strategic insight](#2-the-single-most-important-strategic-insight)
3. [Syllabus checklist — Paper-I](#3-syllabus-checklist--paper-i)
4. [Syllabus checklist — Paper-II](#4-syllabus-checklist--paper-ii)
5. [What the exam actually asks](#5-what-the-exam-actually-asks)
6. [Recommended study order](#6-recommended-study-order)
7. [Day-by-day plan, 5–30 September](#7-day-by-day-plan-5-30-september)
8. [Exam-day tactics](#8-exam-day-tactics)
9. [File index for this folder](#9-file-index-for-this-folder)

---

## 1. Exam structure and marking

| Component | Questions | Marks | Duration | Date & time |
|---|---|---|---|---|
| Technical MCQ | 100 Q x 2 marks | **200** | 2 hrs | 30 Sept, 1–3 pm |
| Technical Descriptive **Paper-I** | Sections A/B/C | **100** | 3 hrs | 29 Sept, 1–4 pm |
| Technical Descriptive **Paper-II** | Sections A/B/C | **100** | 3 hrs | 30 Sept, 9 am–12 noon |
| General English + GK (separate paper) | — | 100 | 3 hrs | (see admit card) |

### Descriptive paper internal structure (both Paper-I and Paper-II)

| Section | Question numbers | Rule | Marks each | Total |
|---|---|---|---|---|
| **A** | Q1 – Q10 | answer **any 8 of 10** | 5 | 40 |
| **B** | Q11 – Q15 | answer **any 3 of 5** | 10 | 30 |
| **C** | Q16 – Q19 | answer **any 2 of 4** | 15 | 30 |
| | | | **Total** | **100** |

Note how generous the choice is. In Section A you may drop 2 of 10; in Section B you drop 2 of 5; in Section C you drop 2 of 4. **You can leave roughly 40% of the paper untouched and still score 100/100.** That changes what "prepared" means: you do not need every corner of the syllabus at 15-mark depth. You need *breadth* at 5-mark depth and *four or five bankable deep areas* for Sections B and C.

### MCQ marking — negative marking of one-third

- Correct answer: **+2**
- Wrong answer: **−1/3 × 2 = −0.667**
- Unattempted: **0**

Three wrong answers wipe out one correct answer. The arithmetic of when to guess is worked out in [§8](#8-exam-day-tactics) — read it before the exam, not during.

---

## 2. The single most important strategic insight

**State it plainly: you are a B.Tech Computer Science graduate sitting a Diploma-level paper. You already know most of this syllabus at a depth *above* what is asked.**

Operating systems, process scheduling, memory management, UNIX/Linux, DBMS and SQL, E-R modelling, computer networks, OSI, TCP/IP, C programming, algorithms, flowcharts, number systems, computer organisation — all of it you have studied at degree level. For those units your job is **not learning, it is recall-refresh and format-drilling**: reminding yourself of the standard textbook phrasing, the standard diagrams, and the standard comparison tables, so that you can produce a clean 5-mark answer in 8 minutes instead of a rambling one in 20.

> ### The real risk is elsewhere.
>
> The Diploma syllabus contains two large blocks that a B.Tech CS graduate has very plausibly **never formally studied**, because they are computer-*literacy* content, not computer-*science* content:
>
> **1. MS Office in detail — Word, Excel, PowerPoint, Access (Paper-I §8).**
> The syllabus is explicit and product-specific: DropCap, WordArt, callouts and captions, footnote vs endnote, tabs/borders/shading, multiple columns, **Mail Merge**, Excel function *categories*, chart components and 3-D charts, PowerPoint *views*, design templates, transition effects and action buttons, Access database planning, forms, queries, reports. This is menu-level, feature-level knowledge. You cannot derive it from first principles. You have to *learn* it.
>
> **2. MS-DOS (Paper-II §1).**
> Booting sequence, system files (IO.SYS, MSDOS.SYS, COMMAND.COM), internal vs external commands, the exact syntax and switches of DIR / COPY / XCOPY / ATTRIB / CHKDSK, and the meaning and difference between **.BAT, .EXE and .COM** files. Again: pure recall, nothing derivable.
>
> **These two blocks are in `CSDip_02_MSOffice_and_DOS.md` and must get a disproportionate share of your study time — plan on roughly 25–30% of total hours for what is maybe 15% of the syllabus.** They are also disproportionately represented in MCQs, because they generate easy single-fact questions.

### Second-tier risk (do not ignore, but do not panic)

| Risk area | Why it is a risk | Where |
|---|---|---|
| **Motherboard component detail** | A degree course teaches architecture, not "which connector has 34 pins" or "what colour is the PS/2 mouse port". Highly examinable, purely factual. | `CSDip_01_HardwareAndDevices.md` §9 |
| **Legacy storage-device facts** | Floppy capacities, CD/DVD capacities, CD 1x = 150 KB/s, IDE master/slave, EPROM UV erase. You may have skipped these entirely. | `CSDip_01` §8 |
| **Legacy protocols: NetBEUI, IPX/SPX** | Named in the syllabus, absent from modern degree courses. Learn the one-line description of each. | `CSDip_03` (networks pointer file) + `CORE_05` |
| **Dial-up / ISDN / VSAT / leased line** | Internet-connectivity types are examinable and dated. | `CSDip_03` |
| **Virus taxonomy in the syllabus's own words** | "Command processor infection", "file-specific infection" — that is 1990s vocabulary, not modern malware taxonomy. Learn *their* categories. | `CSDip_05_Viruses.md` |

### Consequence for how you allocate the 24 days

```
   Effort you need per unit of syllabus:

   MS Office / MS-DOS        ##############################   (learn from scratch)
   Motherboard / storage     ####################             (learn the facts)
   Viruses / Internet types  #############                    (learn vocabulary)
   Networks / OS / DBMS      ######                           (refresh + format drill)
   C programming / SAD       ####                             (refresh only)
   UNIX commands             #####                            (refresh + memorise switches)
```

---

## 3. Syllabus checklist — Paper-I

Tick a box only when you can (a) write a 5-mark answer from memory and (b) get 8/10 on a self-quiz of its facts.

> **Filename note:** `CORE_xx_*.md` files are the shared-core notes being written into `Materials\_Shared\`. The names below are the *conventional* ones. **Confirm the exact filenames by listing `C:\Users\hp\Desktop\prep\Materials\_Shared\` before you go looking for them.**

| Unit | Topic | Where the notes are | Depth needed | Done |
|---|---|---|---|---|
| **§1.1** | Generations of computers (1st → 5th) | `CSDip_01_HardwareAndDevices.md` §1 | Full table, memorise examples | - [ ] |
| **§1.2** | Classification: super / mainframe / mini / workstation / micro | `CSDip_01` §2 | Comparison table + examples | - [ ] |
| **§1.3a** | Bit, byte, nibble, word; KB/MB/GB/TB | `CSDip_01` §3 | Memorise, MCQ-critical | - [ ] |
| **§1.3b** | BCD, ASCII, EBCDIC, Unicode | `CSDip_01` §3 | Memorise code points | - [ ] |
| **§1.3c** | Number systems + all conversions | `CSDip_01` §4 · deeper: `CORE_01_DigitalLogic.md` | **Must be fast and error-free** | - [ ] |
| **§1.3d** | Binary arithmetic; 1's and 2's complement | `CSDip_01` §4 · `CORE_01_DigitalLogic.md` | Fully worked both directions | - [ ] |
| **§1.4** | Functional block diagram; input/output/CPU/ALU/CU/mass storage | `CSDip_01` §5 · deeper: `CORE_02_ComputerOrganisation.md` | Hand-drawable diagram | - [ ] |
| **§2a** | Input devices: keyboard, mouse, scanner, OCR, bar-code | `CSDip_01` §6 | Detail + OCR/OMR/MICR table | - [ ] |
| **§2b** | Output: monitors CRT vs LCD; printers DMP/inkjet/laser; plotters | `CSDip_01` §7 | Comparison tables, working of each | - [ ] |
| **§3a** | ROM / PROM / EPROM / EEPROM / Flash | `CSDip_01` §8 | Comparison table | - [ ] |
| **§3b** | Registers, cache, RAM; capacity/speed comparison | `CSDip_01` §8 · `CORE_02_ComputerOrganisation.md` | Memory hierarchy pyramid | - [ ] |
| **§3c** | SRAM vs DRAM; SDRAM vs DDR | `CSDip_01` §8 | Two comparison tables | - [ ] |
| **§3d** | Magnetic: floppy, hard disk, organisation, drive interfaces | `CSDip_01` §8 | Capacity + access-time sums | - [ ] |
| **§3e** | Optical: CD/DVD read and write mechanism | `CSDip_01` §8 | Pits/lands, laser wavelengths | - [ ] |
| **§4** | Motherboard: MCH (bus, socket, DIMM, AGP), ICH (IDE, PCI, serial/parallel, PS/2, USB), BIOS ROM, CMOS battery, RTC, SMPS | `CSDip_01` §9 | **High detail — hand-drawable labelled diagram** | - [ ] |
| **§5** | Networks: LAN/MAN/WAN, transmission modes, media, topologies, architectures, devices, OSI, TCP/IP, NetBEUI, IPX/SPX, IEEE | `CSDip_03_Networks_and_Internet.md` (Diploma angle) · main: `CORE_05_ComputerNetworks.md` | Refresh; learn legacy protocols | - [ ] |
| **§6** | Internet technology: intranet/internet, email, chat, BBS, video-conf, FTP, Telnet, WWW, browsers, search engines, ISP, dial-up/leased/ISDN/VSAT | `CSDip_03_Networks_and_Internet.md` | Learn connectivity types cold | - [ ] |
| **§7** | Computer languages: analogy with natural language, characteristics of a good language, machine/assembly/high-level | `CSDip_04_Languages_and_Software.md` | Light — one solid 5-marker | - [ ] |
| **§8a** | Hardware–software relationship; classification; system vs application software; compiler vs interpreter | `CSDip_04_Languages_and_Software.md` · `CORE_03_OperatingSystems.md` | Refresh | - [ ] |
| **§8b** | **MS WORD in detail** | `CSDip_02_MSOffice_and_DOS.md` | **HIGH — learn from scratch** | - [ ] |
| **§8c** | **MS EXCEL in detail** | `CSDip_02_MSOffice_and_DOS.md` | **HIGH — learn from scratch** | - [ ] |
| **§8d** | **MS POWERPOINT in detail** | `CSDip_02_MSOffice_and_DOS.md` | **HIGH — learn from scratch** | - [ ] |
| **§8e** | **MS ACCESS in detail** | `CSDip_02_MSOffice_and_DOS.md` | **HIGH — learn from scratch** | - [ ] |
| **§9** | Computer viruses: types, protection, recognition, removal | `CSDip_05_Viruses.md` | Learn the syllabus's own taxonomy | - [ ] |

---

## 4. Syllabus checklist — Paper-II

| Unit | Topic | Where the notes are | Depth needed | Done |
|---|---|---|---|---|
| **§1a** | OS: definition, functions, evolution (sequential, batch, multiprogramming, multiprocessing, real-time, multitasking) | `CORE_03_OperatingSystems.md` | Refresh only | - [ ] |
| **§1b** | Process concept | `CORE_03_OperatingSystems.md` | Refresh only | - [ ] |
| **§1c** | CPU scheduling: FCFS, SJF, Priority, Round Robin, multiprocessor | `CORE_03_OperatingSystems.md` | **Drill Gantt-chart sums** | - [ ] |
| **§1d** | Memory management | `CORE_03_OperatingSystems.md` | Refresh; paging/segmentation is a 15-marker | - [ ] |
| **§1e** | I/O systems and mass storage structure | `CORE_03_OperatingSystems.md` · `CSDip_01` §8 | Refresh + disk scheduling | - [ ] |
| **§1f** | **MS-DOS**: features, booting, system files, BIOS, files & directories, internal vs external commands, BAT/EXE/COM | `CSDip_02_MSOffice_and_DOS.md` | **HIGH — learn from scratch** | - [ ] |
| **§1g** | **Windows OS**: window handling, folder/file management, Accessories (Notepad/WordPad/Paint), version overview | `CSDip_02_MSOffice_and_DOS.md` | Medium — product facts | - [ ] |
| **§2a** | UNIX history, features, structure (kernel/shell/utilities), hardware requirements | `CORE_04_UnixLinux.md` | Refresh | - [ ] |
| **§2b** | Startup/shutdown, booting stages, login, password, `who`, `who am i`, `tty`, `date`, `cal` | `CORE_04_UnixLinux.md` | Memorise exact commands | - [ ] |
| **§2c** | File concept, file types, hierarchical directory structure, file system structure | `CORE_04_UnixLinux.md` | Refresh | - [ ] |
| **§2d** | File/dir commands: `cat`, `cp`, `mkdir`, `cd`, `rm`, `rmdir` | `CORE_04_UnixLinux.md` | Memorise switches | - [ ] |
| **§2e** | File processing: `wc head tail cut paste join split sort grep egrep tr comm cmp diff more less` | `CORE_04_UnixLinux.md` | **Memorise — high MCQ yield** | - [ ] |
| **§2f** | Formatting/printing `pr`, `lp`; help `man`, `help`; maths `bc expr factor units`; comms `write mail wall` | `CORE_04_UnixLinux.md` | Memorise — easily forgotten | - [ ] |
| **§3a** | Data vs information, database, DBMS, DBA, functions of DBMS | `CORE_06_DBMS_SQL.md` | Refresh | - [ ] |
| **§3b** | Relational model, base tables and views, optimisation | `CORE_06_DBMS_SQL.md` | Refresh | - [ ] |
| **§3c** | Relational data objects: domains, relations, kinds of relations, predicates | `CORE_06_DBMS_SQL.md` | Refresh (Date-style vocabulary) | - [ ] |
| **§3d** | E/R model and E/R diagrams | `CORE_06_DBMS_SQL.md` | Must be able to draw one | - [ ] |
| **§3e** | SQL: DDL, DML, retrieval, update, table/conditional/scalar expressions, embedded SQL | `CORE_06_DBMS_SQL.md` | Refresh; embedded SQL is the weak spot | - [ ] |
| **§3f** | Database security: authentication, authorisation, access control, enforcement | `CORE_06_DBMS_SQL.md` | Refresh | - [ ] |
| **§4a** | System concept: definition, characteristics, elements | `CORE_07_SoftwareEngineering.md` · `CSDip_06_SystemAnalysisDesign.md` | Learn the SAD vocabulary | - [ ] |
| **§4b** | System types: physical, abstract, open, closed; information systems | `CSDip_06_SystemAnalysisDesign.md` | Learn — not in a CS degree | - [ ] |
| **§4c** | SDLC phases; role of the system analyst; failure factors | `CORE_07_SoftwareEngineering.md` | Refresh; failure factors is a 10-marker | - [ ] |
| **§5a** | C history and features; algorithms; flowcharts; structured programming | `CORE_09_Programming_C_CPP.md` | Refresh; practise drawing flowcharts | - [ ] |
| **§5b** | Character set, operators, variables, constants, data types, conversion, keywords, operator hierarchy | `CORE_09_Programming_C_CPP.md` | **Memorise precedence table** | - [ ] |
| **§5c** | I/O: program structure, `printf`, `scanf`, `getchar`, `putchar`, `getch`, `putch`, conversion specifiers, math library | `CORE_09_Programming_C_CPP.md` | Refresh; MCQ output-prediction drill | - [ ] |
| **§5d** | Control: `goto`, `if`, `if-else`, nested `if`, `switch-case` | `CORE_09_Programming_C_CPP.md` | Refresh | - [ ] |
| **§5e** | Loops: `for`, `while`, `do-while`, `break`, `continue` | `CORE_09_Programming_C_CPP.md` | Refresh | - [ ] |
| **§5f** | Arrays, functions, pointers, structures, file handling | `CORE_09_Programming_C_CPP.md` · `CORE_08_DataStructures.md` | Refresh; be ready to *write* code | - [ ] |

---

## 5. What the exam actually asks

### An important caveat, stated first

The solved papers available to us — CTSE 2025 Paper-I, Paper-II and MCQ, in `C:\Users\hp\Desktop\prep\_raw\existing_txt\` — are for the **CS (Degree) elective, not the Diploma elective.** Use them for **style, format, tone, marking pattern and difficulty calibration.** Do **not** use them as a content guide for Diploma. The Diploma paper will be:

- **Less theoretically demanding** — no compiler phases, no NP-completeness, no machine learning, no asymptotic analysis, no advanced algorithm-design paradigms.
- **More factual and product-specific** — expect questions naming *products and parts*: "What is Mail Merge and what are its steps?", "Differentiate between internal and external DOS commands", "Explain the components of a motherboard", "Compare Dot Matrix, Inkjet and Laser printers".
- **More diagram-and-table-driven** — hardware block diagrams, printer/monitor comparisons, memory hierarchy, OSI layers, E-R diagrams, flowcharts.

So: same exam-writing craft, different centre of gravity.

### The observed 2025 question pattern (Degree papers — style calibration)

**Character of the questions:** plainly worded, textbook-standard, *not* tricky. There are no puzzle questions and no trap phrasing. Almost every question is of the form "Explain X", "Differentiate between X and Y", "Describe the working of X", "Write a program to do X". If you know the topic, the question does not stand between you and the marks.

**Section A (5 marks) — the shape:** a single concept, defined and briefly elaborated. Real 2025 examples: *"What are the basic functional units of a computer system? Briefly explain the role of each."* · *"Differentiate between an algorithm and a flowchart."* · *"What are the key differences between a stack and a queue?"* · *"Define the Big-Oh notation."* · *"What is Boolean algebra? Mention its basic operators."* · *"What is the role of a linker?"* · *"Differentiate between a primary key and a foreign key."* · *"List the seven layers of the OSI model."* · *"Differentiate between TCP and UDP."*

Note the pattern: **roughly half of all 5-markers are "differentiate between A and B".** That is a gift, because a two-column table answers it perfectly and fast. Build a table for every A-vs-B pair in your syllabus and you have pre-answered half of Section A.

**Section B (10 marks) — the shape:** a mechanism explained, or a procedure applied with an example, or a short piece of code with reasoning. Real 2025 examples: *"Write a C/C++ function to reverse an array. Explain the logic."* · *"Explain the working principle of Quick Sort. What are its average and worst-case complexities?"* · *"Describe the levels of memory organization and the purpose of the memory hierarchy."* · *"Explain Round Robin scheduling with an example."* · *"Compare the different network topologies."* · *"Design a combinational circuit for a 2-bit binary adder and draw the logic diagram."*

Note: **10-markers usually want a worked example or a diagram, not just prose.** An answer with a Gantt chart, a table, or a labelled figure outscores the same content written as paragraphs.

**Section C (15 marks) — the shape:** a broad topic requiring structure — phases, stages, a full comparison, or a design walked through end to end. Real 2025 examples: *"Explain the design and working of a JK flip-flop and how it can implement other flip-flops."* · *"Describe and compare divide-and-conquer and greedy paradigms with a concrete example of each."* · *"Elaborate on the different phases of a compiler, giving the primary task and output of each phase."* · *"Discuss memory management including paging and segmentation."* · *"Discuss the steps in query processing and why optimization matters."*

Note: **15-markers reward organisation over volume.** Almost all of them decompose into a numbered list of phases/types/steps, each of which gets a short paragraph and where possible a diagram. Write the numbered skeleton first, then fill.

**Diploma translation of these shapes** — expect Section C questions like: *"Explain in detail the components of a motherboard with a labelled diagram."* · *"Describe the read and write mechanism of a CD and a DVD."* · *"Explain the features of MS Excel. Discuss the types of functions and the components of a chart."* · *"Discuss the types of computer viruses, how to recognise an infection and how to deal with it."* · *"Explain the seven layers of the OSI reference model with the function of each."*

### MCQ pattern

Four options, single correct answer. "All of the above" appears occasionally but is not abused. Difficulty is mostly **recall and one-step reasoning**: *"Which register holds the address of the next instruction to be executed?"* · *"What is the output of `printf("%d", 5/2);`?"* · *"Which header file is required for `malloc()`?"* · *"What does the `volatile` keyword signify?"* A handful of questions each year are genuinely ambiguous or badly worded — recognise them, take your best elimination, and move on without burning time.

The 2025 Degree topic spread was roughly: Q1–30 programming/DS/algorithms · Q31–50 digital logic + architecture + system software · Q51–67 OS + software engineering · Q68–76 DBMS · Q77–89 networks + web · Q90–100 AI/ML.

**Expected Diploma spread (extrapolated — treat as a planning estimate, not a fact):** a much larger hardware/devices/motherboard/storage block, a substantial MS Office and DOS block, C programming, OS, UNIX commands, DBMS, networks, and viruses. The AI/ML block disappears entirely. **Plan on 20–30 questions being pure hardware/Office/DOS factual recall** — which is exactly the material you are weakest on and exactly why `CSDip_01` and `CSDip_02` deserve the time.

---

## 6. Recommended study order

The order is chosen on one principle: **learn what you don't know first, while you still have time to forget it and re-learn it.** Refresh material can be compressed into the final week; genuinely new material cannot.

1. **MS Office (Word → Excel → PowerPoint → Access)** — largest genuinely-new block, and it needs two exposures spaced apart.
2. **MS-DOS + Windows OS basics** — second genuinely-new block, small enough to finish in a day and a half.
3. **Hardware: motherboard, storage devices, I/O devices, generations/classification** — factual, dense, high MCQ yield.
4. **Number systems and binary arithmetic** — you know this, but it must be *fast and error-free* under time pressure. Drill, don't read.
5. **Viruses, Internet technology, computer languages, System Analysis & Design** — small vocabulary-heavy units, cheap marks.
6. **Networks (Paper-I §5,6)** — refresh from `CORE_05`, add the legacy protocol facts.
7. **OS + UNIX (Paper-II §1,2)** — refresh from `CORE_03`/`CORE_04`, drill scheduling sums and command switches.
8. **DBMS + SQL (Paper-II §3)** — refresh from `CORE_06`.
9. **C programming (Paper-II §5)** — refresh from `CORE_09`, drill output-prediction MCQs.
10. **Consolidation:** mock MCQs, full-length descriptive rehearsals, then revision only.

**Ratio to aim for across the 24 days:** ~40% new material (Office/DOS/hardware), ~30% refresh, ~30% drill and mock. If you find yourself re-reading OS notes you already understand while MS Access remains untouched, you are losing the exam.

---

## 7. Day-by-day plan, 5–30 September

Budget: **3–4 hours per day**, split as roughly 2–2.5 hrs new/refresh material and 1–1.5 hrs drill (MCQs, past-question writing, flashcards). Adjust for your actual working day, but keep the *shape*: new material front, drill throughout, revision-only at the end.

### Week 1 — the unknown material (5–11 Sept)

| Date | Day | Main block (2–2.5 hrs) | Drill block (1–1.5 hrs) |
|---|---|---|---|
| **Fri 5 Sept** | 1 | Read this overview fully. List `Materials\_Shared\` and confirm CORE filenames. Start `CSDip_02` — **MS Word**: components of the window, creating/editing, formatting, symbols/picture/WordArt | Write out the Word window parts from memory |
| **Sat 6 Sept** | 2 | **MS Word** continued: tabs/borders/shading, header/footer, footnote vs endnote, shapes, text box/callouts/captions, tables | Self-quiz: 25 Word facts |
| **Sun 7 Sept** | 3 | **MS Word** finish: autocorrect, spelling & grammar, DropCap, multiple columns, **Mail Merge (steps in order — high-value 10-marker)** | Write a full 10-mark answer on Mail Merge, timed 17 min |
| **Mon 8 Sept** | 4 | **MS Excel**: features, window components, workbook vs worksheet, cell referencing (relative/absolute/mixed), formatting and editing | Practise 15 formula/reference MCQs |
| **Tue 9 Sept** | 5 | **MS Excel**: formulas, the function categories (math, statistical, logical, text, date/time, lookup, financial) with examples of each | Memorise 20 named functions and their arguments |
| **Wed 10 Sept** | 6 | **MS Excel**: sharing and managing data, sorting/filtering; **charts — components (plot area, axes, legend, data series, gridlines, data labels), chart types, 3-D charts** | Sketch and label a chart from memory; 15 MCQs |
| **Thu 11 Sept** | 7 | **MS PowerPoint**: components, **views (Normal, Slide Sorter, Notes Page, Reading, Slide Show, Outline)**, design templates, new presentation, title slide, formatting | Self-quiz: views and what each is for |

### Week 2 — finish new material, start hardware (12–18 Sept)

| Date | Day | Main block | Drill block |
|---|---|---|---|
| **Fri 12 Sept** | 8 | **MS PowerPoint** finish: transition effects, action buttons, custom animation. Then start **MS Access**: database planning, creating a database, tables and field data types | 20 mixed Office MCQs |
| **Sat 13 Sept** | 9 | **MS Access**: adding records, **querying (select, parameter, action queries)**, forms, reports, relationships | Write a 15-mark answer: "Explain MS Access — planning, tables, queries, forms, reports" |
| **Sun 14 Sept** | 10 | **MS-DOS**: features and characteristics, booting sequence, system files (IO.SYS, MSDOS.SYS, COMMAND.COM), BIOS, file naming (8.3), directory structure | Memorise the boot sequence in order |
| **Mon 15 Sept** | 11 | **MS-DOS**: internal vs external commands (full list, with syntax and key switches), **.BAT vs .EXE vs .COM**. Then **Windows**: window operations, file/folder management, Notepad/WordPad/Paint, version overview | Write out the internal-command list from memory; 20 DOS MCQs |
| **Tue 16 Sept** | 12 | **`CSDip_01` §1–§3**: generations, classification, data representation, BCD/ASCII/EBCDIC/Unicode | Memorise ASCII code points and the generations table |
| **Wed 17 Sept** | 13 | **`CSDip_01` §4**: number systems, all conversions, binary arithmetic, 1's and 2's complement | **40 conversion problems, timed.** Target: 30 seconds each |
| **Thu 18 Sept** | 14 | **`CSDip_01` §5–§7**: functional block diagram, input devices, output devices (CRT vs LCD, printers, plotters) | Draw the block diagram and the printer comparison table from memory |

### Week 3 — hardware detail + core refresh (19–25 Sept)

| Date | Day | Main block | Drill block |
|---|---|---|---|
| **Fri 19 Sept** | 15 | **`CSDip_01` §8**: memory hierarchy, SRAM/DRAM, SDRAM/DDR, ROM family, floppy, hard disk in detail, interfaces, SSD | Do the disk capacity and access-time worked sums yourself |
| **Sat 20 Sept** | 16 | **`CSDip_01` §8** optical storage + **§9 motherboard in full detail** | **Hand-draw the labelled motherboard diagram three times** |
| **Sun 21 Sept** | 17 | **`CSDip_05` viruses** + **`CSDip_04` languages and software** + **`CSDip_06` System Analysis & Design** | 25 mixed MCQs; write two 5-mark answers timed |
| **Mon 22 Sept** | 18 | **Networks refresh** — `CORE_05` + `CSDip_03`: LAN/MAN/WAN, modes, media, topologies, devices, OSI, TCP/IP, NetBEUI, IPX/SPX, IEEE 802.x | Draw all topologies + the OSI table from memory |
| **Tue 23 Sept** | 19 | **Internet technology** (`CSDip_03`) + **OS refresh** (`CORE_03`): functions, evolution, process concept, scheduling | **Work 6 scheduling problems** (FCFS/SJF/Priority/RR) with Gantt charts |
| **Wed 24 Sept** | 20 | **OS**: memory management, paging, segmentation, I/O and mass storage. **UNIX refresh** (`CORE_04`): structure, boot, login, file commands | Memorise the file-processing command list with switches |
| **Thu 25 Sept** | 21 | **UNIX** finish (processing, formatting, help, maths, communication commands) + **DBMS refresh** (`CORE_06`): model, E-R, SQL, security | Draw one E-R diagram; write 10 SQL queries |

### Week 4 — mocks and revision only (26–30 Sept)

| Date | Day | Plan |
|---|---|---|
| **Fri 26 Sept** | 22 | **C programming refresh** (`CORE_09`) in the morning: operators and precedence, I/O, control, loops, arrays, functions, pointers. Afternoon: **full-length mock MCQ, 100 Q in 2 hrs, strictly timed, negative marking applied.** Score it honestly and list every topic you got wrong. |
| **Sat 27 Sept** | 23 | **REVISION ONLY.** Morning: attempt a **full 3-hour Paper-I mock** you construct from the syllabus + this file's "likely exam questions" lists. Afternoon: fix the gaps the MCQ mock exposed. No new topics from here on. |
| **Sun 28 Sept** | 24 | **REVISION ONLY.** Morning: **full 3-hour Paper-II mock.** Afternoon: re-read `CSDip_02` (Office/DOS) end to end — this is the material that decays fastest. Evening: the "Numbers you must memorise" tables from `CSDip_01`. Sleep early. |
| **Mon 29 Sept** | 25 | Morning: light skim of Paper-I material only — diagrams, tables, the motherboard figure, printer/monitor comparisons, number-system rules. **Do not learn anything new.** **1–4 pm: PAPER-I.** Evening: eat, 30-min skim of Paper-II Section-C topics, sleep by 10 pm. |
| **Tue 30 Sept** | 26 | **9 am–12 noon: PAPER-II.** Lunch, walk, do not post-mortem the paper. **1–3 pm: TECHNICAL MCQ.** |

### Non-negotiables in this plan

- **The last three days (27, 28, 29 Sept) are revision only.** No new topic after 26 Sept. Late-learned material is unreliable under exam stress and displaces things you already know.
- **Two full-length mocks minimum**, at least one of them the MCQ under real time and real negative marking.
- **Rehearse the 30 Sept double-day at least once**: a 3-hour writing session followed by a 2-hour MCQ with a one-hour break. Writing for three hours by hand is a physical skill; discover the hand cramp on a practice day, not on exam day.
- If you slip behind, **cut refresh days (18–21, 23–26), never the Office/DOS days.** You can bluff a familiar topic; you cannot bluff Mail Merge.

---

## 8. Exam-day tactics

### 8.1 The descriptive papers — using the choice

**The first five minutes decide the paper.** Do not start writing at minute zero.

1. **Read every question in all three sections first (4–5 minutes).** You are not reading to answer; you are reading to *select*.
2. **Mark each question A / B / C:** A = "I can write this cold", B = "I know most of it", C = "no". Then choose: 8 of 10 in Section A, 3 of 5 in Section B, 2 of 4 in Section C. Pick your strongest, and **write those first regardless of question order** — number your answers clearly and the examiner will follow.
3. **Never attempt more than the required number.** Extras are not credited and they steal minutes from the answers that are.
4. **Answer Section A first.** It is 40 marks of low-risk, fast-scoring content, and finishing it builds momentum and banks marks before fatigue sets in.

### 8.2 Time budget — the arithmetic

3 hours = **180 minutes for 100 marks ≈ 1.7 minutes per mark.** Hold back a buffer and the working numbers are:

| Question type | Count | Minutes each | Subtotal |
|---|---|---|---|
| Section A, 5 marks | 8 | **8 min** | 64 min |
| Section B, 10 marks | 3 | **17 min** | 51 min |
| Section C, 15 marks | 2 | **25 min** | 50 min |
| Reading and selecting | — | — | 5 min |
| **Buffer / review** | — | — | **~10–15 min** |
| | | **Total** | **180 min** |

**Enforce the clock, not the answer.** Write the finish-time for each answer in the margin before you start it. When the time is up, finish the sentence and move on — an unfinished 15-marker still earns most of its marks, but an unstarted one earns zero. **The single most common way to lose 20 marks in this format is over-writing an early answer.**

Rough length guide at normal handwriting speed: **5 marks ≈ 3/4 to 1 page**, **10 marks ≈ 1.5–2 pages**, **15 marks ≈ 2.5–3 pages**. More than that is not more marks; it is less time.

### 8.3 How to structure an answer for maximum marks

- **Lead with a one-line definition.** Examiners look for it and it anchors the answer.
- **Then a labelled diagram or a table if the topic admits one.** For this Diploma syllabus, most topics do. Diagrams and tables score fast and read well.
- **Then numbered points, not paragraphs.** "Differentiate" questions → always a two-column table. "Phases/types/steps" questions → always a numbered list.
- **Close with one line of application** ("hence used in ...") — cheap, and it signals understanding.
- **Underline key terms.** Use a ruler for diagram boxes if you have one. Presentation genuinely moves marks in hand-marked papers.
- If you are running short on the last question, **write the skeleton in bullet points rather than nothing** — partial structure earns partial credit.

### 8.4 The MCQ — the guessing arithmetic

Marking: **+2 correct, −0.667 wrong, 0 unattempted.** Work out the expected value (EV) before you sit down:

| Situation | Probability of correct | Expected value per question |
|---|---|---|
| You know it | 1.0 | **+2.0** |
| 1 option eliminated (3 remain) | 1/3 | (1/3)(+2) + (2/3)(−0.667) = **+0.22** |
| 2 options eliminated (2 remain) | 1/2 | (0.5)(+2) + (0.5)(−0.667) = **+0.67** |
| Blind guess (4 options) | 1/4 | (0.25)(+2) + (0.75)(−0.667) = **0.00** |
| Leave blank | — | **0.00** |

**Read that table carefully, because it dictates your whole MCQ strategy:**

- **Blind 1-in-4 guessing is exactly break-even — EV = 0.** One-third negative marking on a four-option paper is precisely calibrated to make random guessing pointless. It neither helps nor hurts on average, but it adds variance for no expected gain. **So do not blind-guess; there is nothing in it.**
- **Eliminate even ONE option and guessing becomes positive (+0.22).** Eliminate two and it is strongly positive (+0.67) — a third of a real mark, which over 20 such questions is +13 marks. **Rule: if you can rule out at least one option, always answer.**
- Practical consequence: **there is almost no question you should leave blank**, because on a factual paper you can nearly always eliminate at least one absurd option. The blanks should be only the handful where all four options look equally plausible and you have no basis at all.

### 8.5 MCQ time and sequencing

120 minutes for 100 questions = **1.2 minutes per question**, but the real distribution is bimodal: most take 20–30 seconds, a few take three minutes.

- **Pass 1 (~50 min):** answer everything you know instantly. Mark the rest with a symbol — `?` for "can work it out", `??` for "guess territory". Never stall on pass 1.
- **Pass 2 (~45 min):** work the `?` questions — calculations, conversions, output prediction.
- **Pass 3 (~20 min):** the `??` questions. Eliminate what you can, then apply the rule in §8.4.
- **Final 5 min:** verify the OMR/answer sheet — that your marks correspond to the right question numbers. **A one-row shift on an OMR sheet is the single most expensive error possible in this exam.** Check at question 25, 50 and 75, not just at the end.
- Number-system conversions and C output questions are the ones worth slowing down for: they are fully determinable, so a careful 90 seconds converts directly into +2.

### 8.6 The 30 September double day

- Paper-II ends at 12 noon; the MCQ starts at 1 pm. **Plan the hour**: a light meal (nothing heavy — you do not want a post-lunch dip in a 2-hour recall test), water, a short walk, and **no post-mortem of Paper-II with other candidates.** Rehashing a paper you cannot change is the fastest way to sabotage the next one.
- Carry: extra pens (at least three of the same ink), a pencil and eraser for OMR if required, ruler, a watch, admit card and ID, water.
- Sleep on 28 and 29 September matters more than any revision you could do in those hours.

---

## 9. File index for this folder

`C:\Users\hp\Desktop\prep\Materials\ComputerScience_Diploma\`

| File | What it covers |
|---|---|
| **`CSDip_00_OVERVIEW.md`** | *(this file)* Exam dates and countdown, structure and marking, the strategic insight, the full syllabus checklist, question-pattern analysis, the 24-day study plan, and exam-day tactics. |
| **`CSDip_01_HardwareAndDevices.md`** | Paper-I §1–§4. Generations and classification of computers; data representation and coding schemes; number systems, conversions and binary arithmetic with complements; functional block diagram; input devices; output devices; storage devices; components of the motherboard in full detail. The most MCQ-dense file in the set. |
| **`CSDip_02_MSOffice_and_DOS.md`** | Paper-I §8 and Paper-II §1 (DOS/Windows portion). MS Word, Excel, PowerPoint and Access feature by feature; MS-DOS features, booting, system files, internal and external commands, BAT/EXE/COM; Windows window and file management, Accessories, version history. **Your highest-priority file — the material you are least likely to already know.** |
| **`CSDip_03_Networks_and_Internet.md`** | Paper-I §5 and §6, at Diploma depth. LAN/MAN/WAN, transmission modes and media, topologies, peer-to-peer vs client-server, connectivity devices, OSI and TCP/IP, legacy protocols (NetBEUI, IPX/SPX), IEEE standards; Internet and intranet services, WWW, browsers and search engines, ISP and connection types (dial-up, leased line, ISDN, VSAT). Points to `CORE_05_ComputerNetworks.md` for the deep treatment. |
| **`CSDip_04_Languages_and_Software.md`** | Paper-I §7 and §8a. Computer languages and the natural-language analogy, characteristics of a good language, machine/assembly/high-level classification; hardware–software relationship, software classification, system vs application software, compilers vs interpreters vs assemblers. |
| **`CSDip_05_Viruses.md`** | Paper-I §9. Virus definition and life cycle; the syllabus's own taxonomy (command-processor, boot-sector, executable-file, file-specific, memory-resident, macro); worms/trojans/other malware for contrast; protecting the PC, recognising an infection, dealing with an infection. |
| **`CSDip_06_SystemAnalysisDesign.md`** | Paper-II §4. System concept, characteristics and elements; physical/abstract/open/closed systems; information systems; SDLC phases at Diploma depth; role of the system analyst; factors causing failure. Points to `CORE_07_SoftwareEngineering.md`. |

### Shared-core files referenced from here

Located in `C:\Users\hp\Desktop\prep\Materials\_Shared\`. **Confirm the exact filenames by listing that directory** — the names below are the conventional references used throughout these notes.

| Reference | Covers | Used by Diploma units |
|---|---|---|
| `CORE_01_DigitalLogic.md` | Number systems, Boolean algebra, K-maps, flip-flops, counters, combinational/sequential design | P-I §1.3 |
| `CORE_02_ComputerOrganisation.md` | CPU design, addressing modes, memory hierarchy, cache, I/O, DMA | P-I §1.4, §3, §4 |
| `CORE_03_OperatingSystems.md` | Processes, scheduling, memory management, file systems, deadlock, security | P-II §1 |
| `CORE_04_UnixLinux.md` | UNIX/Linux structure, shell, commands | P-II §2 |
| `CORE_05_ComputerNetworks.md` | Topologies, media, OSI/TCP-IP, devices, routing, IP addressing | P-I §5, §6 |
| `CORE_06_DBMS_SQL.md` | Data models, E-R, normalisation, SQL, transactions, security | P-II §3 |
| `CORE_07_SoftwareEngineering.md` | SDLC, process models, estimation, testing, QA | P-II §4 |
| `CORE_08_DataStructures.md` | Array, stack, queue, linked list, tree, graph, hashing, sorting, searching | P-II §5f (supporting) |
| `CORE_09_Programming_C_CPP.md` | C/C++ syntax, pointers, arrays, functions, OOP | P-II §5 |

### Other reference locations

| Path | Contents |
|---|---|
| `C:\Users\hp\Desktop\prep\Materials\_Shared\OFFICIAL_SYLLABUS.md` | The ground-truth syllabus and exam pattern. Section 4 is CS Diploma; Section 5 is the overlap table. |
| `C:\Users\hp\Desktop\prep\_raw\existing_txt\` | CTSE 2025 solved Paper-I / Paper-II / MCQ and concept notes — **Degree elective**, used for style calibration only. Read-only. |
| `C:\Users\hp\Desktop\prep\PYQ\` | Past-year question papers. Read-only. |

---

## One-paragraph summary, if you read nothing else

You have 24 days to your first technical exam. You already know most of this Diploma syllabus better than it is asked. The two things that can actually cost you marks are **MS Office** and **MS-DOS**, with motherboard detail and legacy storage facts close behind — so spend the first two weeks there, refresh the familiar core in week three, and reserve 27–29 September for revision and mocks only. In the descriptive papers, read everything first, use the choice ruthlessly, and enforce 8/17/25 minutes per question. In the MCQ, never blind-guess but always answer once you have eliminated one option. Then go and do it again for the Degree papers on 10 and 12 October, with all the shared core already in your head.
