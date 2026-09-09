# FOR_00 — Computer Forensic Elective: Overview, Syllabus Checklist & Study Plan

> **Read this file first, and re-read it every Sunday.** It is the map. Everything else is territory.

---

## 1. The hard facts

| Item | Detail |
|---|---|
| Exam | Nagaland PSC **Combined Technical Services Examination (CTSE) 2026** |
| Elective | **Computer Forensic** |
| **13 Oct 2026, 09:00–12:00** | Technical **Descriptive Paper-I** — 100 marks, 3 hours |
| **13 Oct 2026, 13:00–15:00** | Technical **MCQ** — 100 questions × 2 = **200 marks**, 2 hours |
| **14 Oct 2026, 09:00–12:00** | Technical **Descriptive Paper-II** — 100 marks, 3 hours |
| Total for this elective | **500 marks** |
| Negative marking | **MCQ only: −1/3 of the marks per wrong answer (= −0.667)** |
| Days left from 5 Sep 2026 | **38 days** to Paper-I |

> ⚠️ Note the brutal shape of 13 October: a 3-hour descriptive paper in the morning and a 2-hour, 100-question MCQ in the afternoon, with roughly a one-hour gap. **Physical stamina is an exam skill.** In the last two weeks do at least three full-length timed simulations that replicate this back-to-back load.

### Descriptive paper structure (observed from CTSE 2025 CS-Degree Paper-I; assume identical)

```
Maximum marks 100                Duration 180 minutes
Section A   Q1–Q10    answer any 8    8 × 5  = 40
Section B   Q11–Q15   answer any 3    3 × 10 = 30
Section C   Q16–Q19   answer any 2    2 × 15 = 30
```

**Consequence:** you get choice in every section. You may legitimately abandon your two weakest
topics per section and still score full marks. But choice is only useful if you have *breadth* —
a candidate who knows three topics deeply and nothing else will find all three sitting in
Section C and none in Section A.

### Time budget inside the descriptive paper

| Section | Questions | Marks | Minutes | Per question |
|---|---|---|---|---|
| A | 8 × 5 | 40 | 65 min | ~8 min |
| B | 3 × 10 | 30 | 50 min | ~17 min |
| C | 2 × 15 | 30 | 55 min | ~27 min |
| Reading / choosing / buffer | — | — | 10 min | — |

Answer **Section A first** (fastest marks per minute), then C (the long ones, while you are
still fresh enough to structure them), then B. Write question numbers clearly; examiners in
"answer any N" papers mark the **first N** they find, so cross out anything extra.

---

## 2. Where each official unit lives

