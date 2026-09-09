# FOR_04 — Digital Evidence, the Forensic Process, Mobile Computing & Mobile Forensics
### Covers TP-II Unit 8 (Digital Evidences) and Unit 7 (Mobile Computing)

> TP-II Unit 8 is the **"principles and process" capstone** of the elective — it takes everything
> from FOR_03 (imaging, hashing, recovery, tracing) and frames it as a disciplined, court-defensible
> **process** with named principles (ACPO), a named **model** (identify→…→present), and a
> deliverable (the **report** and **expert testimony**). Unit 7 is two halves welded together: the
> **mobile computing** engineering (cells, protocols, mobile databases, M-business) *and* **mobile
> forensics** (SIM/IMEI, CDR, acquisition levels, Android/iOS). The engineering half overlaps CORE
> networks; the forensic half is unique to this elective and high-yield.
>
> **Cross-references:** imaging/hashing/write blockers/carving/signatures/steganalysis are treated
> in depth in **FOR_03 §5–§6** and file systems/registry/slack in **FOR_02**. Here they are
> **summarised and framed as process/evidence**, not repeated in full — the exam wants you to *place*
> each technique inside the process and the ACPO principles.
>
> ⚠️ **Indian-law accuracy:** §65B IEA 1872 → §63 BSA 2023 (cite both); IT Act sections per FOR_03;
> flag any uncertain section number `⚠️ verify`. Never invent a section number or a case name.

---

# PART A — DIGITAL EVIDENCE AND THE FORENSIC PROCESS (TP-II Unit 8)

# §1. Digital Evidence — Concept and Characteristics

## 1.1 Concept

**Digital evidence = any information of probative value that is stored or transmitted in binary
form** and may be relied upon in court. It is a **silent, invisible witness**: unlike a bloodstain
you can hold, digital evidence must be *made visible* by tools, and it is uniquely **fragile,
easily altered, easily copied, and time-sensitive**.

**Characteristics (learn as a list — a common 5-mark question):**
1. **Latent** — not visible to the naked eye; needs tools/software to be perceived.
2. **Fragile / volatile** — easily changed, damaged or destroyed (a single mount writes to it).
3. **Easily duplicated** — a perfect **bit-for-bit copy** is possible (and is the working method).
4. **Alterable and time-sensitive** — timestamps, RAM, logs change or vanish (order of volatility).
5. **Can transcend jurisdictions** — spread across devices, servers, countries.
6. **Voluminous** — terabytes; needs triage and selective analysis.
7. **Machine/format dependent** — needs the right tool to interpret.

> **Admissibility requirements (the four the examiner wants):** digital evidence must be
> **Authentic** (it is what it claims to be — proven by hash + chain of custody), **Reliable/
> accurate** (sound tools and methods), **Complete** (not cherry-picked), and **legally obtained &
> admissible** (lawful seizure + **§65B IEA / §63 BSA certificate**). Some books add
> **"believable"** (understandable to the court). Cite the certificate requirement explicitly.

## 1.2 Digital-evidence storage devices (where it lives)

HDD, SSD, USB flash, SD/microSD, eMMC/UFS (phones), optical (CD/DVD/Blu-ray), magnetic tape (LTO),
RAM/volatile memory, firmware/NVRAM, RAID/NAS/SAN, and **cloud**. (Geometry, SSD/TRIM problem and
RAID levels are in **FOR_02 §2**; cloud in **FOR_03 §10**.)

## 1.3 Order of volatility (recap — see FOR_03 §4.3 for the full list + RFC 3227)

Most → least volatile: **registers/cache → routing/ARP/process tables & network connections → RAM →
temp/swap files → disk → remote logs → physical topology → archival backups.** Collect most-volatile
first. This is the operational form of the **Law of Progressive Change** (FOR_01 §1.5).

---

# §2. Basic Rules / Principles for Cyber Forensics — the ACPO Principles

> **This is a near-certain question.** Learn the **four ACPO principles** verbatim in substance.
> "ACPO" = the (UK) **Association of Chief Police Officers**; its *Good Practice Guide for Digital
> Evidence* is the most-cited statement of digital-forensic first principles worldwide.

| # | Principle (substance) | What it means in practice |
|:--:|---|---|
| **1** | **No action taken should change data** held on a computer/storage medium that may be relied upon in court | Use **write blockers**; image, don't work on the original; don't boot the evidence machine |
| **2** | If a person **must access the original** data, they must be **competent** to do so and able to **explain the relevance and implications** of their actions | Live acquisition (RAM, unlocked encryption) is allowed **when justified** by a competent examiner — document *why* |
| **3** | An **audit trail** (record of all processes applied) should be created and preserved; an **independent third party should be able to repeat** them and reach the same result | Contemporaneous notes, tool versions, hashes, chain of custody → **reproducibility** |
| **4** | The **person in charge** of the investigation has **overall responsibility** for ensuring these principles are followed | Accountability sits with the officer/lead |

> **How to deploy in the exam:** whenever a question asks "how do you ensure evidence is
> admissible / defensible", answer through the four ACPO principles + hashing + chain of custody +
> §65B/§63. It is a reusable spine for many 10/15-mark answers.
>
> Related frameworks to name-drop: **RFC 3227** (evidence collection order), **NIST SP 800-86**
> (guide to integrating forensics into incident response), **ISO/IEC 27037** (identification,
> collection, acquisition, preservation of digital evidence) ⚠️ verify these document numbers before
> quoting them as exact.

