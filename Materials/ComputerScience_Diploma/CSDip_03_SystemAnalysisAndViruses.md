# CS (Diploma) — Viruses, System Analysis & Design, and Internet Technology

> Covers three separate syllabus units that are grouped here because they are all
> **vocabulary-heavy, low-maths, high-yield** topics — the kind that hand you cheap
> marks if you know the standard phrasing, and cost you nothing to learn:
>
> - **Paper-I Unit 9 — Computer Viruses**
> - **Paper-II Unit 4 — System Analysis & Design**
> - **Paper-I Unit 6 — Internet Technology**
>
> Two of the three are on **Paper-I** (viruses, internet) and one is on **Paper-II**
> (system analysis). All three are also heavily mined for MCQs — the real 2024 paper
> had ~15 questions drawn straight from these units.

---

## Why this file matters

You are a B.Tech CS graduate. Your instinct will be to skip these units as "trivial" —
and that instinct will cost you marks. Here is the honest situation:

1. **Viruses.** You know modern malware taxonomy (ransomware, rootkits, RATs, supply-chain
   attacks). The syllabus does **not** ask for that. It asks for a **1990s-era taxonomy** —
   "command-processor infection", "file-specific infection", "memory-resident infection" —
   phrases you have almost certainly never used. The examiner wants *their* categories back,
   in *their* words. Learn the vocabulary, not the concept (you already have the concept).

2. **System Analysis & Design.** This is management-information-systems vocabulary
   (Elias M. Awad / classic SAD textbooks), not software-engineering-as-you-were-taught.
   "Physical vs abstract system", "open vs closed system", "deterministic vs probabilistic",
   "TPS / MIS / DSS / ESS", "role of the system analyst", "factors causing failure" — these
   are *definitional* answers. A degree course teaches you to *build* software; this unit
   tests whether you can *classify systems* and *name SDLC phases* in the textbook's own terms.

3. **Internet Technology.** The connectivity types — **dial-up, leased line, ISDN, VSAT** —
   are dated and specific. You may never have configured a dial-up modem in your life. These
   are pure recall, and they generate easy single-fact MCQs (the 2024 paper had a full
   matching question on VSAT/dial-up/cable/leased).

**Bottom line:** none of this is hard. All of it is *unfamiliar phrasing of familiar ideas*.
The failure mode is over-confidence, not difficulty. Read for the vocabulary.

### Tick-box checklist — you are done with this file when you can:

- [ ] List the **six virus types in the syllabus** (command-processor, boot-sector,
      executable-file, file-specific, memory-resident, macro) and give one distinguishing
      sentence for each — **without notes**.
- [ ] Distinguish **virus vs worm vs trojan vs ransomware** in a clean four-row table.
- [ ] Write the **symptoms of infection** and the **steps to deal with an infection** as
      numbered lists.
- [ ] Define **system**, list its **characteristics** and its **elements** (the "IPOFC"
      chain).
- [ ] Classify systems five ways: **physical/abstract, open/closed, deterministic/probabilistic,
      man-made/natural, permanent/temporary**.
- [ ] Name and one-line the four **information system** types: **TPS, MIS, DSS, ESS**
      (add OAS/KWS if asked).
- [ ] Recite the **SDLC phases in order** with the deliverable of each.
- [ ] State the **role of the system analyst** and the **factors that cause SDLC failure**.
- [ ] Contrast **intranet vs internet vs extranet**.
- [ ] Name the **internet services** (email, chat, BBS, video-conf, FTP, Telnet, WWW) and
      one line on each.
- [ ] Fill the **connectivity comparison table** (dial-up / leased / ISDN / VSAT / broadband)
      from memory.

### How to use this file

Each topic follows the house format: **Concept → Key points → Worked example / illustration →
Likely exam questions (5 / 10 / 15) → MCQ traps.** Numbers or facts I could not fully verify
are flagged **⚠️ verify** — check them against a second source before quoting them as exact.

> **Mark scheme reminder.** Descriptive Paper-I and Paper-II are each 100 marks / 3 hours:
> Section A = any **8 of 10 × 5**, Section B = any **3 of 5 × 10**, Section C = any **2 of 4 × 15**.
> MCQ = 100 × 2 = 200 with **−1/3 negative marking** per wrong answer. Definitions, tables and
> numbered lists score fastest in the descriptive papers — every topic below is built to
> deliver exactly those.

---

## Topic checklist and where each unit sits