Legend: **[HERE]** = written in this ComputerForensic folder · **[CORE]** = shared-core file in
`..\_Shared\` written by the shared-core process — do **not** study a second version of it.

> ⚠️ **verify the exact CORE filenames** against `C:\Users\hp\Desktop\prep\Materials\_Shared\`
> when that process finishes. The names below are the expected ones; if they differ, the *topic*
> mapping is still correct.

### Technical Paper-I

| Unit | Official title | Coverage | File |
|:--:|---|:--:|---|
| 1 | Introduction to Forensic Science | [HERE] | `FOR_01_ForensicScienceFundamentals.md` §1–§3 |
| 2 | Physical Evidence | [HERE] | `FOR_01` §4 |
| 3 | Scene of Crime | [HERE] | `FOR_01` §5–§6 |
| 4 | Introduction to Computer Hardware | [HERE] | `FOR_02_SystemArtifacts.md` §1–§4 |
| 5 | Windows / Linux / macOS System Artifacts | [HERE] | `FOR_02` §5–§8 |
| 6 | Logic, Formula, Unit (Boolean logic, gates, K-maps, flip-flops, number systems) | [CORE] | `_Shared\CORE_01_DigitalLogic.md` + pointer in `FOR_02` §9 |
| 7 | Computer Networks | [CORE] | `_Shared\CORE_05_ComputerNetworks.md` + forensic slant in `FOR_03` §3 |
| 8 | Operating Systems + UNIX + Windows OS | [CORE] | `_Shared\CORE_03_OperatingSystems.md`, `CORE_04_UnixLinux.md` + forensic slant in `FOR_02` §7 |
| 9 | Computer Organization & Architecture | [CORE] | `_Shared\CORE_02_ComputerOrganisation.md` |

### Technical Paper-II

| Unit | Official title | Coverage | File |
|:--:|---|:--:|---|
| 1 | Cyber Crime, first responder, search & seizure, imaging & hashing, recovery | [HERE] | `FOR_03_CyberCrimeAndIncidentResponse.md` §1–§7 |
| 2 | Web Browsers, Email, VM & Cloud forensics | [HERE] | `FOR_03` §8–§10 |
| 3 | Software Engineering | [CORE] | `_Shared\CORE_07_SoftwareEngineering.md` |
| 4 | Programming in C / OOP / C++ / Web programming | [CORE] | `_Shared\CORE_09_C_CPP.md` |
| 5 | Database & SQL | [CORE] | `_Shared\CORE_06_DBMS_SQL.md` (SQL injection also in `FOR_03` §1) |
| 6 | Data & File Structures | [CORE] | `_Shared\CORE_08_DataStructures.md` |
| 7 | Mobile Computing | [HERE] | `FOR_04_DigitalEvidenceAndMobile.md` §7–§9 |
| 8 | Digital Evidences | [HERE] | `FOR_04` §1–§6 |

### Practice

| File | Contents |
|---|---|
| `FOR_05_MCQ_and_QuestionBank.md` | 120 MCQs with answer key + explanations; 24 × 5-mark, 14 × 10-mark, 10 × 15-mark descriptive questions with model answer skeletons |

---

## 3. Syllabus tick-box checklist

Print this. Tick a box only when you can reproduce the topic **from memory on blank paper**.
Two passes: `[a]` = first read done, `[b]` = recalled from memory.

### TP-I Unit 1 — Introduction to Forensic Science
- [ ] Definition of forensic science; forensic vs criminalistics
- [ ] History & development (international milestones; Indian milestones)
- [ ] Scope & development of forensic science **in India**
- [ ] **Locard's Exchange Principle** (state, explain, example)
- [ ] Law of Individuality
- [ ] Principle of Comparison
- [ ] Principle of Analysis
- [ ] Law of Progressive Change
- [ ] Principle of Circumstantial Facts / Facts do not lie
- [ ] Significance & limitations of forensic science
- [ ] **DFSS** — its role and what sits under it
- [ ] **CFSLs** — locations and their specialities
- [ ] **State FSLs, Regional FSLs, Mobile FSLs (MFSU)**
- [ ] **GEQD / CFSL-Kolkata questioned-document work**
- [ ] Divisions inside an FSL and what each does
- [ ] NCRB, BPR&D, NICFS, DNA/Cyber labs — what they are
- [ ] Ethics: code of conduct, expert-witness duty, bias types, ethical failures

### TP-I Unit 2 — Physical Evidence
- [ ] Definition, functions/value of physical evidence
- [ ] Types (biological, chemical, physical, trace, impression, documentary, electronic)
- [ ] **Class vs individual characteristics** — definition + 6 examples each
- [ ] Search methods: strip/line, grid, spiral (in/out), zone/quadrant, wheel/ray — draw all five
- [ ] **Chain of custody** — meaning, form contents, break consequences

### TP-I Unit 3 — Scene of Crime
- [ ] Meaning; indoor/outdoor; primary/secondary; macroscopic/microscopic
- [ ] Protection & securing; cordon; the three-layer perimeter; entry/exit log
- [ ] Documentation: notes, photography (overall→mid→close-up, with/without scale), videography
- [ ] Sketching: rough vs finished; rectangular coordinate, triangulation, baseline, polar/azimuth
- [ ] 3-D scanning technique
- [ ] Processing: discovery → recognition → examination → collection → preservation → packaging → sealing → labelling → forwarding
- [ ] Correct packaging per evidence type (esp. biological = paper, never plastic)
- [ ] Safety measures / PPE
- [ ] Legal: admissibility of e-evidence, **§65B certificate**, IT Act 2000 key sections, **BSA 2023**

### TP-I Unit 4 — Computer Hardware
- [ ] Components, motherboard, chipset, buses; processor; memory hierarchy
- [ ] HDD geometry: platter, track, sector, cluster, CHS vs LBA
- [ ] SSD: NAND, wear levelling, TRIM, garbage collection — **the forensic problem**
- [ ] Boot process: POST → BIOS/UEFI → MBR/GPT → bootloader → kernel → init
- [ ] File systems: FAT12/16/32, exFAT, NTFS, ext2/3/4, HFS+, APFS — comparison table

### TP-I Unit 5 — System Artifacts
- [ ] Windows registry: hives, file locations, USB history, MRU, Run keys, UserAssist, ShellBags
- [ ] Event logs + key event IDs
- [ ] LNK files, prefetch, jump lists
- [ ] **ADS** — what, why, how to detect
- [ ] Hidden files & attributes
- [ ] **File slack vs volume/drive slack** (guaranteed question)
- [ ] Unallocated space, Recycle Bin ($I/$R), thumbcache, pagefile/hiberfil
- [ ] Linux: layout, inode, permissions, dot-files, /etc/passwd,shadow,group, /var/log, bash_history, cron
- [ ] macOS: launchd/plists, network config, hidden dirs, unified logs, Keychain, Spotlight, FSEvents

### TP-I Units 6–9 — see CORE files
- [ ] CORE digital logic done
- [ ] CORE networks done (+ forensic slant read)
- [ ] CORE OS + UNIX done (+ forensic slant read)
- [ ] CORE COA done

### TP-II Unit 1 — Cyber Crime & Incident Response
- [ ] Cyber-crime forms & classification; internal vs external attacks
- [ ] Crimes against person / property / government / society
- [ ] Social-media crimes; ATM & banking frauds (skimming, cloning, phishing, vishing, UPI)
- [ ] Data privacy issues; DPDP Act 2023 (awareness level)
- [ ] Packet sniffing; spoofing (IP/MAC/ARP/DNS/email/caller-ID)
- [ ] Web security: SQLi, XSS, CSRF, session hijacking, directory traversal, file upload
- [ ] Malware taxonomy: virus, worm, trojan, ransomware, rootkit, keylogger, botnet, spyware, APT
- [ ] **First responder** role, toolkit, do's & don'ts, pull-plug vs graceful shutdown
- [ ] Search & seizure procedure; legal authority
- [ ] **Order of volatility** (memorise the 8-item list, RFC 3227)
- [ ] Live vs dead-box forensics
- [ ] Imaging: bit-stream vs logical copy; write blockers; raw/E01/AFF
- [ ] Hashing: MD5, SHA-1, SHA-256; verification workflow; collisions
- [ ] Deleted-file mechanics; **file carving**; **file signatures table**
- [ ] Steganography & steganalysis
- [ ] Anti-forensics: wiping, encryption, timestomping, obfuscation, log tampering

### TP-II Unit 2 — Browsers, Email, VM/Cloud
- [ ] Browser artifacts: cookies, bookmarks, cache, history, sessions, plugins, downloads
- [ ] Storage locations per browser (Chrome/Firefox/Edge/IE)
- [ ] Private browsing — what survives and where
- [ ] Email protocols SMTP/POP3/IMAP/MIME; ports; architecture (MUA/MSA/MTA/MDA)
- [ ] **Header analysis line-by-line** — trace originating IP, detect spoofing (SPF/DKIM/DMARC)
- [ ] VM forensics: VMDK/VDI/VHD, snapshots, .vmem, memory analysis
- [ ] Cloud forensics: multi-tenancy, jurisdiction, elasticity, chain of custody, SLA

### TP-II Units 3–6 — see CORE files
- [ ] CORE software engineering done
- [ ] CORE C/C++/OOP/web done
- [ ] CORE DBMS/SQL done
- [ ] CORE data structures done

### TP-II Unit 7 — Mobile Computing
- [ ] Cells, frequency reuse, handoff, cellular framework
- [ ] Wireless delivery technologies & switching methods
- [ ] Mobile information access devices
- [ ] Mobile data internetworking standards; WAP stack
- [ ] Cellular data protocols 1G→5G, GSM vs CDMA, GPRS/EDGE/UMTS/HSPA/LTE
- [ ] Mobile computing applications; mobile databases; M-business
- [ ] Mobile forensics: SIM/handset/card, IMEI/IMSI/ICCID, **CDR analysis**
- [ ] Acquisition levels: manual → logical → file system → physical → JTAG → chip-off
- [ ] Android & iOS artifacts; tools

### TP-II Unit 8 — Digital Evidence
- [ ] Storage devices; order of volatility (again)
- [ ] **ACPO 4 principles**
- [ ] Digital forensic process model (6 phases) — draw it
- [ ] Acquisition: physical / logical / sparse; live / static
- [ ] Data validation; imaging & cloning; hash values
- [ ] File extensions vs signatures
- [ ] Registry for evidence (cross-ref)
- [ ] Data recovery techniques
- [ ] MBR vs GPT; partitions, volumes, slack
- [ ] Email tracing; social media analysis; steganalysis
- [ ] **Forensic report writing + expert testimony**
- [ ] Tools table (EnCase, FTK, Autopsy, Cellebrite, Wireshark, Volatility, dd, X-Ways)

---

## 4. Recommended study order (38 days, ~3.5 h/day)

The ordering principle: **do the forensics-unique material first**, because it is (a) worth
the most marks in this elective, (b) entirely new to you, and (c) needs the most repetitions.
The CORE material is engineering you already half-know; it revises fast and late.

### Phase 1 — Forensics-unique foundation (Days 1–12, 5–16 Sep)

| Day | Work |
|---|---|
| 1–2 | `FOR_01` §1–§3: forensic science definition, history, principles, **Indian lab structure**, ethics. Make a one-page mind-map of DFSS→CFSL→SFSL→RFSL→MFSU. |
| 3–4 | `FOR_01` §4–§5: physical evidence, class vs individual, search patterns, chain of custody, crime scene documentation. Hand-draw all 5 search patterns twice. |
| 5 | `FOR_01` §6: Indian legal framework — §65B, IT Act, BSA 2023. Verify the flagged items. |
| 6–7 | `FOR_02` §1–§4: hardware, storage geometry, SSD problem, boot process, file system table. |
| 8–10 | `FOR_02` §5–§6: Windows artifacts — this is the densest, highest-yield block in TP-I. Registry keys and slack space need three passes. |
| 11 | `FOR_02` §7–§8: Linux + macOS artifacts. |
| 12 | **Consolidation day.** Blank-paper recall of everything in Phase 1. MCQ set 1. |

### Phase 2 — Cyber crime & digital evidence (Days 13–24, 17–28 Sep)

| Day | Work |
|---|---|
| 13–14 | `FOR_03` §1–§2: cyber-crime taxonomy, frauds, sniffing, spoofing, web attacks, malware. |
| 15–16 | `FOR_03` §3–§4: first responder, search & seizure, order of volatility, live vs dead. Memorise the volatility list cold. |
| 17–18 | `FOR_03` §5–§6: imaging, write blockers, hashing, deleted files, carving, signatures, stego, anti-forensics. |
| 19 | `FOR_03` §7: browser forensics. |
| 20 | `FOR_03` §8: **email header analysis** — do the walkthrough twice, then invent your own header and trace it. |
| 21 | `FOR_03` §9: VM & cloud forensics. |
| 22–23 | `FOR_04` §1–§6: digital evidence, ACPO, process model, acquisition, MBR/GPT, report writing, tools table. |
| 24 | **Consolidation.** Recall + MCQ set 2 + write two 15-mark answers under time. |

### Phase 3 — Mobile + CORE sweep (Days 25–32, 29 Sep – 6 Oct)

| Day | Work |
|---|---|
| 25–26 | `FOR_04` §7–§9: mobile computing + mobile forensics + tools. |
| 27 | CORE networks revision + `FOR_03` §3 forensic slant. |
| 28 | CORE OS + UNIX revision + `FOR_02` §7 forensic slant. |
| 29 | CORE digital logic + COA revision. |
| 30 | CORE DBMS/SQL (+ SQL injection link) + software engineering. |
| 31 | CORE data structures + C/C++/web programming. |
| 32 | **Full descriptive mock, Paper-I, 3 hours, timed.** |

### Phase 4 — Drill and simulate (Days 33–38, 7–12 Oct)

| Day | Work |
|---|---|
| 33 | Full descriptive mock, Paper-II, timed. Self-mark both mocks harshly. |
| 34 | Full 100-question MCQ under 2 hours. Analyse every wrong answer. |
| 35 | Weak-area repair from mock analysis. |
| 36 | **Full simulation of 13 Oct**: 9–12 Paper-I, break, 13–15 MCQ. |
| 37 | Rapid revision: all "Key points" bullet blocks + every table + all diagrams. |
| 38 (12 Oct) | Light. Re-read `FOR_00`, the volatility list, the signature table, the ACPO principles, the lab structure map. Sleep early. |

### Daily rhythm (3.5 h)

```
0:00–0:20  Active recall of yesterday (blank paper, no notes)
0:20–1:50  New material — read, then immediately convert to bullets in your own words
1:50–2:00  Break
2:00–3:00  Worked examples / diagrams / write one full descriptive answer
3:00–3:30  20 MCQs on today's topic + review
```

---

## 5. Scoring strategy

**MCQ (200 marks, negative 1/3).** With −0.667 per wrong and +2 per right, a pure random guess
among 4 options has expected value (0.25×2) + (0.75×−0.667) = **0.0** — exactly break-even.
So:

| Situation | Action |
|---|---|
| You know it | Answer. |
| You can eliminate **1** option (3 left) | EV = (1/3×2)+(2/3×−0.667) = **+0.22** → answer |
| You can eliminate **2** options (2 left) | EV = (1/2×2)+(1/2×−0.667) = **+0.67** → definitely answer |
| Zero idea, no elimination | EV = 0 → leave it. Not worth the risk or the time. |

Practically: **eliminate-then-guess is profitable; blind guessing is not.** Do two passes —
pass 1 answer everything you know in ~70 minutes, pass 2 work the eliminations in the
remaining 50. Never leave a question you have eliminated even one option on.

**Descriptive.** Examiners reward *structure and coverage*, not prose beauty. For every answer:

1. One-line definition in the first sentence (the examiner's first tick).
2. Headed sub-points, numbered or bulleted.
3. A **diagram or table** wherever remotely justified — 15-mark answers without a diagram lose easy marks.
4. An Indian legal/institutional reference where relevant (§65B, IT Act, CFSL, chain of custody form).
5. A one-line conclusion.

Rough length: 5-mark ≈ 3/4 page, 10-mark ≈ 1.5–2 pages, 15-mark ≈ 3 pages + diagram.

---

## 6. Things to verify before the exam

Collected list of everything flagged ⚠️ across these notes — resolve them against a primary
source (bare act text on india.gov.in / indiacode.nic.in, DFSS/MHA website) in Phase 3:

1. Exact CORE filenames in `_Shared\`.
2. The current section numbering of the **Bharatiya Sakshya Adhiniyam 2023** for electronic
   evidence (the BSA replaced the Indian Evidence Act 1872 w.e.f. 1 July 2024; the §65B analogue
   is generally cited as **BSA §63** with the certificate under **§63(4)** — ⚠️ verify).
3. The current count and locations of CFSLs (the network has been expanded in recent years,
   including new National Forensic Sciences University campuses — ⚠️ verify the current list).
4. Whether NPSC's paper cites the **Indian Evidence Act 1872** or the **BSA 2023** — write both
   in the exam ("§65B IEA, now §63 BSA 2023") and you cannot be marked wrong.
5. IT Act section numbers beyond the core set (§43, §65, §66, §66C, §66D, §66E, §66F, §67, §69,
   §70, §72, §79) — do not invent any others.