---

# §3. The Digital Forensic Process Model — the 6 phases (draw it)

> **Guaranteed descriptive question: "Explain the phases of the digital forensic process / cyber
> forensic investigation."** Learn the six phases, one line each, plus what could go wrong at each.

```
 IDENTIFICATION → PRESERVATION → COLLECTION → EXAMINATION → ANALYSIS → PRESENTATION
   (find it)       (protect it)   (acquire it)  (extract it)  (interpret) (report/testify)
        └───────────────── documentation & chain of custody run through ALL phases ─────────┘
```

| Phase | Goal | Key activities | Failure mode |
|---|---|---|---|
| **1. Identification** | Recognise what and where the evidence is | Identify devices, data sources, scope, legal authority; assess power state; identify volatile vs non-volatile | Missing a device (NAS, phone, cloud); scope creep beyond warrant |
| **2. Preservation** | Prevent any change | Isolate/secure scene, write blockers, order of volatility, **imaging with hashing**, chain of custody, Faraday for phones | Booting the machine; no write blocker; remote wipe |
| **3. Collection / Acquisition** | Obtain the data | Bit-stream/logical/sparse imaging; live vs static; hash source & image | Wrong acquisition type; unverified image |
| **4. Examination** | Extract the relevant data from the mass | Recover deleted files, carve, decrypt, keyword search, filter with hash sets, parse artifacts | Overlooking slack/unallocated/ADS; missing hidden data |
| **5. Analysis** | Interpret and correlate → conclusions | Timeline reconstruction, link analysis, attribution, corroboration across sources | Over-claiming; confirmation bias (FOR_01 §3.4) |
| **6. Presentation / Reporting** | Communicate to the court | Clear report, exhibits, **expert testimony**, §65B/§63 certificate | Jargon; unsupported opinion; broken chain exposed in cross |

> Some models use different labels (**Kruse & Heiser: Acquire → Authenticate → Analyse**; **DFRWS:
> Identification → Preservation → Collection → Examination → Analysis → Presentation → Decision**;
> **NIST SP 800-86: Collection → Examination → Analysis → Reporting**). If asked for a model, give
> the **six-phase** version and mention that NIST condenses it to **four** (Collection, Examination,
> Analysis, Reporting). Naming one alternative model earns a mark.

---

# §4. Data Acquisition Methods

## 4.1 By completeness

| Method | What it captures | Use / trade-off |
|---|---|---|
| **Physical (bit-stream) acquisition** | **Every sector** — allocated + unallocated + slack + HPA/DCO | The forensic default; enables deleted-file recovery & carving; largest, slowest |
| **Logical acquisition** | Only the **active files** the file system reports | Faster/smaller; **no deleted data**; used for huge systems or targeted, authorised subsets |
| **Sparse acquisition** | A logical copy of **selected data + some deleted/unallocated fragments** relevant to the case, without the whole device | Middle ground for very large data sets; capture only what is relevant (common in mobile/enterprise) |
| **Targeted / triage** | Specific artifacts (a few files, memory) captured quickly on scene | Live triage; used to decide priorities |

## 4.2 By system state

| | **Live (dynamic) acquisition** | **Static (dead-box) acquisition** |
|---|---|---|
| System | Running | Powered off |
| Gets | RAM, running processes, network state, **unlocked encrypted volumes**, cloud sessions | Full disk image, repeatable |
| Risk | Alters some state (justify per ACPO P2); rootkit may lie | Loses all volatile evidence |

(Full treatment in **FOR_03 §4.4**; the modern standard is **RAM live first, then dead-box disk**.)

## 4.3 Imaging vs cloning; formats; write blockers; validation (recap)

- **Imaging** = create a *file* (raw/`dd`, **E01/EWF**, **AFF**) representing the device; **cloning**
  = disk-to-disk copy. Prefer imaging for evidence. (Formats: FOR_03 §5.3.)
- **Write blockers** (hardware = gold standard) prevent any write to the evidence. (FOR_03 §5.2.)
- **Data validation** = prove the acquired copy equals the source and stays unchanged, by
  **hashing** (MD5 128-bit / SHA-1 160-bit / SHA-256 256-bit; compute at acquisition, re-verify
  later; use two algorithms). (FOR_03 §5.4, incl. the collision/SSD-GC caveats.)

---

# §5. Hash Algorithms, File Extensions & Signatures, Registry, Recovery, Disks

These are the "toolbox" facts Unit 8 lists; each is treated fully elsewhere — here is the exam-ready
compression with pointers.

## 5.1 Hash values (see FOR_03 §5.4)
**MD5 (128-bit), SHA-1 (160-bit), SHA-256 (256-bit).** Hash = the digital **seal/fingerprint**;
avalanche effect; MD5/SHA-1 collision-broken (still fine against accidental change; use SHA-256 or
dual hashes for defensibility). Uses: **integrity verification**, **de-duplication**, and
**hash-set filtering** (NSRL known-good hashes to *exclude* OS files; known-bad hash sets to *flag*
contraband like CSAM without opening files).

