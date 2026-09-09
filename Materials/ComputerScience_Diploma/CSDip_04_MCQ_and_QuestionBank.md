# CS (Diploma) — MCQ Bank and Descriptive Question Bank

> Elective 3: **Computer Science / Computer Engineering (Diploma)**, NPSC CTSE 2026.
> Companion to `CSDip_00_OVERVIEW.md`. This is the **drill** file — the others are the *learning* files.

---

## Why this file matters

Reading notes feels like studying. It mostly isn't. What actually moves your score in the
next three weeks is **retrieval practice** — being asked a question cold and having to
produce the answer without the page in front of you. This file exists so that every study
session can end with 20–30 minutes of that.

Three specific reasons it matters more than usual for *this* exam:

1. **The MCQ is 200 marks — the single biggest component of the elective**, worth as much as
   Paper-I and Paper-II combined times one. And it is almost pure recall. There is no way to
   reason your way to "which DOS file is the command interpreter"; you either know it or you
   don't. Drilling is the only method.
2. **Negative marking of one-third makes *calibration* a skill.** You need to know the
   difference between "I know this", "I can eliminate two options" and "I have no idea",
   because those three states have different correct actions. Practising with the answer key
   covered teaches you that self-awareness. See §1.
3. **The descriptive papers are answered from skeletons, not from prose.** An examiner marking
   500 scripts is looking for the points on their marking scheme. The model answers in §3 and
   §4 are written as *point-lists on purpose* — that is the shape your answer should have on
   the page.

### How to use this file

| When | How |
|---|---|
| After learning a topic | Do the MCQs for just that topic, answer key covered |
| Mid-September | Do 30 mixed MCQs a day, timed at 30 s each |
| 26 September | The full 100-question mock in §2.14, strictly 2 hours, negative marking applied |
| **Any spare hour** | Work the real 2024 papers in `PYQ\_text\CTSE2024_ComputerScience_Diploma_Paper*.txt` — 400 real questions, better than anything synthetic |
| Throughout | Pick 2 descriptive questions a day and write **only the skeleton** in 3 minutes, then compare |
| 27–28 September | Build your mock Paper-I and Paper-II by picking 10 + 5 + 4 questions from §3 / §4 |

> **The rule that matters:** cover the answer, commit to an answer *out loud or on paper*,
> then check. Reading a question and its answer together teaches you nothing — it produces
> the feeling of knowing without the ability to retrieve.

---

## Checklist for this file

- [ ] Read §1 (guessing strategy) **before** the first mock, not during
- [ ] MCQ set A — Hardware, generations, classification (§2.1)
- [ ] MCQ set B — Number systems and data representation (§2.2)
- [ ] MCQ set C — Input / output devices (§2.3)
- [ ] MCQ set D — Storage devices (§2.4)
- [ ] MCQ set E — Motherboard and ports (§2.5)
- [ ] MCQ set F — MS Word (§2.6)
- [ ] MCQ set G — MS Excel (§2.7)
- [ ] MCQ set H — MS PowerPoint and MS Access (§2.8)
- [ ] MCQ set I — MS-DOS and Windows (§2.9)
- [ ] MCQ set J — OS, UNIX (§2.10)
- [ ] MCQ set K — Networks, Internet, viruses (§2.11)
- [ ] MCQ set L — DBMS, SQL, C programming, SAD (§2.12)
- [ ] **MCQ set M — the 2024-calibrated set: networks, Internet, Office 2010, C/C++ (§2.13) — do this one first**
- [ ] Read §0 (the real 2024 paper analysis) and worked through both 2024 `.txt` papers
- [ ] Full 100-question mock assembled and sat under time (§2.14)
- [ ] Paper-I descriptive bank — all 5-markers skeletoned (§3.1)
- [ ] Paper-I 10-markers (§3.2) and 15-markers (§3.3)
- [ ] Paper-II descriptive bank — 5-markers (§4.1), 10-markers (§4.2), 15-markers (§4.3)
- [ ] Two full-length descriptive rehearsals done by hand

---

## 0. CALIBRATION AGAINST THE REAL CTSE 2024 CS (DIPLOMA) PAPERS — read this first