| # | Topic | Paper | Depth | Best answer format |
|---|---|---|---|---|
| A | Computer viruses — definition, working | P-I §9 | Medium | Definition + numbered life-cycle |
| B | Virus types (the syllabus's six) | P-I §9 | **High** | Table, one row per type |
| C | Worms / trojans / ransomware (context) | P-I §9 | Low | Four-row comparison table |
| D | Protection, recognising, dealing with infection | P-I §9 | Medium | Three numbered lists |
| E | System concept, characteristics, elements | P-II §4 | Medium | Definition + IPOFC diagram |
| F | Types of system | P-II §4 | **High** | Five two-column tables |
| G | Information systems (TPS/MIS/DSS/ESS) | P-II §4 | Medium | Pyramid + one-line each |
| H | SDLC phases | P-II §4 | **High** | Numbered phases + deliverables |
| I | Role of system analyst; failure factors | P-II §4 | Medium | Two numbered lists |
| J | Intranet / internet / extranet | P-I §6 | Medium | Three-column table |
| K | Internet services | P-I §6 | Medium | List, one line each |
| L | WWW, browsers, search engines | P-I §6 | Medium | Definition + how-search-works |
| M | Connectivity (ISP, dial-up, leased, ISDN, VSAT) | P-I §6 | **High** | Comparison table |

---

# PART 1 — COMPUTER VIRUSES (Paper-I, Unit 9)

## A. What a virus is and how it works

### Concept

A **computer virus** is a small program (a piece of malicious code) that **attaches itself
to another program or file** and, when that host is run, **copies itself into other programs
or files** — it *replicates*. That self-replication, riding on a host, is the defining
property. The biological analogy is exact: a virus cannot live on its own; it hijacks a host
cell (a legitimate program) and uses it to reproduce.

Two properties together define a virus:

1. **It replicates** (makes copies of itself), and
2. **It needs a host / a trigger** — it does not run by itself; it runs when the infected
   program runs, the infected document is opened, or the infected disk is booted.

A program that replicates **without needing a host** and spreads by itself across a network
is a **worm** (see Part C) — that distinction is a classic MCQ.

### The life cycle — the numbered answer

A virus goes through recognisable phases. This numbered list is the ideal shape for a
5-mark "how does a virus work" answer:

1. **Infection / insertion.** The virus code is attached to a host (program, boot sector,
   or document macro). This usually happens when you run infected software, open an infected
   attachment, or boot from an infected disk / USB.
2. **Dormant phase (latency).** The virus sits idle, doing nothing visible, waiting for a
   trigger. Not all viruses have this phase.
3. **Trigger (activation).** A condition fires it — a particular date (e.g. the "Friday the
   13th" virus), a number of executions, or a specific user action.
4. **Replication / propagation.** Each time the infected host runs, the virus copies itself
   into other clean files or disks, spreading the infection.
5. **Execution / payload / damage.** The virus delivers its **payload** — the harmful action:
   deleting files, corrupting data, displaying messages, slowing the system, or opening a
   backdoor. Some payloads are merely annoying; some are destructive.

> **Exam phrasing tip.** Examiners love the words **"replicate"** and **"payload"**. Use both
> in any virus answer. Note: replication is *always* present; a destructive payload is *not*
> — some viruses only replicate and consume resources.

### Key points

- A virus is **man-made software**, written deliberately. (The 2024 paper asked "Why do people
  write these?" with the intended answer being about **viruses** — motives include mischief,
  vandalism, showing off skill, financial gain, and disruption.)
- A virus **cannot infect hardware directly** — it corrupts *data and programs*. (2024 MCQ:
  "A computer virus is unable to do —" answer **"Disabling hardware"**. Modern nuance: malware
  *can* damage hardware indirectly, e.g. overwriting firmware/BIOS or overheating — mark this
  as ⚠️ verify against the intended textbook answer, which says a virus cannot physically
  destroy hardware.)
- Viruses spread through **executable files, boot sectors, email attachments, infected
  removable media (USB/CD), macros in documents, and network shares**.
- **Plain-text and pure-data formats generally cannot carry a virus** because they contain no
  executable code. (2024 MCQ: "Which document format cannot contain a virus?" — the intended
  answer was **.rtf** ⚠️ verify. The safe underlying principle: formats that support **macros
  or embedded code** (.doc, .docx, .xls, .pdf with scripts) *can* carry malware; a format with
  no code-execution capability cannot. `.txt` is the cleanest true example.)

---

## B. Types of viruses — the syllabus's own taxonomy (HIGH PRIORITY)

This is the single most examinable sub-topic in the unit, and it is worded in **1990s
vocabulary you must reproduce exactly.** Learn these six categories in the syllabus's own
words.

| # | Virus type | What it infects / how it works | Key identifier |
|---|---|---|---|
| 1 | **Command-processor infection** | Infects the **command interpreter** — `COMMAND.COM` in DOS (the shell that reads and executes your commands). Because the command processor is loaded and run constantly, the virus gains control very frequently. | Targets the shell / `COMMAND.COM` |
| 2 | **Boot-sector infection** | Infects the **boot sector** (the Master Boot Record / DOS boot record) of a disk. It loads into memory **before the OS**, every time you boot from the infected disk. Spreads mainly via infected floppies/USB left in the drive at boot. | Runs at boot, before the OS |
| 3 | **Executable-file infection** | Attaches to **executable program files** (`.EXE`, `.COM`, `.SYS`). When you run the program, the virus runs first (or alongside) and infects other executables. The classic "file virus" / "parasitic virus". | Rides on `.EXE`/`.COM` programs |
| 4 | **File-specific infection** | Targets **one particular named file or one particular type of file** — it is selective, only infecting a specific target rather than any executable. | Highly selective — one file/type |
| 5 | **Memory-resident infection** | Loads itself into **RAM and stays resident (TSR — Terminate-and-Stay-Resident)**. It stays active in memory even after the host program ends, and infects every program that runs or every disk that is accessed while it is resident. | Lives in RAM, infects on-the-fly |
| 6 | **Macro virus** | Written in the **macro language** of an application (e.g. VBA in MS Word/Excel). It infects **documents and templates** (e.g. Word's `Normal.dot`), not programs. Spreads when infected documents are shared. Was the most common virus type in the late 1990s because documents are shared far more than programs. | Infects documents via macros |

### How to keep them straight (the memory hook)

Group them by **what they attach to**:

- **The shell** → command-processor virus.
- **The disk's boot area** → boot-sector virus.
- **Program files** → executable-file virus (any) and file-specific (one specific target).
- **Where it lives while active** → memory-resident (stays in RAM) vs non-resident
  (runs, infects, exits).
- **Documents, not programs** → macro virus.

> **A useful extra distinction (often asked):** a **resident** virus stays in memory and works
> in the background; a **non-resident / direct-action** virus executes, finds and infects a few
> targets, then hands control back and exits without staying in memory. Also worth naming:
> **polymorphic virus** (changes its own code/signature on each infection to evade scanners)
> and **stealth virus** (actively hides its presence from antivirus, e.g. by intercepting
> disk reads). These two are not in the six-type list but are common MCQ distractors.

### MCQ traps for virus types

- **Boot-sector virus loads before the OS** — a favourite "true/false" fact. True.
- **Macro virus infects documents, not programs** — do not say it infects `.EXE` files.
- A **memory-resident** virus is **not** the same as a boot virus; a boot virus *becomes*
  resident, but resident refers specifically to staying in RAM.
- **Command-processor virus = `COMMAND.COM`**, not "any command you type".

---

## C. Worms, trojans and other malware — for context and contrast

The syllabus's virus unit sits inside a broader malware picture. You need the contrasts
because "differentiate virus and worm" is a stock 5-marker and the distinctions are prime
MCQ material.

| Malware | Self-replicates? | Needs a host? | Spreads by | One-line definition |
|---|:---:|:---:|---|---|
| **Virus** | Yes | **Yes** (attaches to a file/program/boot sector) | Running the infected host; sharing files/media | Malicious code that attaches to a host and replicates when the host runs |
| **Worm** | Yes | **No** (standalone) | **By itself, across networks** (exploits, email) | A standalone program that self-replicates and spreads over networks without a host |
| **Trojan horse** | **No** | Disguises itself as legitimate software | User is tricked into installing it | Malware disguised as a useful program; does NOT self-replicate |
| **Ransomware** | Sometimes | Often delivered by trojan/worm | Phishing, exploits | Encrypts the victim's files and demands payment for the key |
| **Spyware** | No | — | Bundled with software, drive-by | Secretly collects user information |
| **Backdoor / RAT** | No | — | Trojan delivery | Lets an attacker take remote control of the PC over the internet |

Notes that turn into MCQs:

- **The virus-vs-worm line = self-propagation.** A worm spreads **on its own** across a
  network; a virus needs the user to run/open the host. (The syllabus itself often lumps
  these, but the exam distinguishes them.)
- **Trojan does not replicate** — that is its defining contrast with viruses and worms.
  (2024 MCQ: "a program that allows someone to take control of another user's PC via the
  internet" → **Backdoor Trojan**.)
- **Virus hoax** = a fake warning (usually a chain email) telling you a non-existent virus
  will destroy your PC and urging you to forward the message. It carries no code — the
  "damage" is the panic and wasted effort. (2024 MCQ: "Which one is a virus hoax?" → the
  famous **"Good Times"** hoax.)
- **Spam / UCE / junk mail** are the same thing (Unsolicited Commercial Email) — a 2024 MCQ
  grouped Spam / Junk Mail / UCE together and asked which was the odd one out (Gmail).

---

## D. Protecting, recognising, and dealing with an infection

These three are natural sub-parts of a 10-mark or 15-mark question ("Discuss the types of
viruses, how to recognise an infection and how to deal with it"). Keep each as a numbered
list.

### D.1 Protecting the PC (prevention)

1. **Install and update antivirus / anti-malware software**, and keep its virus definitions
   current — an out-of-date scanner is nearly useless.
2. **Keep the OS and applications patched** — most infections exploit known, already-fixed
   vulnerabilities.
3. **Use a firewall** (software and/or hardware router) to block unauthorised network access.
4. **Do not run unknown executables or open unexpected email attachments**; be wary of links.
5. **Scan removable media (USB, CD/DVD) before use**; disable autorun.
6. **Disable macros by default** in Office; enable only for trusted documents.
7. **Take regular backups** kept offline/separate — the only reliable recovery from
   destructive malware and ransomware.
8. **Use standard (non-administrator) user accounts** for daily work to limit what malware
   can do.
9. **Download software only from trusted / official sources.**
10. **Configure the browser for security** and keep a **separate network for
    internet-facing machines** where possible. (Both appear as 2024 MCQ "safety tip" options;
    the *wrong* option — i.e. NOT a safety tip — was "always explore/open money-related mails".)

### D.2 Recognising an infection (symptoms)

Common signs that a PC may be infected:

1. The computer runs **noticeably slower** than usual, or freezes/crashes often.
2. Programs **fail to start, behave oddly, or close unexpectedly**.
3. **Unusual error messages, pop-ups or on-screen messages** appear.
4. **Files or folders disappear, get renamed, change size, or become corrupted.**
5. **Free disk space or memory shrinks** for no clear reason (the virus is replicating).
6. The system **boots slowly or fails to boot**; the OS won't load (2024 MCQ hint:
   "PC boots but will not start the OS" as a troubleshooting scenario — often the boot area).
7. **Antivirus software is disabled** or cannot be updated (malware often kills it).
8. **Unexpected network activity**, the modem/disk light active when idle, or programs
   accessing the internet on their own.
9. **Emails you did not send** go out from your account.

### D.3 Dealing with an infection (removal / recovery)

1. **Disconnect from the network / internet** to stop it spreading and to cut off any
   backdoor.
2. **Do not panic and do not reboot repeatedly** — some viruses do damage on each boot.
3. **Run a full scan with up-to-date antivirus**; let it **quarantine or clean** the
   infected files.
4. If the running OS is compromised, **boot from a clean rescue disk / bootable antivirus
   media** and scan from outside the infected OS.
5. **Delete or repair** the files the scanner cannot clean; for boot-sector infections,
   repair the boot record (e.g. `FDISK /MBR` in DOS-era systems ⚠️ verify for the specific
   OS).
6. **Restore lost/corrupted data from a clean backup.**
7. **Change passwords** (they may have been captured) after the system is clean.
8. In severe cases, **reformat and reinstall the OS** from trusted media, then restore data.
9. **Patch the vulnerability** that let it in, so you are not re-infected immediately.

---

## Likely exam questions — Viruses

**5-mark**
- What is a computer virus? Explain how it works. *(definition + numbered life cycle)*
- Differentiate between a virus and a worm. *(two-column table)*
- What is a Trojan horse? How does it differ from a virus? *(table)*
- List any five symptoms that indicate a computer may be infected.
- What is a macro virus? Why did it become so common?
- What is a virus hoax?

**10-mark**
- Explain the different types of computer viruses. *(the six-row table — this is the safe
  banker; add polymorphic/stealth for extra marks.)*
- How can a PC be protected from viruses? Also explain how to recognise an infection.
  *(two numbered lists.)*
- Compare virus, worm, trojan and ransomware. *(four-row table + one line each.)*

**15-mark**
- Discuss computer viruses in detail: what they are, how they work, their types, how to
  recognise an infection and how to deal with one. *(This is the "everything" question —
  structure it exactly as Parts A→D above: definition + life cycle, the six types table,
  recognition list, protection + removal lists. A labelled structure with tables outscores
  prose easily.)*

## MCQ traps — Viruses (from the real 2024 paper and their kin)

- "A virus is unable to do —" → **disabling hardware** (per textbook answer). ⚠️ verify.
- "Where is your office **not** vulnerable?" → **SMPS** (the power supply is not an
  infection vector; internet/email/CD are).
- "Why do people write these?" → **Virus.**
- "Which is a virus hoax?" → **Good Times.**
- "Take control of another user's PC via the internet" → **Backdoor Trojan.**
- "Which document format cannot contain a virus?" → intended **.rtf** (⚠️ verify; the sound
  principle is: a format with no macros/embedded code cannot carry one — `.txt` is the
  cleanest case).
- "Which is NOT a safety tip while using the internet?" → **"Always explore money-related
  mails."**

---

# PART 2 — SYSTEM ANALYSIS & DESIGN (Paper-II, Unit 4)

> **Shared-core pointer.** The software-process side of this unit — waterfall / prototype /
> spiral / RAD models, cost estimation, testing strategies, quality assurance — is treated
> in depth in the shared-core software-engineering notes (conventionally
> **`CORE_07_SoftwareEngineering.md`** — ⚠️ confirm the exact filename by listing
> `Materials\_Shared\`; at time of writing the `_Shared` folder contains
> `CORE_01_DigitalLogic`, `CORE_02_ComputerOrganization`, `CORE_03_OperatingSystems`,
> `CORE_04_UnixLinux`, `CORE_05_ComputerNetworks`). **This file covers the diploma-specific
> angle**: the *systems-theory vocabulary* (system concept, characteristics, elements, and
> the classification of systems), *information-system types*, the *SDLC phases at diploma
> depth*, the *role of the system analyst*, and *failure factors* — the material a B.Tech
> course usually skips because it is MIS vocabulary rather than software engineering.

## E. The system concept — definition, characteristics, elements

### Concept — intuition first

Before "system analysis" means anything, you need the textbook's idea of a **system**. Strip
away the jargon: a system is just **a set of parts that work together toward a common goal.**
A car, a human body, a payroll department, a hospital, a computer — all systems. The parts
interact; the whole does something none of the parts could do alone.

**Definition (memorise one clean line):**
> A **system** is an orderly grouping of interdependent components (elements) linked together
> according to a plan to achieve a specific objective (a common goal).

### Characteristics of a system

A stock 5- or 10-marker. Learn these named characteristics:

1. **Organisation** — the arrangement of components in a structure (order/hierarchy) that
   gives the system its form.
2. **Interaction / interdependence** — components depend on and affect one another; a change
   in one affects others.
3. **Interrelationship** — the components are connected and coordinated toward the goal.
4. **Integration** — the parts work as a unified whole, not as isolated pieces (the whole is
   greater than the sum of parts — *synergy*).
5. **Central objective** — the system exists to achieve a defined common goal; every part
   serves it.
6. **Boundary and environment** — a system has a boundary that separates it from its
   environment; what is outside the boundary is the environment.

### Elements of a system — the IPOFC chain

Every system can be described by these elements. This is the ideal thing to **draw** as a
left-to-right flow diagram:

```
   ENVIRONMENT (boundary around the whole)
   +--------------------------------------------------+
   |                                                  |
   |  INPUT  ---->  PROCESS  ---->  OUTPUT            |
   |    ^                              |              |
   |    |                              v              |
   |    +------- FEEDBACK <----- CONTROL              |
   |                                                  |
   +--------------------------------------------------+
```

1. **Input** — the data/energy/material entering the system (e.g. raw data, forms).
2. **Processor / process** — the part that transforms input into output (the logic/procedures).
3. **Output** — the result the system produces (reports, products, decisions).
4. **Control** — the element that governs the process (management, rules, the control
   program) to keep it on track toward the objective.
5. **Feedback** — output information fed back to compare actual results against the goal, so
   the system can self-correct. **Positive feedback** reinforces; **negative feedback**
   corrects/dampens.
6. **Boundary & environment** — the limit of the system and everything outside it that
   affects it.

> **Exam-safe short form:** the basic elements are **Input, Process (Processor), Output,
> Control, Feedback**, operating within a **Boundary/Environment**.
> (2024 MCQ: "Which is NOT a basic element of a system?" — options were Resources,
> Procedures, Processes, **Procurement** → answer **Procurement**.)

## F. Types of system (HIGH PRIORITY — five classifications)

The syllabus explicitly names **physical/abstract** and **open/closed**; the standard SAD
textbook adds three more pairs. Each pair is a clean two-column table — pre-build all five.

**1. Physical vs Abstract**

| Physical system | Abstract system |
|---|---|
| Tangible entities that physically exist | Conceptual / non-physical — ideas, models, formulas |
| Can be static (fixed) or dynamic (changing) | Exists as a representation of a real system |
| Example: a computer, a car, a payroll office | Example: a mathematical model, a set of formulas, a design blueprint |

**2. Open vs Closed**

| Open system | Closed system |
|---|---|
| **Interacts freely** with its environment — takes input and returns output | **Cut off** from its environment; does not interact with it |
| Adapts to environmental change | Isolated, self-contained; largely theoretical (truly closed systems are rare) |
| Example: a business organisation, a living organism | Example: a sealed chemical reaction; a fully isolated program |

**3. Deterministic vs Probabilistic**

| Deterministic system | Probabilistic (stochastic) system |
|---|---|
| Behaviour is **fully predictable**; output is known if input and state are known | Behaviour involves **uncertainty / probability**; output cannot be predicted with certainty |
| Example: a computer program, a correct arithmetic operation | Example: weather forecasting, inventory demand, a warehouse system |

**4. Man-made vs Natural** *(commonly listed)*

| Man-made system | Natural system |
|---|---|
| Designed and built by humans | Exists in nature, not created by humans |
| Example: a transport system, an information system | Example: the solar system, an ecosystem |

**5. Permanent vs Temporary** *(commonly listed)*

| Permanent system | Temporary system |
|---|---|
| Exists for a long, indefinite period | Set up for a limited time then dismantled |
| Example: an organisation's accounting system | Example: a system built for a one-off event/project |

> **MCQ calibration (2024 matching question):** open = "interacts freely with its
> environment"; closed = "cut off from its environment"; physical = "tangible entities,
> static or dynamic"; abstract = "non-physical / conceptual, model of a real system."
> Learn those four phrases word-for-word — the matching question used them almost verbatim.

## G. Information systems (TPS / MIS / DSS / ESS)

### Concept

An **information system** is a man-made system that **collects, processes, stores and
distributes information** to support the operations, management and decision-making of an
organisation. Its basic elements are **people, hardware, software, data and procedures**
(sometimes networks is added as a sixth). *(2024 MCQ: "basic element of an information
system?" → People / Hardware / Software → All of the above.)*

Information systems are usually drawn as a **pyramid**, matching the levels of management they
serve — bottom = operational/day-to-day, top = strategic:

```
                /\
               /  \      ESS  — Executive Support System (top / strategic)
              /----\
             /      \    DSS  — Decision Support System (middle-upper / tactical)
            /--------\
           /          \  MIS  — Management Information System (middle)
          /------------\
         /              \ TPS  — Transaction Processing System (bottom / operational)
        /----------------\
```

| Type | Full form | Serves | What it does | Example |
|---|---|---|---|---|
| **TPS** | Transaction Processing System | Operational staff | **Captures, classifies, stores, updates and retrieves day-to-day transaction data**; the base that feeds all other systems | Billing, payroll, order entry, ATM transactions |
| **MIS** | Management Information System | Middle management | Summarises TPS data into **routine reports** for monitoring and control | Monthly sales report, inventory summary |
| **DSS** | Decision Support System | Middle/upper management | Interactive tools + models to support **semi-structured decisions** ("what-if" analysis) | Sales forecasting, budgeting model |
| **ESS / EIS** | Executive Support / Information System | Top executives | Highly summarised, big-picture information for **strategic** decisions | Company-wide performance dashboard |
| *(OAS)* | Office Automation System | All office staff | Supports communication/productivity (email, word processing, scheduling) | MS Office, email, calendars |
| *(KWS)* | Knowledge Work System | Knowledge workers | Supports creation of new knowledge (CAD, analysis tools) | CAD workstations |

> **MCQ calibration (2024):** "Which is **not** a Computer-Based Information System (CBIS)?"
> → options TPS, MIS, **Networking System**, OAS → answer **Networking System**. And "which
> system captures, classifies, stores, maintains, updates and retrieves data for record
> keeping and input to other CBIS?" → **TPS**. And "which is **not** part of OAS?" →
> **System designing** (mailing, typing, scheduling are OAS; system design is not).

## H. The System Development Life Cycle (SDLC) — phases (HIGH PRIORITY)

### Concept

The **SDLC** is the structured sequence of stages a system passes through from first idea to
final retirement. Different books split it into 5–8 phases with slightly different names; the
**substance is always the same**. Learn one canonical ordered list and be able to state the
**deliverable (output) of each phase** — examiners reward that.

### The phases (canonical seven-phase version)

| # | Phase | What happens | Deliverable / output |
|---|---|---|---|
| 1 | **Preliminary investigation / Problem identification** | Recognise the problem or need; do a quick scope check. | Problem statement; project request |
| 2 | **Feasibility study** | Is the project worth doing? Assess **technical, economic (cost–benefit), operational, legal and schedule** feasibility. | Feasibility report; go / no-go decision |
| 3 | **Requirements analysis (System analysis)** | Study the current system; gather and analyse user requirements; model data & processes (DFDs, ER). | **SRS** (System/Software Requirements Specification) |
| 4 | **System design** | Decide **how** the system will meet the requirements — structure of files, databases, inputs, outputs, processes and screens/interfaces. | Design document (logical + physical design) |
| 5 | **Coding / development (implementation)** | Programmers write and unit-test the code from the design. | Working program modules |
| 6 | **Testing** | Verify the system against requirements — unit, integration, system, acceptance testing. | Tested, validated system; test reports |
| 7 | **Implementation / deployment & Maintenance** | Install, convert data, train users, go live; then **maintain** — fix bugs and enhance over the system's life. | Operational live system; maintenance updates |

> **Two-way memory aid:** *"Investigate → Feasibility → Analyse → Design → Code → Test →
> Implement & Maintain."* (2024 MCQ: "first phase of SDLC?" → **Problem Analysis** among the
> options given; "phase where structure of files, databases, input, output, processes and
> screens is decided?" → **Designing**; "which is NOT a phase of SDLC?" → **Networking**.)

**Note on models.** The *phases* above are the life cycle; the *models* (Waterfall,
Prototyping, Spiral, RAD/DSDM) are different ways of *sequencing/iterating* those phases —
covered in the shared-core SE notes. Two diploma-level facts worth carrying here:
**RAD (Rapid Application Development)** is also known as / associated with **Prototyping and
DSDM** (2024 MCQ), and **feasibility study types** are **technical, economic, operational,
legal and schedule** (2024 MCQ: "type of feasibility?" → All of the above).

## I. Role of the system analyst; factors causing failure

### Role of the system analyst

The **system analyst** is the **bridge between the users/management and the technical
developers** — the person who understands the business problem *and* enough technology to
specify a solution. Present as a numbered list of roles/responsibilities:

1. **Investigator / fact-finder** — studies the existing system, gathers requirements
   (interviews, questionnaires, observation, document study).
2. **Problem-solver / analyst** — analyses requirements and defines what the new system must
   do; models data and processes.
3. **Communicator / liaison** — communicates effectively, one-on-one, with users, business
   managers **and** programmers; translates business needs into technical terms and back.
4. **System designer** — specifies the design of files, databases, inputs, outputs and
   interfaces.
5. **Project manager / coordinator** — plans, schedules and coordinates the project team and
   resources.
6. **Change agent** — introduces and manages the change the new system brings; trains and
   supports users.
7. **Ethical professional** — deals **fairly, honestly and ethically** with team members,
   managers and users, and **maintains confidentiality**.

> Common role labels an analyst wears (2024 MCQ): **business analyst, requirements analyst,
> project manager** — the question asked which is NOT a role and the answer was "All of the
> above" *are* roles. Also (2024): "not important for analysts to maintain confidence" is a
> **false** statement — confidentiality *is* required.

### Factors causing failure in the SDLC / a system project

A stock 10-marker. Why systems fail:

1. **Incomplete, unclear or changing requirements** — the biggest single cause.
2. **Poor communication** between users, analysts and developers.
3. **Lack of user involvement / management support.**
4. **Unrealistic schedule, budget or scope** (over-optimistic planning).
5. **Inadequate feasibility study** — building the wrong thing.
6. **Poor project management** and lack of proper planning/control.
7. **Insufficient testing** — defects reach production.
8. **Resistance to change** / inadequate user training.
9. **Technology risk** — chosen technology is immature or unsuitable.
10. **Inadequate maintenance / no post-implementation review.**

## Likely exam questions — System Analysis & Design

**5-mark**
- Define a system. State its characteristics.
- Explain the basic elements of a system with a diagram. *(IPOFC + feedback)*
- Differentiate between an open system and a closed system. *(table)*
- Differentiate between a physical and an abstract system. *(table)*
- What is a deterministic system? Give an example.
- Differentiate between TPS and MIS.

**10-mark**
- Explain the different types of systems with examples. *(the five paired tables — a strong
  banker.)*
- Describe the types of information systems (TPS, MIS, DSS, ESS) with a pyramid and examples.
- Explain the role of the system analyst.
- Discuss the factors that cause failure in system development.

**15-mark**
- Explain the SDLC in detail — describe each phase and its deliverable. *(the seven-phase
  table; add a short line on Waterfall vs Prototyping vs Spiral for extra depth.)*
- "A system analyst is the bridge between users and developers." Discuss the role of the
  system analyst and the factors that cause a system project to fail.

## MCQ traps — System Analysis & Design

- Basic elements of a system → Input, Process, Output, Control, Feedback (**not**
  Procurement).
- CBIS types → TPS, MIS, DSS, ESS, OAS (**not** "Networking System").
- OAS includes mailing, typing, scheduling (**not** "system designing").
- SDLC phases (**not** "Networking").
- RAD ⇔ Prototyping / DSDM.
- Feasibility types → technical, economic, operational, legal, schedule.
- Structured tools: DFD, ERD, STD are structured tools; **RAD is a methodology, not a tool**
  (2024 MCQ: "which is NOT a structured tool?" → **RAD**).
- Charles Bachman won the Turing Award for **DBMS** (network data model) — a 2024 SAD-section
  MCQ, easy to confuse; note it is DBMS, not SAD.

---

# PART 3 — INTERNET TECHNOLOGY (Paper-I, Unit 6)

> **Shared-core pointer.** The *network fundamentals* underneath the internet — LAN/MAN/WAN,
> the OSI and TCP/IP models, transmission media and modes, topologies, and connectivity
> devices (hub/switch/router/bridge/gateway) — are covered in depth in
> **`Materials\_Shared\CORE_05_ComputerNetworks.md`** (and the Paper-I networks unit,
> §5). **This part covers the diploma-specific internet layer**: intranet vs internet,
> the internet *services*, the WWW / browsers / search engines, and the *connectivity types*
> (dial-up / leased / ISDN / VSAT) — which are dated, specific, and heavily examined.

## J. Intranet vs Internet vs Extranet

### Concept

- **Internet** — the global, public "network of networks" connecting millions of computers
  worldwide; open to everyone. *(2024 MCQ: "Once restricted to a few scientists, it quickly
  became universal. It reaches everywhere." → **Internet**.)*
- **Intranet** — a **private network internal to one organisation**, using the same
  internet technologies (TCP/IP, browsers, web pages) but **accessible only to authorised
  members** of that organisation.
- **Extranet** — a **controlled extension of an intranet to selected outsiders**
  (suppliers, partners, customers) over the internet, usually secured by login/VPN.

| Feature | Intranet | Internet | Extranet |
|---|---|---|---|
| Scope | Within one organisation | Global / worldwide | Organisation + selected partners |
| Access | Private, authorised users only | Public, anyone | Restricted external users |
| Ownership | One organisation | No single owner | One org + its partners |
| Security | High (behind firewall) | Low / open | Controlled (login/VPN) |
| Example use | Company noticeboard, HR portal | Public websites, email | Supplier order portal, B2B |

> **MCQ calibration (2024):** "Which service is **not** possible with an intranet?" →
> **Public Web sites** (an intranet is private; public sites belong to the internet.
> Private discussion groups, access to legacy databases and teleconferencing *are* possible
> internally).

## K. Internet services

The syllabus names these services explicitly — learn one line for each:

| Service | What it does |
|---|---|
| **Email (Electronic mail)** | Send/receive messages and attachments. Sending uses **SMTP**; retrieving/storing in the mailbox uses **POP3** or **IMAP**. |
| **Chatting / Instant messaging** | Real-time text (and voice/video) conversation between users; chat rooms use an **avatar/nickname** as your online identity; often implemented in **Java** ⚠️ (2024 MCQ said Java). |
| **Bulletin Board System (BBS) / Newsgroups (Usenet)** | Post-and-read message boards on topics; **Usenet** is one of the **oldest** internet services, older than the WWW. A **web forum** is the modern alternative to a real-time chat room. |
| **Video conferencing** | Real-time audio + video meeting between remote participants. Components: **camera, microphone, monitor/display, speakers, codec, network** — *(2024 MCQ: an "interpreter" is NOT a component)*. Apps: NetMeeting, CU-SeeMe, WebEx. |
| **FTP (File Transfer Protocol)** | Transfer arbitrary files between computers over the internet (upload/download). *(2024 MCQ: "transfer arbitrary files across the internet" → **FTP**.)* |
| **Telnet** | Log in to and use a remote computer over the network as if sitting at it (a remote terminal). *(Note: Telnet is a **service/protocol**, NOT a type of internet connection — a 2024 trap.)* |
| **WWW (World Wide Web)** | The system of interlinked hypertext documents (web pages) accessed via browsers over the internet. |
| **VoIP** | Voice calls over the internet (telephone-to-telephone, or PC-to-PC), e.g. Skype. |
| **VoD / Podcast / Streaming** | On-demand audio/video; a **playback buffer** allows smooth streaming despite network jitter. |

> **Netiquette & terminology (all real 2024 MCQs):** **Netiquette** = suggested rules for
> polite online behaviour; **Internauts / Netizens** = internet users; **postmaster@domain**
> = the address to contact when you know a domain but not a username; **mailbot** = an
> automatic email auto-responder; **user agents** = email client programs (Gmail, Outlook,
> Thunderbird, Apple Mail).

## L. The World Wide Web, browsers and search engines

### WWW essentials

- **WWW** = a collection of **hypertext/hypermedia documents (web pages)** linked by
  **hyperlinks** and served over the internet. Invented by **Tim Berners-Lee in 1989**
  (2024 MCQ).
- Its enabling technologies: **HTML** (page markup), **HTTP** (transfer protocol), and the
  **URL** (address).
- **URL (Uniform Resource Locator)** — the unique **address of a file/resource on the
  internet** (2024 MCQ). Form: `protocol://host/path` e.g. `https://www.example.com/page.html`.
- **W3C (World Wide Web Consortium)** develops the standards/guidelines for the long-term
  growth of the Web (2024 MCQ).
- **Web server** — software/computer that **stores, retrieves and distributes the Web's
  files** (serves pages to browsers) (2024 MCQ). **Web browser** — the client program that
  requests and displays those pages.

### Web browser

A **browser** is the client application used to access and display web pages (Chrome,
Firefox, Edge, Safari). Typical **elements of the browser window**: **title bar, menu bar,
toolbar, address/URL bar, viewing/content window, status bar, scroll bars, tabs, bookmarks/
favourites bar.** *(2024 MCQ asked which is NOT an element of the browser window.)*

### Search engines — how searching works

A **search engine** (Google, Bing) is a service that helps users **find information on the
Web by keyword**. Its core requirement is a **huge database/index** of web pages (2024 MCQ:
"most required to a search engine" → **Database**). It works in three stages:

1. **Crawling** — automated programs (**spiders / crawlers / bots**) follow links and fetch
   web pages.
2. **Indexing** — the fetched pages are analysed and stored in a searchable **index**
   (by keywords).
3. **Searching / ranking** — when you enter a query, the engine matches it against the index
   and returns results **ranked by relevance** (using text matching, keyword frequency,
   link popularity, etc.). *(2024 MCQ: "approach NOT used in web searching" → **Priority
   setting** was the odd option; text matching, indexing, pattern matching, keyword
   frequency are used.)*

## M. Connectivity — ISP and connection types (HIGH PRIORITY)

### Concept

To reach the internet you connect through an **ISP (Internet Service Provider)** — a company
that sells internet access (and often email, hosting, etc.). You need: a **device + a
modem/router + a physical line + an account with an ISP**. The *type* of line/account is the
examinable part, because the options are dated and specific.

### Connection-type comparison table (learn this cold)

| Connection | Line / medium | Speed (approx) | How it works | Notes |
|---|---|---|---|---|
| **Dial-up** | Ordinary telephone line + **modem** | ~**56 kbps** (very slow) | Modem **dials** the ISP over the voice phone line; ties up the phone while connected | Oldest, cheapest, obsolete; connection established using a modem |
| **Leased line** | **Permanent dedicated** telephone line | High, fixed (e.g. T1 ≈ **1.544 Mbps** ⚠️ verify) | A private line **permanently connected** to the ISP — always on, dedicated bandwidth | Expensive; for businesses; created with a permanent telephone line |
| **ISDN** | Digital telephone line (Integrated Services Digital Network) | **64 / 128 kbps** (BRI: 2B+D) ⚠️ verify | Sends **digital** voice+data over the phone network; faster and cleaner than dial-up | Narrowband ISDN and Broadband ISDN (B-ISDN) exist |
| **Cable** | **Coaxial cable TV** network | Several Mbps+ | Shares the cable-TV line; a cable modem connects the PC | Faster than dial-up; shared bandwidth in a locality |
| **DSL / Broadband** | Telephone copper (DSL) or fibre | Mbps–Gbps | "Always-on" high-speed digital line; DSL runs data above voice frequencies so phone stays free | The modern default |
| **VSAT** | **Satellite** (Very Small Aperture Terminal) | Varies | An **earthbound station** with a small dish communicates via a satellite — used where cabling is impractical (remote areas) | Satellite communication; higher latency |
| **Wireless / Wi-Fi / mobile** | Radio (Wi-Fi, 3G/4G/5G) | Varies | Connect via radio frequency to an access point / cell tower | Hotspot = a Wi-Fi access point |

> **MCQ calibration (2024 matching question):** **VSAT** = "an earthbound station used in
> satellite communication"; **Dial-up** = "established using a modem"; **Cable connection**
> = "created/carried over cable"; **Leased connection** = "created with a permanent telephone
> line." Learn those four phrases verbatim.
> Also (2024): **Telnet is NOT a type of internet connection** (it is a remote-login
> service); **Bluetooth is NOT a way to connect to the internet** in the intended answer
> (Wi-Fi, hotspot are) ⚠️ verify — Bluetooth tethering technically exists, but the exam
> treated Bluetooth as the odd one out.

## Likely exam questions — Internet Technology

**5-mark**
- Differentiate between the internet and an intranet. *(table)*
- What is a URL? Give its structure with an example.
- Differentiate between a web browser and a web server.
- List and briefly explain any five internet services.
- What is video conferencing? Name its components.
- What is an ISP?

**10-mark**
- Explain the various services provided by the internet. *(the services table.)*
- Explain the different types of internet connections. *(the connectivity table — a strong
  banker; VSAT/ISDN/leased/dial-up are the diploma-favourite content.)*
- How does a search engine work? Explain crawling, indexing and ranking.
- Differentiate between intranet, internet and extranet. *(three-column table.)*

**15-mark**
- Explain internet technology in detail: intranet vs internet, the main internet services,
  the WWW with browsers and search engines, and the types of internet connectivity.
  *(The "everything" question — structure exactly as Parts J→M.)*

## MCQ traps — Internet Technology

- Intranet **cannot** host **public web sites** (it is private).
- **SMTP** sends mail; **POP3** receives/stores it in the mailbox.
- **Usenet** is one of the **oldest** internet services (older than the WWW).
- **FTP** transfers arbitrary files; **Telnet** is remote login (NOT a connection type).
- **Video conferencing** components do **not** include an "interpreter".
- Search engine's most-required asset = **database/index**; "priority setting" is not a
  search approach.
- **URL** = address of a file on the internet; **W3C** sets Web standards; **Tim Berners-Lee**
  invented the WWW (1989).
- Connection matching: **VSAT = satellite / earthbound station**, **dial-up = modem**,
  **leased = permanent line**.

---

## One-paragraph summary, if you read nothing else

Three cheap-mark units. For **viruses**, learn the syllabus's own six-type taxonomy
(command-processor, boot-sector, executable-file, file-specific, memory-resident, macro),
the virus-vs-worm-vs-trojan contrasts, and the three numbered lists (protect / recognise /
deal-with). For **system analysis**, this is MIS vocabulary, not software engineering: define
a system and its IPOFC elements, classify systems five ways (physical/abstract, open/closed,
deterministic/probabilistic, man-made/natural, permanent/temporary), name TPS/MIS/DSS/ESS,
recite the SDLC phases with their deliverables, and know the analyst's role and the failure
factors. For **internet technology**, know intranet-vs-internet, the internet services, the
WWW/browser/search-engine story, and above all the dated connectivity table (dial-up, leased,
ISDN, VSAT). All three are more about reproducing the textbook's exact words than about
understanding — so drill the phrasing, build every "differentiate" table in advance, and
answer with tables and numbered lists.

### Where the rest of these units live

| You need... | Look in |
|---|---|
| Network fundamentals (OSI, TCP/IP, media, topologies, devices) | `Materials\_Shared\CORE_05_ComputerNetworks.md` + Paper-I §5 |
| Software process models, cost estimation, testing, QA | `CORE_07_SoftwareEngineering.md` ⚠️ confirm filename in `_Shared\` |
| Legacy protocols (NetBEUI, IPX/SPX), IEEE 802.x | `CORE_05_ComputerNetworks.md` |
| Hardware, storage, motherboard | `CSDip_01_HardwareAndDevices.md` |
| MS Office / MS-DOS / Windows | `CSDip_02_MSOffice_and_DOS.md` (written by another agent) |
| Exam dates, strategy, day-by-day plan | `CSDip_00_OVERVIEW.md` |