## 5.2 File extensions vs file signatures (see FOR_03 §6.3 for the full table)
**Extension = renamable name; signature (magic bytes) = true type.** Must-know headers: **JPEG
`FF D8 FF`**, **PDF `%PDF`(25 50 44 46)**, **PNG `89 50 4E 47`**, **ZIP/Office `PK`(50 4B 03 04)**,
**GIF `GIF87a/GIF89a`**, **EXE `MZ`(4D 5A)**, **ELF `7F 45 4C 46`**. Signature analysis detects
**extension-mismatch masquerading**.

## 5.3 Windows Registry as evidence (see FOR_02 §5)
The registry is an **unintentional activity log**. High-value keys: **USBSTOR / MountedDevices /
MountPoints2** (device history + user attribution), **UserAssist** (GUI program execution, ROT-13),
**ShellBags** (folders browsed), **RecentDocs / RunMRU / TypedPaths / WordWheelQuery** (files, run
commands, search terms), **Run/RunOnce/Services** (persistence), **TimeZoneInformation** (interpret
all timestamps). Keys carry a **LastWrite** time; values do not. Cite this in any "registry as
evidence" answer.

## 5.4 Data recovery techniques (see FOR_03 §6)
**Undelete** (metadata survives) → **carving** (content-based, no metadata) → **journal/shadow-copy**
recovery (`$LogFile`, `$UsnJrnl`, **Volume Shadow Copies**). Deleted-file mechanics differ by FS
(FAT `0xE5`; NTFS MFT unallocated; ext3/4 zero pointers). **SSD TRIM often destroys deleted data
autonomously** (FOR_02 §2.2).

## 5.5 Windows disks, files and partitions — **MBR vs GPT** (a guaranteed compare)

| Aspect | **MBR (Master Boot Record)** | **GPT (GUID Partition Table)** |
|---|---|---|
| Era / firmware | Legacy **BIOS** | **UEFI** |
| Location | **First sector, LBA 0** (512 bytes): 446 B bootstrap + 64 B partition table (4×16) + `55 AA` signature | **GPT header at LBA 1**; partition entries follow; a **protective MBR at LBA 0** for backward compat |
| Max partitions | **4 primary** (or 3 primary + 1 extended → logical drives) | **128** partitions typically (no extended/logical hack) |
| Max disk size | **~2 TB** (32-bit LBA × 512 B) | **~9.4 ZB** (64-bit LBA) |
| Redundancy | None (single MBR — a corrupt MBR loses the map) | **Backup GPT header + table at end of disk**; **CRC32** on header/table → integrity + recovery |
| Partition IDs | 1-byte type code | **GUID** type + unique partition GUID |
| Forensic points | MBR is a single easily-imaged sector; **MBR bootkits**; recover the 4 entries; disk signature at offset 440 | Examine backup GPT to detect tampering; recover deleted partitions from the backup table; **partition GUIDs** aid identification |

> **MCQ nuggets:** **MBR = 512 bytes, `55 AA` boot signature, max 4 primary partitions, 2 TB
> limit; GPT = UEFI, 128 partitions, huge size, redundant + CRC-checked.** The **partition table
> lives in the MBR (LBA 0)**; **GPT keeps a backup at the end of the disk.**

Also relevant: **partitions vs volumes**, **slack space** (file/RAM/volume slack — FOR_02 §5.9),
unallocated space, and **inter-partition/boot-record slack** as hiding places.

## 5.6 Email tracing, social-media analysis, steganalysis (see FOR_03 §6.5, §9, §1.5)
- **Email tracing:** read `Received:` headers **bottom→top** to the originating IP; check
  **SPF/DKIM/DMARC**, `From` vs `Return-Path`/`Message-ID`/`Reply-To`; then ISP legal process +
  §65B/§63 preservation. (Full walkthrough: FOR_03 §9.)
- **Social-media analysis:** documented open-source capture (URL + timestamp + hash) → platform
  legal process → device app-database forensics. (FOR_03 §1.5.)
- **Steganalysis:** statistical (chi-square, RS), signature, structure/size, comparison-to-original.
  (FOR_03 §6.5.)

---

# §6. Forensic Report Writing and Expert Testimony

> This closes the process (Phase 6). It is easy marks because it is a **list of qualities and
> contents** — and a CS graduate typically neglects it. Learn the report contents and the courtroom
> rules.

## 6.1 The forensic report — qualities and contents

**Qualities (state these):** **accurate, objective/impartial, complete, clear (plain language),
reproducible, defensible, and within the examiner's competence.** Report facts and findings; keep
opinion clearly separated and supported.

**Standard contents (as a list — reproduce in the exam):**
1. **Case/administrative details** — case/FIR number, requesting agency, examiner name & qualifications, dates.
2. **Authorisation & scope** — the warrant/authority and what was asked.
3. **Items received / chain of custody** — exhibit list, description, serial numbers, seal condition on receipt, **hash values**.
4. **Tools and methods** — hardware/software used **with versions**; write blocker used; SOP followed.
5. **Acquisition details** — type of image, source & image **hashes**, verification result.
6. **Findings** — the objective facts recovered (files, artifacts, timeline), with locations.
7. **Analysis / interpretation** — what the findings mean, correlations, timeline reconstruction.
8. **Conclusions / opinion** — clearly labelled as opinion, tied to findings, with limitations.
9. **Exhibits/appendices** — screenshots, extracted files, hash lists, logs.
10. **Declaration & signature** — including the **§65B IEA / §63 BSA certificate** for the electronic record.