The 2024 papers at `C:\Users\hp\Desktop\prep\PYQ\2024\ComputerScience-Diploma\` have now been
OCR'd successfully into
`C:\Users\hp\Desktop\prep\PYQ\_text\CTSE2024_ComputerScience_Diploma_PaperI.txt` and
`..._PaperII.txt`. **Read them yourself — they are the single most valuable document in your
whole prep folder.** What follows is the analysis, and it changes several assumptions made in
`CSDip_00_OVERVIEW.md`.

### 0.1 ⚠️ The biggest finding: in 2024, BOTH technical papers were 200-question MCQs

Verbatim from the 2024 cover sheets:

> **"(PAPER - 1) COMPUTER SCIENCE (DIPLOMA) … No. of Questions : 200 … Time Allowed : 3 Hours …
> This Question Booklet contains 200 questions. This is an objective type test in which [each]
> question has four responses … All questions carry equal marks of 1 (one) each. There will be
> negative marking of one-third mark for each wrong answer."**

Booklet numbers 430043 (Paper-1) and 440046 (Paper-2), series A, `2024/43` and `2024/44`.

So in 2024 the CS (Diploma) elective was **two 200-question OMR papers of 3 hours each**, with
no descriptive writing at all. The **2026 official pattern PDF**, by contrast, specifies a
100-question × 2-mark MCQ plus two 100-mark **descriptive** papers.

| | CTSE 2024 (actual, Diploma) | CTSE 2026 (official pattern) |
|---|---|---|
| Technical papers | Paper-1 and Paper-2, **both MCQ** | MCQ + Descriptive P-I + Descriptive P-II |
| Questions | 200 each | 100 (MCQ) |
| Marks per question | 1 | 2 |
| Duration | 3 hours each | 2 hrs MCQ, 3 hrs each descriptive |
| Negative marking | **1/3 mark per wrong answer** | **1/3 (i.e. −0.667 on a 2-mark question)** |

**⚠️ What to do with this conflict.** The official 2026 pattern PDF is the governing document
and your admit card will confirm it, so **prepare for the descriptive papers** — that is the
prudent asymmetry, because MCQ preparation is a subset of descriptive preparation but not the
reverse. But recognise two consequences:

1. **The MCQ load may be far heavier than 100 questions.** If 2026 follows 2024's actual
   practice you could face 400 objective questions across two papers. Objective drilling is
   therefore *more* valuable than the overview file assumed, not less.
2. **The negative-marking ratio is identical either way** (one-third), so all the guessing
   arithmetic in §1 holds unchanged.
3. If the paper you open on 29 September turns out to be objective, **do not panic** — the
   content is the same, only the output format differs.

### 0.2 The actual 2024 topic distribution — this is the real gold

Counted from the OCR'd papers. **This is far more reliable than any extrapolation.**

**Paper-1 (2024) — 200 questions:**

| Q range | Topic block | ≈ Count | Share |
|---|---|---|---|
| 1–50 | **Computer networks and data communication** | ~50 | **25%** |
| 51–56 | MS Office (Word, Excel, PowerPoint) — first sprinkle | 6 | 3% |
| 57–72 | Number systems, BCD, ASCII, generations, classification, characteristics of computers | 16 | 8% |
| 73–90 | Input/output devices, registers, memory, storage, software types | 18 | 9% |
| 91–99 | System software, translators, SDLC, flowcharts, OS basics | 9 | 4.5% |
| 100–134 | Registers, buses, **motherboard, chipset, BIOS, beep codes, storage capacities, IDE/SATA/PATA**, and **MS Excel 2010 / MS Word formatting in detail** | ~35 | **17.5%** |
| 135–164 | **Internet technology** — intranet, email, netiquette, spam, Usenet, chat, web forums, video conferencing, web servers, URLs, browsers, **connection types**, search engines, FTP, VoIP | ~30 | **15%** |
| 165–175 | **MS PowerPoint and MS Access in detail** | 11 | 5.5% |
| 176–200 | Software classification, firmware, open source, ALU, machine language, cyber attacks, misc hardware facts, **viruses**, programming-language concepts | ~25 | 12.5% |

**Paper-2 (2024) — 200 questions:**

| Q range | Topic block | ≈ Count | Share |
|---|---|---|---|
| 1–26 | **Operating systems** — definition, modes, multiprogramming, system calls, process states, PCB, scheduling criteria, convoy effect, RR quantum, aging, **an SJF average-waiting-time calculation**, MMU, swapping, paging | 26 | 13% |
| 27–40 | **MS-DOS** (internal/external commands, .bat/.cmd/.btm, .com), CLI vs GUI, hypervisor, **Windows 10** desktop and File Explorer | 14 | 7% |
| 41–80 | **DBMS** — Bachman, transactions, DBMS vs file system, data models, three schema levels, DBA duties, **E-R model** (strong entities, specialization, generalization, aggregation), relational model, intension/extension, entity and referential integrity, **relational algebra**, relational calculus, QBE, QUEL, **SQL DDL/DML**, set operators, audit trail, **database security** (authentication / authorization / access management / accountability), DISTINCT, privileges | 40 | **20%** |
| 81–95 | **System Analysis and Design** — analyst's roles, elements of a system, open/closed/physical/abstract, information systems, CBIS, TPS, OAS, SDLC phases, structured tools (DFD, ERD, STD, RAD), feasibility types, design phase, RAD/DSDM | 15 | 7.5% |
| 96–110 | **UNIX** — virtual consoles, shell, commands, control characters (Ctrl-U/S/Q/D), exit/logout, `$` prompt, X Window, file permissions, `man` | 15 | 7.5% |
| 111–161 | **Programming in C** — features, pseudocode, algorithm properties, flowchart symbols, character sets, IDE, `gcc`, comments, keywords, Turbo-C shortcuts, **expression evaluation**, `%6.2f`, operator precedence, functions, loops, `goto`, valid identifiers, **many output-prediction programs**, arrays, strings, `malloc`/`calloc`, recursion, jump statements | ~51 | **25.5%** |
| 162–200 | **C++ and Object-Oriented Programming, plus Windows GDI graphics programming** — classes, constructors, destructors, inheritance types, pointers, operator overloading, header files, casts, access specifiers, infix→postfix, and **Borland OWL / Windows GDI graphics (TWindow, TFrameWindow, device contexts, R2_ drawing modes)** | ~39 | **19.5%** |

### 0.3 The five things this changes about your study plan

1. **🔴 Networks is the single biggest block in Paper-I — about a quarter of it.** The overview
   file classes networks as "refresh only" (`CORE_05`). That under-rates it badly. 2024 asked
   about line coding (AMI, NRZ, biphase), propagation methods, SONET, piconet, NFC, GPS
   satellite orbits (GEO/LEO/MEO), IGMP, SCTP, port numbers, IPv6 zero-compression, throughput
   vs bandwidth, straight-through cable, W3C/IAB/ISOC/IETF, mesh-link count n(n−1)/2, user
   agents vs MTAs, and NetBEUI/IPX-SPX. **Give `CORE_05_ComputerNetworks.md` full attention,
   not a skim.**
2. **🔴 C++ and OOP appear heavily in Paper-II even though the Diploma syllabus §5 only names
   "Programming in C".** Roughly 39 questions in 2024 — classes, constructors, destructors,
   inheritance, operator overloading, pointers. There was even a block on **Windows GDI
   graphics programming with Borland OWL**, which is in no version of the syllabus. **Do not
   skip C++.** Budget at least two days on OOP and C++ syntax from `CORE_09`.
   ⚠️ verify whether the GDI/OWL block recurs — it may have been a one-off from an old question
   bank. Do not spend more than 30 minutes on it.
3. **🟢 MS Office was confirmed as examinable and product-version-specific.** 2024 asked about
   *MS Excel 2010's* `AGGREGATE()` function, the `Translate` command's menu location, the
   Paste Special dialog, `Ctrl+F1` to collapse the ribbon, the Sunburst chart, PowerPoint 2007
   transition names, the default 4:3 slide ratio, Access 2010's `.accdb` extension and its data
   types. **The overview file was right that this matters — and it is even more version-specific
   than expected.** Learn it from an actual copy of Office if you can open one.
4. **🟢 Motherboard/hardware detail was confirmed** — form factor, north bridge vs south bridge,
   built-in controllers, POST beep codes, BIOS boot step ordering, ATA/SATA/PATA/IDE, DIMM
   slots, storage-capacity matching (CD 640 MB / DVD 4.7 GB / floppy 1.4 MB / Blu-ray ≈ 4× DVD),
   power-supply functions. `CSDip_01` §9 earns its length.
5. **🟡 MS-DOS was smaller than feared** — about 6 questions in 2024, all easy (internal vs
   external commands, batch-file extensions, where `.com` runs). Still learn it (it is cheap
   marks) but **do not give it 25% of your hours.** Move that time to networks and C/C++.

### 0.4 The 2024 question *styles* you must practise

The 2024 paper used five recurring formats. Practise all five, because the format itself costs
time if it is unfamiliar.

| Style | Example from 2024 | How to attack it |
|---|---|---|
| **"Which is NOT …"** — the most common form by far | *"Which is not a polar line coding scheme?"* · *"Which is not a part of mother board?"* | Read the word NOT twice. Find the three that fit, and the odd one is your answer. Many candidates lose marks purely by missing "not" |
| **Match the following (a–d ↔ i–iv)** | *"a. Switch, b. Bridge, c. Repeater, d. Router ↔ physical layer / physical+datalink / determines network of destination / connects LANs and WANs"* | Anchor on the **one** pair you are certain of, then eliminate options that contradict it. You rarely need all four |
| **"Select the right option: i & ii / ii & iii / only i"** | *"Some statements about ping are: i… ii… iii… Select the right option"* | Evaluate each numbered statement independently as true/false first, *then* pick the option. Do not read the options first |
| **Output prediction (C / C++)** | `x = -3 * -4 % -6 / -5;` · `printf("%d %d %d", a, ++a, a++);` · `printf(6 + "Happy Sunday");` | Work them on paper. Note that several 2024 items relied on **undefined behaviour** (the `a, ++a, a++` one) — pick the "textbook" answer the examiner intends |
| **Single-fact recall** | *"Which port number is used for SMTP?"* · *"The extension of Access 2010 file is —"* | Instant or skip. Never spend more than 20 seconds |

**Also note:** the 2024 OCR shows several questions that are **duplicated verbatim** (P-I Q135
and Q136 are identical) and several with **garbled or missing options**. Expect one or two
unanswerable items per paper; identify them fast and move on.

### 0.5 Actual 2024 questions worth memorising the answers to

These are real questions from the 2024 Diploma papers. Anything asked once has an elevated
chance of being asked again in the same or altered form.

| From | Question | Answer |
|---|---|---|
| P-I Q35 | Port number for SMTP | **25** |
| P-I Q43 | Non-routable protocol designed for a single LAN segment | **NetBEUI** |
| P-I Q44 | Protocol for data transport on a NetWare network | **IPX** (SPX is the connection-oriented transport atop it) |
| P-I Q45 | IEEE standard for wireless hotspots | **802.11** |
| P-I Q47 | Body that develops protocols/guidelines for long-term Web growth | **W3C** |
| P-I Q69 | Value of "111" | Depends on base — hex 111 ≠ binary 111. ⚠️ OCR garbled; the intended pairing is likely (6E)₁₆ = 110₁₀ |
| P-I Q70 | ASCII can be extended up to | **8-bit** |
| P-I Q184 | Function keys on a standard PC keyboard | **12** |
| P-I Q185 | AIX is whose operating system | **IBM** |
| P-I Q186 | Who invented the WWW in 1989 | **Tim Berners-Lee** |
| P-I Q187 | Links needed for 10 PCs in mesh topology | **45** = n(n−1)/2 |
| P-I Q194 | Which is a virus hoax | **Good Times** |
| P-I Q200 | `myString, myStack, myFriend` naming style | **Camel case** |
| P-I Q128 | Capacity matching | CD ≈ **640 MB**, DVD **4.7 GB**, floppy **1.4 MB**, Blu-ray ≈ **4× a DVD** |
| P-I Q123 | Chipset providing support for main memory, cache and PCI bus controllers | **North bridge** |
| P-I Q166 | Default PowerPoint slide width:height ratio | **4:3** |
| P-I Q173 | Extension of an Access 2010 file | **.accdb** |
| P-I Q113 | Shortcut to collapse/expand the ribbon | **Ctrl + F1** |
| P-II Q8 | Carnegie Mellon's operating system | **Mach** |
| P-II Q20 | Average waiting time, SJF, bursts 6/8/3/3 | **7 ms** (order P3,P4,P1,P2 → waits 0,3,6,12 → 21/4 ≈ 5.25 ⚠️ verify: with bursts 3,3,6,8 the waits are 0,3,6,12, mean 5.25; the key says 7 ms, which matches the order P1 first. **Work it yourself and trust your own Gantt chart**) |
| P-II Q29/30 | `VOL`, `TIME`, `COPY`, `PATH` internal; **`SYS` and `TREE` external** | — |
| P-II Q41 | First Turing Award recipient, for DBMS work | **Charles Bachman** |
| P-II Q104 | Default UNIX prompt | **`$`** |
| P-II Q106 | UNIX's graphical environment | **X Window** |
| P-II Q122 | Turbo C shortcut to compile | **Alt + F9** (Ctrl+F9 = compile *and* run) |
| P-II Q193 | Postfix of `A+B*C^D-(E/F-G)` | Work it with the stack algorithm — a guaranteed-marks question if you know the method |

> **Homework, 1 hour, do it this week:** open both 2024 `.txt` files, work through all 400
> questions, and mark every one you cannot answer. That list *is* your revision syllabus.

### 0.6 What this bank is therefore calibrated on

- **Primary:** the real CTSE 2024 CS (Diploma) Paper-1 and Paper-2, analysed above.
- **Secondary:** the official Diploma syllabus (Section 4 of `OFFICIAL_SYLLABUS.md`).
- **Tertiary:** the 2025 CS (Degree) descriptive question shapes, for the §3/§4 descriptive
  banks — since 2024 gives us no descriptive Diploma questions to copy.

---

## 1. MCQ strategy under one-third negative marking

### 1.1 The arithmetic, done once

Marking: **correct = +2**, **wrong = −(1/3) × 2 = −0.667**, **blank = 0**.

| Your state of knowledge | P(correct) | Expected value if you answer |
|---|---|---|
| You know it | 1.00 | **+2.00** |
| 3 options remain (eliminated 1) | 1/3 | (1/3)(2) + (2/3)(−0.667) = **+0.22** |
| 2 options remain (eliminated 2) | 1/2 | (1/2)(2) + (1/2)(−0.667) = **+0.67** |
| Blind guess, 4 options | 1/4 | (1/4)(2) + (3/4)(−0.667) = **0.00** |
| Leave blank | — | **0.00** |

### 1.2 What follows from it

- **A blind 1-in-4 guess is exactly break-even.** One-third negative marking on a four-option
  paper is precisely calibrated so that random guessing has zero expected value. It cannot
  help you on average; it only adds variance. **So there is no reason to blind-guess.**
- **Eliminate one option and answering becomes positive (+0.22).** Eliminate two and it is
  **+0.67** — over 20 such questions that is **+13 marks**, which in a competitive exam is a
  large number of ranks.
- **Therefore the operating rule is: if you can rule out even ONE option, answer. If all four
  are genuinely equally plausible, leave it blank.**
- On a factual paper like this one, there is almost always one absurd option. Expect to leave
  **fewer than 5 questions blank** in the whole paper.

### 1.3 The elimination habits that actually work

| Cue | What to do |
|---|---|
| Two options are opposites (e.g. "volatile" / "non-volatile") | The answer is usually one of those two — eliminate the other two |
| One option is far longer and more qualified | Often correct on badly-written papers, but do not rely on it |
| "All of the above" present | If you are sure *any one* option is wrong, "All of the above" dies with it |
| "None of the above" present | Rarely correct on this style of paper. Deprioritise it |
| A number option that is not a power of 2, in a memory/capacity question | Almost always wrong |
| An option using vocabulary from a *different* unit | Distractor imported from another topic — eliminate |

### 1.4 Time and sequencing (120 min / 100 Q)

| Pass | Time | What you do |
|---|---|---|
| 1 | ~50 min | Answer everything you know instantly. Mark others `?` (workable) or `??` (guess) |
| 2 | ~45 min | Work the `?` set — conversions, C output, calculations |
| 3 | ~20 min | The `??` set — eliminate, then apply the §1.2 rule |
| 4 | ~5 min | **Verify OMR alignment at Q25, Q50, Q75, Q100** |

> **The most expensive single mistake available to you in this exam is a one-row shift on the
> OMR sheet.** It can cost 100+ marks. Check alignment at each quarter, not just at the end.

---

## 2. MCQ Bank — 120 questions

**Weighting is deliberate.** MS Office, MS-DOS, hardware and motherboard facts are
over-represented relative to their syllabus share, because (a) they generate easy single-fact
MCQs so the examiner writes lots of them, and (b) they are where a B.Tech CS candidate is
weakest. Shared-core topics (OS, networks, DBMS, C) are represented lightly in sets A–L —
drill those from `CORE_01` … `CORE_09` and their own question sets.

> **⚠️ Read §0.2 before you rely on this weighting.** The real 2024 paper devoted **25% of
> Paper-I to networks** and **45% of Paper-II to C and C++**. Sets A–L below are the
> *weak-spot* drill; they are not a scale model of the paper. **Set M (§2.13) is the
> 2024-calibrated set** covering exactly the blocks the real paper over-weighted, and it is
> the more important of the two. Do sets A–L to fix your gaps; do set M to rehearse the paper.

| Set | Topic | Qs | Syllabus unit |
|---|---|---|---|
| A | Generations, classification, basic organisation | 10 | P-I §1.1, 1.2, 1.4 |
| B | Data representation and number systems | 12 | P-I §1.3 |
| C | Input and output devices | 12 | P-I §2 |
| D | Storage devices | 14 | P-I §3 |
| E | Motherboard, buses, ports | 14 | P-I §4 |
| F | MS Word | 12 | P-I §8b |
| G | MS Excel | 12 | P-I §8c |
| H | MS PowerPoint and MS Access | 10 | P-I §8d, 8e |
| I | MS-DOS and Windows | 14 | P-II §1f, 1g |
| J | Operating systems and UNIX | 8 | P-II §1, §2 |
| K | Networks, Internet, viruses | 8 | P-I §5, §6, §9 |
| L | DBMS, SQL, C, System Analysis | 6 | P-II §3, §4, §5 |
| **M** | **2024-calibrated: networks, Internet, Office 2010, C/C++** | **40** | P-I §5,6,8 · P-II §5 |
| | **Total** | **172** | |

> Answer keys with explanations follow each set. **Cover them.**

---

### 2.1 Set A — Generations, classification, basic organisation

**A1.** The first generation of computers used which component as the main switching element?
&nbsp;&nbsp;(a) Transistor &nbsp;(b) Vacuum tube &nbsp;(c) Integrated circuit &nbsp;(d) Microprocessor

**A2.** ENIAC, EDVAC and UNIVAC-I belong to which generation?
&nbsp;&nbsp;(a) First &nbsp;(b) Second &nbsp;(c) Third &nbsp;(d) Fourth

**A3.** The transistor, which defined the second generation, was invented at:
&nbsp;&nbsp;(a) IBM &nbsp;(b) Bell Laboratories &nbsp;(c) MIT &nbsp;(d) Intel

**A4.** Integrated Circuits (ICs) are the defining technology of the:
&nbsp;&nbsp;(a) First generation &nbsp;(b) Second generation &nbsp;(c) Third generation &nbsp;(d) Fourth generation

**A5.** VLSI / the microprocessor characterises which generation?
&nbsp;&nbsp;(a) Second &nbsp;(b) Third &nbsp;(c) Fourth &nbsp;(d) Fifth

**A6.** Which of the following is *not* one of the three components of the CPU as described in
the Diploma syllabus's functional block diagram?
&nbsp;&nbsp;(a) ALU &nbsp;(b) Control Unit &nbsp;(c) Main memory &nbsp;(d) Printer

**A7.** Which class of computer is characterised by supporting hundreds to thousands of
simultaneous users, very high I/O throughput, and use in banks and railways?
&nbsp;&nbsp;(a) Supercomputer &nbsp;(b) Mainframe &nbsp;(c) Minicomputer &nbsp;(d) Microcomputer

**A8.** A computer optimised for a single user running compute-intensive engineering or
graphics applications, more powerful than a PC but not multi-user like a mainframe, is a:
&nbsp;&nbsp;(a) Workstation &nbsp;(b) Server &nbsp;(c) Supercomputer &nbsp;(d) Terminal

**A9.** PARAM, developed by C-DAC, is an example of a:
&nbsp;&nbsp;(a) Mainframe &nbsp;(b) Supercomputer &nbsp;(c) Minicomputer &nbsp;(d) Workstation

**A10.** The unit that co-ordinates and directs the operation of all other units by generating
timing and control signals is the:
&nbsp;&nbsp;(a) ALU &nbsp;(b) Control unit &nbsp;(c) Memory unit &nbsp;(d) Input unit

<details><summary><strong>Answers A1–A10</strong></summary>

| Q | Ans | Why |
|---|---|---|
| A1 | **(b)** | Vacuum tubes (thermionic valves); huge, hot, ~2000 tubes in ENIAC |
| A2 | **(a)** | All 1940s–early-1950s vacuum-tube machines |
| A3 | **(b)** | Bardeen, Brattain and Shockley at Bell Labs, 1947 |
| A4 | **(c)** | 3rd gen = SSI/MSI integrated circuits (1964–1971) |
| A5 | **(c)** | 4th gen = LSI/VLSI, microprocessor on a chip (1971 onward) |
| A6 | **(d)** | Printer is an output device, outside the CPU |
| A7 | **(b)** | Mainframe = throughput and concurrency, not raw FLOPS |
| A8 | **(a)** | Workstation = single-user, high-performance |
| A9 | **(b)** | PARAM series, C-DAC Pune |
| A10 | **(b)** | Control unit — fetch/decode/control signal generation |

**Trap:** A7 vs A9. *Supercomputer* = maximum speed on one huge calculation (weather, nuclear
simulation). *Mainframe* = maximum number of transactions and users. Papers love this pair.
</details>

---

### 2.2 Set B — Data representation and number systems

**B1.** A nibble consists of how many bits?
&nbsp;&nbsp;(a) 2 &nbsp;(b) 4 &nbsp;(c) 8 &nbsp;(d) 16

**B2.** Standard ASCII is a how-many-bit code?
&nbsp;&nbsp;(a) 4 &nbsp;(b) 7 &nbsp;(c) 8 &nbsp;(d) 16

**B3.** How many distinct characters can standard 7-bit ASCII represent?
&nbsp;&nbsp;(a) 64 &nbsp;(b) 127 &nbsp;(c) 128 &nbsp;(d) 256

**B4.** EBCDIC is a code of how many bits, and associated with which vendor?
&nbsp;&nbsp;(a) 7-bit, Intel &nbsp;(b) 8-bit, IBM &nbsp;(c) 16-bit, Microsoft &nbsp;(d) 8-bit, DEC

**B5.** The decimal number 45 in binary is:
&nbsp;&nbsp;(a) 101011 &nbsp;(b) 101101 &nbsp;(c) 110101 &nbsp;(d) 101110

**B6.** The hexadecimal equivalent of binary 11011110 is:
&nbsp;&nbsp;(a) DE &nbsp;(b) ED &nbsp;(c) BE &nbsp;(d) DF

**B7.** The octal equivalent of decimal 100 is:
&nbsp;&nbsp;(a) 144 &nbsp;(b) 164 &nbsp;(c) 134 &nbsp;(d) 154

**B8.** The 2's complement of the 8-bit number 00101100 is:
&nbsp;&nbsp;(a) 11010011 &nbsp;(b) 11010100 &nbsp;(c) 11010101 &nbsp;(d) 00101101

**B9.** In BCD, the decimal number 59 is represented as:
&nbsp;&nbsp;(a) 0101 1001 &nbsp;(b) 0011 1011 &nbsp;(c) 1011 1001 &nbsp;(d) 0101 1011

**B10.** Which of the following bit patterns is **invalid** in BCD?
&nbsp;&nbsp;(a) 0111 &nbsp;(b) 1001 &nbsp;(c) 1010 &nbsp;(d) 0000

**B11.** One kilobyte is exactly:
&nbsp;&nbsp;(a) 1000 bytes &nbsp;(b) 1024 bytes &nbsp;(c) 1024 bits &nbsp;(d) 8000 bits

**B12.** Unicode UTF-16 uses how many bits for a character in the Basic Multilingual Plane?
&nbsp;&nbsp;(a) 7 &nbsp;(b) 8 &nbsp;(c) 16 &nbsp;(d) 32

<details><summary><strong>Answers B1–B12</strong></summary>

| Q | Ans | Working / why |
|---|---|---|
| B1 | **(b)** | Nibble = 4 bits = one hex digit |
| B2 | **(b)** | 7 bits; the 8th bit was originally parity. "Extended ASCII" is 8-bit |
| B3 | **(c)** | 2⁷ = **128** (codes 0–127). Trap: (b) 127 is the *highest code*, not the count |
| B4 | **(b)** | Extended Binary Coded Decimal Interchange Code, 8-bit, IBM mainframes |
| B5 | **(b)** | 45 = 32+8+4+1 = 101101 |
| B6 | **(a)** | 1101 = D, 1110 = E → DE |
| B7 | **(a)** | 100 = 64+32+4 = 1100100₂ → group by 3 from right: 001·100·100 = **144₈** |
| B8 | **(b)** | 1's comp of 00101100 = 11010011; +1 = **11010100** |
| B9 | **(a)** | 5 = 0101, 9 = 1001 |
| B10 | **(c)** | 1010 = 10 decimal — BCD codes only 0–9, so 1010–1111 are invalid |
| B11 | **(b)** | 2¹⁰ = 1024 |
| B12 | **(c)** | UTF-16 BMP = 16 bits; supplementary planes use surrogate pairs (32 bits) |

**Trap:** B3 — "how many characters" vs "highest code number" differ by one. Also B8: candidates
routinely give the 1's complement when 2's is asked. Always do the "+1".
</details>

---

### 2.3 Set C — Input and output devices

**C1.** The standard PC keyboard layout is called:
&nbsp;&nbsp;(a) DVORAK &nbsp;(b) QWERTY &nbsp;(c) AZERTY &nbsp;(d) COLEMAK

**C2.** The standard enhanced PC keyboard has how many keys?
&nbsp;&nbsp;(a) 84 &nbsp;(b) 101/104 &nbsp;(c) 128 &nbsp;(d) 96

**C3.** An optical mouse detects movement using:
&nbsp;&nbsp;(a) A rubber ball and two rollers &nbsp;(b) An LED/laser and a small camera sensor
&nbsp;(c) A magnetic field &nbsp;(d) A gyroscope

**C4.** Mouse pointer speed is usually quoted in:
&nbsp;&nbsp;(a) Hz &nbsp;(b) DPI/CPI &nbsp;(c) Baud &nbsp;(d) Pixels

**C5.** OCR stands for:
&nbsp;&nbsp;(a) Optical Character Recognition &nbsp;(b) Optical Code Reader
&nbsp;(c) Ordered Character Retrieval &nbsp;(d) Optical Cathode Ray

**C6.** MICR, used mainly on bank cheques, stands for:
&nbsp;&nbsp;(a) Magnetic Ink Character Recognition &nbsp;(b) Micro Ink Code Reader
&nbsp;(c) Magnetic Image Colour Recognition &nbsp;(d) Multiple Input Character Reader

**C7.** A bar-code reader works by:
&nbsp;&nbsp;(a) Weighing the item &nbsp;(b) Measuring reflected light from bars and spaces
&nbsp;(c) Reading a magnetic strip &nbsp;(d) Radio frequency

**C8.** Which is an **impact** printer?
&nbsp;&nbsp;(a) Laser &nbsp;(b) Inkjet &nbsp;(c) Dot matrix &nbsp;(d) Thermal

**C9.** A laser printer's speed is measured in:
&nbsp;&nbsp;(a) CPS &nbsp;(b) LPM &nbsp;(c) PPM &nbsp;(d) DPI

**C10.** A dot matrix printer's speed is measured in:
&nbsp;&nbsp;(a) CPS (characters per second) &nbsp;(b) PPM &nbsp;(c) DPI &nbsp;(d) Hz

**C11.** Which printer can produce **carbon copies** in a single pass?
&nbsp;&nbsp;(a) Laser &nbsp;(b) Inkjet &nbsp;(c) Dot matrix &nbsp;(d) Thermal inkjet

**C12.** In a CRT monitor, the picture is produced by:
&nbsp;&nbsp;(a) Liquid crystals twisting polarised light &nbsp;(b) An electron beam striking a phosphor coating
&nbsp;(c) Organic LEDs emitting light &nbsp;(d) Plasma cells

<details><summary><strong>Answers C1–C12</strong></summary>

| Q | Ans | Why |
|---|---|---|
| C1 | **(b)** | QWERTY — named after the first six letters of the top row |
| C2 | **(b)** | 101-key enhanced; 104 with the Windows keys. Older AT keyboard = 84 keys |
| C3 | **(b)** | LED (or laser) illuminates the surface; a tiny CMOS camera takes thousands of images/sec and a DSP computes displacement |
| C4 | **(b)** | Dots (counts) per inch |
| C5 | **(a)** | Converts a scanned image of text into editable character codes |
| C6 | **(a)** | Magnetic Ink Character Recognition — E-13B font on cheques |
| C7 | **(b)** | Dark bars absorb, light spaces reflect; a photodiode reads the pattern |
| C8 | **(c)** | Dot matrix hammers pins through a ribbon onto the paper — impact |
| C9 | **(c)** | Pages per minute |
| C10 | **(a)** | Characters per second |
| C11 | **(c)** | Only impact printers can, because they physically strike the paper |
| C12 | **(b)** | Electron gun → deflection → phosphor glows |

**Trap:** C11 is a classic. "Which printer is used where multi-part stationery/carbon copies are
needed" → **dot matrix**, always. Also remember: **laser = page printer, inkjet & DMP =
character/line printers.**
</details>

---

### 2.4 Set D — Storage devices

**D1.** Which memory retains its contents when power is removed?
&nbsp;&nbsp;(a) SRAM &nbsp;(b) DRAM &nbsp;(c) ROM &nbsp;(d) Cache

**D2.** A PROM can be programmed:
&nbsp;&nbsp;(a) Never &nbsp;(b) Once, by the user &nbsp;(c) Any number of times electrically &nbsp;(d) Only at the factory

**D3.** An EPROM is erased by:
&nbsp;&nbsp;(a) A high electrical voltage &nbsp;(b) Ultraviolet light through a quartz window
&nbsp;(c) Heating it &nbsp;(d) Software command

**D4.** EEPROM differs from EPROM in that it is:
&nbsp;&nbsp;(a) Faster to read &nbsp;(b) Erasable electrically, byte by byte, in circuit
&nbsp;(c) Volatile &nbsp;(d) Larger in capacity

**D5.** Which is the **fastest** storage in the memory hierarchy?
&nbsp;&nbsp;(a) Cache &nbsp;(b) Main memory &nbsp;(c) CPU registers &nbsp;(d) Hard disk

**D6.** SRAM is faster than DRAM primarily because:
&nbsp;&nbsp;(a) It uses capacitors &nbsp;(b) It uses a flip-flop per bit and needs no refresh
&nbsp;(c) It is placed on the hard disk &nbsp;(d) It has a wider bus

**D7.** DRAM must be **refreshed** because each cell stores a bit as:
&nbsp;&nbsp;(a) A magnetic domain &nbsp;(b) A charge on a capacitor that leaks away
&nbsp;(c) A latched flip-flop state &nbsp;(d) An optical pit

**D8.** DDR SDRAM achieves roughly double the bandwidth of SDR SDRAM at the same clock because
it transfers data:
&nbsp;&nbsp;(a) On both the rising and falling edges of the clock &nbsp;(b) On a 128-bit bus
&nbsp;(c) Without refresh &nbsp;(d) Using two memory controllers

**D9.** A concentric circle on one surface of a hard-disk platter is called a:
&nbsp;&nbsp;(a) Sector &nbsp;(b) Track &nbsp;(c) Cylinder &nbsp;(d) Cluster

**D10.** The set of all tracks at the same radius across all platters is a:
&nbsp;&nbsp;(a) Sector &nbsp;(b) Cluster &nbsp;(c) Cylinder &nbsp;(d) Block

**D11.** The smallest unit of disk space that the file system will allocate to a file is a:
&nbsp;&nbsp;(a) Bit &nbsp;(b) Sector &nbsp;(c) Cluster (allocation unit) &nbsp;(d) Cylinder

**D12.** The traditional hard-disk sector size is:
&nbsp;&nbsp;(a) 128 bytes &nbsp;(b) 512 bytes &nbsp;(c) 1024 bytes &nbsp;(d) 4096 bits

**D13.** The capacity of a standard 3.5-inch high-density floppy disk is:
&nbsp;&nbsp;(a) 360 KB &nbsp;(b) 720 KB &nbsp;(c) 1.2 MB &nbsp;(d) 1.44 MB

**D14.** On a CD, data is physically recorded as:
&nbsp;&nbsp;(a) Magnetic domains &nbsp;(b) Pits and lands read by laser reflection
&nbsp;(c) Electrical charges &nbsp;(d) Holes punched in the substrate

<details><summary><strong>Answers D1–D14</strong></summary>

| Q | Ans | Why |
|---|---|---|
| D1 | **(c)** | ROM is non-volatile; SRAM, DRAM and cache are all volatile |
| D2 | **(b)** | Programmable ROM — one-time, blown fuses/antifuses (OTP) |
| D3 | **(b)** | UV through the quartz window, ~20 minutes; erases the whole chip |
| D4 | **(b)** | Electrically erasable, selectively, without removing the chip |
| D5 | **(c)** | Registers > cache > main memory > secondary |
| D6 | **(b)** | 6-transistor flip-flop cell, no refresh cycle stealing access time |
| D7 | **(b)** | 1 transistor + 1 capacitor; charge leaks, so refresh every few ms |
| D8 | **(a)** | **D**ouble **D**ata **R**ate = both clock edges |
| D9 | **(b)** | Track |
| D10 | **(c)** | Cylinder |
| D11 | **(c)** | Cluster = 1, 2, 4, 8 … sectors. Cause of internal fragmentation / slack space |
| D12 | **(b)** | 512 bytes classically; modern drives use 4096-byte "Advanced Format" |
| D13 | **(d)** | 3.5" HD = 1.44 MB. (5.25" HD = 1.2 MB; 3.5" DD = 720 KB; 5.25" DD = 360 KB) |
| D14 | **(b)** | Pits and lands; the transition between them encodes a 1 |

**Traps:**
- D13 is the classic floppy question — memorise **all four** capacities in the table above,
  because the examiner may ask any of them.
- D8: "DDR" does **not** mean double clock speed; it means two transfers per clock cycle.
- D11: cluster vs sector. The *disk* is formatted into sectors; the *file system* allocates
  clusters.
</details>

---

### 2.5 Set E — Motherboard, buses and ports

**E1.** The chipset component traditionally called the **Northbridge** is also known as the:
&nbsp;&nbsp;(a) I/O Controller Hub &nbsp;(b) Memory Controller Hub &nbsp;(c) Super I/O &nbsp;(d) BIOS

**E2.** Which of the following connects **directly** to the Memory Controller Hub in the classic
two-chip chipset layout?
&nbsp;&nbsp;(a) USB ports &nbsp;(b) IDE channels &nbsp;(c) DIMM slots and the AGP slot &nbsp;(d) PS/2 ports

**E3.** AGP was designed specifically for:
&nbsp;&nbsp;(a) Sound cards &nbsp;(b) Graphics/display adapters &nbsp;(c) Network cards &nbsp;(d) Hard drives

**E4.** DIMM stands for:
&nbsp;&nbsp;(a) Dual Inline Memory Module &nbsp;(b) Direct Internal Memory Map
&nbsp;(c) Dynamic Inline Memory Module &nbsp;(d) Dual Interface Main Memory

**E5.** A standard parallel ATA (IDE) ribbon cable supports how many devices per channel?
&nbsp;&nbsp;(a) 1 &nbsp;(b) 2 (master and slave) &nbsp;(c) 4 &nbsp;(d) 7

**E6.** A 40-pin IDE connector paired with an **80-conductor** cable is used for:
&nbsp;&nbsp;(a) Floppy drives &nbsp;(b) Higher-speed UDMA hard-disk modes
&nbsp;(c) SCSI devices &nbsp;(d) Serial ports

**E7.** The floppy-drive ribbon connector on a motherboard has how many pins?
&nbsp;&nbsp;(a) 26 &nbsp;(b) 34 &nbsp;(c) 40 &nbsp;(d) 50

**E8.** The traditional 9-pin D-type connector on a PC's back panel is a:
&nbsp;&nbsp;(a) Parallel port &nbsp;(b) Serial (RS-232 / COM) port &nbsp;(c) VGA port &nbsp;(d) Game port

**E9.** The 25-pin female D-type connector traditionally used for a printer is the:
&nbsp;&nbsp;(a) Serial port &nbsp;(b) Parallel (LPT / Centronics) port &nbsp;(c) SCSI port &nbsp;(d) MIDI port

**E10.** By colour convention, the **green** PS/2 port is for the:
&nbsp;&nbsp;(a) Keyboard &nbsp;(b) Mouse &nbsp;(c) Monitor &nbsp;(d) Speaker

**E11.** The CMOS battery on a motherboard is typically a:
&nbsp;&nbsp;(a) AA alkaline cell &nbsp;(b) CR2032 3 V lithium coin cell
&nbsp;(c) 9 V PP3 &nbsp;(d) Ni-Cd rechargeable pack

**E12.** If the CMOS battery fails, the most visible symptom is:
&nbsp;&nbsp;(a) The hard disk is erased &nbsp;(b) The system loses date/time and BIOS settings at every power-off
&nbsp;(c) The RAM fails &nbsp;(d) The monitor shows no signal permanently

**E13.** The POST (Power-On Self Test) is performed by:
&nbsp;&nbsp;(a) The operating system &nbsp;(b) The BIOS firmware in ROM
&nbsp;(c) COMMAND.COM &nbsp;(d) The device drivers

**E14.** On an ATX power supply, the main motherboard power connector has how many pins?
&nbsp;&nbsp;(a) 12 &nbsp;(b) 20 or 24 &nbsp;(c) 34 &nbsp;(d) 40

<details><summary><strong>Answers E1–E14</strong></summary>

| Q | Ans | Why |
|---|---|---|
| E1 | **(b)** | Northbridge = Memory Controller Hub (MCH); Southbridge = I/O Controller Hub (ICH) |
| E2 | **(c)** | MCH handles the fast stuff: CPU (FSB), RAM, AGP/PCIe graphics |
| E3 | **(b)** | Accelerated Graphics Port — a dedicated point-to-point graphics bus |
| E4 | **(a)** | Dual Inline Memory Module — independent contacts on both sides (SIMM had them tied) |
| E5 | **(b)** | Two: one jumpered master, one slave |
| E6 | **(b)** | 80-conductor cable keeps 40 pins but adds 40 ground wires to reduce crosstalk for UDMA/66 and above |
| E7 | **(b)** | 34 pins — this is a favourite MCQ |
| E8 | **(b)** | DB-9 male on the PC = serial COM port |
| E9 | **(b)** | DB-25 female = parallel LPT port |
| E10 | **(b)** | **Green = mouse, purple = keyboard.** Memorise it |
| E11 | **(b)** | CR2032, 3 V lithium |
| E12 | **(b)** | CMOS RAM holding settings + RTC lose their standby power |
| E13 | **(b)** | BIOS, before any OS is loaded |
| E14 | **(b)** | ATX 20-pin, extended to 24-pin in ATX12V 2.0 |

**Traps:**
- E7 vs E5: **floppy = 34 pins, IDE = 40 pins, SCSI-1 = 50 pins.** Three numbers, learn all three.
- E10: green/purple PS/2 colours are asked surprisingly often.
- E6: the trap answer is "80 pins". The *cable* has 80 conductors; the *connector* still has 40 pins.
</details>

---

### 2.6 Set F — MS Word

**F1.** The horizontal bar at the very top of the Word window showing the document name is the:
&nbsp;&nbsp;(a) Menu bar &nbsp;(b) Title bar &nbsp;(c) Status bar &nbsp;(d) Ruler

**F2.** The default file extension of a Word 2007+ document is:
&nbsp;&nbsp;(a) .doc &nbsp;(b) .docx &nbsp;(c) .txt &nbsp;(d) .wrd

**F3.** **Drop Cap** is used to:
&nbsp;&nbsp;(a) Convert text to capitals &nbsp;(b) Make the first letter of a paragraph large and dropped over several lines
&nbsp;(c) Drop a picture into text &nbsp;(d) Lower the case of selected text

**F4.** Text that appears at the **bottom of every page** is placed in the:
&nbsp;&nbsp;(a) Header &nbsp;(b) Footer &nbsp;(c) Footnote &nbsp;(d) Endnote

**F5.** The key difference between a **footnote** and an **endnote** is that:
&nbsp;&nbsp;(a) Footnotes are numbered, endnotes are not
&nbsp;(b) A footnote appears at the bottom of the same page; an endnote appears at the end of the document or section
&nbsp;(c) Footnotes cannot be edited &nbsp;(d) Endnotes cannot contain references

**F6.** **Mail Merge** requires which two documents?
&nbsp;&nbsp;(a) Main document and data source &nbsp;(b) Header and footer
&nbsp;(c) Template and macro &nbsp;(d) Form and report

**F7.** In Mail Merge, the placeholders inserted into the main document are called:
&nbsp;&nbsp;(a) Fields (merge fields) &nbsp;(b) Bookmarks &nbsp;(c) Hyperlinks &nbsp;(d) Captions

**F8.** **WordArt** is used to:
&nbsp;&nbsp;(a) Insert clipart &nbsp;(b) Create decorative, stylised text objects
&nbsp;(c) Draw freehand &nbsp;(d) Check spelling

**F9.** The shortcut Ctrl + Z performs:
&nbsp;&nbsp;(a) Redo &nbsp;(b) Undo &nbsp;(c) Zoom &nbsp;(d) Save

**F10.** Red wavy underlines in Word indicate:
&nbsp;&nbsp;(a) Grammar errors &nbsp;(b) Possible spelling errors &nbsp;(c) Tracked changes &nbsp;(d) Hyperlinks

**F11.** A **text box** or **callout** is used to:
&nbsp;&nbsp;(a) Hold text that can be positioned independently anywhere on the page
&nbsp;(b) Increase font size &nbsp;(c) Create a table &nbsp;(d) Add a footnote

**F12.** To split a page into two or more vertical text columns you use:
&nbsp;&nbsp;(a) Insert → Table &nbsp;(b) Page Layout → Columns &nbsp;(c) Format → Tabs &nbsp;(d) Insert → Text Box

<details><summary><strong>Answers F1–F12</strong></summary>

| Q | Ans | Note |
|---|---|---|
| F1 | **(b)** | Title bar |
| F2 | **(b)** | .docx (Office Open XML). Pre-2007 = .doc |
| F3 | **(b)** | Drop Cap — "dropped" or "in margin" style |
| F4 | **(b)** | Footer. Header = top of every page |
| F5 | **(b)** | Position, not numbering — both are auto-numbered |
| F6 | **(a)** | Main document + data source (recipient list) → merged output |
| F7 | **(a)** | Merge fields, e.g. «FirstName» |
| F8 | **(b)** | Stylised/decorative text |
| F9 | **(b)** | Undo. Redo = Ctrl+Y |
| F10 | **(b)** | Red wavy = spelling; green wavy (classic) = grammar |
| F11 | **(a)** | Free-floating container |
| F12 | **(b)** | Columns |

**Trap:** F4 vs F5. **Footer** (page furniture, every page) is not the same thing as **footnote**
(a reference note tied to a specific word). This pair is an examiner favourite.
</details>

---

### 2.7 Set G — MS Excel

**G1.** The intersection of a row and a column in a worksheet is called a:
&nbsp;&nbsp;(a) Cell &nbsp;(b) Field &nbsp;(c) Record &nbsp;(d) Range

**G2.** Every formula in Excel must begin with:
&nbsp;&nbsp;(a) A colon &nbsp;(b) An equals sign (=) &nbsp;(c) A hash &nbsp;(d) An apostrophe

**G3.** A **workbook** is:
&nbsp;&nbsp;(a) A single sheet &nbsp;(b) A file containing one or more worksheets
&nbsp;(c) A row of data &nbsp;(d) A chart

**G4.** The reference `$A$1` is a:
&nbsp;&nbsp;(a) Relative reference &nbsp;(b) Absolute reference &nbsp;(c) Mixed reference &nbsp;(d) 3-D reference

**G5.** The reference `A$1` is a:
&nbsp;&nbsp;(a) Relative reference &nbsp;(b) Absolute reference &nbsp;(c) Mixed reference &nbsp;(d) Circular reference

**G6.** `=SUM(A1:A10)` adds:
&nbsp;&nbsp;(a) Cells A1 and A10 only &nbsp;(b) All cells from A1 to A10 inclusive
&nbsp;(c) Row 1 to row 10 entirely &nbsp;(d) Nothing — invalid syntax

**G7.** Which function counts only the cells in a range that contain **numbers**?
&nbsp;&nbsp;(a) COUNT &nbsp;(b) COUNTA &nbsp;(c) COUNTBLANK &nbsp;(d) SUM

**G8.** Which of these is a **logical** function?
&nbsp;&nbsp;(a) AVERAGE &nbsp;(b) IF &nbsp;(c) LEFT &nbsp;(d) NOW

**G9.** VLOOKUP belongs to which function category?
&nbsp;&nbsp;(a) Statistical &nbsp;(b) Lookup and Reference &nbsp;(c) Financial &nbsp;(d) Text

**G10.** Which chart type is best for showing each part as a percentage of a single whole?
&nbsp;&nbsp;(a) Line chart &nbsp;(b) Pie chart &nbsp;(c) Scatter chart &nbsp;(d) Bar chart

**G11.** In a chart, the key that identifies each data series by colour is the:
&nbsp;&nbsp;(a) Axis &nbsp;(b) Legend &nbsp;(c) Plot area &nbsp;(d) Gridline

**G12.** The error `#DIV/0!` means:
&nbsp;&nbsp;(a) A cell reference is invalid &nbsp;(b) A formula divides by zero or an empty cell
&nbsp;(c) The column is too narrow &nbsp;(d) A name is misspelt