## 6.2 Expert testimony (link to FOR_01 §3.3 duties of an expert)

- Expert opinion is admissible under **§45 Indian Evidence Act 1872 (now §39 BSA 2023 ⚠️ verify)**;
  it is **advisory — the court is not bound** and must apply its own mind.
- Reports of certain **Government Scientific Experts** may be used **without calling the expert**
  (old **CrPC §293**, now the corresponding **BNSS** provision ⚠️ verify number) — the GEQD,
  Chemical Examiner, FSL Director, etc. (FOR_01 §2.5).
- **The expert's primary duty is to the court**, not to the party that engaged them; testify **only
  within your field**; explain in plain language; disclose assumptions, limitations and anything
  detracting from the opinion; be ready to produce **case notes, tool logs, hashes and SOPs**.
- **Cross-examination targets:** the **chain of custody**, whether a **write blocker** was used,
  **hash verification**, tool validation, and examiner competence — which is exactly why the report
  must pre-answer all of them. **Never overstate** ("consistent with" vs "conclusively proves").

### §6.3 Likely exam questions (Part A)
| Marks | Question |
|:--:|---|
| 5 | List the characteristics of digital evidence. |
| 5 | State the ACPO principles of digital evidence. |
| 5 | Distinguish MBR and GPT. |
| 5 | Distinguish physical, logical and sparse acquisition. |
| 5 | What are the contents of a forensic report? |
| 10 | Explain the phases of the digital forensic process model with a diagram. |
| 10 | Discuss data acquisition methods (physical/logical/sparse, live/static) and when each is used. |
| 10 | Discuss forensic report writing and the duties of an expert witness in an Indian court. |
| 15 | Describe the complete lifecycle of digital evidence from identification to presentation, referencing ACPO principles, hashing, chain of custody and the §65B/§63 certificate. |

### MCQ traps (Part A)
- **ACPO has 4 principles**; Principle 1 = "no action should change the data".
- Process model (6): **Identification → Preservation → Collection → Examination → Analysis →
  Presentation**; **NIST condenses to 4** (Collection, Examination, Analysis, Reporting).
- **MBR max 4 primary partitions, ~2 TB, `55 AA`; GPT 128 partitions, UEFI, backup table + CRC.**
- **Logical acquisition does not capture deleted data; physical (bit-stream) does.**
- **Expert opinion is advisory** and admissible under IEA §45 / BSA §39 (⚠️ verify §39).
- Admissibility needs the **§65B IEA / §63 BSA certificate**.

---

# PART B — MOBILE COMPUTING (TP-II Unit 7, engineering half)

> This half overlaps CORE networks; keep it tight. The examiner wants the **cellular concepts**
> (cells, reuse, handoff), the **generation timeline (1G→5G)**, **GSM vs CDMA**, and **mobile
> databases / M-business**. Then Part C turns to the forensic payoff.

# §7. Mobile Connectivity and Cellular Concepts

## 7.1 Cells and the cellular idea

**Concept:** radio spectrum is scarce. Instead of one giant transmitter, the area is divided into
small **cells**, each served by a **base station (BTS/Node B/eNodeB/gNodeB)** at low power, so the
**same frequencies can be reused** in non-adjacent cells. This **frequency reuse** multiplies
capacity — the founding idea of cellular telephony.

| Term | Meaning |
|---|---|
| **Cell** | Geographic area served by one base station; drawn as a **hexagon** (tessellates without gaps/overlap) |
| **Frequency reuse** | Reusing the same channel set in cells far enough apart to avoid co-channel interference; **reuse factor / cluster size** (e.g. 3, 7) |
| **Cell splitting / sectoring** | Split a congested cell into smaller cells, or sector the antenna (e.g. 3×120°) to add capacity |
| **Handoff / handover** | Transferring an active call from one cell to the next as the user moves (**hard** handoff = break-before-make, GSM; **soft** handoff = make-before-break, CDMA) |
| **Roaming** | Using the network outside the home network's coverage |
| **MSC / HLR / VLR** | Mobile Switching Centre; Home & Visitor Location Registers — track subscriber location and route calls |

**Wireless delivery technologies & switching methods:** early cellular used **circuit switching**
(a dedicated channel for the call, like a landline). Data services moved to **packet switching**
(**GPRS/EDGE** overlay on GSM), and modern networks (**LTE/5G**) are **all-IP packet-switched**,
carrying even voice as packets (**VoLTE**). Switching evolution — *circuit → packet → all-IP* — is
worth one sentence.

## 7.2 Cellular generations (1G → 5G) — the timeline

| Gen | Era | Switching | Key technology | Data |
|:--:|---|---|---|---|
| **1G** | 1980s | Circuit | **Analog** (AMPS) | Voice only |
| **2G** | 1990s | Circuit (+packet overlay) | **Digital** — **GSM** (TDMA/FDMA) and **CDMA (IS-95)**; **SMS** | ~kbps; **GPRS (2.5G)** ~ up to ~114 kbps; **EDGE (2.75G)** ~up to ~384 kbps |
| **3G** | 2000s | Packet + circuit | **UMTS/WCDMA**, **CDMA2000**; **HSPA/HSPA+** | ~Mbps mobile broadband |
| **4G** | 2010s | **All-IP packet** | **LTE / LTE-Advanced** (OFDMA); **VoLTE** | tens–hundreds of Mbps |
| **5G** | 2019+ | All-IP | **NR** (New Radio), mmWave, massive MIMO, network slicing | Gbps, ultra-low latency, massive IoT |

## 7.3 GSM vs CDMA (a classic compare)

| Aspect | **GSM** | **CDMA** |
|---|---|---|
| Access method | **TDMA + FDMA** (time + frequency slots) | **Code Division** — all share the band, separated by unique codes |
| Subscriber identity | **SIM card** — identity is portable between handsets | Historically **handset-bound** (no removable SIM in classic CDMA) |
| Handoff | **Hard** (break-before-make) | **Soft** (make-before-make) |
| Global reach | Dominant worldwide | Fewer markets |
| Forensic note | **SIM is a discrete evidence item** (see §9); IMSI/ICCID on the SIM | Subscriber data tied to the device; no SIM to seize (in classic CDMA) |

## 7.4 Mobile information access devices, internetworking standards, WAP

- **Devices:** smartphones, tablets, feature phones, wearables, IoT/M2M modules, in-vehicle units.
- **Mobile data internetworking standards:** **GPRS/EDGE (2G data), UMTS/HSPA (3G), LTE/5G-NR**;
  local wireless **Wi-Fi (802.11)**, **Bluetooth**, **NFC**, **Zigbee**.
- **WAP (Wireless Application Protocol)** — the early stack for delivering web-like content to
  constrained phones: layered as **WAE / WSP / WTP / WTLS / WDP** over the bearer, with **WML**
  markup and a **WAP gateway** translating between WAP and HTTP. Largely historical (superseded by
  full mobile browsers) but examinable as a named stack. ⚠️ verify layer names before writing all
  five.

## 7.5 Mobile databases, tools/technology, and M-business

**Mobile database — concept and needs:** a database that runs on or synchronises with mobile
devices under **intermittent connectivity, limited power/storage, and mobility**. Requirements:
**local storage + replication/synchronisation** with a central server, **conflict resolution**,
**caching**, **disconnected operation**, and **security/encryption** on a device that is easily lost.

| Concept | Note |
|---|---|
| **Replication & synchronisation** | Local copy syncs with server when connected; **conflict resolution** (last-writer-wins, merge) needed |
| **Caching / hoarding** | Pre-fetch likely-needed data for offline use |
| **Transaction models** | Long-lived/disconnected transactions; **optimistic** concurrency suits mobility |
| **On-device engines** | **SQLite** (Android/iOS default), Realm; server side syncs to the enterprise DB |
| **Forensic payoff** | **SQLite databases are where the evidence is** on phones — SMS, call logs, contacts, chat apps, browser history all live in SQLite files (see §11) |

**M-business (mobile commerce):** conducting commerce via mobile devices — mobile banking/payments
(**UPI**, wallets), m-ticketing, location-based services, m-marketing. Enablers: secure mobile
payment, location awareness, ubiquity, personalisation. **Forensic relevance:** payment-app
databases, UPI transaction records, location history — heavily used in fraud cases (FOR_03 §1.6).

### §7.6 Likely exam questions (Part B)
| Marks | Question |
|:--:|---|
| 5 | What is frequency reuse? Why are cells drawn as hexagons? |
| 5 | Distinguish hard and soft handoff. |
| 5 | Distinguish GSM and CDMA. |
| 5 | What is a mobile database and what challenges does mobility create? |
| 10 | Trace the evolution of cellular networks from 1G to 5G. |
| 10 | Explain mobile database synchronisation and its forensic significance. |
| 15 | Describe the architecture of a cellular mobile network (cells, base stations, MSC/HLR/VLR, handoff) and explain how mobility and switching evolved from 1G to 5G. |

### MCQ traps (Part B)
- **GSM uses TDMA/FDMA + SIM; CDMA uses code division, historically SIM-less.**
- **GPRS/EDGE are 2.5G/2.75G packet data**; **UMTS/WCDMA = 3G**; **LTE = 4G**; **NR = 5G**.
- **1G analog, 2G digital (+SMS).**
- **Cells are hexagonal** (tessellation, uniform coverage).
- **Soft handoff = CDMA (make-before-break); hard handoff = GSM.**
- **SQLite** is the default on-device mobile database.

---

# PART C — MOBILE FORENSICS (TP-II Unit 7, forensic half)

# §8. Mobile Forensics — Concept and Challenges

**Concept:** the science of recovering digital evidence from mobile devices under forensically sound
conditions. A phone is a **richer, harder** exhibit than a PC: it holds calls, SMS, chats, photos
(with GPS), app data, location history and health data — but it is **always-on, always-networked,
encrypted by default, and endlessly varied** in OS/model.

**Why it is harder than disk forensics:**
- **Always connected** → risk of **remote wipe / new data overwriting** → **isolate immediately**
  (**Faraday bag / airplane mode**, keep charged).