<details><summary><strong>Answers G1–G12</strong></summary>

| Q | Ans | Note |
|---|---|---|
| G1 | **(a)** | Cell |
| G2 | **(b)** | `=` (Lotus-style `+` also works but `=` is the answer) |
| G3 | **(b)** | Workbook = the file; worksheet = a sheet inside it |
| G4 | **(b)** | Both `$` = absolute; does not change when copied |
| G5 | **(c)** | Column relative, row absolute = mixed |
| G6 | **(b)** | `:` is the range operator |
| G7 | **(a)** | COUNT = numeric only; COUNTA = any non-empty |
| G8 | **(b)** | IF, AND, OR, NOT are logical. AVERAGE = statistical, LEFT = text, NOW = date/time |
| G9 | **(b)** | Lookup and Reference |
| G10 | **(b)** | Pie — parts of one whole |
| G11 | **(b)** | Legend |
| G12 | **(b)** | Divide by zero |

**Error-code table worth memorising** (high MCQ yield):

| Error | Meaning |
|---|---|
| `#####` | Column too narrow to display the value |
| `#DIV/0!` | Division by zero |
| `#NAME?` | Unrecognised text / misspelt function name |
| `#REF!` | Reference to a deleted cell |
| `#VALUE!` | Wrong data type in an operand |
| `#N/A` | Value not available (typical of a failed lookup) |
| `#NUM!` | Invalid numeric argument |
| `#NULL!` | Invalid intersection of two ranges |
</details>

---

### 2.8 Set H — MS PowerPoint and MS Access

**H1.** The default file extension of a PowerPoint 2007+ presentation is:
&nbsp;&nbsp;(a) .ppt &nbsp;(b) .pptx &nbsp;(c) .ppsx &nbsp;(d) .potx

**H2.** Which PowerPoint view shows thumbnails of all slides for reordering?
&nbsp;&nbsp;(a) Normal view &nbsp;(b) Slide Sorter view &nbsp;(c) Notes Page view &nbsp;(d) Reading view

**H3.** The effect applied when moving **from one slide to the next** is a:
&nbsp;&nbsp;(a) Animation &nbsp;(b) Transition &nbsp;(c) Action button &nbsp;(d) Template

**H4.** An effect applied to an **individual object on a slide** (text, picture) is:
&nbsp;&nbsp;(a) A transition &nbsp;(b) An animation &nbsp;(c) A theme &nbsp;(d) A layout

**H5.** The function key that starts a slide show from the first slide is:
&nbsp;&nbsp;(a) F2 &nbsp;(b) F5 &nbsp;(c) F7 &nbsp;(d) F12

**H6.** An **action button** in PowerPoint is used to:
&nbsp;&nbsp;(a) Format text &nbsp;(b) Provide a clickable control that jumps to a slide, file or URL
&nbsp;(c) Insert a chart &nbsp;(d) Print handouts

**H7.** In MS Access, a **table** stores data in rows and columns; a row is called a:
&nbsp;&nbsp;(a) Field &nbsp;(b) Record &nbsp;(c) Query &nbsp;(d) Form