- **Encryption by default** (modern Android/iOS full-disk/file-based encryption) → data unreadable
  without the passcode; **locked vs unlocked (AFU/BFU) state matters** hugely.
- **Proprietary, fast-changing** hardware/OS/connectors → tool support lags.
- **Volatile, hard to write-block** — you cannot easily attach a hardware write blocker to a soldered
  eMMC/UFS; acquisition inevitably interacts with the live device (document per ACPO P2).
- **State: BFU vs AFU** — **Before First Unlock** (keys not yet derived, very little accessible) vs
  **After First Unlock** (keys in memory, far more data recoverable). Keep an AFU phone **powered and
  unlocked-alive** if lawful.

---

# §9. SIM, Handset and Card Evidence; IMEI vs IMSI

## 9.1 The three evidence sources in a phone

| Source | What it holds |
|---|---|
| **Handset (internal memory)** | The bulk: OS, apps, **SQLite databases** (SMS, call log, contacts, chat, browser), photos/videos with EXIF/GPS, location history, account tokens |
| **SIM/USIM card** | **IMSI, ICCID**, operator data, **phonebook (ADN)**, **SMS (some stored on SIM)**, last dialled numbers (LND), location info (LAI/TMSI) |
| **Removable media (SD card)** | Photos, videos, downloads, app data, sometimes backups — image separately with a write blocker |

## 9.2 **IMEI vs IMSI vs ICCID** — memorise the distinction (guaranteed MCQ)

| Identifier | Identifies | Length / format | Where it lives |
|---|---|---|---|
| **IMEI** (International Mobile **Equipment** Identity) | The **handset/device** | **15 digits** (TAC + serial + check digit); dial **`*#06#`** to display | In the **phone hardware** |
| **IMSI** (International Mobile **Subscriber** Identity) | The **subscriber** (the SIM/account) | up to **15 digits** = **MCC (3) + MNC (2–3) + MSIN** | On the **SIM/USIM** |
| **ICCID** (Integrated Circuit Card ID) | The **SIM card itself** (serial number) | up to **19–20 digits** | Printed on and stored in the **SIM** |
| **MSISDN** | The **phone number** | | Network (HLR), not necessarily on the SIM |

> **The one-liner:** **IMEI = the device; IMSI = the subscriber; ICCID = the SIM card; MSISDN = the
> number.** Swap a stolen phone's SIM and the **IMEI stays** (traces the handset) while the **IMSI
> changes** — which is exactly how stolen-handset tracing works. **CEIR** (Central Equipment
> Identity Register) / the **`sancharsaathi.gov.in`** portal blocks stolen IMEIs in India ⚠️ verify
> name before quoting.

## 9.3 CDR analysis — Call Detail Records (a high-value topic)

**Concept:** a **CDR** is the **metadata record a telecom operator keeps for every call/SMS/data
session** — *not* the content, but who/when/where/how long. Subpoena the operator; CDRs are a
mainstay of Indian investigations (they place a suspect near a scene and map their network).

**Typical CDR fields:**

| Field | Use |
|---|---|
| **Calling & called numbers (A-party / B-party)** | Who contacted whom |
| **Date, time, duration** | Timeline; pattern of life |
| **Call type** (voice/SMS/data), direction (MO/MT) | Nature of contact |
| **IMEI** | Which **handset** was used (catches SIM-swapping across handsets) |
| **IMSI** | Which **SIM/subscriber** |
| **Cell ID / LAC + tower location, azimuth/sector** | **Approximate location** of the phone at the time — the crux of CDR-based placing of a suspect |
| **First/last cell** | Movement during a call |

**What CDR analysis achieves:** place a suspect near the crime scene at the time (tower/cell
location), establish contact between conspirators, build a **timeline and social-network graph**,
detect **SIM-swap** (same IMEI, different IMSI) or **handset-swap** (same IMSI, different IMEI), and
corroborate other evidence. **Limitations to state:** cell location is **approximate** (coverage
area, not GPS), can be affected by tower load/handoff, and **CDR is metadata — content needs lawful
interception** (IT Act §69) or on-device recovery.

## 9.4 Tower dump

A **tower dump** = all phones that connected to a given tower/cell in a time window — used to find an
unknown suspect present at a scene. Privacy-sensitive; needs lawful authority.

---

# §10. Mobile Acquisition Levels — the pyramid (learn the order)

> A **classic question**: "Explain the levels of mobile data acquisition." Learn them from **least
> to most invasive / least to most complete** and note the trade-off (more data ⇄ more risk/skill).

```
        MOST data, MOST invasive/technical
                 ▲
   5. Chip-off  ─┤  desolder the memory chip, read directly
   4. JTAG/ISP  ─┤  connect to test/eMMC pads, read raw NAND
   3. Physical  ─┤  bit-for-bit image of flash (deleted data)
   2. File system┤  copy the live file-system (app DBs, more than logical)
   1. Logical   ─┤  API/backup extraction (contacts, SMS, call log, media)
   0. Manual    ─┘  scroll & photograph the screen by hand
                 ▼
        LEAST data, LEAST invasive
```

| Level | Method | Recovers | Notes / risk |
|:--:|---|---|---|
| **Manual** | Operate the phone, photograph screens | Only what is visible | Changes state; no deleted data; last resort or quick triage |
| **Logical** | Use the OS/backup API (e.g. ADB backup, iTunes-style backup, vendor sync) | Contacts, SMS, call logs, media, some app data | Fast, safe, tool-supported; **usually no deleted data**; needs the device unlocked |
| **File system** | Pull the device's file-system (databases, caches, config) | **App SQLite DBs, logs, more artifacts** including some "deleted" rows in SQLite (unvacuumed/WAL) | Often needs root/exploit/agent; richer than logical |
| **Physical** | **Bit-for-bit image of the flash** | **Everything incl. unallocated/deleted** (if not encrypted) | The goal; hard on modern encrypted phones |
| **JTAG / ISP** | Connect to **JTAG test points** or **In-System Programming (eMMC pads)** to read raw memory | Full physical image without desoldering | Advanced; needed for damaged/locked devices |
| **Chip-off** | **Desolder the NAND/eMMC/UFS chip** and read it in a reader | Raw physical memory | **Destructive**, expensive, expert-only; **encryption still blocks reading** without keys |

> **Key modern caveat:** on encrypted phones, **physical/JTAG/chip-off give you ciphertext** unless
> you also have the key (from an AFU state, a known passcode, or an exploit). So **logical/file-system
> acquisition from an unlocked/AFU device is often more valuable than a chip-off of a locked one.**
> Say this — it is the sophisticated point examiners reward.

**SQLite recovery angle:** even "deleted" chat/SMS rows often survive in **SQLite free-pages,
WAL/journal files, and unvacuumed space** — a major reason file-system acquisition matters. Deleted
rows are recoverable by carving the SQLite structures.

---

# §11. Android and iOS Artifacts

| Artifact | **Android** | **iOS** |
|---|---|---|
| Storage/FS | Historically ext4/F2FS; user data in `/data/data/<app>/` | **APFS**; data under `/private/var/mobile/` |
| Encryption | **FBE** (file-based encryption), earlier FDE | **Data Protection** (per-file keys tied to passcode + Secure Enclave) |
| Contacts | `contacts2.db` (SQLite) | `AddressBook.sqlitedb` |
| SMS/MMS | `mmssms.db` | `sms.db` |
| Call log | `calllog.db` / `contacts2.db` | `call_history.db` / `CallHistory.storedata` |
| Chat apps | Per-app SQLite in `/data/data/<pkg>/databases/` (e.g. WhatsApp `msgstore.db`, often encrypted) | Per-app in the app container; WhatsApp `ChatStorage.sqlite` |
| Browser | Chrome SQLite (`History`) | Safari `History.db` |
| Photos/media | DCIM + `MediaStore`; **EXIF incl. GPS** | Photos library + `Photos.sqlite`; EXIF/GPS |
| Location | Google location history, cell/Wi-Fi caches | `cache.sqlite`, frequent locations, `KnowledgeC.db` (device usage timeline) |
| Accounts/tokens | `accounts.db`, app credentials | Keychain (Secure Enclave-protected) |
| Backups | ADB backup, cloud (Google) | iTunes/Finder backup (may be encrypted), **iCloud** |
| System usage | `usagestats`, logcat | **`KnowledgeC.db`**, `powerlog`, unified logs |

> **The recurring theme:** **almost every phone artifact is a SQLite database.** An Android/iOS
> answer that says "SMS in `mmssms.db`/`sms.db`, calls in `calllog.db`/`call_history.db`, contacts,
> and app chat DBs are SQLite files recovered by file-system acquisition, with deleted rows carved
> from SQLite free-pages/WAL" scores well. ⚠️ verify exact filenames per OS version before quoting
> them as absolute — they drift across versions; the **concept** (SQLite app DBs + EXIF/GPS +
> location DBs like KnowledgeC) is the examinable part.

### §11.1 Likely exam questions (Part C)
| Marks | Question |
|:--:|---|
| 5 | Distinguish IMEI, IMSI and ICCID. |
| 5 | What is a CDR? List its main fields. |
| 5 | What evidence can be recovered from a SIM card? |
| 5 | Why must a seized phone be placed in a Faraday bag? |
| 5 | Distinguish logical and physical acquisition of a mobile phone. |
| 10 | Explain the levels of mobile forensic acquisition from manual to chip-off. |
| 10 | Explain CDR analysis and how it places a suspect at a scene, with its limitations. |
| 10 | Describe the artifacts recoverable from an Android or iOS device. |
| 15 | Discuss the challenges of mobile forensics (encryption, connectivity, BFU/AFU state) and explain, with the acquisition-level pyramid, how you would forensically acquire a locked smartphone. |

### MCQ traps (Part C)
- **IMEI = equipment/handset (15 digits, `*#06#`); IMSI = subscriber (on SIM); ICCID = SIM serial.**
- **Same IMEI + different IMSI = SIM swap; same IMSI + different IMEI = handset swap.**
- **CDR is metadata (who/when/where), not call content.** Content needs §69 interception.
- **Chip-off is destructive; JTAG/ISP is non-destructive but advanced; both yield ciphertext if
  encrypted.**
- **Faraday bag** prevents remote wipe / network changes.
- **Cell/tower location is approximate**, not GPS-precise.
- Most phone artifacts are **SQLite**; deleted rows survive in **WAL/free-pages**.

---