**H8.** In MS Access, a column of a table is a:
&nbsp;&nbsp;(a) Record &nbsp;(b) Field &nbsp;(c) Report &nbsp;(d) Macro

**H9.** Which Access object is designed primarily for **printed output**?
&nbsp;&nbsp;(a) Table &nbsp;(b) Query &nbsp;(c) Form &nbsp;(d) Report

**H10.** The Access field property that guarantees each record has a unique identifier is:
&nbsp;&nbsp;(a) Index &nbsp;(b) Primary key &nbsp;(c) Validation rule &nbsp;(d) Default value

<details><summary><strong>Answers H1–H10</strong></summary>

| Q | Ans | Note |
|---|---|---|
| H1 | **(b)** | .pptx. `.ppsx` = slide **show** (opens straight into presentation); `.potx` = template |
| H2 | **(b)** | Slide Sorter |
| H3 | **(b)** | Transition = between slides |
| H4 | **(b)** | Animation = within a slide |
| H5 | **(b)** | F5 from the start; Shift+F5 from the current slide |
| H6 | **(b)** | Hyperlinked control |
| H7 | **(b)** | Record = row = one entity instance |
| H8 | **(b)** | Field = column = one attribute |
| H9 | **(d)** | Report |
| H10 | **(b)** | Primary key |

**Trap:** H3 vs H4 — **transition between slides, animation within a slide.** Guaranteed to be
asked in some form. Also H7/H8: record = row, field = column; candidates swap them under pressure.
</details>

---

### 2.9 Set I — MS-DOS and Windows

**I1.** In MS-DOS, the command interpreter (the program that reads and executes your typed
commands) is:
&nbsp;&nbsp;(a) IO.SYS &nbsp;(b) MSDOS.SYS &nbsp;(c) COMMAND.COM &nbsp;(d) CONFIG.SYS

**I2.** Which of the following is an **internal** DOS command?
&nbsp;&nbsp;(a) FORMAT &nbsp;(b) DIR &nbsp;(c) CHKDSK &nbsp;(d) XCOPY

**I3.** Which of the following is an **external** DOS command?
&nbsp;&nbsp;(a) COPY &nbsp;(b) DEL &nbsp;(c) FORMAT &nbsp;(d) CLS

**I4.** Internal commands are so called because they are:
&nbsp;&nbsp;(a) Stored as separate .EXE files on disk &nbsp;(b) Built into COMMAND.COM and loaded in memory
&nbsp;(c) Only usable by the administrator &nbsp;(d) Written in assembly

**I5.** The DOS file-naming convention is:
&nbsp;&nbsp;(a) 8 characters name + 3 character extension &nbsp;(b) 11 characters, no extension
&nbsp;(c) 255 characters &nbsp;(d) 8 characters only

**I6.** `DIR /P` does what?
&nbsp;&nbsp;(a) Prints the directory &nbsp;(b) Pauses after each screenful
&nbsp;(c) Lists in wide format &nbsp;(d) Shows hidden files

**I7.** `DIR /W` displays the listing:
&nbsp;&nbsp;(a) One file per line with details &nbsp;(b) In wide format, names only, multiple columns
&nbsp;(c) Sorted by date &nbsp;(d) With subdirectories recursively

**I8.** The command used to change a file's read-only, hidden, system or archive attribute is:
&nbsp;&nbsp;(a) CHKDSK &nbsp;(b) ATTRIB &nbsp;(c) LABEL &nbsp;(d) EDIT

**I9.** A **.BAT** file is:
&nbsp;&nbsp;(a) A compiled binary &nbsp;(b) A plain-text file of DOS commands executed in sequence
&nbsp;(c) A device driver &nbsp;(d) A backup file

**I10.** The essential difference between a **.COM** and an **.EXE** file is that:
&nbsp;&nbsp;(a) .COM is text, .EXE is binary
&nbsp;(b) .COM is a single-segment program limited to 64 KB with no relocation header; .EXE has a header and may use multiple segments
&nbsp;(c) .EXE is older &nbsp;(d) .COM cannot be executed

**I11.** When two files of the same base name but different extensions exist, DOS executes them
in which order of preference?
&nbsp;&nbsp;(a) .BAT, .COM, .EXE &nbsp;(b) .COM, .EXE, .BAT &nbsp;(c) .EXE, .COM, .BAT &nbsp;(d) Alphabetical

**I12.** The DOS wildcard `*` stands for:
&nbsp;&nbsp;(a) Exactly one character &nbsp;(b) Any sequence of characters
&nbsp;(c) A directory &nbsp;(d) A drive letter

**I13.** In Windows, deleted files from a hard disk are temporarily held in the:
&nbsp;&nbsp;(a) Clipboard &nbsp;(b) Recycle Bin &nbsp;(c) Temp folder &nbsp;(d) My Documents

**I14.** Which Windows accessory is a **plain-text** editor with no formatting?
&nbsp;&nbsp;(a) WordPad &nbsp;(b) Notepad &nbsp;(c) Paint &nbsp;(d) Character Map

<details><summary><strong>Answers I1–I14</strong></summary>

| Q | Ans | Note |
|---|---|---|
| I1 | **(c)** | COMMAND.COM — the shell / command interpreter |
| I2 | **(b)** | DIR is internal |
| I3 | **(c)** | FORMAT.COM is a separate file on disk — external |
| I4 | **(b)** | Resident inside COMMAND.COM, always in memory, no disk access needed |
| I5 | **(a)** | The "8.3" convention |
| I6 | **(b)** | /P = pause |
| I7 | **(b)** | /W = wide |
| I8 | **(b)** | ATTRIB +R/−R, +H/−H, +S/−S, +A/−A |
| I9 | **(b)** | Batch file — plain text, one command per line |
| I10 | **(b)** | .COM = memory image, ≤64 KB, one segment; .EXE = relocatable, header, multi-segment |
| I11 | **(b)** | **.COM → .EXE → .BAT** |
| I12 | **(b)** | `*` = any number of characters; `?` = exactly one |
| I13 | **(b)** | Recycle Bin (not for files deleted from removable media or with Shift+Delete) |
| I14 | **(b)** | Notepad = plain text; WordPad = basic rich text (.rtf) |

**The three DOS system files, in load order — memorise:**

| File | Role |
|---|---|
| **IO.SYS** | Low-level device I/O routines; loads first, interfaces with the BIOS |
| **MSDOS.SYS** | The DOS kernel — file system, memory management, system calls |
| **COMMAND.COM** | The command interpreter / shell — displays the prompt, runs commands |

**Internal vs external — the list to memorise:**

| Internal (in COMMAND.COM) | External (separate .COM/.EXE on disk) |
|---|---|
| DIR, COPY, DEL/ERASE, REN, TYPE, CLS, MD/MKDIR, CD/CHDIR, RD/RMDIR, DATE, TIME, VER, VOL, PATH, PROMPT, SET, ECHO, EXIT | FORMAT, CHKDSK, SCANDISK, DISKCOPY, XCOPY, ATTRIB, LABEL, TREE, MORE, SORT, FIND, PRINT, EDIT, FDISK, DEFRAG, BACKUP, RESTORE, DOSKEY, MEM, SYS |

**Trap:** I2/I3 pairs appear every year. The rule of thumb: **if it does something big to a disk
(FORMAT, CHKDSK, FDISK, DEFRAG, XCOPY) it is external. If it is a small everyday file/console
operation it is internal.** `COPY` is internal but `XCOPY` is external — that exact pair is a
favourite.
</details>

---

### 2.10 Set J — Operating systems and UNIX
> Core treatment in `CORE_03_OperatingSystems.md` and `CORE_04_UnixLinux.md`. Sampler only here.

**J1.** Which CPU scheduling algorithm is guaranteed to give the minimum average waiting time
for a given set of processes arriving together?
&nbsp;&nbsp;(a) FCFS &nbsp;(b) SJF &nbsp;(c) Round Robin &nbsp;(d) Priority

**J2.** Round Robin scheduling is essentially FCFS plus:
&nbsp;&nbsp;(a) Priorities &nbsp;(b) Preemption on a time quantum &nbsp;(c) Aging &nbsp;(d) Multiple queues

**J3.** The problem in which a low-priority process never executes because higher-priority
processes keep arriving is:
&nbsp;&nbsp;(a) Deadlock &nbsp;(b) Starvation &nbsp;(c) Thrashing &nbsp;(d) Fragmentation

**J4.** In UNIX, the command that displays the users currently logged in is:
&nbsp;&nbsp;(a) `whoami` &nbsp;(b) `who` &nbsp;(c) `ls` &nbsp;(d) `ps`

**J5.** Which UNIX command counts the lines, words and characters in a file?
&nbsp;&nbsp;(a) `cat` &nbsp;(b) `wc` &nbsp;(c) `cut` &nbsp;(d) `sort`

**J6.** `head -5 file.txt` displays:
&nbsp;&nbsp;(a) The last 5 lines &nbsp;(b) The first 5 lines &nbsp;(c) Every 5th line &nbsp;(d) 5 characters

**J7.** Which command searches files for lines matching a pattern?
&nbsp;&nbsp;(a) `find` &nbsp;(b) `grep` &nbsp;(c) `tr` &nbsp;(d) `join`

**J8.** In UNIX, the component that interacts directly with the hardware is the:
&nbsp;&nbsp;(a) Shell &nbsp;(b) Kernel &nbsp;(c) Utilities &nbsp;(d) Application layer

<details><summary><strong>Answers J1–J8</strong></summary>

| Q | Ans | Note |
|---|---|---|
| J1 | **(b)** | SJF is provably optimal for average waiting time |
| J2 | **(b)** | RR = FCFS + preemptive time slice |
| J3 | **(b)** | Starvation / indefinite blocking; cured by **aging** |
| J4 | **(b)** | `who`. `who am i` / `whoami` shows just you |
| J5 | **(b)** | `wc` — `-l` lines, `-w` words, `-c` characters |
| J6 | **(b)** | `head` = start of file, `tail` = end |
| J7 | **(b)** | `grep` = Global Regular Expression Print |
| J8 | **(b)** | Kernel. Shell is the user interface; utilities sit on top |
</details>

---

### 2.11 Set K — Networks, Internet and viruses

**K1.** How many layers does the OSI reference model have?
&nbsp;&nbsp;(a) 4 &nbsp;(b) 5 &nbsp;(c) 7 &nbsp;(d) 8

**K2.** A device that regenerates a weakened signal to extend network distance, operating at
the physical layer, is a:
&nbsp;&nbsp;(a) Router &nbsp;(b) Repeater &nbsp;(c) Gateway &nbsp;(d) Bridge

**K3.** In which topology does a single cable break bring down the entire network?
&nbsp;&nbsp;(a) Star &nbsp;(b) Bus &nbsp;(c) Mesh &nbsp;(d) Tree

**K4.** A transmission mode allowing communication in both directions but only one at a time is:
&nbsp;&nbsp;(a) Simplex &nbsp;(b) Half duplex &nbsp;(c) Full duplex &nbsp;(d) Multiplex

**K5.** The protocol used to transfer files between hosts on the Internet is:
&nbsp;&nbsp;(a) SMTP &nbsp;(b) FTP &nbsp;(c) Telnet &nbsp;(d) HTTP

**K6.** A **boot sector virus** infects:
&nbsp;&nbsp;(a) Word documents &nbsp;(b) The master boot record / DOS boot record of a disk
&nbsp;(c) The command interpreter only &nbsp;(d) Network packets

**K7.** A **macro virus** is written in:
&nbsp;&nbsp;(a) Assembly language &nbsp;(b) The macro/scripting language of an application such as VBA
&nbsp;(c) C++ &nbsp;(d) Machine code

**K8.** Which malicious program is **self-replicating across a network without needing a host
program**?
&nbsp;&nbsp;(a) Virus &nbsp;(b) Worm &nbsp;(c) Trojan horse &nbsp;(d) Logic bomb

<details><summary><strong>Answers K1–K8</strong></summary>

| Q | Ans | Note |
|---|---|---|
| K1 | **(c)** | 7 — Physical, Data Link, Network, Transport, Session, Presentation, Application |
| K2 | **(b)** | Repeater — layer 1 |
| K3 | **(b)** | Bus — single shared backbone is a single point of failure |
| K4 | **(b)** | Half duplex (walkie-talkie) |
| K5 | **(b)** | FTP, ports 20 (data) / 21 (control) |
| K6 | **(b)** | Boot sector / MBR |
| K7 | **(b)** | VBA in Word/Excel; spreads via documents, not executables |
| K8 | **(b)** | Worm — a virus needs a host, a worm does not |
</details>

---

### 2.12 Set L — DBMS, SQL, C, System Analysis

**L1.** Which SQL statement removes all rows from a table but keeps the table structure and
cannot be rolled back in most systems?
&nbsp;&nbsp;(a) DELETE &nbsp;(b) DROP &nbsp;(c) TRUNCATE &nbsp;(d) ALTER

**L2.** An attribute or set of attributes that uniquely identifies each tuple of a relation is a:
&nbsp;&nbsp;(a) Foreign key &nbsp;(b) Primary key &nbsp;(c) Domain &nbsp;(d) View

**L3.** In an E-R diagram, an **entity** is represented by a:
&nbsp;&nbsp;(a) Diamond &nbsp;(b) Rectangle &nbsp;(c) Ellipse &nbsp;(d) Line

**L4.** What is the output of `printf("%d", 7/2);` in C?
&nbsp;&nbsp;(a) 3.5 &nbsp;(b) 3 &nbsp;(c) 4 &nbsp;(d) 0

**L5.** Which of the following is **not** a valid C keyword?
&nbsp;&nbsp;(a) static &nbsp;(b) volatile &nbsp;(c) function &nbsp;(d) register

**L6.** The first phase of the classical SDLC is:
&nbsp;&nbsp;(a) Design &nbsp;(b) Coding &nbsp;(c) Preliminary investigation / requirement analysis &nbsp;(d) Testing

<details><summary><strong>Answers L1–L6</strong></summary>

| Q | Ans | Note |
|---|---|---|
| L1 | **(c)** | TRUNCATE is DDL; DELETE is DML and is logged/rollbackable |
| L2 | **(b)** | Primary key |
| L3 | **(b)** | Rectangle = entity, ellipse = attribute, diamond = relationship |
| L4 | **(b)** | Integer division truncates: 3 |
| L5 | **(c)** | `function` is not a C keyword |
| L6 | **(c)** | Preliminary investigation / feasibility study, then requirement analysis |
</details>

---

### 2.13 Set M — the 2024-calibrated set (40 questions)

These are modelled directly on the blocks the **real 2024 Diploma paper** over-weighted and on
its actual question styles: networks (25% of Paper-I), C and C++ (45% of Paper-II), Internet
technology (15% of Paper-I), and version-specific MS Office. **If you only have time for one
set, do this one.**

#### M(a) — Networks and data communication (12 Q)

**M1.** Which is **not** one of the four fundamental characteristics determining the
effectiveness of a data communication system?
&nbsp;&nbsp;(a) Delivery &nbsp;(b) Accuracy &nbsp;(c) Timeliness/Jitter &nbsp;(d) Designing

**M2.** The five components of a data communication system are message, sender, receiver,
transmission medium and:
&nbsp;&nbsp;(a) Switch &nbsp;(b) Protocol &nbsp;(c) Router &nbsp;(d) Modem

**M3.** If a periodic signal decomposes into sine waves of 100, 300, 500, 700 and 900 Hz, its
bandwidth is:
&nbsp;&nbsp;(a) 200 Hz &nbsp;(b) 400 Hz &nbsp;(c) 800 Hz &nbsp;(d) 2500 Hz

**M4.** Which is **not** a polar line-coding scheme?
&nbsp;&nbsp;(a) NRZ &nbsp;(b) RZ &nbsp;(c) Biphase (Manchester) &nbsp;(d) AMI

**M5.** A measure of how fast data can *actually* be sent through a network — as opposed to the
theoretical channel capacity — is:
&nbsp;&nbsp;(a) Bandwidth &nbsp;(b) Throughput &nbsp;(c) Frequency &nbsp;(d) Latency

**M6.** Which port number is used by SMTP?
&nbsp;&nbsp;(a) 20 &nbsp;(b) 22 &nbsp;(c) 25 &nbsp;(d) 80

**M7.** A non-routable protocol designed for a single LAN segment, containing no network
address, is:
&nbsp;&nbsp;(a) NetBEUI &nbsp;(b) IPX &nbsp;(c) TCP &nbsp;(d) SMTP

**M8.** Which IEEE standard covers wireless LANs and hotspots?
&nbsp;&nbsp;(a) 802.3 &nbsp;(b) 802.5 &nbsp;(c) 802.11 &nbsp;(d) 802.16

**M9.** How many links are required to connect 10 PCs in a full mesh topology?
&nbsp;&nbsp;(a) 30 &nbsp;(b) 35 &nbsp;(c) 40 &nbsp;(d) 45

**M10.** A multiport bridge with buffering, whose many ports reduce collision traffic, is a:
&nbsp;&nbsp;(a) Repeater &nbsp;(b) Gateway &nbsp;(c) Router &nbsp;(d) Switch

**M11.** `FDEC:0:0:0:0:BBFF:0:FFFF` and `FDEC::BBFF:0:FFFF` are:
&nbsp;&nbsp;(a) Two different IPv6 addresses &nbsp;(b) The same IPv6 address
&nbsp;(c) MAC addresses &nbsp;(d) IPv4-mapped addresses

**M12.** Which is **not** a Transport-layer protocol?
&nbsp;&nbsp;(a) TCP &nbsp;(b) UDP &nbsp;(c) SCTP &nbsp;(d) SNMP

<details><summary><strong>Answers M1–M12</strong></summary>