# §12. Forensic Tools — the reference table (know 2–3 lines on each)

> A "name and describe forensic tools" question is common, and every walkthrough answer is stronger
> if you name the right tool for the step. Learn the **category → tool → one-line use**.

| Tool | Type / vendor | Primary use |
|---|---|---|
| **EnCase** | Commercial suite (OpenText/Guidance) | Full disk imaging (**E01**), analysis, keyword search, reporting; long courtroom pedigree; **EnScript** automation |
| **FTK** (Forensic Toolkit) + **FTK Imager** | Commercial (Exterro/AccessData) | Indexed searching, analysis; **FTK Imager** is the free, ubiquitous **imaging/preview** tool (raw/E01/AD1, memory capture) |
| **Autopsy / The Sleuth Kit (TSK)** | **Open source** (Brian Carrier) | GUI (Autopsy) over TSK CLI; file-system analysis, carving, timeline, keyword, hash sets — the standard free suite |
| **X-Ways Forensics** | Commercial (lightweight) | Fast, low-footprint disk analysis and imaging |
| **Cellebrite UFED** | Commercial (mobile) | **Industry-standard mobile acquisition** (logical/file-system/physical), lock bypass, app parsing |
| **Magnet AXIOM / Oxygen Forensic Detective / MSAB XRY** | Commercial | Mobile + computer + cloud artifact analysis; strong app/cloud parsing |
| **Wireshark** / **tcpdump** | **Open source** (network) | Packet capture/analysis (**PCAP**); protocol dissection; the network sniffer/analyser |
| **Volatility** / **Rekall** | **Open source** (memory) | **Memory (RAM) forensics** — processes, network, injected/fileless malware, keys |
| **`dd` / `dcfldd` / `dc3dd`** | Open source (imaging) | Command-line **bit-stream imaging**; dcfldd/dc3dd add hashing & progress |
| **HashCalc / md5sum / sha256sum / hashdeep** | Utilities | Compute/verify **hash values** for integrity |
| **RegRipper / Registry Explorer** | Open source/free | Parse **Windows registry** hives into readable artifacts |
| **PhotoRec / Scalpel / Foremost** | Open source | **File carving** from unallocated space |
| **Plaso / log2timeline** | Open source | **Super-timeline** creation across many artifact types |
| **Bulk Extractor** | Open source | Scan images for emails, cards, URLs without parsing the FS |
| **NSRL (RDS)** | NIST hash set | Known-good hashes to **filter out** OS/software files |
| **SANS SIFT / Kali / CAINE** | Forensic Linux distros | Bootable toolkits bundling the above |

> **Quick mapping to memorise:** **imaging → FTK Imager / dd / EnCase**; **disk analysis → Autopsy/
> TSK, EnCase, FTK, X-Ways**; **memory → Volatility**; **network → Wireshark**; **mobile →
> Cellebrite UFED / XRY / AXIOM**; **registry → RegRipper**; **carving → PhotoRec/Scalpel**;
> **hashing → hashdeep/sha256sum**; **timeline → Plaso**.

### §12.1 Likely exam questions
| Marks | Question |
|:--:|---|
| 5 | Name two tools each for disk, memory, network and mobile forensics. |
| 5 | What is FTK Imager used for? |
| 10 | Describe the major digital forensic tools and their uses in a table. |
| 15 | For a case involving a running PC and a locked smartphone, name the tools you would use at each stage (volatile capture, imaging, disk analysis, mobile acquisition, network, reporting) and justify each. |

### MCQ traps
- **Volatility = memory; Wireshark = network; Autopsy/Sleuth Kit = disk; Cellebrite UFED = mobile.**
- **FTK Imager (free) images/previews; the full FTK indexes/searches.**
- **The Sleuth Kit is the CLI; Autopsy is its GUI.**
- **EnCase's native image format is E01.**
- **NSRL** hashes are used to **exclude** known files, not to find them.

---

## Appendix — verify-before-exam list for FOR_04
1. **ACPO** = 4 principles (safe). Framework doc numbers **NIST SP 800-86**, **ISO/IEC 27037**,
   **RFC 3227** — RFC 3227 safe; ⚠️ verify the NIST/ISO numbers before quoting exactly.
2. **§45 IEA 1872 → §39 BSA 2023** (expert opinion) and **CrPC §293 → BNSS** (government scientific
   experts) — ⚠️ verify the new section numbers; cite both codes.
3. **§65B IEA → §63 BSA** certificate — ⚠️ verify sub-section; cite both.
4. **IT Act §69** (interception) for call/data content — safe as concept; confirm sub-sections.
5. **CEIR / Sanchar Saathi (sancharsaathi.gov.in)** for IMEI blocking — ⚠️ verify name/URL.
6. **WAP stack layer names** (WAE/WSP/WTP/WTLS/WDP) — ⚠️ verify before writing all five.
7. **Android/iOS artifact filenames** (`mmssms.db`, `sms.db`, `calllog.db`, `call_history.db`,
   `KnowledgeC.db`, WhatsApp DB names) drift by version — ⚠️ verify; the SQLite concept is the marks.
8. IMEI **15 digits**, ICCID **19–20 digits**, IMSI **≤15 (MCC+MNC+MSIN)** — safe, but double-check
   ICCID length wording.