| Q | Ans | Why |
|---|---|---|
| M1 | **(d)** | The four are delivery, accuracy, timeliness and jitter. "Designing" is the intruder |
| M2 | **(b)** | Message, sender, receiver, medium, **protocol** |
| M3 | **(c)** | Bandwidth = highest − lowest = 900 − 100 = **800 Hz** |
| M4 | **(d)** | AMI is **bipolar** (three levels: +, 0, −), not polar |
| M5 | **(b)** | Throughput = actual; bandwidth = potential |
| M6 | **(c)** | 25. (20/21 FTP, 22 SSH, 23 Telnet, 53 DNS, 80 HTTP, 110 POP3, 143 IMAP, 443 HTTPS) |
| M7 | **(a)** | NetBEUI — asked verbatim in 2024 |
| M8 | **(c)** | 802.11. (802.3 Ethernet, 802.5 Token Ring, 802.15 Bluetooth/piconet, 802.16 WiMAX) |
| M9 | **(d)** | n(n−1)/2 = 10 × 9 / 2 = **45**. (Each node needs n−1 = 9 ports) |
| M10 | **(d)** | Switch |
| M11 | **(b)** | `::` compresses one run of consecutive all-zero groups — they are identical |
| M12 | **(d)** | SNMP is Application layer |

**Memorise the port table.** It generated several 2024 questions and costs 5 minutes to learn.
</details>

#### M(b) — Internet technology (8 Q)

**M13.** Which service is **not** possible on an intranet?
&nbsp;&nbsp;(a) Private discussion groups &nbsp;(b) Access to legacy databases
&nbsp;(c) Teleconferencing &nbsp;(d) Public web sites

**M14.** Mail servers **receive and store** e-mail in mailboxes using:
&nbsp;&nbsp;(a) SMTP &nbsp;(b) POP3 &nbsp;(c) SNMP &nbsp;(d) FTP

**M15.** Gmail, Outlook, Thunderbird and Apple Mail are examples of:
&nbsp;&nbsp;(a) Message transfer agents &nbsp;(b) User agents &nbsp;(c) Mail servers &nbsp;(d) Webmail protocols

**M16.** A set of suggestions for courteous conduct on the Internet is called:
&nbsp;&nbsp;(a) Netizens &nbsp;(b) Netiquette &nbsp;(c) Flaming &nbsp;(d) Spam

**M17.** The oldest of the Internet services listed — a decade older than the World Wide Web — is:
&nbsp;&nbsp;(a) Usenet &nbsp;(b) Telnet &nbsp;(c) Podcast &nbsp;(d) VoIP

**M18.** Every file on the Internet has an address known as its:
&nbsp;&nbsp;(a) MAC address &nbsp;(b) IP address &nbsp;(c) URL &nbsp;(d) DNS record

**M19.** Match the connection type to its description:
a. VSAT b. Dial-up c. Cable d. Leased line
i. established using a modem ii. permanent dedicated telephone line
iii. earth-bound station used in satellite communication iv. via radio frequency over TV cable
&nbsp;&nbsp;(a) a-iii, b-i, c-iv, d-ii &nbsp;(b) a-i, b-iv, c-ii, d-iii
&nbsp;(c) a-ii, b-iv, c-iii, d-i &nbsp;(d) a-ii, b-iv, c-i, d-iii

**M20.** Smooth playback of streamed audio and video is made possible by:
&nbsp;&nbsp;(a) VoD &nbsp;(b) A playback buffer &nbsp;(c) A string buffer &nbsp;(d) A device buffer

<details><summary><strong>Answers M13–M20</strong></summary>

| Q | Ans | Why |
|---|---|---|
| M13 | **(d)** | An intranet is private by definition; hosting a *public* website is an Internet/extranet function |
| M14 | **(b)** | **SMTP pushes mail between servers; POP3/IMAP let the client retrieve from the mailbox.** Learn this split |
| M15 | **(b)** | User agents (UA). MTAs are the servers (sendmail, Postfix, Exchange) |
| M16 | **(b)** | Netiquette. *Netizens* = the people; *flaming* = abusive posting |
| M17 | **(a)** | Usenet (1980) predates the Web (1989–91). Telnet is older still but the 2024 key was Usenet — ⚠️ verify if it recurs |
| M18 | **(c)** | Uniform Resource Locator |
| M19 | **(a)** | a-iii, b-i, c-iv, d-ii |
| M20 | **(b)** | Playback (jitter) buffer |
</details>

#### M(c) — MS Office, version-specific (8 Q)

**M21.** In Excel, `######` displayed in a cell means:
&nbsp;&nbsp;(a) The formula is wrong &nbsp;(b) The column is not wide enough to show the content
&nbsp;(c) The cell is protected &nbsp;(d) The value is negative

**M22.** Which shortcut collapses or expands the Office ribbon?
&nbsp;&nbsp;(a) Ctrl+F1 &nbsp;(b) Ctrl+F2 &nbsp;(c) Alt+F1 &nbsp;(d) Ctrl+F4

**M23.** The ribbon — the "dynamic toolbar" of modern Office — replaced which older elements?
&nbsp;&nbsp;(a) The status bar &nbsp;(b) The menu bar and toolbars &nbsp;(c) The clipboard &nbsp;(d) The task pane

**M24.** To start a bulleted list automatically in Word you type:
&nbsp;&nbsp;(a) A hyphen and Enter &nbsp;(b) An asterisk `*` followed by a space
&nbsp;(c) A hash and a tab &nbsp;(d) Ctrl+B

**M25.** Which is **not** a valid page-border setting in Word?
&nbsp;&nbsp;(a) Box &nbsp;(b) Shadow &nbsp;(c) 3-D &nbsp;(d) Window

**M26.** By default, PowerPoint slides are sized for an on-screen show with a width : height
ratio of:
&nbsp;&nbsp;(a) 4:3 &nbsp;(b) 3:4 &nbsp;(c) 5:4 &nbsp;(d) 16:9

**M27.** In MS Access, the rows and columns of a table are respectively called:
&nbsp;&nbsp;(a) Fields and records &nbsp;(b) Records and fields &nbsp;(c) Queries and forms &nbsp;(d) Forms and reports

**M28.** The default file extension of an MS Access 2010 database is:
&nbsp;&nbsp;(a) .mdb &nbsp;(b) .accdb &nbsp;(c) .adp &nbsp;(d) .xlsx

<details><summary><strong>Answers M21–M28</strong></summary>

| Q | Ans | Why |
|---|---|---|
| M21 | **(b)** | Widen the column or reduce the font |
| M22 | **(a)** | Ctrl+F1 |
| M23 | **(b)** | Introduced in Office 2007, replacing menus and toolbars |
| M24 | **(b)** | `*` + space (AutoFormat As You Type). `1.` + space starts a numbered list |
| M25 | **(d)** | Box, Shadow, 3-D, Custom and None are the settings. "Window" is invented |
| M26 | **(a)** | **4:3** is the classic default; 16:9 became default in PowerPoint 2013+. **The 2024 key was 4:3** |
| M27 | **(b)** | Rows = records, columns = fields |
| M28 | **(b)** | `.accdb` from Access 2007; `.mdb` was 2003 and earlier |

**⚠️ Version warning.** 2024 asked explicitly about *Excel 2010's* `AGGREGATE()` function, where
`Translate` lives (the **Review** tab), the Paste Special dialog's options (Add, Transpose,
Skip blanks — but **not** `ISTEXT`, which is a worksheet function), and the Sunburst chart
(introduced in **Excel 2016**, so "not available in Excel 2007/2010"). If you can open a copy
of Office, **click through the tabs once** — 20 minutes of clicking beats 2 hours of reading.
</details>

#### M(d) — C and C++ (12 Q)

**M29.** Using C's hierarchy of operations, what is `i` after `i = 3/2*4 + 3/8 + 3;`?
&nbsp;&nbsp;(a) 7 &nbsp;(b) 10 &nbsp;(c) 8 &nbsp;(d) 12

**M30.** What does `%6.2f` specify in `printf("%6.2f", fahr);`?
&nbsp;&nbsp;(a) Decimal integer at least 6 wide
&nbsp;(b) Floating point, at least 6 wide, 2 digits after the decimal point
&nbsp;(c) Floating point, 2 wide, 6 after the point &nbsp;(d) 6 significant figures

**M31.** Which is **not** a reserved keyword in C?
&nbsp;&nbsp;(a) long &nbsp;(b) public &nbsp;(c) register &nbsp;(d) volatile

**M32.** Which variable name is **invalid** in C?
&nbsp;&nbsp;(a) last_name &nbsp;(b) Avg &nbsp;(c) branch name &nbsp;(d) INTEREST

**M33.** Arrange in decreasing order of precedence: A. `< > <= >=` B. `!` C. `=` D. `== !=`
&nbsp;&nbsp;(a) A, B, D, C &nbsp;(b) B, A, D, C &nbsp;(c) B, D, C, A &nbsp;(d) A, D, B, C

**M34.** What is printed?
```c
int a[15], i;
a[0] = 0; a[1] = 1;
for (i = 2; i < 15; ++i) a[i] = a[i-2] + a[i-1];
```
&nbsp;&nbsp;(a) The first 15 natural numbers &nbsp;(b) The first 15 Fibonacci numbers
&nbsp;(c) 15! &nbsp;(d) Powers of 2

**M35.** What does `printf(6 + "Happy Sunday");` print?
&nbsp;&nbsp;(a) Happy &nbsp;(b) Sunday &nbsp;(c) Happy Sunday &nbsp;(d) 6Happy Sunday

**M36.** A string constant in C is a one-dimensional character array terminated by:
&nbsp;&nbsp;(a) `'0'` &nbsp;(b) `'\0'` &nbsp;(c) `'\n'` &nbsp;(d) `EOF`

**M37.** Which is **not** a jump statement in C?
&nbsp;&nbsp;(a) goto &nbsp;(b) break &nbsp;(c) continue &nbsp;(d) switch

**M38.** Which operator **cannot** be overloaded in C++?
&nbsp;&nbsp;(a) `+` &nbsp;(b) `-` &nbsp;(c) `*` &nbsp;(d) `::`

**M39.** A special member function preceded by a tilde `~` is a:
&nbsp;&nbsp;(a) Constructor &nbsp;(b) Destructor &nbsp;(c) Friend function &nbsp;(d) Virtual function

**M40.** Convert the infix expression `A + B * C ^ D - (E / F - G)` to postfix.
&nbsp;&nbsp;Show your stack working.

<details><summary><strong>Answers M29–M40</strong></summary>

| Q | Ans | Working |
|---|---|---|
| M29 | **(a)** | Integer arithmetic, left to right for equal precedence: `3/2 = 1`, `1*4 = 4`; `3/8 = 0`; `4 + 0 + 3 = ` **7** |
| M30 | **(b)** | Width 6 (minimum, including the point), precision 2 |
| M31 | **(b)** | `public` is C++/Java, not C |
| M32 | **(c)** | Identifiers cannot contain a space |
| M33 | **(b)** | Unary `!` > relational `< >` > equality `== !=` > assignment `=`. **B, A, D, C** |
| M34 | **(b)** | Each term is the sum of the previous two — Fibonacci |
| M35 | **(b)** | The string literal is a `char*`; adding 6 skips "Happy " (6 characters) leaving `"Sunday"` |
| M36 | **(b)** | The null character `'\0'`, ASCII 0. Note `'0'` is ASCII 48 — the classic trap |
| M37 | **(d)** | `switch` is a selection statement. Jumps are `goto`, `break`, `continue`, `return` |
| M38 | **(d)** | The five non-overloadable operators: `::` `.` `.*` `?:` and `sizeof` |
| M39 | **(b)** | Destructor |
| M40 | — | See below |

**M40 worked (infix → postfix, stack algorithm):**
Precedence: `^` (right-associative) > `* /` > `+ -`.

| Token | Stack | Output |
|---|---|---|
| A | | A |
| + | + | A |
| B | + | A B |
| * | + * | A B |
| C | + * | A B C |
| ^ | + * ^ | A B C |
| D | + * ^ | A B C D |
| − | − (pop ^, *, + first) | A B C D ^ * + |
| ( | − ( | A B C D ^ * + |
| E | − ( | … E |
| / | − ( / | … E |
| F | − ( / | … E F |
| − | − ( − (pop /) | … E F / |
| G | − ( − | … E F / G |
| ) | − (pop − , discard parens) | … E F / G − |
| end | (pop −) | **A B C D ^ * + E F / G − −** |

**Answer: `ABCD^*+EF/G--`**

**Note on M29 and M35.** Both are pure-reasoning questions that reward 60 seconds of careful
work with a guaranteed +2. On the real paper, hunt these down in pass 2 — they are the highest
expected value per minute on the whole sheet.

**Note on undefined behaviour.** The 2024 paper included `printf("%d %d %d", a, ++a, a++)`,
whose result is **undefined in C** (unsequenced modification of `a`). The examiner wants the
right-to-left-evaluation answer that Turbo C produces. If you meet one of these, give the
textbook answer, do not argue with the paper. ⚠️ verify against your own compiler if curious,
but do not let it cost you time in the hall.
</details>

---

### 2.14 How to build your own 100-question mock (26 September)

Do **not** simply re-do the sets above in order — you will remember the answers, not the facts.
Instead:

1. Number every question in §2.1–§2.13 (there are 172).
2. Pick 100 of them **in a scrambled order** — e.g. write out the numbers 1–172, strike out 72
   at random, then answer the remainder in reverse order. **Keep all 40 of Set M in the 100** —
   it is the part calibrated to the real paper.
3. Sit them in **exactly 120 minutes** with a watch, and mark every answer on a numbered sheet
   (simulate the OMR).
4. Score with real marking: **+2 correct, −0.667 wrong, 0 blank.**
5. Record two numbers: your **score**, and your **hit rate on the questions you guessed**. If
   your guess hit rate is well below your own estimate, you are over-confident and should guess
   less; if it is above, you are leaving marks on the table.

**Target score for a comfortable position:** 140+/200 with fewer than 5 blanks.

---

## 3. Paper-I descriptive question bank

> Paper-I covers: introduction to computers, input/output devices, storage devices, motherboard,
> computer networks, Internet technology, computer languages, computer software (MS Office),
> computer viruses.
>
> **Format reminder:** Section A — any 8 of 10 × 5 marks. Section B — any 3 of 5 × 10.
> Section C — any 2 of 4 × 15.
>
> Each answer below is a **skeleton**: the points the examiner's marking scheme will contain.
> Write in that structure — definition, then diagram/table, then numbered points, then one line
> of application.

### 3.1 Section A — 5-mark questions (Paper-I)

**P1-A1. Define the terms bit, byte, nibble and word. [5]**
- Bit — binary digit, 0 or 1, smallest unit of data.
- Nibble — 4 bits; exactly one hexadecimal digit.
- Byte — 8 bits; the smallest addressable unit; holds one ASCII character.
- Word — the number of bits the CPU processes as a unit (16/32/64-bit); determines register and bus width.
- Close with the multiples table: 1 KB = 2¹⁰ B, 1 MB = 2²⁰ B, 1 GB = 2³⁰ B, 1 TB = 2⁴⁰ B.

**P1-A2. Differentiate between a compiler and an interpreter. [5]**
- Two-column table, 5 rows: unit of translation (whole program / line by line); output (object code / none, executes directly); speed of translation vs execution; error reporting (all at once / stops at first); memory requirement; examples (C, C++ / BASIC, Python).

**P1-A3. Convert (a) (1101101)₂ to decimal and octal, (b) (357)₈ to binary and hexadecimal. [5]**
- Show the positional working for each, do not just state the answer.
- (a) 1101101₂ = 64+32+8+4+1 = **109₁₀**; group in 3s: 1·101·101 = **155₈**.
- (b) 357₈ = 011 101 111 = **011101111₂**; regroup in 4s from the right: 0000 1110 1111 = **0EF₁₆ = EF₁₆**.
- One line stating the general rule: octal ↔ binary is 3 bits per digit, hex ↔ binary is 4 bits per digit.

**P1-A4. What is 2's complement? Subtract 27 from 45 using 8-bit 2's complement arithmetic. [5]**
- Definition: 1's complement (invert all bits) + 1; used so subtraction can be done by the adder.
- 45 = 00101101, 27 = 00011011.
- 1's comp of 27 = 11100100; 2's comp = 11100101.
- Add: 00101101 + 11100101 = 1 00010010.
- Discard the carry out of the MSB → **00010010 = 18** ✓.
- State the rule: carry out = 1 means the result is positive and the carry is discarded.

**P1-A5. Differentiate between SRAM and DRAM. [5]**
- Table: cell structure (flip-flop, 6 transistors / 1 transistor + 1 capacitor); refresh (not required / required every few ms); speed (faster / slower); density and cost per bit; power; typical use (cache / main memory).

**P1-A6. Differentiate between an impact and a non-impact printer, with examples. [5]**
- Mechanism (physical strike through ribbon / no contact — thermal, electrostatic, spray).
- Noise, speed, print quality, multi-part/carbon copy capability, running cost.
- Examples: impact — dot matrix, daisy wheel, line printer. Non-impact — inkjet, laser, thermal.

**P1-A7. Explain the working of an optical mouse. [5]**
- An LED (or laser) illuminates the surface at a shallow angle.
- A small CMOS image sensor photographs the surface thousands of times per second.
- A DSP compares successive images and computes the displacement (Δx, Δy).
- Displacement is sent to the PC (USB/PS-2) and moved on screen; resolution in DPI/CPI.
- Advantages over the ball mouse: no moving parts to clog, no cleaning, works on most surfaces, higher precision.

**P1-A8. What is cache memory? Why is it used? [5]**
- Definition: small, very fast memory between CPU and main memory.
- Rationale: CPU is far faster than DRAM; cache bridges the speed gap.
- Locality of reference — temporal and spatial — makes it work.
- Levels L1/L2/L3; hit, miss, hit ratio.
- One line: effective access time = h × t_cache + (1−h) × t_main.

**P1-A9. Differentiate between primary and secondary memory. [5]**
- Table: volatility, speed, capacity, cost/bit, direct CPU access, examples.

**P1-A10. What is a bar-code reader? Where is it used? [5]**
- A scanner that reads a printed pattern of parallel bars and spaces of varying width.
- Light source + photodetector measures reflected light; dark bars absorb, spaces reflect.
- The pulse train is decoded into digits by the decoder.
- Standards: UPC, EAN, Code 39.
- Applications: retail point of sale, inventory, library issue, courier tracking.

**P1-A11. What is the function of the ALU and the Control Unit? [5]**
- ALU: performs all arithmetic (add, subtract, multiply, divide) and logic (AND, OR, NOT, compare, shift) operations; works with accumulator and status/flag register.
- CU: fetches, decodes, sequences; generates timing and control signals; directs data movement between units; does not process data itself.
- Together = CPU. One-line analogy: CU is the manager, ALU is the workshop.

**P1-A12. Differentiate between CRT and LCD monitors. [5]**
- Table: technology (electron gun + phosphor / liquid crystals + backlight), size and weight, power consumption, radiation and flicker, geometric distortion, native resolution, viewing angle, cost, life.

**P1-A13. What is a plotter? How does it differ from a printer? [5]**
- Definition: an output device that draws continuous lines by moving a pen or cutting head over paper under vector control.
- Types: drum plotter, flatbed plotter, inkjet/electrostatic plotter.
- Difference: printer prints dots to form an image (raster); plotter draws continuous vector lines.
- Applications: engineering drawings, CAD, architectural plans, maps, large-format posters.

**P1-A14. Explain the terms track, sector, cylinder and cluster. [5]**
- Track: one concentric circle on one platter surface.
- Sector: the smallest physically addressable division of a track, traditionally 512 bytes.
- Cylinder: the set of all tracks of the same number on all platter surfaces — reachable without moving the head assembly.
- Cluster: the smallest unit the file system will allocate, = 1, 2, 4 … sectors; the cause of slack space.
- Add: capacity = heads × cylinders × sectors/track × bytes/sector.

**P1-A15. What is BIOS? State its functions. [5]**
- Basic Input Output System — firmware stored in a ROM/flash chip on the motherboard.
- Functions: (1) POST — Power-On Self Test; (2) initialise and identify hardware; (3) locate the boot device and load the bootstrap loader; (4) provide low-level I/O service routines; (5) hold the CMOS setup utility.
- Distinguish BIOS (the program, in ROM) from CMOS (the RAM holding its settings, kept alive by the battery).

**P1-A16. Differentiate between the Internet and an intranet. [5]**
- Table: scope (global public / single organisation, private), ownership, access control, security, content, cost, examples.

**P1-A17. List and explain briefly any five services provided by the Internet. [5]**
- Email; chat (text / voice / video); bulletin boards and newsgroups; video conferencing; FTP; Telnet; WWW. Pick five, one or two lines each with the protocol name.

**P1-A18. What is a search engine? Name any four. [5]**
- Definition: a program/website that indexes web pages and returns links matching a query.
- Three components: crawler/spider, indexer and database, query processor + ranking.
- Examples: Google, Bing, Yahoo, DuckDuckGo. Distinguish from a *directory* (human-curated) and a *browser* (client software).

**P1-A19. What is a computer virus? How does it differ from a worm? [5]**
- Virus: a program that attaches itself to a host program or boot sector and replicates when the host runs.
- Worm: a stand-alone self-replicating program that spreads over a network, needs no host and no user action.
- Table of 4 differences: host required, propagation, user action, typical damage.

**P1-A20. List any five symptoms by which you may recognise a virus infection. [5]**
- Unexplained slowdown; unexpected reduction in free memory or disk space; files change size, date or disappear; frequent crashes and unusual error messages; programs take longer to load or fail; strange messages/graphics; antivirus disabled; unexpected disk activity or network traffic; boot failure.

**P1-A21. What are the characteristics of a good programming language? [5]**
- Simplicity and readability; naturalness for the problem domain; abstraction support; portability; efficiency of generated code; well-defined syntax and semantics; strong error detection; good library and tool support; maintainability; cost of learning and use.

**P1-A22. Differentiate between system software and application software. [5]**
- Purpose (manage/operate the machine vs solve a user problem); dependence; who writes it; generality; runs in background vs foreground; examples (OS, compiler, device driver, utility vs MS Word, Photoshop, PageMaker, Tally).

### 3.2 Section B — 10-mark questions (Paper-I)

**P1-B1. Explain the generations of computers with the defining technology, characteristics and examples of each. [10]**
- One-line intro: a generation is defined by the *switching technology* used.
- Then a five-row table: Generation | Period | Technology | Memory | Language | Speed | Examples | Limitations.
  1. 1st (1946–1958): vacuum tube; magnetic drum; machine language; ms; ENIAC, EDVAC, EDSAC, UNIVAC-I; huge, hot, unreliable.
  2. 2nd (1959–1964): transistor; magnetic core; assembly and early HLL (FORTRAN, COBOL); µs; IBM 1401, IBM 7094, CDC 1604.
  3. 3rd (1965–1971): IC (SSI/MSI); semiconductor + core; HLL, multiprogramming OS; ns; IBM 360/370, PDP-8, PDP-11.
  4. 4th (1971– ): LSI/VLSI microprocessor; semiconductor RAM; GUI OS, 4GLs; ns/ps; IBM PC, Apple II, Pentium.
  5. 5th (present/future): ULSI, parallel processing, AI; natural-language interfaces; quantum and neural research.
- Close: each generation reduced size, cost and power while increasing speed, reliability and storage.

**P1-B2. Classify computers on the basis of size and capacity, and compare them. [10]**
- Comparison table: Type | Users | Processing power | Memory/storage | Cost | Typical applications | Examples.
- Supercomputer — fastest, measured in FLOPS, used for weather, nuclear, molecular modelling; PARAM, CRAY, Sunway.
- Mainframe — very high throughput, thousands of concurrent users/terminals, huge I/O; banking, railways, census; IBM z-series.
- Minicomputer — mid-range, departmental, tens–hundreds of users; PDP-11, VAX.
- Workstation — powerful single-user, engineering/CAD/graphics; Sun SPARC, HP, Silicon Graphics.
- Microcomputer — single-user PC/laptop/palmtop; based on a microprocessor.
- Close with a note that the boundaries have blurred: a modern PC outruns a 1990 mainframe.

**P1-B3. Explain, with a labelled block diagram, the basic functional organisation of a computer. [10]**
- Diagram: draw **Input Unit** on the left → into **CPU** box in the centre, and **Output Unit** on the right. Inside the CPU box draw two sub-boxes: **ALU** and **Control Unit**. Below/beside the CPU draw **Memory Unit (Primary)**, connected both ways to CPU. Below that draw **Secondary / Mass Storage** connected to memory and CPU. Use **solid arrows for data flow** (input → memory → ALU → memory → output) and **dashed arrows for control signals** radiating from the CU to every other block.
- Then explain each block: input unit (accept, convert to binary, supply to memory); memory unit (store program and data, intermediate and final results); ALU (arithmetic and logic); control unit (fetch–decode–execute, timing and control); output unit (convert from binary to human-readable); mass storage (permanent bulk storage).
- Mention the stored-program (von Neumann) concept in one line.

**P1-B4. Compare dot matrix, inkjet and laser printers. [10]**
- Lead with the impact/non-impact distinction, then the table (this is the answer's centre of gravity):

| Feature | Dot matrix | Inkjet | Laser |
|---|---|---|---|
| Type | Impact | Non-impact | Non-impact |
| Mechanism | Pins strike an inked ribbon | Nozzles spray tiny ink droplets | Laser writes a charge image on a drum; toner adheres; heat fuses it |
| Speed | 30–600 CPS (slow) | 4–20 PPM (medium) | 8–100+ PPM (fast) |
| Print quality | Low (9/24-pin, visible dots) | Good, 600–4800 DPI, excellent colour | Excellent, sharp text, 600–2400 DPI |
| Noise | Very noisy | Quiet | Quiet |
| Initial cost | Low | Low | High |
| Running cost per page | **Lowest** | Highest (cartridges) | Low–medium |
| Colour | Limited | Excellent | Good, but costly |
| Carbon copies | **Yes** | No | No |
| Best for | Invoices, multi-part stationery, harsh environments | Home, photos, low volume colour | Office, high volume text |

- Then a short paragraph on the working of each, and a closing recommendation line.

**P1-B5. Describe the components of a hard disk drive and how data is organised on it. [10]**
- Components with function: platters (aluminium/glass, magnetic coating, both surfaces used); spindle and spindle motor (rotates at 5400/7200/10000/15000 RPM); read/write heads (one per surface, fly on an air bearing microns above); actuator arm and voice-coil actuator (positions heads); head-actuator assembly moves as one; logic/controller board; air filter; sealed HDA (head-disk assembly).
- Organisation: track → sector → cylinder → cluster; low-level format writes the sector structure; partition table and MBR; boot sector; FAT/MFT; root directory; data area.
- Capacity formula: `capacity = heads × cylinders × sectors per track × bytes per sector`, with a worked example: 4 heads × 16383 cylinders × 63 sectors × 512 B ≈ 2.1 GB (the old CHS limit).
- Access time = seek time + rotational latency + transfer time. Average rotational latency at 7200 RPM = (60/7200)/2 = **4.17 ms** — show this calculation.

**P1-B6. Explain the read and write mechanism of a CD and a DVD. [10]**
- Physical structure: polycarbonate substrate, reflective aluminium (or dye/alloy) layer, lacquer, label; a **single continuous spiral track** from the centre outwards (unlike a disk's concentric tracks).
- Reading: a laser diode beam is focused on the track; a **land** reflects the beam strongly; a **pit** is 1/4 wavelength deep, so reflection from a pit interferes destructively and reflects weakly; the photodetector sees the intensity change. **A transition pit↔land = 1; no transition = 0** (EFM encoding).
- CD-R writing: a high-power laser burns/darkens an organic dye layer, permanently creating low-reflectivity spots — write once.
- CD-RW writing: a phase-change alloy (Ag-In-Sb-Te) is switched between **crystalline (reflective)** and **amorphous (non-reflective)** states by different laser powers — rewritable, ~1000 cycles.
- Comparison table:

| Feature | CD | DVD |
|---|---|---|
| Laser wavelength | 780 nm (infra-red) | 650 nm (red) |
| Track pitch | 1.6 µm | 0.74 µm |
| Minimum pit length | 0.83 µm | 0.4 µm |
| Capacity | 650–700 MB | 4.7 GB single layer / 8.5 GB dual layer / 17 GB double sided dual layer |
| Layers | 1 | Up to 2 per side, 2 sides |
| 1x data rate | 150 KB/s | 1.38 MB/s |

- Add Blu-ray for contrast: 405 nm blue-violet laser, 25 GB per layer.
- Close: shorter wavelength → smaller focused spot → smaller pits → more capacity. That single sentence explains the whole progression.

**P1-B7. Explain the ROM family: ROM, PROM, EPROM, EEPROM and Flash. [10]**
- Common property: non-volatile, retains contents without power, used for firmware/BIOS.
- Table: Type | Programmed by | Erasable? | Erase method | Erase granularity | Reprogram cycles | Typical use.
  - **Mask ROM** — at manufacture, by mask; not erasable; mass production firmware; cheapest per unit at volume.
  - **PROM** — once, by the user, using a PROM programmer that blows fuses; not erasable; OTP.
  - **EPROM** — electrically programmed, erased by UV light through a quartz window, ~20 min, whole chip at once; ~100–1000 cycles.
  - **EEPROM** — electrically programmed and erased, **byte by byte, in circuit**; ~10⁴–10⁶ cycles; used for CMOS settings and small config stores.
  - **Flash** — a type of EEPROM erased in **blocks/sectors** rather than bytes, hence much faster and denser; NOR (byte-readable, for BIOS) vs NAND (page-based, for SSD/pen drives).
- Close with the trend line: each step made reprogramming easier and cheaper, which is why modern BIOS is flash and can be updated in software.

**P1-B8. Explain the memory hierarchy with a diagram, comparing cache, primary and secondary memory by capacity and speed. [10]**
- Diagram: a pyramid. Apex at the top = **Registers**, then **L1 cache**, **L2/L3 cache**, **Main memory (RAM)**, **Secondary storage (HDD/SSD)**, base = **Tertiary/off-line (tape, optical)**. Label the left side of the pyramid "**increasing speed and cost per bit ↑**" and the right side "**increasing capacity ↑ (downwards)**".
- Table:

| Level | Typical capacity | Typical access time | Cost per bit | Managed by | Volatile |
|---|---|---|---|---|---|
| Registers | tens–hundreds of bytes | < 1 ns | Highest | Compiler/CPU | Yes |
| L1 cache | 32–128 KB | 1–2 ns | Very high | Hardware | Yes |
| L2/L3 cache | 256 KB – 32 MB | 3–20 ns | High | Hardware | Yes |
| Main memory | 4–64 GB | 50–100 ns | Medium | OS | Yes |
| SSD | 128 GB – 4 TB | 25–100 µs | Low | OS/file system | No |
| Hard disk | 500 GB – 20 TB | 5–15 ms | Very low | OS/file system | No |
| Tape / optical | 100 GB – PB | seconds–minutes | Lowest | Operator | No |

- Explain the principle of locality (temporal, spatial) that makes the hierarchy work, hit ratio, and effective access time with a one-line worked example: h = 0.9, t_cache = 2 ns, t_main = 100 ns → EAT = 0.9(2) + 0.1(100) = **11.8 ns**.

**P1-B9. Explain the OSI reference model and the function of each layer. [10]**
> Deep treatment: `CORE_05_ComputerNetworks.md`. Diploma answer needs the 7-layer table with one function line and the PDU name for each, plus a mnemonic ("All People Seem To Need Data Processing", top-down).

**P1-B10. Explain the different network topologies with diagrams and compare them. [10]**
> Deep treatment: `CORE_05_ComputerNetworks.md`. Diploma answer: sketch bus, star, ring, mesh, tree, hybrid; table comparing cable cost, ease of installation, fault tolerance, fault isolation, expandability, performance under load.

**P1-B11. Explain the different options for connecting to the Internet and compare them. [10]**
- Dial-up: modem over PSTN, up to 56 kbps, ties up the phone line, per-minute billing, obsolete.
- Leased line: dedicated permanent point-to-point circuit, symmetric, fixed monthly cost, high reliability, for organisations.
- ISDN: digital over copper; BRI = 2B + D = 2 × 64 + 16 kbps; PRI = 30B + D in India/Europe.
- DSL/broadband: ADSL over the same copper, asymmetric, always on.
- VSAT: Very Small Aperture Terminal, satellite dish + indoor unit, works anywhere including remote areas, high latency (~500 ms round trip via geostationary), weather-affected, expensive.
- Cable, leased fibre, 3G/4G/5G mobile for completeness.
- Comparison table: speed, cost, availability, latency, symmetry, typical user.

**P1-B12. What is a computer virus? Explain how it works and how to protect a PC against it. [10]**
> Full treatment in `CSDip_03_SystemAnalysisAndViruses.md` §1. Skeleton: definition; life cycle (dormant → propagation → triggering → execution); how it attaches and gains control; then the protection list (updated antivirus with real-time scanning, OS and application patching, firewall, scan removable media, disable macros, avoid unknown attachments and pirated software, least-privilege accounts, regular verified backups, write-protect, boot order and BIOS password).

**P1-B13. Explain the features of MS Excel, the categories of functions available, and the components of a chart. [10]**
> Full treatment in `CSDip_02_MSOffice_and_DOS.md`. Skeleton: features (grid of cells, automatic recalculation, formulas and 400+ built-in functions, formatting, sorting/filtering, charts, pivot tables, what-if analysis, sharing); function categories with an example of each (Math & Trig — SUM, ROUND; Statistical — AVERAGE, COUNT, MAX; Logical — IF, AND, OR; Text — LEFT, CONCATENATE, LEN; Date & Time — NOW, TODAY, DATEDIF; Lookup & Reference — VLOOKUP, HLOOKUP, INDEX, MATCH; Financial — PMT, NPV, FV; Database — DSUM, DCOUNT); chart components (chart area, plot area, category/X axis, value/Y axis, data series, data points, data labels, legend, chart title, axis titles, gridlines) and chart types.

**P1-B14. Explain Mail Merge in MS Word — what it is, when it is used, and the steps involved. [10]**
> Full treatment in `CSDip_02_MSOffice_and_DOS.md`. Skeleton: definition (combining a main document with a data source to produce many personalised copies); the two/three files involved; the six-step wizard in order (select document type → select starting document → select recipients → write your letter and insert merge fields → preview your letters → complete the merge); insert merge field / address block / greeting line; filtering and sorting recipients; merge to new document vs directly to printer vs to email; applications (circulars, invitations, envelopes, mailing labels, certificates).

### 3.3 Section C — 15-mark questions (Paper-I)

**P1-C1. Explain in detail the components of a motherboard, with a labelled diagram. [15]**
> Full treatment in `CSDip_01_HardwareAndDevices.md` §9. Skeleton:
- Definition and role — the main printed circuit board carrying the chipset, sockets, slots and connectors that interconnect every component.
- **Diagram to draw:** a large rectangle. Top-left = **CPU socket** with heatsink mount holes. To its right = 2–4 long **DIMM slots**. Below the socket = **MCH / Northbridge** (with heatsink), joined to the CPU by the **FSB / system bus**, to the DIMM slots by the **memory bus**, and downwards to the **AGP / PCIe x16** slot. Below the MCH = **ICH / Southbridge**, joined by an internal link. Around the ICH: **PCI slots** (row on the left-bottom), **primary and secondary IDE connectors** and **SATA ports** (right edge), **floppy connector (34-pin)**, **BIOS ROM chip**, **CMOS coin battery**, **super-I/O chip** driving the **serial, parallel, PS/2 keyboard (purple) and mouse (green)** back-panel connectors, **USB headers**, front-panel header. Top-right = **24-pin ATX SMPS connector**; near the CPU = **4/8-pin 12 V connector**. Add the **crystal oscillator / RTC** near the Southbridge, and **VRM capacitors** near the CPU socket.
- Then a component-by-component table: name | where it sits | function.
- **Memory Controller Hub (Northbridge)** — the fast half of the chipset. Handles: **system bus / FSB** to the CPU; the **processor socket** (LGA/PGA/ZIF, pin count, one CPU per socket); **DIMM slots** (168-pin SDRAM, 184-pin DDR, 240-pin DDR2/DDR3, 288-pin DDR4; notches prevent wrong insertion); **AGP** (dedicated 32-bit 66 MHz graphics port, 1x/2x/4x/8x, superseded by PCI Express x16).
- **I/O Controller Hub (Southbridge)** — the slow half. Handles: **primary and secondary IDE channels** (40-pin, two devices each, master/slave jumpers, 80-conductor cable for UDMA); **PCI bus** (32-bit, 33 MHz, 133 MB/s, plug-and-play); **serial ports** (DB-9, RS-232, bit-at-a-time, COM1/COM2); **parallel port** (DB-25, byte-at-a-time, LPT1, SPP/EPP/ECP modes); **PS/2 ports** (6-pin mini-DIN, purple keyboard / green mouse); **USB** (4-pin, hot-pluggable, up to 127 devices via hubs, 1.5/12/480 Mbps for USB 1.1/2.0, 5 Gbps USB 3.0, supplies 5 V power).
- **BIOS ROM** — firmware; POST, hardware initialisation, bootstrap loading, setup utility; flash so it can be updated.
- **CMOS battery** — CR2032 3 V lithium; keeps the CMOS RAM (BIOS settings) and RTC alive when the PSU is off; symptoms of failure.
- **Real Time Clock** — a low-power counter driven by a **32.768 kHz** crystal, keeping date and time independent of the OS.
- **SMPS connector** — ATX 20/24-pin main connector plus the 4-pin/8-pin 12 V CPU connector; rails at +3.3 V, +5 V, +12 V, −12 V, +5 V standby; the PS_ON signal lets the OS switch the supply off.
- Close: modern boards have collapsed the MCH into the CPU die, leaving a single PCH — mention as a one-line "current practice" note, it shows awareness. **⚠️ verify** whether the examiner expects the legacy two-chip model; the syllabus wording (MCH + ICH) implies they do, so **answer the legacy model first** and add the modern note at the end.

**P1-C2. Explain the various storage devices used in a computer system, classifying them and comparing capacity, speed and cost. [15]**
- Classification tree: Primary (semiconductor: RAM — SRAM/DRAM; ROM — mask/PROM/EPROM/EEPROM/flash) | Secondary (magnetic: floppy, hard disk, tape; optical: CD/DVD/Blu-ray; solid state: SSD, pen drive, memory card) | Tertiary/offline (tape libraries, optical jukebox).
- Then take each in turn with construction, working, capacity and use, as in §3.2 B5–B8.
- Grand comparison table: device | capacity | access time | transfer rate | cost per GB | volatility | access method (random/sequential).
- Close with the hierarchy diagram and the trade-off statement.

**P1-C3. Explain the number systems used in computers and demonstrate all the conversions between them with examples. [15]**
- Define positional number systems, base/radix, and the four systems with their digit sets.
- Table of the six conversion directions with the method and a worked example of each:
  1. Decimal → binary (repeated division by 2, read remainders upwards): 156 → 10011100.
  2. Binary → decimal (positional weights): 10011100 = 128+16+8+4 = 156.
  3. Decimal → octal / hex (repeated division by 8 / 16): 156 → 234₈, 9C₁₆.
  4. Octal/hex → decimal (positional weights).
  5. Binary ↔ octal (3-bit groups) and binary ↔ hex (4-bit groups) — the shortcut, no arithmetic needed.
  6. Octal ↔ hex (go via binary).
- Fractional conversion: repeated multiplication by 2, read integer parts downwards. Worked: 0.6875 → 0.1011.
- Then binary arithmetic: addition rules and a worked sum; subtraction by borrowing; **1's complement subtraction** (add the 1's complement, then **end-around carry**) and **2's complement subtraction** (add the 2's complement, discard the carry) — both fully worked, and both cases (positive and negative results).
- Close with the reason all this matters: hardware can only add, so subtraction is done by complement addition, saving a subtractor circuit.

**P1-C4. Explain the input and output devices of a computer in detail. [15]**
- Definition and the role of the I/O units in the block diagram.
- Input devices, each with a short working description: keyboard (types — 84-key, 101/104-key enhanced, ergonomic, membrane vs mechanical, virtual; key groups — alphanumeric, numeric keypad, function, cursor control, special/modifier; how a keystroke is scanned into a scan code); mouse (mechanical/ball, optical, laser, wireless; scroll wheel; DPI); trackball, joystick, light pen, touch screen, digitiser tablet; scanners (flatbed, handheld, drum, sheet-fed; resolution in DPI, colour depth); OCR; OMR; MICR; bar-code reader; MIDI, microphone, webcam; smart-card reader; biometric devices.
- Output devices: monitors (CRT working with electron gun/deflection/phosphor/shadow mask, refresh rate, resolution, dot pitch; LCD working with liquid crystal, polarisers, backlight, TFT active matrix; LED and plasma for completeness) with the CRT vs LCD table; printers (impact vs non-impact, the three-way comparison table, working of each); plotters (drum, flatbed); speakers; projectors; COM (computer output on microfilm) for completeness.
- Close: a table of "device → is it input, output, or both" (touch screen, modem, NIC, hard disk and multifunction printer are **both**) — a very common MCQ and a good closing paragraph.

**P1-C5. Explain the features of MS Word and any five of its important facilities in detail. [15]**
> Full treatment in `CSDip_02_MSOffice_and_DOS.md`. Skeleton: what a word processor is; the Word window components (title bar, ribbon and tabs, quick access toolbar, rulers, scroll bars, status bar, view buttons, zoom); creating, saving and editing; then five facilities in depth with steps: (1) formatting — character, paragraph, page; (2) tables — insert, merge/split, borders and shading, formula; (3) header/footer and footnote/endnote; (4) Mail Merge steps in order; (5) columns, Drop Cap, WordArt, text boxes/callouts/captions; plus spelling & grammar and AutoCorrect. Give menu paths.

**P1-C6. Discuss the types of computer viruses, how to recognise an infection and how to deal with it. [15]**
> Full treatment in `CSDip_03_SystemAnalysisAndViruses.md`. Skeleton: definition and life cycle; the six syllabus types explained separately with an example each (command processor infection, boot sector infection, executable file infection, file-specific infection, memory resident infection, macro virus); other malware for contrast (worm, trojan, ransomware, spyware, logic bomb); protection measures; symptoms of infection; and the step-by-step removal procedure (isolate → boot clean → scan → quarantine/clean → restore from backup → change passwords → patch the entry point).

**P1-C7. Explain the seven layers of the OSI reference model in detail, with the function of each, and compare it with TCP/IP. [15]**
> Deep treatment: `CORE_05_ComputerNetworks.md`. Diploma-level answer: 7-layer diagram, function table with PDU and example protocols/devices per layer, encapsulation walkthrough of one message top to bottom, then the OSI vs TCP/IP comparison table (layers, development order, protocol dependence, transport reliability, practical use).

---

## 4. Paper-II descriptive question bank

> Paper-II covers: operating systems (with MS-DOS and Windows), UNIX, DBMS, System Analysis and
> Design, and programming in C.
> Same structure: Section A any 8 of 10 × 5, Section B any 3 of 5 × 10, Section C any 2 of 4 × 15.

### 4.1 Section A — 5-mark questions (Paper-II)

**P2-A1. Define an operating system and state any five of its functions. [5]**
- Definition: system software acting as an interface between the user/applications and the hardware, managing resources.
- Functions: process management; memory management; file management; device/IO management; security and protection; user interface; job/resource scheduling; error detection; accounting.

**P2-A2. Differentiate between multiprogramming and multitasking. [5]**
- Multiprogramming: several programs in memory, CPU switched when the running one blocks on I/O; goal = CPU utilisation; batch context.
- Multitasking: time-shared multiprogramming; CPU switched on a time quantum; goal = interactive response; each user's task appears to run simultaneously.
- Table with 4 rows: switching trigger, objective, user interaction, example.

**P2-A3. Differentiate between internal and external DOS commands, with examples. [5]**
- Internal: built into COMMAND.COM, resident in memory, execute immediately, no disk file — DIR, COPY, DEL, REN, TYPE, CLS, MD, CD, RD, DATE, TIME, VER, PATH, PROMPT.
- External: separate executable files (.COM/.EXE) in the DOS directory, must be found on disk and loaded before running, can be deleted or missing — FORMAT, CHKDSK, XCOPY, ATTRIB, DISKCOPY, LABEL, TREE, EDIT, FDISK, SORT, FIND, MORE.
- Table: location, memory residency, speed, dependence on the DOS directory, effect if deleted.

**P2-A4. What are the DOS system files? State the function of each. [5]**
- IO.SYS — low-level device I/O routines, extends and interfaces with the BIOS; loaded first.
- MSDOS.SYS — the DOS kernel; file management, memory management, system calls (INT 21h).
- COMMAND.COM — the command interpreter/shell; displays the prompt, contains the internal commands, loads and runs external programs.
- Add: IO.SYS and MSDOS.SYS are hidden, read-only, system files; all three are placed by `FORMAT /S` or `SYS C:`.

**P2-A5. Explain the difference between .BAT, .COM and .EXE files. [5]**
- Table: file type (ASCII text vs binary vs binary); who executes it (COMMAND.COM interprets line by line / loaded and run directly); size limit (none / ≤64 KB one segment / no practical limit, multi-segment); relocation header (n/a / none / yes); load speed; typical use.
- End with the execution priority: **.COM before .EXE before .BAT**.

**P2-A6. What is booting? Differentiate between cold and warm booting. [5]**
- Booting: the process of loading the operating system into main memory and preparing the machine for use.
- Cold boot: from power-off; full POST is run; started by the power switch.
- Warm boot: with power already on; POST is skipped or shortened; Ctrl+Alt+Del or the reset button.
- One-line note on why warm booting is faster and when a cold boot is necessary (hardware left in a bad state).

**P2-A7. Explain the structure of the UNIX operating system. [5]**
- Layered diagram: **Hardware** at the centre → **Kernel** → **Shell** → **Application/utility programs** → **User** at the outside. Draw as concentric circles.
- Kernel: the core; memory, process, file and device management; the only layer that talks to the hardware.
- Shell: the command interpreter; reads commands, expands wildcards, handles redirection and pipes; types — Bourne (sh), C (csh), Korn (ksh), Bash.
- Utilities: the several hundred small programs (`ls`, `grep`, `wc`, `sort` …).

**P2-A8. What is the difference between `cmp`, `comm` and `diff`? [5]**
- `cmp` — byte-by-byte comparison of two files; reports the byte and line of the **first** difference; works on binary files too.
- `comm` — compares two **sorted** files and produces three columns: lines only in file1, only in file2, in both.
- `diff` — reports the **changes needed** to convert file1 into file2, in an editor-script form (`a` append, `c` change, `d` delete).
- One line each on typical use.

**P2-A9. Define data, information, database and DBMS. [5]**
- Data: raw unprocessed facts and figures.
- Information: data processed into a form that is meaningful and useful for decision-making.
- Database: an organised, integrated, shared collection of related data stored with controlled redundancy.
- DBMS: the software that defines, creates, stores, manipulates, controls and maintains a database.
- Close with the data → processing → information diagram in one line.

**P2-A10. What are the functions of a Database Administrator (DBA)? [5]**
- Schema definition and modification; storage structure and access-method definition; granting authorisation and access control; integrity constraint specification; performance monitoring and tuning; backup and recovery planning; liaison with users; data dictionary maintenance.

**P2-A11. Differentiate between a base table and a view. [5]**
- Base table: physically stored, has its own data, named relation in the database.
- View: a virtual/derived table defined by a stored query; no data of its own; recomputed on reference; provides logical data independence and security; may or may not be updatable.
- Table with 5 rows.

**P2-A12. Define a system. State any five characteristics of a system. [5]**
- Definition: an organised set of interrelated and interdependent components working together towards a common objective.
- Characteristics: organisation; interaction; interdependence; integration; central objective; boundary and environment; inputs/processing/outputs; feedback and control.

**P2-A13. Differentiate between an open system and a closed system. [5]**
- Open: exchanges matter, energy or information with its environment; adapts; e.g. a business information system, a living organism.
- Closed: isolated, no environmental interaction, self-contained, tends to decay/entropy; only relatively closed systems exist in practice; e.g. a sealed chemical reaction, a stand-alone offline program.
- Table with 4–5 rows.

**P2-A14. What is the role of a system analyst? [5]**
- Investigator and fact-finder; problem definer; analyst of the existing system; designer of the proposed system; liaison and communicator between users and programmers; change agent; motivator; project manager; documenter; evaluator after implementation.

**P2-A15. Differentiate between an algorithm and a flowchart. [5]**
- Algorithm: a finite, ordered, unambiguous step-by-step *textual* procedure to solve a problem.
- Flowchart: a *graphical/pictorial* representation of the same, using standard symbols.
- Table: representation, symbols, ease of understanding, ease of modification, language dependence, suitability for complex logic.
- List the flowchart symbols: oval (start/stop), parallelogram (input/output), rectangle (process), diamond (decision), arrow (flow line), circle (connector).

**P2-A16. Explain the hierarchy (precedence) of operators in C. [5]**
- Table from highest to lowest: `()` `[]` `.` `->` → unary `! ~ ++ -- + - * & sizeof` (right-to-left) → `* / %` → `+ -` → `<< >>` → `< <= > >=` → `== !=` → `&` → `^` → `|` → `&&` → `||` → `?:` → assignment `= += -= …` (right-to-left) → comma `,`.
- One worked example: `a = 2 + 3 * 4 % 5` → `3*4 = 12`, `12%5 = 2`, `2+2 = 4`.

**P2-A17. Differentiate between `while` and `do-while` loops in C. [5]**
- Entry-controlled vs exit-controlled; condition tested before vs after the body; minimum executions 0 vs 1; syntax including the semicolon after `while` in `do-while`; when each is preferable.
- Add a tiny code example of each producing different output when the condition is false at the start.

**P2-A18. Differentiate between `printf`/`scanf` and `getchar`/`putchar`. [5]**
- Formatted vs unformatted I/O; multiple values with conversion specifiers vs a single character; header `<stdio.h>` for all; buffering; `getch`/`putch` from `<conio.h>` are non-standard, non-echoing, DOS/Turbo-C specific.

**P2-A19. What is the difference between `break` and `continue` in C? [5]**
- `break`: terminates the innermost loop or `switch` entirely; control passes to the statement after it.
- `continue`: skips the rest of the current iteration and jumps to the next iteration's update/test; only valid in loops.
- Small code trace for both over `for(i=1;i<=5;i++)`.

**P2-A20. Differentiate between FCFS and SJF scheduling. [5]**
- Table: selection criterion, preemption, average waiting time, starvation possibility, convoy effect, implementability (SJF needs the burst time to be known/estimated).

**P2-A21. What is thrashing? [5]**
- Definition: a state in which the system spends more time paging (swapping pages in and out) than executing processes.
- Cause: degree of multiprogramming too high → each process's resident set falls below its working set → page fault rate explodes → CPU utilisation collapses → the scheduler adds more processes → worse.
- Draw the CPU-utilisation vs degree-of-multiprogramming curve (rises, peaks, then falls off a cliff).
- Cures: working-set model, page-fault frequency control, reduce multiprogramming, add memory, local page replacement.

**P2-A22. Explain the terms authentication, authorisation and access control in database security. [5]**
- Authentication: verifying *who you are* (username/password, biometrics, certificates).
- Authorisation: deciding *what you are allowed to do* (GRANT/REVOKE of SELECT, INSERT, UPDATE, DELETE on objects).
- Access control: the mechanism that enforces authorisation at access time — discretionary (DAC, owner grants), mandatory (MAC, labels/clearances), role-based (RBAC).
- Enforcement: the DBMS checks every request against the authorisation catalogue; views and stored procedures are used to restrict at row/column granularity; audit trails record attempts.

### 4.2 Section B — 10-mark questions (Paper-II)

**P2-B1. Explain the evolution of operating systems from serial processing to multitasking. [10]**
> Deep treatment: `CORE_03_OperatingSystems.md`. Skeleton: serial/manual processing (no OS, sign-up sheet, setup time); simple batch (resident monitor, JCL, job sequencing); multiprogrammed batch (several jobs in memory, overlap CPU with I/O, needs memory protection and interrupts); time-sharing/multitasking (quantum, interactive terminals, CTSS/MULTICS/UNIX); multiprocessing (multiple CPUs, symmetric vs asymmetric); real time (hard vs soft deadlines); distributed and network OS; modern mobile/embedded. For each: the problem it solved and the hardware feature it needed.

**P2-B2. Explain FCFS, SJF, Priority and Round Robin scheduling, and compute the average waiting time for a given set of processes. [10]**
> Deep treatment: `CORE_03_OperatingSystems.md`. Skeleton: define the metrics first (arrival time, burst time, completion, turnaround = completion − arrival, waiting = turnaround − burst, response time). Then each algorithm in 3 lines + a **Gantt chart** + a table of WT and TAT. **Always draw the Gantt chart — it is where the marks are.** Use one common process set across all four so the comparison is direct, e.g. P1(0,7) P2(2,4) P3(4,1) P4(5,4). Close with a comparison table: preemptive?, starvation?, optimal for?, suitable for?

**P2-B3. Describe the booting process of a PC running MS-DOS, step by step. [10]**
> Full treatment in `CSDip_02_MSOffice_and_DOS.md`. Skeleton, in strict order:
1. Power on → SMPS asserts Power Good → CPU reset, jumps to the BIOS entry vector (FFFF:0000).
2. **POST** — BIOS tests CPU, memory, keyboard, video, ports; beep codes signal failure.
3. BIOS reads the boot order from CMOS, loads the **boot sector (512 bytes)** of the first bootable device into memory at 0000:7C00 and jumps to it.
4. The boot record checks for and loads **IO.SYS**.
5. IO.SYS loads **MSDOS.SYS** (the kernel), which initialises the file system and internal data structures.
6. **CONFIG.SYS** is read — DEVICE=, FILES=, BUFFERS=, LASTDRIVE=, SHELL=.
7. **COMMAND.COM** is loaded (the command interpreter) in two parts, resident and transient.
8. **AUTOEXEC.BAT** is executed — PATH, PROMPT, environment, TSRs, launching an application.
9. The DOS prompt `C:\>` appears; the system is ready.
- Then define cold vs warm boot and the role of the bootstrap loader.

**P2-B4. Explain the internal and external commands of MS-DOS with syntax and examples. [10]**
> Full treatment in `CSDip_02_MSOffice_and_DOS.md`. Skeleton: the internal/external distinction (as in P2-A3); then two tables:

| Internal | Syntax | Purpose |
|---|---|---|
| DIR | `DIR [drive:][path] [/P] [/W] [/A] [/S] [/O]` | List directory contents |
| COPY | `COPY source destination` | Copy files |
| DEL / ERASE | `DEL filename` | Delete files |
| REN | `REN oldname newname` | Rename |
| TYPE | `TYPE filename` | Display a text file |
| MD / CD / RD | `MD dirname` etc. | Create / change / remove directory |
| CLS, DATE, TIME, VER, VOL, PATH, PROMPT | — | Console and environment |

| External | Syntax | Purpose |
|---|---|---|
| FORMAT | `FORMAT drive: [/S] [/Q] [/U]` | Format a disk; `/S` makes it bootable |
| CHKDSK | `CHKDSK [drive:] [/F]` | Check the disk and FAT, report/fix errors |
| XCOPY | `XCOPY source dest [/S] [/E] [/V]` | Copy directories and subdirectories |
| ATTRIB | `ATTRIB [+R|-R][+H|-H][+S|-S][+A|-A] file` | Change file attributes |
| DISKCOPY, LABEL, TREE, MORE, SORT, FIND, EDIT, FDISK, DEFRAG, SYS | — | — |

- Add wildcards (`*`, `?`), redirection (`>`, `>>`, `<`) and the pipe (`|`) with one example each: `DIR *.TXT > LIST.TXT`, `DIR | MORE`.

**P2-B5. Explain the essential UNIX file-processing commands with their options. [10]**
> Deep treatment: `CORE_04_UnixLinux.md`. Skeleton: a table of command | syntax | purpose | key options, covering `wc` (-l -w -c), `head`/`tail` (-n, -f), `cut` (-c -d -f), `paste` (-d), `join` (-1 -2), `split` (-l), `sort` (-n -r -k -u), `grep`/`egrep` (-i -v -n -c -l -w), `tr` (-d -s), `comm`, `cmp`, `diff`, `more`/`less`, `pr` (-h -n -d -l), `lp`. Then 4–5 worked pipeline examples: `sort emp.txt | uniq -c | sort -nr | head -5`.

**P2-B6. What is an E-R model? Draw and explain an E-R diagram for a library system. [10]**
> Deep treatment in the shared DBMS notes. Skeleton: definition; the symbols table (rectangle = entity, double rectangle = weak entity, ellipse = attribute, double ellipse = multivalued, dashed ellipse = derived, underlined = key, diamond = relationship, lines = participation, double line = total participation); cardinality 1:1, 1:N, M:N.
- **Diagram to draw:** entities **BOOK** (Book_ID key, Title, Author, Publisher, Price), **MEMBER** (Member_ID key, Name, Address, Phone), **LIBRARIAN**. Relationship diamond **ISSUED_TO** between BOOK and MEMBER, M:N, with attributes Issue_Date and Due_Date on the relationship. Relationship **MANAGES** between LIBRARIAN and BOOK.
- Then explain the mapping of the diagram to relational tables, showing that the M:N relationship becomes its own table with a composite key.

**P2-B7. Explain the SQL data definition and data manipulation statements with examples. [10]**
> Deep treatment in the shared DBMS notes. Skeleton: DDL — CREATE TABLE with data types and constraints (PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, CHECK, DEFAULT), ALTER TABLE ADD/MODIFY/DROP, DROP TABLE, TRUNCATE, CREATE VIEW/INDEX. DML — INSERT, UPDATE, DELETE, SELECT with WHERE, ORDER BY, GROUP BY, HAVING, aggregate functions, joins, subqueries. **Write actual SQL for every one** on a single EMPLOYEE(empno, name, dept, salary) example — examiners give marks for the syntax being right, not the prose.

**P2-B8. Explain the phases of the System Development Life Cycle (SDLC). [10]**
> Full treatment in `CSDip_03_SystemAnalysisAndViruses.md` §2. Skeleton: draw the waterfall diagram; then each phase with its purpose, activities, who does it, and the deliverable it produces:
1. Preliminary investigation / recognition of need — feasibility study (technical, economic, operational, schedule, legal) → feasibility report.
2. Requirement analysis / system analysis — fact-finding (interview, questionnaire, observation, record review), DFDs, data dictionary → SRS.
3. System design — logical then physical; output, input, file/database, procedure and control design → design specification.
4. Coding / development → source code.
5. Testing — unit, integration, system, acceptance → test reports.
6. Implementation / conversion — direct, parallel, pilot, phased; training; file conversion → live system.
7. Maintenance and review — corrective, adaptive, perfective, preventive.
- Close with a line on why it is a *cycle*: maintenance eventually triggers a new investigation.

**P2-B9. Discuss the factors causing failure in the SDLC. [10]**
> Full treatment in `CSDip_03_SystemAnalysisAndViruses.md` §2. Skeleton, grouped: (a) requirements — incomplete, ambiguous, changing scope/"scope creep"; (b) management — unrealistic schedules and budgets, poor planning, weak project control, inadequate resources; (c) people — lack of top-management support, no user involvement, poor communication between analyst and user, user resistance to change, inadequate training, staff turnover; (d) technical — wrong technology choice, poor design, inadequate testing, poor documentation; (e) process — skipping phases, no feasibility study, no change control, no risk management. Give a one-line remedy for each group.

**P2-B10. Write a C program to (a) find the largest of three numbers and (b) print the Fibonacci series up to n terms. Explain the logic. [10]**
- Write the full program with `#include`, `main()`, declarations, input, logic, output and `return 0`. Indent it. Add 3–4 lines of explanation and a dry run for a sample input.
- Fibonacci logic: initialise `a=0, b=1`; print; loop n−2 times computing `c=a+b`, print `c`, shift `a=b, b=c`. Handle n=1 and n=2 as special cases.

**P2-B11. Explain arrays in C — declaration, initialisation, one- and two-dimensional — with examples. [10]**
> Deep treatment in the shared C notes. Skeleton: definition (a collection of homogeneous elements in contiguous memory, accessed by index); declaration syntax; zero-based indexing; initialisation at declaration and at run time; memory layout diagram; 2-D arrays as arrays of arrays, row-major storage, address calculation formula `addr = base + [(i × ncols) + j] × size`; passing an array to a function (name decays to a pointer, so it is effectively by reference); one worked program (sum of an array, or matrix addition).

**P2-B12. Explain memory management in an operating system: partitioning, paging and segmentation. [10]**
> Deep treatment: `CORE_03_OperatingSystems.md`. Skeleton: purpose of memory management; contiguous allocation (single, fixed partition, variable partition; first/best/worst fit; internal vs external fragmentation, compaction); paging (frames and pages, page table, logical-to-physical translation diagram, no external fragmentation, TLB); segmentation (variable-size logical units, segment table with base and limit, matches the program's structure, external fragmentation returns); segmentation with paging. Include the address-translation diagram for paging — it is where the marks concentrate.

**P2-B13. Explain the Windows desktop and file/folder management operations. [10]**
> Full treatment in `CSDip_02_MSOffice_and_DOS.md`. Skeleton: desktop components (icons, taskbar, Start button/menu, notification area, shortcuts, Recycle Bin); window anatomy (title bar, minimise/maximise/restore/close, menu/ribbon, scroll bars, status bar, borders) and operations (open, close, move by dragging the title bar, resize by dragging a border, minimise, maximise, restore, switch with Alt+Tab, arrange/cascade/tile); Windows Explorer / File Explorer navigation pane and tree; file and folder operations (create, rename F2, copy Ctrl+C/Ctrl+V, move Ctrl+X, delete Del vs Shift+Del, restore from Recycle Bin, search, properties, attributes, sharing); Accessories (Notepad, WordPad, Paint, Calculator, Character Map, Snipping Tool) with what each is for; a one-paragraph version history table.

### 4.3 Section C — 15-mark questions (Paper-II)

**P2-C1. Explain MS-DOS in detail: its features, booting process, system files, and internal and external commands. [15]**
> Full treatment in `CSDip_02_MSOffice_and_DOS.md`. Combine P2-A3, P2-A4, P2-B3 and P2-B4 into one structured answer with headings. Add: features and characteristics of MS-DOS (single-user, single-tasking, 16-bit, CUI/command-line, 8.3 file naming, hierarchical directory structure, FAT12/FAT16 file system, 640 KB conventional memory limit, no built-in networking or GUI, small footprint); the directory tree diagram with root, subdirectories, path and the `\` separator; wildcards, redirection and piping; and the CONFIG.SYS / AUTOEXEC.BAT roles.

**P2-C2. Explain the UNIX operating system: its history, features, structure, and the essential commands with examples. [15]**
> Deep treatment: `CORE_04_UnixLinux.md`. Skeleton: history (Bell Labs 1969, Thompson and Ritchie, rewritten in C in 1973, AT&T System V vs BSD, POSIX, Linux); features (multi-user, multitasking, portability because written in C, hierarchical file system, security through ownership and permissions, shell programming, pipes and filters, device independence — everything is a file); the concentric structure diagram (hardware → kernel → shell → utilities → user); hardware requirements; then grouped command tables — session (`login`, `passwd`, `who`, `who am i`, `tty`, `date`, `cal`, `exit`, `shutdown`); file and directory (`ls`, `cat`, `cp`, `mv`, `rm`, `mkdir`, `rmdir`, `cd`, `pwd`); processing (`wc`, `head`, `tail`, `cut`, `paste`, `sort`, `grep`, `tr`, `comm`, `cmp`, `diff`); printing (`pr`, `lp`); help (`man`); maths (`bc`, `expr`, `factor`, `units`); communication (`write`, `wall`, `mail`). Give a worked example for at least eight of them.

**P2-C3. Explain the concept of a system, its characteristics, elements and types, with examples. [15]**
> Full treatment in `CSDip_03_SystemAnalysisAndViruses.md` §2. Skeleton: definition; the characteristics (organisation, interaction, interdependence, integration, central objective); the elements with a **diagram** (inputs → processing → outputs, with feedback and control loops, inside a boundary, within an environment, with interfaces to other systems); the types with examples for each pair — physical vs abstract, open vs closed, deterministic vs probabilistic, man-made vs natural, permanent vs temporary, adaptive vs non-adaptive; then information systems as a class — TPS, MIS, DSS, ESS/EIS, OAS, KMS — with a pyramid diagram showing which organisational level each serves. Close with an example worked through: a college admission system, identified against every characteristic and element.

**P2-C4. Explain the System Development Life Cycle in detail: all phases, the role of the system analyst, and the factors causing failure. [15]**
> Full treatment in `CSDip_03_SystemAnalysisAndViruses.md` §2. Combine P2-B8, P2-B9 and P2-A14. Structure: (i) definition and the waterfall diagram; (ii) each of the seven phases with activities and deliverables; (iii) the role of the analyst, mapped phase by phase (in analysis he is a fact-finder, in design an architect, in implementation a trainer and change agent); (iv) failure factors grouped as in P2-B9; (v) a closing paragraph on how iterative/prototyping models address the waterfall's weaknesses.

**P2-C5. Explain the relational model in detail: relations, domains, keys, base tables and views, and the SQL language. [15]**
> Deep treatment in the shared DBMS notes. Skeleton: Codd's relational model; terminology table (relation/table, tuple/row, attribute/column, degree, cardinality, domain); properties of a relation (no duplicate tuples, unordered tuples and attributes, atomic values); kinds of relations (base, view/virtual, snapshot, query result, temporary); keys (super, candidate, primary, alternate, foreign, composite) each with a definition and an example from one running schema; relations and predicates (a relation is the extension of a predicate — Date's framing, which is what the syllabus wording points at); then SQL DDL and DML as in P2-B7, plus views (CREATE VIEW, updatability), and a closing note on query optimisation.

**P2-C6. Discuss CPU scheduling in detail: the criteria, and FCFS, SJF, Priority, Round Robin and multiprocessor scheduling, with examples. [15]**
> Deep treatment: `CORE_03_OperatingSystems.md`. Skeleton: the CPU–I/O burst cycle; when scheduling decisions occur; preemptive vs non-preemptive; the scheduling criteria (CPU utilisation, throughput, turnaround time, waiting time, response time — say which are maximised and which minimised); then each algorithm with a Gantt chart and a WT/TAT table on one common process set; SJF preemptive (SRTF) as well; priority scheduling and starvation/aging; Round Robin and the effect of quantum size (too large → FCFS; too small → context-switch overhead dominates); multilevel queue and multilevel feedback queue; multiprocessor scheduling (asymmetric vs symmetric SMP, load balancing — push and pull migration, processor affinity). Close with the comparison table.

**P2-C7. Explain control statements and loops in C in detail, with syntax, flowcharts and examples. [15]**
> Deep treatment in the shared C notes. Skeleton: the three structured-programming constructs (sequence, selection, iteration); then each statement with **syntax + flowchart + short example + output**: `if`, `if-else`, nested `if`, `else-if` ladder, `switch-case` (with the role of `break` and `default`, and the restriction to integral/character constant labels), `goto` (and why to avoid it); loops `for`, `while`, `do-while` with the entry/exit-controlled distinction, nested loops; jump statements `break`, `continue`, `return`. Include a comparison table of the three loops (initialisation/test/update placement, entry or exit controlled, minimum iterations, best use case) and one complete program using several of them (e.g. a menu-driven calculator using `switch` inside a `do-while`).

**P2-C8. Explain database security: authentication, authorisation, access control and enforcement mechanisms. [15]**
> Deep treatment in the shared DBMS notes. Skeleton: the threats first (loss of integrity, availability and confidentiality; unauthorised access; inference; SQL injection; insider misuse); countermeasures — access control, inference control, flow control, encryption; authentication (something you know/have/are, password policy, OS vs DBMS authentication); authorisation (GRANT and REVOKE syntax with examples, privilege types, WITH GRANT OPTION and cascading revocation, roles); access-control models (DAC, MAC with Bell–LaPadula labels, RBAC) compared in a table; enforcement (the DBMS authorisation catalogue checked at parse/execute time, views for row and column restriction, stored procedures, audit trails, encryption at rest and in transit, backup and recovery). Close with a short paragraph on SQL injection as the most common practical failure of enforcement and its prevention by parameterised queries.

---

## 5. Final drill discipline — the last 10 days

| Day | Drill |
|---|---|
| Daily | 30 MCQs from a set you did **not** do yesterday, timed at 30 s each |
| Alternate days | Two skeletons written cold from §3 or §4, 3 minutes each, then compared |
| 26 Sept | Full 100-question MCQ mock, 2 hours, negative marking scored |
| 27 Sept | Full Paper-I mock: pick Q1–Q10 from §3.1, Q11–Q15 from §3.2, Q16–Q19 from §3.3. Sit 3 hours, by hand |
| 28 Sept | Full Paper-II mock built the same way from §4. Sit 3 hours, by hand |
| 29 Sept am | Re-read the answer keys' **trap notes** only. Nothing else |

> **Write by hand for the mocks.** Three hours of continuous handwriting is a physical skill. If
> your hand is going to cramp, find out on 27 September, not at 2:30 pm on 29 September.

---

## Appendix — numbers most likely to be asked

| Fact | Value |
|---|---|
| ASCII bits / characters | 7 bits / 128 characters (extended 8-bit / 256) |
| EBCDIC | 8-bit, IBM |
| Unicode UTF-8 / UTF-16 / UTF-32 | 8–32 bits variable / 16 bits (BMP) / 32 bits |
| Nibble / byte / word | 4 / 8 / 16–64 bits |
| 1 KB / MB / GB / TB | 2¹⁰ / 2²⁰ / 2³⁰ / 2⁴⁰ bytes |
| BCD valid codes | 0000–1001 only; 1010–1111 invalid |
| Floppy 5.25" DD / HD | 360 KB / 1.2 MB |
| Floppy 3.5" DD / HD | 720 KB / **1.44 MB** |
| Hard disk sector size | 512 bytes (4096 in Advanced Format) |
| CD capacity / 1x speed | 650–700 MB / 150 KB/s |
| DVD capacity / 1x speed | 4.7 GB SL, 8.5 GB DL / 1.38 MB/s |
| Blu-ray capacity | 25 GB per layer |
| CD / DVD / BD laser wavelength | 780 nm / 650 nm / 405 nm |
| IDE connector pins | 40 (80-conductor cable for UDMA) |
| Floppy connector pins | **34** |
| SCSI-1 connector pins | 50 |
| Serial port | DB-9 male (also DB-25) |
| Parallel port | DB-25 female |
| PS/2 colours | Purple = keyboard, green = mouse |
| PS/2 connector | 6-pin mini-DIN |
| USB 1.1 / 2.0 / 3.0 speeds | 12 Mbps / 480 Mbps / 5 Gbps |
| USB max devices | 127 |
| ATX main power connector | 20-pin (24-pin ATX12V 2.0) |
| CMOS battery | CR2032, 3 V lithium |
| RTC crystal | 32.768 kHz |
| PCI bus | 32-bit, 33 MHz, 133 MB/s |
| OSI layers | 7 |
| DOS file naming | 8.3 |
| DOS conventional memory | 640 KB |
| DOS execution priority | .COM → .EXE → .BAT |
| ISDN BRI | 2B + D = 2 × 64 + 16 kbps |
| Dial-up maximum | 56 kbps |
| Rotational latency at 7200 RPM | 4.17 ms average |
| MCQ negative marking | −1/3 of 2 = −0.667 |
