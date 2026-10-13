# Computer Forensic Paper-I — Rapid Revision, Importance Ratings & Model Answers

**NPSC CTSE 2026 · Elective: Computer Forensic (Scientific Assistant, Police) · Technical Paper-I (descriptive, 100 marks, 3 h) · Tue 13 Oct 2026, 09:00 IST**

## If you have only 20 minutes: read these first

1. **Locard's Exchange Principle** ("every contact leaves a trace") plus the other basic principles of forensic science.
2. **Chain of custody:** what it is, what goes on the form, and why a break makes evidence inadmissible.
3. **Crime-scene search methods:** spiral, strip/line, grid, zone and wheel. *Draw them.*
4. **Crime-scene documentation:** notes, photography (overall → mid-range → close-up with scale), videography, sketching and 3-D scanning.
5. **Collection → preservation → packaging → sealing → labelling → forwarding** of evidence. Paper, not plastic, for biological evidence.
6. **Class vs individual characteristics** of physical evidence.
7. **Organisation of FSLs in India:** DFSS/CFSLs, State FSLs, RFSLs and mobile units.
8. **Booting process** (BIOS/UEFI → MBR/GPT → boot loader → kernel) and **file systems** (FAT, NTFS, ext4, APFS).
9. **Windows artifacts:** registry hives, event logs, LNK files, **ADS**, **slack space**, hidden files.
10. **Linux artifacts:** permissions (`rwx`/octal), `/etc/passwd` and `/etc/shadow`, logs. **Mac:** launchd plists, hidden directories, logs.

## How the importance ratings work

<span class="imp i10">10</span> sure to come · <span class="imp i9">9</span> very likely · <span class="imp i8">8</span> likely · <span class="imp i7">7</span> good chance · <span class="imp i6">6</span>/<span class="imp i5">5</span> moderate · <span class="imp i4">4</span>–<span class="imp i1">1</span> background only

**Why these ratings:** no Computer Forensic CTSE paper has been published yet, so the ratings follow how NPSC set the 2025 CS papers. Those papers lifted **syllabus phrases word for word** and asked them as "explain / differentiate / describe" questions. **Units 1–5 are unique to forensics** and come from a forensic examiner, so they carry the most marks and get the highest ratings. **Units 6–9** (logic, networks, OS, COA) are shared CS core, which you already know.

## Exam-hall plan (Sec A any 8 of 10 × 5 · Sec B any 3 of 5 × 10 · Sec C any 2 of 4 × 15)

- **Answer the forensic questions first,** where you can draw search patterns, chain-of-custody flows or the boot sequence. Then use CS-core questions to fill your remaining choices.
- **Every 10- and 15-mark answer:** definition → classification/table → diagram → procedure/steps → significance → conclusion.
- **Time budget:** 5-mark ≈ 8 min · 10-mark ≈ 15 min · 15-mark ≈ 25 min · keep 10 min to review.

**Contents:** Unit 1 Forensic Science · Unit 2 Physical Evidence · Unit 3 Scene of Crime · Unit 4 Computer Hardware · Unit 5 System Artifacts · Unit 6 Logic & Digital · Unit 7 Networks · Unit 8 OS/UNIX/Windows · Unit 9 COA. Each unit ends with its likely questions and model answers.

## Unit 1 — Introduction to Forensic Science

### Definition of forensic science
**Importance: 7/10** · opening line of every Unit-1 answer; a direct 5-mark candidate

In simple words: science used to answer questions that a court needs answered.

- **Forensic Science** — the application of scientific principles, techniques and methods to the investigation of crime and to matters of law, to establish facts admissible in a court of justice. ("Forensic" = Latin *forensis*, "of the forum", the court.)
- **Criminalistics** — the branch concerned with the recognition, collection, identification, individualisation and interpretation of **physical evidence** (the laboratory side).
- **Digital / Computer Forensics** — identification, preservation, extraction, analysis, documentation and presentation of **digital evidence** in a legally admissible manner.

### History and development (international)
**Importance: 8/10** · "fathers of …" are classic MCQs and a 5-mark "history" note

In simple words: a handful of pioneers turned police guesswork into lab science.

| Year / person | Contribution |
|---|---|
| 1248, Song Ci (China) | *Xi Yuan Ji Lu* ("Washing Away of Wrongs") — earliest known forensic-medicine treatise |
| 1814, **Mathieu Orfila** | *Traité des poisons* — **Father of Forensic Toxicology** |
| 1823, Purkinje | First classification of fingerprint patterns |
| 1879, **Alphonse Bertillon** | **Anthropometry (Bertillonage)** — first systematic personal-identification system by body measurements; **Father of Criminal Identification**; later superseded by fingerprints |
| 1880, Faulds & Herschel | Published on fingerprints for identification |
| 1892, **Francis Galton** | *Finger Prints* — individuality and permanence of ridges; **Galton details (minutiae)** |
| 1893, **Hans Gross** (Austria) | *Handbuch für Untersuchungsrichter* — **Father of Criminalistics**; coined the term |
| 1901, Karl Landsteiner | ABO blood groups → forensic serology |
| 1901, **Edward Henry** | **Henry Classification System** of fingerprints (developed in Bengal, India) |
| 1910, **Edmond Locard** | First **police crime laboratory, Lyon** (France); **Locard's Exchange Principle**; "Sherlock Holmes of France" |
| 1915, Leone Lattes | Blood group from a dried bloodstain |
| 1920s, **Calvin Goddard** | **Comparison microscope** → modern firearms/ballistics identification |
| 1930s, Albert Osborn | *Questioned Documents* — scientific document examination |
| 1984, Alec Jeffreys | **DNA fingerprinting** (first used in the Colin Pitchfork case) |

Exam tip: "every contact leaves a trace" = Locard, not Gross. First crime lab = Locard, Lyon, 1910.

### Development of forensic science in India
**Importance: 8/10** · "development and scope in India" is a verbatim syllabus phrase

In simple words: India gave the world its first fingerprint bureau and built a Centre–State lab network from Calcutta outward.

| Year | Development |
|---|---|
| 1849 | Chemical Examiner's Laboratory, Madras Presidency; similar labs followed in **Calcutta (1853)** and Agra/Bombay ⚠️ years as per standard texts — verify before quoting exact dates |
| **1897** | **Anthropometric Bureau, Calcutta** → renamed **Finger Print Bureau** — widely described as the **world's first fingerprint bureau**; under Edward Henry, with **Azizul Haque** and **Hem Chandra Bose** doing the classification work |
| 1904 | GEQD (questioned documents) work begins at **Shimla** |
| 1930 | Ballistics laboratory, Calcutta |
| 1952 | First State FSL, Calcutta (West Bengal) ⚠️ verify |
| **1957** | **CFSL Calcutta (Kolkata)** — the **first/oldest CFSL** |
| 1970 | **BPR&D** established (MHA) |
| 1986 | **NCRB** established |
| 2000 | **IT Act 2000** — legal basis for electronic evidence |
| **2002** | **Directorate of Forensic Science** created under **MHA**, taking CFSLs & GEQDs out of BPR&D; later renamed **DFSS** |
| 2009 / **2020** | GFSU Gandhinagar (2009) → **National Forensic Sciences University (NFSU)**, Institution of National Importance (2020) |
| 2023–24 | **BNS, BNSS, BSA** replace IPC, CrPC, Evidence Act (in force **1 July 2024**); BNSS makes forensic investigation **mandatory for offences punishable with 7 years or more** (commonly cited BNSS §176(3)) |

### Scope of forensic science in India
**Importance: 7/10** · same syllabus phrase; easy table answer

In simple words: scope = every kind of question a lab can answer for police and courts.

| Branch | Answers questions on |
|---|---|
| Physics | Glass, paint, soil, tool marks, tyre/footwear marks, erased numbers |
| Chemistry | Explosives, petroleum, fire debris, trap cases (phenolphthalein) |
| Toxicology | Poisons, alcohol, drugs in viscera/body fluids |
| Biology / Serology | Blood, semen, saliva, hair, fibre, diatoms (drowning), wildlife |
| DNA | Identity, paternity, disaster-victim ID, sexual assault |
| Ballistics | Firearms, bullets, cartridge cases, range of fire, GSR |
| Questioned Documents | Handwriting, signatures, forgery, counterfeit currency |
| Fingerprints | Individual identification; AFIS/**NAFIS** |
| Forensic Medicine | Autopsy, cause/manner/time of death |
| Forensic Psychology | Polygraph, narco-analysis, BEOS (only with consent — *Selvi v. State of Karnataka*, 2010) |
| **Cyber / Digital** | Computers, mobiles, networks, cloud, CCTV, audio-video authentication |

**Growth drivers:** rising cybercrime, BNSS mandatory forensics, NAFIS, DNA expansion, NFSU manpower. **Constraints:** backlog/pendency, shortage of examiners, uneven State capacity.

### Basic principles of forensic science
**Importance: 10/10** · the core of Unit 1; Locard alone is near-certain

In simple words: six laws that explain why physical evidence exists, why it can identify, and why it must be handled carefully.

| Principle | Statement | Example | Digital analogue |
|---|---|---|---|
| **Locard's Exchange Principle** | When two objects come into contact there is always a **mutual exchange** of material — "every contact leaves a trace" | Burglar leaves prints/fibres on the sill, carries glass fragments away in his shoes | Opening a file leaves MFT timestamp, prefetch, LNK, registry MRU traces |
| **Law of Individuality** | Every object, natural or man-made, has an individuality not duplicated in any other | Striations on a bullet from one barrel; identical twins differ in fingerprints | SHA-256 hash, MAC address, IMEI |
| **Principle of Comparison** | Only **like can be compared with like** — questioned vs known/control sample of same type | Test-fire bullets from the seized gun; specimen handwriting in same script | Hash of working copy vs original image |
| **Principle of Analysis** | Analysis is only as good as the **sample, method and analyst** | Blood left in a hot car → useless DNA | Imaging without a write blocker corrupts timestamps |
| **Law of Progressive Change** | Everything **changes with time** — criminal, scene and evidence | Body decomposes, accelerant evaporates, footprint dries | **Order of volatility** — RAM, ARP cache vanish first |
| **Principle of Circumstantial Facts** | "Facts do not lie, men can and do" — physical evidence is not subject to memory or motive, but must be interpreted correctly | Witnesses turn hostile; the fingerprint on the weapon does not | Logs and hashes do not change their story (if integrity is certified) |

- Add-on (some texts): **Principle of Probability** — identification is expressed as likelihood; the more independent class features agree, the lower the chance of coincidental match (e.g. fingerprint minutiae). Also **Principle of Presentation** — findings must be presented in a form the court understands.
- Locard caveat: absence of trace ≠ absence of contact (detection depends on time, medium, analyst skill).
- Memory hook **L-I-C-A-P-C**: "**L**ittle **I**tems **C**an **A**lways **P**rove **C**rime".

### Significance of forensic science
**Importance: 7/10** · verbatim syllabus phrase; easy 5 marks

In simple words: it gives the court proof that does not depend on what people say.

1. **Objective scientific proof**, independent of witness reliability (hostile witnesses are common).
2. **Links** victim, suspect, scene and weapon (the linkage triangle — based on Locard).
3. **Identifies** persons (fingerprint, DNA) and objects (weapon, vehicle, device).
4. **Reconstructs** the sequence of events (bloodstain pattern, trajectory, timeline).
5. **Corroborates or refutes** statements and alibis.
6. **Exonerates the innocent** as much as it convicts the guilty.
7. Mandatory under **BNSS** for serious offences — raises conviction quality.
8. Essential for **cybercrime**, where there is often no eyewitness at all.

### Organisation and functioning of Central and State FSLs
**Importance: 10/10** · unique-forensic syllabus phrase; examiner is an FSL scientist

In simple words: Centre runs DFSS → CFSLs/GEQDs; each State runs SFSL → RFSLs → mobile units.

<div class="fig">
<svg viewBox="0 0 680 400" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u1-arr" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="400" fill="#fff"/>
<text x="170" y="20" text-anchor="middle" font-weight="bold">CENTRAL (Union)</text>
<text x="520" y="20" text-anchor="middle" font-weight="bold">STATE (Police = State subject)</text>
<line x1="345" y1="10" x2="345" y2="395" stroke="#999" stroke-dasharray="5,4"/>
<rect x="70" y="32" width="200" height="34" fill="#e8f0fe" stroke="#222"/>
<text x="170" y="54" text-anchor="middle">Ministry of Home Affairs</text>
<rect x="50" y="96" width="240" height="44" fill="#e8f0fe" stroke="#222"/>
<text x="170" y="115" text-anchor="middle" font-weight="bold">DFSS, New Delhi (2002)</text>
<text x="170" y="131" text-anchor="middle" font-size="11">Directorate of Forensic Science Services</text>
<line x1="170" y1="66" x2="170" y2="94" stroke="#222" marker-end="url(#u1-arr)"/>
<rect x="10" y="176" width="150" height="80" fill="#e6f4ea" stroke="#222"/>
<text x="85" y="194" text-anchor="middle" font-weight="bold">CFSLs</text>
<text x="85" y="211" text-anchor="middle" font-size="11">Kolkata (1957, oldest)</text>
<text x="85" y="225" text-anchor="middle" font-size="11">Hyderabad, Chandigarh</text>
<text x="85" y="239" text-anchor="middle" font-size="11">Guwahati (NE), Bhopal,</text>
<text x="85" y="252" text-anchor="middle" font-size="11">Pune</text>
<rect x="180" y="176" width="150" height="80" fill="#e6f4ea" stroke="#222"/>
<text x="255" y="194" text-anchor="middle" font-weight="bold">GEQDs</text>
<text x="255" y="211" text-anchor="middle" font-size="11">Questioned documents</text>
<text x="255" y="225" text-anchor="middle" font-size="11">Shimla (principal),</text>
<text x="255" y="239" text-anchor="middle" font-size="11">Kolkata, Hyderabad</text>
<line x1="130" y1="140" x2="90" y2="174" stroke="#222" marker-end="url(#u1-arr)"/>
<line x1="210" y1="140" x2="250" y2="174" stroke="#222" marker-end="url(#u1-arr)"/>
<rect x="10" y="290" width="150" height="44" fill="#fef7e0" stroke="#222"/>
<text x="85" y="309" text-anchor="middle" font-size="11">CFSL New Delhi</text>
<text x="85" y="324" text-anchor="middle" font-size="11">under CBI (not DFSS)</text>
<rect x="180" y="290" width="150" height="100" fill="#f1f3f4" stroke="#222"/>
<text x="255" y="307" text-anchor="middle" font-size="11" font-weight="bold">Other MHA bodies</text>
<text x="255" y="324" text-anchor="middle" font-size="11">BPR&amp;D (1970)</text>
<text x="255" y="339" text-anchor="middle" font-size="11">NCRB (1986): NAFIS</text>
<text x="255" y="354" text-anchor="middle" font-size="11">NFSU (2020)</text>
<text x="255" y="369" text-anchor="middle" font-size="11">I4C (cybercrime)</text>
<rect x="400" y="32" width="240" height="34" fill="#e8f0fe" stroke="#222"/>
<text x="520" y="54" text-anchor="middle">State Home Dept / State Police</text>
<rect x="400" y="96" width="240" height="44" fill="#e6f4ea" stroke="#222"/>
<text x="520" y="115" text-anchor="middle" font-weight="bold">State FSL (SFSL)</text>
<text x="520" y="131" text-anchor="middle" font-size="11">State capital · Director, SFSL</text>
<line x1="520" y1="66" x2="520" y2="94" stroke="#222" marker-end="url(#u1-arr)"/>
<rect x="400" y="176" width="240" height="44" fill="#fef7e0" stroke="#222"/>
<text x="520" y="195" text-anchor="middle" font-weight="bold">Regional FSLs (RFSL)</text>
<text x="520" y="211" text-anchor="middle" font-size="11">zonal, routine high-volume work</text>
<line x1="520" y1="140" x2="520" y2="174" stroke="#222" marker-end="url(#u1-arr)"/>
<rect x="400" y="256" width="240" height="44" fill="#fce8e6" stroke="#222"/>
<text x="520" y="275" text-anchor="middle" font-weight="bold">Mobile FSL Units (MFSU)</text>
<text x="520" y="291" text-anchor="middle" font-size="11">district vans, go to the scene</text>
<line x1="520" y1="220" x2="520" y2="254" stroke="#222" marker-end="url(#u1-arr)"/>
<line x1="330" y1="216" x2="398" y2="128" stroke="#222" stroke-dasharray="4,3" marker-end="url(#u1-arr)"/>
<text x="372" y="190" text-anchor="middle" font-size="11">referral</text>
<text x="520" y="330" text-anchor="middle" font-size="11">Nagaland: State FSL under Nagaland Police;</text>
<text x="520" y="345" text-anchor="middle" font-size="11">central support from CFSL Guwahati</text>
</svg>
<div class="cap">Fig: Organisation of the forensic science set-up in India (Centre and State)</div>
</div>

**DFSS (Directorate of Forensic Science Services)** — under **MHA**, HQ **New Delhi**, created **2002** (as DFS, carved out of BPR&D), headed by Director-cum-Chief Forensic Scientist. Functions: administrative and technical control of **CFSLs and GEQDs**; services to central agencies (CBI, NIA, ED, NCB, CAPFs) and States in referred cases; **referral/second-opinion** lab; national **standards, SOPs, quality assurance**; R&D; training of scientists, police, judges and prosecutors; advising MHA on policy.

**CFSLs** — multidisciplinary central labs: **Kolkata (1957, oldest)**, Hyderabad, Chandigarh, **Guwahati (serves the North-East incl. Nagaland)**, Bhopal, Pune. **CFSL New Delhi is under the CBI**, not DFSS (standard MCQ trap). Functions: exhibits from central agencies, courts and States in important cases; second opinion; scene attendance in sensational cases; expert testimony; R&D and method validation; training.

**GEQD** — Government Examiner of Questioned Documents: Shimla (principal), Kolkata, Hyderabad; handwriting, signatures, forgery, counterfeit currency.

**State FSL** — under State Home Department (police is a State subject), usually in the capital; routine casework for the State, scene visits in serious cases, expert evidence in State courts, supervises RFSLs and mobile units, trains State police.

**RFSL** — zonal branches; routine high-volume work (viscera toxicology, excise, narcotics screening, serology); reduce turnaround and transport risk (Law of Progressive Change); complex work (DNA, cyber, ballistics, documents) escalated.

**MFSU** — "laboratory on wheels": crime-scene kit, photography, forensic light source, fingerprint kit, casting material, presumptive reagents, packaging, sometimes write-blocker/imaging kit. Backbone of BNSS mandatory scene visits (7+ year offences).

**Nagaland:** State-level work is handled by the State FSL under Nagaland Police; central support from CFSL Guwahati. ⚠️ verify exact current location/status before writing details.

**Divisions of a full-service FSL**

| Division | Examines |
|---|---|
| Biology | Hair, fibre, pollen, diatoms, botanical, wildlife |
| Serology | Blood, semen, saliva; species of origin; grouping |
| DNA | STR profiling, paternity, sexual assault, DVI |
| Chemistry | Explosives, petroleum, fire debris, trap cases |
| Toxicology | Poisons, alcohol, drugs in viscera |
| Narcotics (NDPS) | Identification/quantification of drugs |
| Physics | Glass, paint, soil, tool marks, erased numbers |
| Ballistics | Firearms, ammunition, range of fire, GSR |
| Questioned Documents | Handwriting, forgery, ink, currency |
| Fingerprints | Latent development, comparison, NAFIS |
| **Cyber / Computer Forensics** | Computers, mobiles, CCTV, audio-video, malware |
| Photography | Scene/exhibit, UV/IR, enhancement |
| Lie Detection / Psychology | Polygraph, narco-analysis, BEOS (consent) |
| Prohibition & Excise | Liquor, illicit spirit, methanol |

### Ethics in forensic science
**Importance: 8/10** · verbatim syllabus item; easy 5-mark list

In simple words: the scientist serves the truth and the court, not the police or the party paying.

**Code of conduct:** objectivity and impartiality (disclose exculpatory findings) · competence (only within one's field) · validated methods and SOPs · complete contemporaneous documentation · integrity of evidence and chain of custody; preserve part of sample for re-examination · confidentiality (no press comment on pending cases) · **no overstatement** ("consistent with", not "100% match") · independence from pressure · disclose conflicts of interest · CPD and proficiency testing · correct errors promptly · no outcome-contingent fee.

**Duty of expert witness:** primary duty is to the **court**; explain plainly; state basis and limitations; concede valid points on cross-examination. Expert opinion: Evidence Act §45 (now BSA 2023 §39 ⚠️ verify) — **advisory, court not bound**.

**Bias types:** confirmation, contextual, expectation, motivational/role, anchoring, reverse reasoning. **Countermeasures:** linear sequential unmasking, context management, blind verification, accreditation (ISO/IEC 17025 labs).

**Ethical failures:** drylabbing (reporting tests never done), overstating, fabricating data/credentials, selective reporting, testifying beyond expertise, hiding contamination, leaking to media.

## Unit 2 — Physical Evidence

### Physical evidence — definition and value
**Importance: 7/10** · syllabus opener; definition earns the first marks

In simple words: any object or trace that can show a crime happened or link someone to it.

**Definition:** any tangible article, material or trace — from a body to a single fibre, or digital data — that can establish that a crime was committed, or provide a link between the crime and its victim, or the crime and its perpetrator.

**What it does:** proves **corpus delicti** (a crime occurred) · establishes **modus operandi** · **links** suspect–victim–scene (Locard) · proves/disproves witness accounts · **identifies** the suspect · gives investigative leads · **exonerates** the innocent.

### Types of physical evidence
**Importance: 9/10** · "types of physical evidence" is a direct syllabus phrase

In simple words: classify by what it is made of, and by how it got there.

**(a) By nature:** biological (blood, semen, hair) · chemical (drugs, poisons, explosives) · physical (glass, soil, tool marks) · documentary · impression/pattern (fingerprints, footprints, bite marks) · **electronic/digital** (disks, phones, CCTV, logs) · miscellaneous.

**(b) By evidential value / origin:**

| Type | Meaning | Examples |
|---|---|---|
| **Transient** | Temporary, lost quickly — record first | Odour, temperature, wet stains, smoke, impressions in snow |
| **Pattern** | Produced by physical contact/action, shows a pattern | Bloodstain pattern, glass fracture, tyre marks, powder pattern |
| **Conditional** | Produced by an event or action at the scene | Lights on/off, doors locked, TV channel, body position, clock stopped |
| **Transfer / Trace** | Material exchanged between persons/objects (Locard) | Hair, fibre, soil, paint, glass fragments |
| **Associative** | Personal items linking suspect to the scene | Wallet, ID card, phone, keys |

Exam tip: digital evidence is simultaneously **transient** (RAM), **transfer** (log entries created by intrusion) and **associative** (phone at the scene) — say it.

### Class vs individual characteristics
**Importance: 10/10** · the classic "differentiate" question of Unit 2

In simple words: class features narrow it to a group; individual features point to one source.

- **Class characteristic** — features common to a group of objects, arising from design, manufacture or species; evidence can be associated only with a **group**, never a single source.
- **Individual characteristic** — features from random, accidental wear, damage or imperfection; can be associated with **one source** with a high degree of certainty.

| Aspect | Class | Individual |
|---|---|---|
| Origin | Design / manufacture / species | Random wear, damage, imperfection |
| Points to | A **group** of sources | **One** source |
| Conclusion | "Consistent with"; can **exclude** | "Identified" (individualised) |
| Weight | Corroborative | Conclusive |
| Mismatch | Exclusion | Exclusion |

| Evidence | Class | Individual |
|---|---|---|
| Footwear | Brand, size, tread design | Cuts, nicks, wear, embedded stone |
| Fingerprint | Loop, whorl, arch; ridge count | **Minutiae** — ridge endings, bifurcations |
| Bullet | Calibre, lands & grooves, twist direction | **Striations** unique to that barrel |
| Tool mark | Tool type and width | Striae from nicks on that edge |
| Blood | ABO, Rh, species | **DNA STR profile** (except identical twins) |
| Glass | Type, colour, **refractive index**, density | **Physical fit** of fracture edges |
| Paint | Layer sequence, colour, chemistry | Physical fit of a chip |
| Handwriting | Copybook style | Personal habits, letter formation |
| **Digital** | File type, MIME, camera model (EXIF) | **Hash (SHA-256)**, MAC, IMEI, serial number |

Key insight: many matching class characteristics give **cumulative probability**, not true individualisation; one class mismatch is enough to **exclude**.

### Search methods for locating physical evidence
**Importance: 10/10** · unique-forensic phrase; draw the patterns (diagram in Unit 3)

In simple words: search the scene in a fixed pattern so no area is missed or walked over twice.

Choice depends on **size, terrain, number of searchers, indoor/outdoor**. Methods: strip/line, grid, spiral, zone/quadrant, wheel/ray, link — full table and the pattern diagram are in Unit 3 ("Search techniques"). Discovery aids: oblique light, **alternate light source**, UV/IR, **luminol/BLUESTAR** (latent blood), fingerprint powders/ninhydrin/cyanoacrylate, metal detectors, ground-penetrating radar.

### Chain of custody
**Importance: 10/10** · "guaranteed exam material"; the first thing defence attacks

In simple words: a signed written record of every hand the evidence passed through, from scene to court.

**Definition:** the chronological documentation recording the **seizure, custody, control, transfer, analysis and disposition** of physical or electronic evidence — an unbroken record of *who* had it, *when*, *where*, *why* and *what they did*. Also "chain of evidence" / "paper trail".

**Rule in one line:** every person who handles the evidence signs for it, with **no unexplained gap** between signatures.

<div class="fig">
<svg viewBox="0 0 680 230" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u2-arr" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="230" fill="#fff"/>
<rect x="10" y="20" width="120" height="56" fill="#e8f0fe" stroke="#222"/>
<text x="70" y="42" text-anchor="middle" font-weight="bold">1. Seizure</text>
<text x="70" y="60" text-anchor="middle" font-size="11">collector + panchas</text>
<rect x="150" y="20" width="120" height="56" fill="#e8f0fe" stroke="#222"/>
<text x="210" y="42" text-anchor="middle" font-weight="bold">2. Pack/Seal</text>
<text x="210" y="60" text-anchor="middle" font-size="11">exhibit no., seal</text>
<rect x="290" y="20" width="120" height="56" fill="#e6f4ea" stroke="#222"/>
<text x="350" y="42" text-anchor="middle" font-weight="bold">3. Malkhana</text>
<text x="350" y="60" text-anchor="middle" font-size="11">secure storage</text>
<rect x="430" y="20" width="120" height="56" fill="#e6f4ea" stroke="#222"/>
<text x="490" y="42" text-anchor="middle" font-weight="bold">4. Transport</text>
<text x="490" y="60" text-anchor="middle" font-size="11">forwarding letter</text>
<rect x="570" y="20" width="100" height="56" fill="#fef7e0" stroke="#222"/>
<text x="620" y="42" text-anchor="middle" font-weight="bold">5. FSL</text>
<text x="620" y="60" text-anchor="middle" font-size="11">seal checked</text>
<rect x="430" y="130" width="120" height="56" fill="#fef7e0" stroke="#222"/>
<text x="490" y="152" text-anchor="middle" font-weight="bold">6. Analysis</text>
<text x="490" y="170" text-anchor="middle" font-size="11">re-sealed + report</text>
<rect x="290" y="130" width="120" height="56" fill="#fce8e6" stroke="#222"/>
<text x="350" y="152" text-anchor="middle" font-weight="bold">7. Court</text>
<text x="350" y="170" text-anchor="middle" font-size="11">produced as exhibit</text>
<rect x="150" y="130" width="120" height="56" fill="#f1f3f4" stroke="#222"/>
<text x="210" y="152" text-anchor="middle" font-weight="bold">8. Disposal</text>
<text x="210" y="170" text-anchor="middle" font-size="11">per court order</text>
<line x1="130" y1="48" x2="148" y2="48" stroke="#222" marker-end="url(#u2-arr)"/>
<line x1="270" y1="48" x2="288" y2="48" stroke="#222" marker-end="url(#u2-arr)"/>
<line x1="410" y1="48" x2="428" y2="48" stroke="#222" marker-end="url(#u2-arr)"/>
<line x1="550" y1="48" x2="568" y2="48" stroke="#222" marker-end="url(#u2-arr)"/>
<path d="M620,76 L620,158 L552,158" fill="none" stroke="#222" marker-end="url(#u2-arr)"/>
<line x1="430" y1="158" x2="412" y2="158" stroke="#222" marker-end="url(#u2-arr)"/>
<line x1="290" y1="158" x2="272" y2="158" stroke="#222" marker-end="url(#u2-arr)"/>
<text x="340" y="112" text-anchor="middle" font-size="11">At EVERY arrow: released by (name, sign, date, time) → received by (name, sign, date, time) + purpose</text>
<text x="340" y="214" text-anchor="middle" font-size="11">Digital evidence: hash (SHA-256) recorded at acquisition and re-verified at each step</text>
</svg>
<div class="cap">Fig: Chain of custody — every transfer is a signed link</div>
</div>

**Steps:** (1) seizure documented with independent witnesses (*panchnama*/seizure memo) → (2) unique exhibit number, packaging, sealing, labelling → (3) entry in **malkhana** register / secure storage → (4) transport with forwarding letter → (5) FSL receipt, seal condition noted → (6) examination, re-sealing, report → (7) production in court → (8) final disposition by court order.

**Form fields:** case/FIR no., police station, sections · unique exhibit no. · description (make, model, serial/IMEI, damage) · date, time, exact place of collection · collector's name, designation, signature · witnesses' signatures · method of packaging, **seal number/impression** · **hash value** (digital) · every transfer (released by / received by, date, time, purpose) · storage location and conditions · examination record (seal intact on receipt? re-sealed?) · final disposition.

**Why it matters:** proves **authenticity** (same object as seized) · **integrity** (not altered) · **accountability** for every period · defeats tampering/substitution/planting claims · allows reconstruction of handling.

**How it breaks:** unexplained gap; broken/mismatched seal; no independent witnesses; missing signature; evidence left unsecured; improper storage; original (not copy) examined; **hash mismatch**; missing §65B / **BSA §63 certificate** for electronic records. Consequence: evidence liable to be excluded or loses evidentiary value — can collapse the prosecution case.

## Unit 3 — Scene of Crime

### Meaning and types of scene of crime
**Importance: 9/10** · "meaning and types" is a direct 5-mark phrase

In simple words: the place of the crime plus every place where its evidence may be found.

**Scene of crime:** the place where the offence was committed, together with the surrounding area over which physical evidence may be distributed — including approach routes, escape routes and any place where evidence of the crime may be found.

| Basis | Types |
|---|---|
| Location | **Indoor** · **Outdoor** · **Conveyance** (vehicle, train, vessel) · underwater |
| Sequence | **Primary** — where the main criminal act occurred · **Secondary** — related places (body dump site, weapon discard site, suspect's house, vehicle used) |
| Size | **Macroscopic** — the scene and its large components (room, body, vehicle) · **Microscopic** — small details (hair, fibre, latent print, droplet) |
| Condition | Organised/unaltered vs **altered/contaminated** (rescuers, relatives, weather, media) |
| Offence | Homicide, burglary, arson, explosion, accident, sexual assault, **cybercrime** |

| Factor | Indoor | Outdoor |
|---|---|---|
| Boundary | Walls — easy | Ill-defined — officer decides |
| Preservation | Easy (lock, guard) | Difficult |
| Threat | People, cleaning, pets | **Weather, animals, traffic** — urgent |
| Search | Zone/quadrant | Strip, grid, spiral |

**Cybercrime scene** can be physical (room with computer), logical (file system, memory) and remote (cloud, server abroad) — all at once.

### Protection of the scene of crime
**Importance: 10/10** · first-officer duties are a sure 5-mark question

In simple words: the first officer's job is to **freeze** the scene, not investigate it.

**Duties of the first responder (in order):** (1) assess **safety** and hazards → (2) **preserve life** — medical aid first; document body position before moving → (3) detain and separate persons present; note names and movements → (4) establish **boundary and cordon** (make it bigger than needed) → (5) fix a single **common approach path (CAP)** → (6) maintain an **entry/exit log** for everyone, including seniors → (7) exclude unauthorised persons, media, onlookers → (8) protect **perishable/transient** evidence (cover footprints, note odours, lights) → (9) do not touch, smoke, eat, use toilet/phone → (10) record initial observations (time, weather, doors, appliances) → (11) inform IO, FSL/MFSU, fingerprint bureau, photographer, doctor → (12) formal **handover** to IO with log.

<div class="fig">
<svg viewBox="0 0 520 260" width="520" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="520" height="260" fill="#fff"/>
<rect x="10" y="10" width="500" height="240" fill="#f1f3f4" stroke="#222" stroke-dasharray="6,4"/>
<text x="20" y="28" font-weight="bold">OUTER cordon — public &amp; media; command post</text>
<rect x="60" y="45" width="400" height="180" fill="#fef7e0" stroke="#222" stroke-dasharray="6,4"/>
<text x="70" y="63" font-weight="bold">INNER cordon — authorised personnel only</text>
<rect x="160" y="85" width="200" height="110" fill="#fce8e6" stroke="#222"/>
<text x="260" y="103" text-anchor="middle" font-weight="bold">CORE scene</text>
<text x="260" y="119" text-anchor="middle" font-size="11">SOCO/forensic team only</text>
<text x="260" y="152" text-anchor="middle" font-size="18" font-weight="bold">X</text>
<text x="260" y="172" text-anchor="middle" font-size="11">focal point (body/device)</text>
<line x1="20" y1="240" x2="250" y2="160" stroke="#1a73e8" stroke-width="3"/>
<text x="118" y="232" font-size="11" fill="#1a73e8">Common Approach Path</text>
<text x="400" y="245" font-size="11">Entry/exit log at inner gate</text>
</svg>
<div class="cap">Fig: Three-layer cordon with a single common approach path</div>
</div>

**Digital scene additions:** if off, leave off; if on, do not switch off (photograph screen first); move suspects away from keyboards; isolate phones in a **Faraday bag**; photograph and label every cable and port.

### Documentation — note taking, photography, videography
**Importance: 10/10** · every head is a verbatim syllabus phrase

In simple words: record the scene exactly as found, **before** anything is touched; notes, photos, video and sketch are complementary, not alternatives.

**Note taking:** contemporaneous; bound numbered notebook, ink, no erasures (strike through and initial); record call time, arrival, weather, lighting, persons present, condition of doors/windows/lights, body position, transient observations, each item's description/location, who collected what, departure time; note **negative findings**. Notes are disclosable to defence.

**Photography — three levels:**

| Level | Shows | Purpose |
|---|---|---|
| **Overall / long-range** | Whole scene, exterior, approaches, all walls, ceiling, floor | Where the scene is |
| **Mid-range** | Item **with a fixed landmark** (door, table) | Spatial relationship |
| **Close-up** | Item fills frame — **first without scale, then with scale** and ID label | Detail; scale allows life-size reproduction |

Rules: photograph before moving/marking, then again with evidence markers; all corners, entry/exit points; body from all sides and surface beneath; maintain a **photo log** (no., subject, direction, time, settings, photographer); no filters/editing; keep originals with hash. Digital scene: screen, front/rear of devices, serial numbers/IMEI, cable layout, sticky notes.

**Videography:** continuous walkthrough showing spatial relationships; begin with statement to camera (case no., date, time, place, operator); slow, steady, no rapid pan/zoom; **no opinions in narration** (or mute audio); shoot **before** stills and markers; do not edit; keep original with hash. BNSS 2023 requires audio-video recording of search and seizure in certain cases ⚠️ verify section.

### Sketching and 3-D scanning
**Importance: 9/10** · rough vs final and measurement methods are favourite questions

In simple words: photos show appearance; sketches give **measurements**.

| Rough sketch | Final / finished sketch |
|---|---|
| Made **at the scene**, freehand | Made **later, in office**, by hand or CAD |
| **Not to scale** (but all measurements written in) | **Drawn to scale** (e.g. 1:50) |
| Original must be **preserved** (court record) | Neat, for court presentation |

**Essential elements:** case no., date, time · address · **north arrow** · scale (or "not to scale") · **legend/key** of numbered items · sketcher and measurer names/signatures · witnesses.

**Measurement methods:**
- **Rectangular coordinates** — perpendicular distances from the object to **two fixed walls at right angles** (indoor).
- **Triangulation** — distances from the object to **two (or three) fixed reference points** (outdoor, no straight walls).
- **Baseline** — distance **along** a fixed straight line plus **perpendicular offset** from it (long scenes, roads, fields).
- **Polar / azimuth** — **distance and angle (bearing)** from one fixed point (open areas; total station).
- **Cross-projection (exploded)** — walls folded flat around the floor plan for evidence on walls/ceiling; **elevation** — side view for heights.

<div class="fig">
<svg viewBox="0 0 680 210" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="680" height="210" fill="#fff"/>
<rect x="15" y="30" width="140" height="130" fill="#f1f3f4" stroke="#222" stroke-width="2"/>
<circle cx="95" cy="95" r="5" fill="#d93025"/>
<line x1="15" y1="95" x2="90" y2="95" stroke="#1a73e8" stroke-dasharray="4,3"/>
<line x1="95" y1="30" x2="95" y2="90" stroke="#1a73e8" stroke-dasharray="4,3"/>
<text x="50" y="90" text-anchor="middle" font-size="11">a</text>
<text x="104" y="62" font-size="11">b</text>
<text x="85" y="185" text-anchor="middle" font-weight="bold">Rectangular coord.</text>
<text x="85" y="200" text-anchor="middle" font-size="11">2 walls at 90°</text>
<circle cx="190" cy="150" r="5" fill="#222"/>
<circle cx="320" cy="150" r="5" fill="#222"/>
<text x="190" y="168" text-anchor="middle" font-size="11">A</text>
<text x="320" y="168" text-anchor="middle" font-size="11">B</text>
<circle cx="265" cy="70" r="5" fill="#d93025"/>
<line x1="190" y1="150" x2="262" y2="74" stroke="#1a73e8" stroke-dasharray="4,3"/>
<line x1="320" y1="150" x2="268" y2="74" stroke="#1a73e8" stroke-dasharray="4,3"/>
<text x="255" y="185" text-anchor="middle" font-weight="bold">Triangulation</text>
<text x="255" y="200" text-anchor="middle" font-size="11">2 fixed points</text>
<line x1="350" y1="140" x2="500" y2="140" stroke="#222" stroke-width="2"/>
<text x="352" y="156" font-size="11">baseline</text>
<circle cx="450" cy="75" r="5" fill="#d93025"/>
<line x1="450" y1="80" x2="450" y2="140" stroke="#1a73e8" stroke-dasharray="4,3"/>
<line x1="350" y1="130" x2="450" y2="130" stroke="#0b8043" stroke-dasharray="2,2"/>
<text x="400" y="125" text-anchor="middle" font-size="11">along</text>
<text x="456" y="112" font-size="11">offset</text>
<text x="425" y="185" text-anchor="middle" font-weight="bold">Baseline</text>
<text x="425" y="200" text-anchor="middle" font-size="11">along + offset</text>
<circle cx="560" cy="140" r="5" fill="#222"/>
<line x1="560" y1="140" x2="660" y2="140" stroke="#222"/>
<circle cx="640" cy="65" r="5" fill="#d93025"/>
<line x1="560" y1="140" x2="636" y2="69" stroke="#1a73e8" stroke-dasharray="4,3"/>
<path d="M600,140 A40,40 0 0,0 589,113" fill="none" stroke="#222"/>
<text x="606" y="128" font-size="11">θ</text>
<text x="585" y="95" font-size="11">d</text>
<text x="600" y="185" text-anchor="middle" font-weight="bold">Polar</text>
<text x="600" y="200" text-anchor="middle" font-size="11">distance + angle</text>
<text x="340" y="18" text-anchor="middle" font-size="11">red dot = item of evidence; dashed = measured distance</text>
</svg>
<div class="cap">Fig: Measurement methods used in crime-scene sketching</div>
</div>

**3-D scanning:** laser scanner (LIDAR) or photogrammetry placed at several stations, rotates 360°, measures distance by **time-of-flight / phase shift** → millions of X,Y,Z points (**point cloud**); reference targets/spheres let scans be **registered** into one model; photos mapped for colour. **Advantages:** captures everything measured at once (measure later what nobody thought of), non-contact, fast, mm-order accuracy, reconstruction (trajectory, line-of-sight, blood spatter origin), virtual walkthrough in court. **Limitations:** costly, training, large data, no micro-detail (won't show a latent print), line-of-sight shadows, glossy/dark surfaces, model is itself electronic evidence (needs certificate).

### Search techniques for a crime scene
**Importance: 10/10** · "draw and explain the search patterns" is near-certain

In simple words: pick a geometric pattern that suits the scene and walk it methodically.

<div class="fig">
<svg viewBox="0 0 680 330" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u3-arr" markerWidth="7" markerHeight="7" refX="6" refY="3.5" orient="auto"><path d="M0,0 L7,3.5 L0,7 z" fill="#1a73e8"/></marker></defs>
<rect x="0" y="0" width="680" height="330" fill="#fff"/>
<rect x="20" y="15" width="180" height="120" fill="#f1f3f4" stroke="#222"/>
<path d="M35,125 L35,25 L65,25 L65,125 L95,125 L95,25 L125,25 L125,125 L155,125 L155,25 L185,25 L185,120" fill="none" stroke="#1a73e8" stroke-width="2" marker-end="url(#u3-arr)"/>
<text x="110" y="152" text-anchor="middle" font-weight="bold">Strip / Line (lane)</text>
<rect x="250" y="15" width="180" height="120" fill="#f1f3f4" stroke="#222"/>
<path d="M265,125 L265,25 L295,25 L295,125 L325,125 L325,25 L355,25 L355,125 L385,125 L385,25 L415,25 L415,125" fill="none" stroke="#1a73e8" stroke-width="2"/>
<path d="M260,120 L420,120 L420,95 L260,95 L260,70 L420,70 L420,45 L260,45 L260,22 L415,22" fill="none" stroke="#d93025" stroke-width="2" marker-end="url(#u3-arr)"/>
<text x="340" y="152" text-anchor="middle" font-weight="bold">Grid (double strip)</text>
<rect x="480" y="15" width="180" height="120" fill="#f1f3f4" stroke="#222"/>
<path d="M570,75 L590,75 L590,55 L550,55 L550,95 L610,95 L610,35 L530,35 L530,115 L630,115 L630,25 L500,25 L500,125 L650,125" fill="none" stroke="#1a73e8" stroke-width="2" marker-end="url(#u3-arr)"/>
<circle cx="570" cy="75" r="4" fill="#222"/>
<text x="570" y="152" text-anchor="middle" font-weight="bold">Spiral (in or out)</text>
<rect x="20" y="180" width="180" height="120" fill="#f1f3f4" stroke="#222"/>
<line x1="110" y1="180" x2="110" y2="300" stroke="#222" stroke-width="2"/>
<line x1="20" y1="240" x2="200" y2="240" stroke="#222" stroke-width="2"/>
<text x="65" y="215" text-anchor="middle">A</text>
<text x="155" y="215" text-anchor="middle">B</text>
<text x="65" y="275" text-anchor="middle">C</text>
<text x="155" y="275" text-anchor="middle">D</text>
<line x1="20" y1="210" x2="110" y2="210" stroke="#999" stroke-dasharray="3,3"/>
<line x1="65" y1="180" x2="65" y2="240" stroke="#999" stroke-dasharray="3,3"/>
<text x="110" y="317" text-anchor="middle" font-weight="bold">Zone / Quadrant</text>
<rect x="250" y="180" width="180" height="120" fill="#f1f3f4" stroke="#222"/>
<circle cx="340" cy="240" r="55" fill="none" stroke="#222"/>
<circle cx="340" cy="240" r="4" fill="#222"/>
<line x1="340" y1="240" x2="395" y2="240" stroke="#1a73e8" stroke-width="2"/>
<line x1="340" y1="240" x2="285" y2="240" stroke="#1a73e8" stroke-width="2"/>
<line x1="340" y1="240" x2="340" y2="185" stroke="#1a73e8" stroke-width="2"/>
<line x1="340" y1="240" x2="340" y2="295" stroke="#1a73e8" stroke-width="2"/>
<line x1="340" y1="240" x2="379" y2="201" stroke="#1a73e8" stroke-width="2"/>
<line x1="340" y1="240" x2="301" y2="279" stroke="#1a73e8" stroke-width="2"/>
<line x1="340" y1="240" x2="301" y2="201" stroke="#1a73e8" stroke-width="2"/>
<line x1="340" y1="240" x2="379" y2="279" stroke="#1a73e8" stroke-width="2"/>
<text x="340" y="317" text-anchor="middle" font-weight="bold">Wheel / Ray</text>
<rect x="480" y="180" width="180" height="120" fill="#f1f3f4" stroke="#222"/>
<circle cx="500" cy="280" r="6" fill="#d93025"/>
<circle cx="545" cy="215" r="6" fill="#d93025"/>
<circle cx="600" cy="260" r="6" fill="#d93025"/>
<circle cx="640" cy="200" r="6" fill="#d93025"/>
<line x1="505" y1="274" x2="541" y2="221" stroke="#1a73e8" stroke-width="2" marker-end="url(#u3-arr)"/>
<line x1="550" y1="220" x2="595" y2="255" stroke="#1a73e8" stroke-width="2" marker-end="url(#u3-arr)"/>
<line x1="605" y1="254" x2="636" y2="207" stroke="#1a73e8" stroke-width="2" marker-end="url(#u3-arr)"/>
<text x="570" y="317" text-anchor="middle" font-weight="bold">Link (evidence-to-evidence)</text>
</svg>
<div class="cap">Fig: Crime-scene search patterns (blue = searcher path; grid adds a perpendicular red pass)</div>
</div>

| Pattern | How | Best for | Weakness |
|---|---|---|---|
| **Strip / Line (lane)** | Area divided into lanes; searchers walk parallel, shoulder-to-shoulder, return in adjacent lane | Large open outdoor areas, many searchers | One viewing angle |
| **Grid (double strip)** | Strip search done twice, second pass **perpendicular** to the first | Critical outdoor scenes, small items | **Most thorough**, but 2× time/manpower |
| **Spiral** | One searcher circles **inward** (edge → centre) or **outward** (centre → edge) | Small confined areas, single body, underwater | Gaps, hard to keep even |
| **Zone / Quadrant / Sector** | Scene divided into zones (rooms, quadrants), each sub-divided and searched by a team | **Indoor**, buildings, vehicles, complex scenes | Zone boundaries missed |
| **Wheel / Ray** | Searchers start at centre and move outward along radii like spokes | Small circular scenes with focal point | **Diverging gaps** at periphery — rarely used |
| **Link** | Each item found leads to the next logically connected item (e.g. blood trail, footprints) | Scenes with an evidence trail | Unconnected items missed; combine with another pattern |

(Link method is listed in standard texts; not in the main source notes.)

**General rules:** general → specific; periphery inward to the focal point; search the CAP first; search 3-D (floor, walls, ceiling, under furniture, drains); **search twice** with different personnel; record **negative evidence**.

### Processing of physical evidence
**Importance: 10/10** · recognition → forwarding is the likely 10/15-mark question

In simple words: find it, record it, pick it up safely, keep it unchanged, pack it, seal it, label it, send it with a letter.

<div class="fig">
<svg viewBox="0 0 680 110" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u3-arr2" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="110" fill="#fff"/>
<rect x="5" y="20" width="76" height="34" fill="#e8f0fe" stroke="#222"/><text x="43" y="42" text-anchor="middle" font-size="11">Recognise</text>
<rect x="90" y="20" width="76" height="34" fill="#e8f0fe" stroke="#222"/><text x="128" y="42" text-anchor="middle" font-size="11">Document</text>
<rect x="175" y="20" width="76" height="34" fill="#e6f4ea" stroke="#222"/><text x="213" y="42" text-anchor="middle" font-size="11">Collect</text>
<rect x="260" y="20" width="76" height="34" fill="#e6f4ea" stroke="#222"/><text x="298" y="42" text-anchor="middle" font-size="11">Preserve</text>
<rect x="345" y="20" width="76" height="34" fill="#fef7e0" stroke="#222"/><text x="383" y="42" text-anchor="middle" font-size="11">Package</text>
<rect x="430" y="20" width="76" height="34" fill="#fef7e0" stroke="#222"/><text x="468" y="42" text-anchor="middle" font-size="11">Seal</text>
<rect x="515" y="20" width="76" height="34" fill="#fce8e6" stroke="#222"/><text x="553" y="42" text-anchor="middle" font-size="11">Label</text>
<rect x="600" y="20" width="76" height="34" fill="#fce8e6" stroke="#222"/><text x="638" y="42" text-anchor="middle" font-size="11">Forward</text>
<line x1="81" y1="37" x2="89" y2="37" stroke="#222" marker-end="url(#u3-arr2)"/>
<line x1="166" y1="37" x2="174" y2="37" stroke="#222" marker-end="url(#u3-arr2)"/>
<line x1="251" y1="37" x2="259" y2="37" stroke="#222" marker-end="url(#u3-arr2)"/>
<line x1="336" y1="37" x2="344" y2="37" stroke="#222" marker-end="url(#u3-arr2)"/>
<line x1="421" y1="37" x2="429" y2="37" stroke="#222" marker-end="url(#u3-arr2)"/>
<line x1="506" y1="37" x2="514" y2="37" stroke="#222" marker-end="url(#u3-arr2)"/>
<line x1="591" y1="37" x2="599" y2="37" stroke="#222" marker-end="url(#u3-arr2)"/>
<rect x="5" y="70" width="671" height="28" fill="#f1f3f4" stroke="#222"/>
<text x="340" y="89" text-anchor="middle" font-size="11">Safety (PPE) throughout · chain-of-custody entry starts at collection and continues to court</text>
</svg>
<div class="cap">Fig: Processing pipeline for physical evidence</div>
</div>

**Recognition:** know what is relevant to *this* offence — reconstruct hypothetically and look for predicted traces; beware "rubbish-looking" evidence (cigarette end, receipt), **negative evidence**, and evidence on the suspect/victim (nail scrapings, clothes). Presumptive tests at scene (Kastle-Meyer for blood, acid phosphatase for semen) are **screening, not confirmatory**.

**Collection:** document first; collect whole item where possible; **most fragile/transient first**; else swab (moist sterile swab for dried stain), scrape, tape-lift, cast (dental stone), lift (prints); always collect **control/reference samples** (needed for Principle of Comparison); clean tools and **change gloves between items**; unique exhibit number and CoC entry at once.

**Safety measures (PPE):** **universal precautions** — treat all body fluids as infectious (HIV, hepatitis); double nitrile gloves, coverall, mask, goggles, shoe covers; sharps in **puncture-proof containers**, use forceps, never recap needles; respirator for chemicals/drug labs; clear fire/structural/electrical hazards first; elimination samples from scene staff; anti-static strap for electronics; never eat/drink/smoke at scene; dispose PPE as biohazard.

**Preservation:** wet blood/semen **air-dried at room temperature in shade** (no heat/sun); dried DNA samples cool & dry, refrigerate/freeze; liquid blood in EDTA tube at 4 °C, not frozen; viscera in **saturated saline** with preservative control; fire debris in **airtight metal cans**; documents flat, never folded/stapled; digital media in **anti-static bags**, away from magnets/heat; phones network-isolated and charged.

**Packaging:**

| Evidence | Packaging |
|---|---|
| **Biological** (dried bloodstained clothes, swabs) | **Paper bags/envelopes, cardboard** — never plastic (moisture → bacteria/mould → DNA degrades) |
| Trace (hair, fibre, glass, paint) | **Paper bindle (druggist's fold)** inside envelope/vial |
| **Arson debris / accelerants** | **Airtight clean metal cans** or nylon bags — not paper, not ordinary plastic (the exception) |
| Liquids | Leak-proof screw-cap bottle in secondary container |
| Sharps | Rigid puncture-proof box, blade immobilised, hazard label |
| Firearms | Unloaded, rigid box, secured |
| Documents | Flat in transparent folder |
| HDD / USB / cards | **Anti-static (ESD) bag** + padded box |
| Mobile phone | **Faraday bag** |

Rules: **one item, one package**; item cannot move inside; package at point of collection; controls separate; **suspect's and victim's items packed, transported and stored separately**.

**Sealing:** tamper-evident — cannot open without visibly breaking the seal; traditional Indian practice: cloth-wrapped/stitched packet with **lac/wax seal impression**, and the **specimen seal impression** sent to the lab separately; modern: evidence tape signed and dated **across the seam**; seal applied before independent witnesses; seal number recorded in seizure memo and CoC. Digital equivalent of a seal = **hash value**.

**Labelling (on the package itself):** case/FIR no., police station, sections · unique exhibit no. · description · date, time, place of collection · collector's and witnesses' names/signatures · person/place seized from · seal details · hazard warnings · handling instructions ("refrigerate", "fragile", "anti-static").

**Forwarding to FSL:** a **forwarding letter/requisition** from IO (or court) with case details, **list of exhibits with seals**, brief **history of the case**, and **specific questions** to be answered; **specimen seal impression** enclosed; carried **by hand by a responsible officer** (not ordinary post); perishables sent first, refrigerated if needed; lab issues **acknowledgement noting seal condition** — next link in the chain.

### Likely questions with model answers

**Q. State and explain Locard's Exchange Principle with examples.** *(5 marks · Likelihood 9/10)*

Locard's Exchange Principle, given by Edmond Locard (who set up the first police crime laboratory at Lyon in 1910), states that whenever two objects come into contact there is always a **mutual exchange of material** between them — "every contact leaves a trace". The criminal brings something to the scene and takes something away from it. The exchange may be too small to detect, but it always occurs.
Examples: (1) A burglar breaking a window leaves fingerprints and clothing fibres on the sill and carries glass fragments away in his shoe soles. (2) In an assault, the victim's blood and hair transfer to the assailant's clothing, while fibres from the assailant are found under the victim's nails.
Digital analogue: a user cannot open a file without leaving traces — MFT timestamps, prefetch entries, LNK files, registry MRU keys and browser cache.
Significance: it is the basis of **trace/transfer evidence** and of linking suspect, victim and scene. Limitation: detection depends on time elapsed, medium and analyst skill, so absence of a trace is not proof of absence of contact.

**Q. Differentiate between class and individual characteristics of physical evidence with examples.** *(5 marks · Likelihood 10/10)*

**Class characteristics** are features common to a group of objects, arising from design, manufacture or species. They associate evidence only with a group of possible sources — e.g. shoe brand, size and tread design; bullet calibre and number/twist of lands and grooves; ABO blood group; glass refractive index; fingerprint pattern type (loop, whorl, arch).
**Individual characteristics** arise from random, accidental wear, damage or imperfection and associate evidence with **one** source — e.g. cuts and wear marks on a sole; barrel-specific striations on a bullet; DNA STR profile; physical fit of broken glass edges; fingerprint minutiae (ridge endings, bifurcations).

| Class | Individual |
|---|---|
| Group of sources | Single source |
| From manufacture/design | From random wear/damage |
| Corroborative | Conclusive |
| e.g. file type, camera model | e.g. SHA-256 hash, IMEI |

A mismatch in a class characteristic is enough to **exclude** a source; many matching class features only raise cumulative probability.

**Q. What is chain of custody? Why is it important?** *(5 marks · Likelihood 10/10)*

Chain of custody is the chronological documentation recording the **seizure, custody, control, transfer, analysis and disposition** of physical or electronic evidence — who had it, when, where, why and what was done to it — from collection at the scene to production in court and final disposal. Every person who handles the exhibit signs for it, with no unexplained gap.
The form records: case/FIR number, unique exhibit number, description (serial/IMEI), date, time and place of seizure, collector and witnesses' signatures, seal number, hash value (digital), every transfer (released by/received by with date, time and purpose), storage conditions and final disposition.
Importance: (1) proves **authenticity** — the exhibit in court is the one seized; (2) proves **integrity** — it was not altered; (3) fixes **accountability**; (4) defeats claims of tampering, substitution or planting; (5) a break (missing signature, broken seal, hash mismatch, missing BSA §63 certificate) can make the evidence inadmissible or worthless and collapse the prosecution case.

**Q. Describe the duties of the first officer at the scene of crime.** *(5 marks · Likelihood 9/10)*

The first officer's job is to **freeze** the scene, not investigate it. Duties in order: (1) assess safety — armed suspect, fire, gas, electricity, biohazard; (2) preserve life — give medical aid; if the body must be moved, first mark and photograph its position; (3) detain and separate persons present and note their details and movements; (4) establish a boundary and cordon (outer, inner, core), making it larger than seems necessary; (5) fix a single common approach path; (6) keep an entry/exit log of every person, including senior officers; (7) exclude media, relatives and onlookers; (8) protect transient evidence — cover footprints from rain, note odours, temperature, lights on/off; (9) not touch, smoke, eat or use the toilet or telephone; (10) record time of arrival, weather, condition of doors and windows; (11) inform the IO, FSL/mobile unit, fingerprint bureau and photographer; (12) hand over formally to the IO with the log. At a digital scene: do not switch devices on or off, photograph the screen, isolate phones in a Faraday bag.

**Q. Distinguish between rough sketch and finished sketch. Name the methods of measurement.** *(5 marks · Likelihood 8/10)*

A **rough sketch** is drawn freehand **at the scene**, not to scale, but carries all measurements, numbered evidence items, north direction, room dimensions and positions of doors, windows and furniture. It is the original record and must be preserved. A **finished sketch** is prepared later in the office, by hand or CAD, **to scale** (e.g. 1:50), neatly, with a legend, scale ratio, north arrow, case number and signatures, for court presentation.
Every sketch must have: case number, date, time, location, north arrow, scale (or "not to scale"), legend, names of sketcher/measurer and witnesses.
Measurement methods: **rectangular coordinates** (perpendicular distances from two walls at right angles — indoor); **triangulation** (distances from two fixed points — outdoor); **baseline** (distance along a fixed line plus perpendicular offset); **polar** (distance and angle from one fixed point); **cross-projection** (walls folded flat, for evidence on walls/ceiling).

**Q. Why must biological evidence be packed in paper and not plastic? Write the general rules of packaging.** *(5 marks · Likelihood 8/10)*

Plastic is airtight: residual moisture in blood, semen or saliva stains cannot escape, so bacteria and fungi grow and **degrade the DNA** and other biological markers. Paper "breathes", letting the sample keep drying. Wet stains are first **air-dried at room temperature in the shade** (never heat or sunlight) and then packed in paper bags, envelopes or cardboard boxes. Exception: **arson debris** goes in airtight metal cans, because accelerant vapours escape through paper and ordinary plastic. Digital media go in anti-static bags, phones in Faraday bags.
General rules: (1) one item, one package; (2) the item must not move inside; (3) package at the point of collection; (4) control samples packed separately; (5) suspect's and victim's articles packed, transported and stored separately; (6) sharps in puncture-proof containers; (7) seal tamper-evident and label each package with case number, exhibit number, description, date, place and signatures.

**Q. Describe the organisation and functioning of forensic science laboratories in India.** *(10 marks · Likelihood 9/10)*

Forensic services in India are organised at two levels because police is a State subject while the Union handles central agencies and inter-State matters (draw the organisational chart above).
**Central level.** The **Ministry of Home Affairs** controls the **Directorate of Forensic Science Services (DFSS)**, New Delhi, created in 2002 (as DFS, carved out of BPR&D) and headed by a Director-cum-Chief Forensic Scientist. DFSS exercises administrative and technical control over the **Central Forensic Science Laboratories** and the **Government Examiners of Questioned Documents**. Its functions are: services to central agencies (CBI, NIA, ED, NCB, CAPFs) and to States in referred or sensational cases; acting as a **referral laboratory** for second opinion; framing national standards, SOPs and quality-assurance norms; R&D; and training forensic scientists, police, prosecutors and judicial officers.
**CFSLs** are at **Kolkata (1957, the oldest)**, Hyderabad, Chandigarh, **Guwahati (serving the North-East including Nagaland)**, Bhopal and Pune. CFSL New Delhi is under the **CBI**, not DFSS. CFSLs examine exhibits from central agencies and courts, give second opinions, attend important scenes, give expert evidence and validate methods. **GEQDs** at Shimla, Kolkata and Hyderabad examine handwriting, signatures, forgeries and counterfeit currency. Allied bodies: BPR&D (1970), NCRB (1986, NAFIS), NFSU (2020), I4C.
**State level.** Each State has a **State FSL** under the Home Department/Police, usually in the capital, headed by a Director. It handles routine casework for the whole State, attends serious scenes, gives evidence in State courts, supervises regional units and trains police in evidence handling. **Regional FSLs** are zonal branches doing high-volume routine work (viscera toxicology, excise, narcotics screening, serology), reducing delay and transport risk. **Mobile Forensic Units** are laboratories on wheels with scene kits, photography, light sources, fingerprint and presumptive-test kits and packaging material; they are the backbone of BNSS mandatory scene visits for offences punishable with 7 years or more. In Nagaland, a State FSL under Nagaland Police handles State work with central support from CFSL Guwahati.
**Divisions** of a full FSL: biology, serology, DNA, chemistry, toxicology, narcotics, physics, ballistics, questioned documents, fingerprints, **cyber forensics**, photography, lie detection, prohibition & excise.
**Functioning:** exhibits arrive sealed with a forwarding letter; seals are checked against the specimen; the case is registered and allotted to the division; analysis uses validated methods; the report is issued with re-sealed exhibits; the scientist testifies if summoned.

**Q. Explain the different search methods used for locating physical evidence at a crime scene, with diagrams.** *(10 marks · Likelihood 9/10)*

A scene search must be **systematic, exhaustive and documented**; the method depends on the size of the area, terrain, number of searchers and whether the scene is indoor or outdoor (draw the six-panel pattern diagram above).
**1. Strip/Line (lane) search** — the area is marked into parallel lanes; searchers walk shoulder-to-shoulder along a lane and return along the adjacent one. Suited to large open outdoor areas with many searchers; weakness: one viewing angle.
**2. Grid (double-strip) search** — a strip search is done, then repeated at right angles. Each area is seen twice from two directions, so it is the **most thorough** method for critical outdoor scenes and small items, but needs double time and manpower.
**3. Spiral search** — one searcher moves in a spiral, inward from the boundary to the centre or outward from the centre. Suited to small confined areas, a single body or underwater; drawbacks: gaps, hard to keep even, outward spiral risks walking over evidence.
**4. Zone/Quadrant/Sector search** — the scene is divided into zones (rooms, quadrants) and each is sub-divided and searched by a team. Best for **indoor** scenes, buildings, vehicles and complex scenes; zones can be cross-checked, but boundaries may be missed.
**5. Wheel/Ray search** — searchers start at the centre and move outward along radii like spokes. Used for small circular scenes with a focal point; leaves widening gaps between spokes, so it is rarely used alone.
**6. Link search** — each item found leads logically to the next (blood trail, footprints). Useful where evidence forms a trail; combine with another method for unconnected items.
**General rules:** search the common approach path first; work from general to specific and periphery inward; search in three dimensions (floor, walls, ceiling, drains); photograph and record before moving; search twice with different personnel; record negative evidence. Discovery aids: oblique light, alternate light sources, UV/IR, luminol, fingerprint powders, metal detectors.

**Q. Describe crime-scene documentation: note taking, photography, videography and sketching.** *(10 marks · Likelihood 9/10)*

Golden rule: **document before you disturb**. The four methods are complementary, not alternatives.
**Note taking** — contemporaneous notes in a bound, page-numbered notebook in ink, with no erasures (errors struck through and initialled). They record time of call and arrival, weather and lighting, persons present, condition of doors, windows, lights and appliances, position of the body, transient observations (odour, temperature), description and location of each exhibit, who collected what and when, negative findings, and time of departure. Notes are disclosable to the defence.
**Photography** — in three levels: (1) **overall** shots of the whole scene, exterior, approaches, all walls, ceiling and floor; (2) **mid-range** shots of each item with a fixed landmark to show its position; (3) **close-ups** filling the frame, first **without a scale** and then **with a scale** and identification label. Photograph before anything is moved, then with markers in place; keep a photo log (number, subject, direction, time, settings, photographer); no editing; retain originals with hash.
**Videography** — a slow, steady walkthrough giving spatial context, starting with a spoken statement of case number, date, time, place and operator; no opinion in narration (or mute audio); done before stills and markers; unedited original kept with hash.
**Sketching** — gives measurements a photograph cannot. The **rough sketch** is freehand at the scene, not to scale but with all measurements; the **finished sketch** is drawn to scale later with legend, scale ratio and north arrow. Measurements by rectangular coordinates, triangulation, baseline or polar method; cross-projection for walls and ceiling.
**3-D scanning** adds a measured point-cloud model of the whole scene for reconstruction and virtual walkthroughs in court.

**Q. Describe the crime-scene procedure from protection of the scene to forwarding of evidence to the laboratory.** *(15 marks · Likelihood 9/10)*

The crime scene is the place of the offence and the surrounding area where evidence may be found. Because of Locard's principle traces are always left, and because of the Law of Progressive Change they start disappearing at once. So the procedure must be fast, systematic and fully documented.
**1. Protection of the scene.** The first officer assesses safety, preserves life (marking the body's position if it must be moved), detains and separates persons present, and sets up a **three-layer cordon** (outer for public and media, inner for authorised staff, core for the forensic team) with a single **common approach path**. An **entry/exit log** is kept for everyone. Transient evidence is protected (footprints covered, odours and lights noted). Nobody touches, smokes or eats at the scene. The IO, mobile forensic unit, fingerprint bureau and photographer are informed, and the scene is formally handed over.
**2. Preliminary survey.** The IO and forensic expert walk the approach path, note the layout, likely points of entry and exit, and plan the search pattern and documentation.
**3. Documentation.** Contemporaneous **notes** in a bound notebook; **photography** in overall, mid-range and close-up (without, then with scale) views with a photo log; **videography** walkthrough without opinion; **rough sketch** at the scene with measurements by rectangular coordinates, triangulation, baseline or polar method, later redrawn as a **finished sketch** to scale; 3-D scanning where available.
**4. Search.** A suitable pattern is used — zone/quadrant indoors; strip, grid or spiral outdoors; link search along trails — aided by oblique light, alternate light sources, luminol and fingerprint powders. The approach path is searched first, the search is three-dimensional, and it is repeated by different personnel.
**5. Recognition and collection.** The investigator identifies what is relevant to the offence, including negative evidence and traces on suspect and victim. Presumptive tests are only screening. Items are collected after documentation, most transient first, whole where possible, otherwise by swab, scrape, tape-lift, cast or lift, with **control samples**. Gloves and tools are changed between items. Each item gets a unique exhibit number and a chain-of-custody entry, and a seizure memo is signed before independent witnesses.
**6. Safety measures.** Universal precautions — double gloves, coverall, mask, goggles, shoe covers; sharps in puncture-proof containers; respirators for chemicals; elimination samples from staff; anti-static precautions for electronics.
**7. Preservation.** Wet biological stains are air-dried in the shade; DNA samples kept cool and dry; liquid blood refrigerated in EDTA; viscera in saturated saline; fire debris in airtight cans; digital media away from magnets and heat; phones isolated from the network.
**8. Packaging.** Biological items in **paper**, never plastic (moisture degrades DNA); trace in paper bindles; arson debris in metal cans; liquids in leak-proof bottles; sharps in rigid boxes; drives in anti-static bags; phones in Faraday bags. One item per package; suspect's and victim's items separate.
**9. Sealing.** Tamper-evident — lac/wax seal impression on cloth-wrapped packets, or signed evidence tape across the seam, applied before witnesses; a specimen seal impression is kept for the laboratory. For digital evidence, the hash value acts as the seal.
**10. Labelling.** Each package carries case/FIR number, exhibit number, description, date, time and place of collection, signatures of collector and witnesses, seal details and hazard or handling instructions.
**11. Forwarding.** Exhibits go to the FSL with a **forwarding letter** listing the exhibits and seals, giving a brief case history and the **specific questions** to be answered, with the specimen seal impression. A responsible officer carries them by hand; perishables go first. The laboratory acknowledges receipt and records the seal condition.
Throughout, the **chain of custody** is unbroken: every transfer is signed with date, time and purpose. A gap, broken seal or hash mismatch can make the evidence inadmissible. Proper procedure therefore decides whether the science can be used in court at all.

## Unit 4 — Introduction to Computer Hardware

### Components of a computer and why they matter forensically
**Importance: 7/10** · direct syllabus heading; basis of "what to seize and in what order"

In simple words: a computer = CPU + memory + storage + I/O + buses on a motherboard; each holds evidence that lives for a different length of time.

| Component | Role | Forensic note |
|---|---|---|
| CPU | Executes instructions (ALU, CU, registers, cache) | Registers/cache = most volatile; lost in nanoseconds |
| RAM | Working memory | Running processes, keys, passwords, network connections — **lost on power-off** |
| Storage (HDD/SSD) | Persistent data | Main source of files, artifacts, deleted data |
| Motherboard | Connects everything | BIOS/UEFI settings, CMOS clock (time offset!) |
| I/O & ports (USB, SATA, NVMe, Thunderbolt) | Attach devices | Point to removable media to look for |
| NIC | Network access | MAC address, links machine to network logs |
| PSU | Power | Pull-the-plug vs graceful shutdown decision |

Exam tip: always end with "note the CMOS clock time vs. actual time" — it is the forensic hook of hardware.

### Motherboard — chipset, sockets, slots, BIOS/UEFI, CMOS
**Importance: 7/10** · syllabus phrase; easy 5-marker

In simple words: the main circuit board that every component plugs into.

- **Chipset:** controls data flow between CPU, memory and peripherals. Classically **Northbridge** (CPU–RAM–GPU, fast) + **Southbridge** (I/O, USB, SATA, slow); modern systems move the northbridge into the CPU and keep one **PCH** (Platform Controller Hub).
- **CPU socket:** LGA (pins on board, Intel) / PGA (pins on CPU) / BGA (soldered, laptops).
- **Slots:** DIMM (desktop RAM), SO-DIMM (laptop RAM), PCIe (GPU, NIC, NVMe adapters), M.2 (NVMe/SATA SSD).
- **Connectors:** SATA, USB headers, power (24-pin ATX).
- **BIOS** (Basic Input/Output System): firmware in flash ROM; runs POST, initialises hardware, finds a boot device. 16-bit, uses MBR.
- **UEFI** (Unified Extensible Firmware Interface): modern replacement — GPT disks > 2 TiB, Secure Boot, faster, graphical, network boot.
- **CMOS:** small battery-backed memory storing BIOS settings — **boot order, system date/time**, passwords. RTC (real-time clock) runs from the CMOS battery.

Exam tip: *Forensic relevance* — enter BIOS/UEFI setup (with storage disconnected) to record **system time vs. true time** and **boot order** so the suspect disk is never booted accidentally.

### Processor (CPU)
**Importance: 5/10** · background; MCQ material

In simple words: the "brain" that fetches, decodes and executes instructions.

- Parts: **ALU** (arithmetic/logic), **CU** (control), **registers** (PC, IR, MAR, MDR, accumulator, general), **cache** L1/L2/L3.
- Multi-core, clock speed (GHz), 32-bit vs 64-bit (address space 4 GiB vs 16 EiB theoretical).
- Architecture: x86/x64 (CISC, Intel/AMD), ARM (RISC, phones, Apple Silicon M-series).
- Forensic note: CPU architecture decides which tools/memory profiles work; Apple Silicon / T2 chips encrypt internal storage in hardware — chip-off imaging is useless without keys.

### Memory — RAM, ROM, cache and the order of volatility
**Importance: 8/10** · volatility is a core forensic principle (RFC 3227)

In simple words: volatile memory forgets when power goes; non-volatile keeps data.

| Type | Volatile? | Technology / use |
|---|---|---|
| Registers, cache (SRAM) | Yes | Flip-flops, fast, no refresh; L1/L2/L3 cache |
| DRAM (SDRAM, DDR1–DDR5) | Yes | Capacitors, needs refresh; main memory |
| ROM | No | Factory-programmed |
| PROM | No | Programmable once |
| EPROM | No | Erased by UV light |
| EEPROM / Flash | No | Electrically erasable; BIOS chips, SSDs, pen drives |

**Order of volatility (RFC 3227) — collect top first:**
1. Registers, cache 2. Routing table, ARP cache, process table, kernel statistics, **memory (RAM)** 3. Temporary file systems 4. Disk 5. Remote logging/monitoring data 6. Physical configuration, network topology 7. Archival media.

- **What RAM gives:** running processes, open network connections, decrypted keys (BitLocker/VeraCrypt), passwords, chat fragments, injected malware that never touches disk.
- **Data remanence:** DRAM keeps contents for seconds after power loss (longer when cooled) → **cold-boot attack**.
- Capture tools: FTK Imager, DumpIt, WinPmem, LiME (Linux); analyse with **Volatility**.

Exam tip: "If the machine is ON, capture RAM before pulling the plug" — write this line in any seizure answer.

### Storage devices — HDD geometry
**Importance: 8/10** · sectors/clusters underpin slack space and recovery

In simple words: an HDD stores bits magnetically on spinning platters read by moving heads.

| Term | Meaning |
|---|---|
| Platter | Magnetic disk (both surfaces used) |
| Head | Reads/writes one surface, on an actuator arm |
| Track | One concentric ring on a surface |
| Cylinder | Same track number across all surfaces |
| **Sector** | Smallest physical unit: **512 bytes** (Advanced Format: **4096 bytes**) |
| **Cluster** (allocation unit/block) | Smallest unit the **file system** allocates = 2ⁿ sectors (e.g. 8 × 512 = 4 KiB) |

- Addressing: **CHS** (Cylinder-Head-Sector, old) → **LBA** (Logical Block Addressing, sectors numbered 0, 1, 2 …).
- **Hidden areas:** **HPA** (Host Protected Area) and **DCO** (Device Configuration Overlay) — set via ATA commands, invisible to the OS; must be detected and imaged.
- Deleted data on HDD stays until overwritten → **recovery and carving work well**.

### SSD, flash and optical — the SSD forensic problem
**Importance: 9/10** · classic "how do SSDs affect forensics" question

In simple words: SSDs store data in NAND flash managed by a controller that moves and erases data on its own.

- NAND is written in **pages** but erased only in **blocks**; it cannot overwrite in place.
- **FTL (Flash Translation Layer):** maps logical LBAs to changing physical pages.
- **Wear levelling:** spreads writes across all cells so none wear out early → old copies of data may sit in unmapped/over-provisioned cells unreachable through the normal interface.
- **TRIM:** OS tells the SSD which blocks are deleted; **garbage collection** then erases them in the background.
- **Forensic impact:** deleted files on a TRIM-enabled SSD are usually **unrecoverable** (reads return zeros); GC may run **whenever the drive has power, even behind a write-blocker** → two images taken at different times can have **different hashes**; carving yields little.
- Countermeasures: image immediately, minimise powered time, document TRIM status (`fsutil behavior query DisableDeleteNotify` on Windows), chip-off/vendor-mode for advanced labs.
- **Flash media** (USB pen drive, SD card): NAND + simple controller, usually FAT32/exFAT; less aggressive TRIM, so recovery is often still possible.
- **Optical** (CD 700 MB, DVD 4.7 GB, Blu-ray 25 GB): pits and lands read by laser; CD-R/DVD-R are write-once — good for archival evidence; multi-session discs may hide earlier sessions.

Exam tip: write the line "SSD = TRIM + garbage collection + wear levelling ⇒ less deleted-data recovery and hash may change between acquisitions."

### Networking components
**Importance: 6/10** · syllabus item; short-note material

In simple words: devices that move data between computers; each keeps logs or tables an investigator can use.

| Device | OSI layer | Forensic value |
|---|---|---|
| NIC | 1–2 | Holds the **MAC address** (48-bit; first 24 bits = **OUI**, identifies vendor) |
| Hub | 1 | Broadcasts to all ports — easy sniffing |
| **Switch** | 2 | Forwards by MAC; **CAM table** (MAC→port) shows which device was on which port |
| **Router** | 3 | Forwards by IP; **ARP table, NAT/DHCP logs, routing table** — link internal IP to device |
| Firewall | 3–7 | Allow/deny logs of connections |
| Wireless AP | 1–2 | Associated clients, SSID logs |
| Modem | 1 | Connects to ISP; ISP holds IP-to-subscriber records |

Exam tip: MAC is changeable (spoofing) — corroborate with DHCP lease logs.

### Operating system basics
**Importance: 5/10** · background for Unit 5 and Unit 8

In simple words: the OS manages hardware and gives programs services (files, memory, processes, devices).

- Functions: process management, memory management (paging, virtual memory → **pagefile/swap holds RAM fragments**), file-system management, device management (drivers), security (users, permissions), user interface.
- Kernel types: monolithic (Linux), hybrid (Windows NT, macOS XNU), microkernel.
- Every OS keeps its own **artifacts**: logs, configuration databases (Registry, plists, /etc), user histories — the subject of Unit 5.

### The booting process — BIOS/MBR and UEFI/GPT
**Importance: 9/10** · named in FSPEC as top forensic item; "explain the boot process" is a classic

In simple words: booting is the chain that takes the machine from power-on to a running OS; each link reads the next from a fixed place.

**Legacy BIOS path:**
1. **Power on** → CPU jumps to the BIOS firmware in ROM/flash.
2. **POST** (Power-On Self-Test) checks CPU, RAM, video, keyboard; beep codes on failure.
3. BIOS reads the **boot order from CMOS** and picks a boot device.
4. Reads **sector 0 = MBR** (512 bytes): **446 B boot code + 64 B partition table (4 × 16 B) + 2 B signature 0x55AA**.
5. MBR code finds the **active partition** and loads its **Volume Boot Record (VBR)**.
6. VBR loads the **boot loader**: `NTLDR` (Windows XP) / **`bootmgr` → `winload.exe`** (Vista+), or **GRUB** (Linux).
7. Boot loader loads the **kernel** (`ntoskrnl.exe`; Linux `vmlinuz` + initramfs).
8. Kernel starts first processes: Windows `smss.exe` → `winlogon.exe`, services; Linux **`init`/`systemd` (PID 1)** → login.

**UEFI path:**
1. Power on → UEFI firmware initialises hardware (SEC → PEI → DXE phases), runs POST checks.
2. Boot Manager reads boot entries from **NVRAM** variables.
3. Reads the **GPT** and finds the **EFI System Partition (ESP, FAT32)**.
4. Runs the EFI loader: Windows **`\EFI\Microsoft\Boot\bootmgfw.efi` → `winload.efi`**; Linux `grubx64.efi`/shim.
5. **Secure Boot** verifies digital signatures of each loader.
6. Kernel loads → same as step 8 above.

<div class="fig">
<svg viewBox="0 0 680 250" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u4-arr1" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="250" fill="#fff"/>
<text x="10" y="22" font-weight="bold">Legacy BIOS</text>
<rect x="10" y="35" width="80" height="44" fill="#f1f3f4" stroke="#222"/><text x="50" y="61" text-anchor="middle">Power on</text>
<rect x="110" y="35" width="80" height="44" fill="#e8f0fe" stroke="#222"/><text x="150" y="55" text-anchor="middle">BIOS</text><text x="150" y="70" text-anchor="middle">+ POST</text>
<rect x="210" y="35" width="90" height="44" fill="#e8f0fe" stroke="#222"/><text x="255" y="55" text-anchor="middle">CMOS boot</text><text x="255" y="70" text-anchor="middle">order</text>
<rect x="320" y="35" width="90" height="44" fill="#fef7e0" stroke="#222"/><text x="365" y="55" text-anchor="middle">MBR</text><text x="365" y="70" text-anchor="middle">(LBA 0)</text>
<rect x="430" y="35" width="105" height="44" fill="#fef7e0" stroke="#222"/><text x="482" y="55" text-anchor="middle">VBR → boot</text><text x="482" y="70" text-anchor="middle">loader</text>
<rect x="555" y="35" width="115" height="44" fill="#e6f4ea" stroke="#222"/><text x="612" y="55" text-anchor="middle">Kernel →</text><text x="612" y="70" text-anchor="middle">init / smss</text>
<line x1="90" y1="57" x2="108" y2="57" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="190" y1="57" x2="208" y2="57" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="300" y1="57" x2="318" y2="57" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="410" y1="57" x2="428" y2="57" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="535" y1="57" x2="553" y2="57" stroke="#222" marker-end="url(#u4-arr1)"/>
<text x="10" y="132" font-weight="bold">UEFI</text>
<rect x="10" y="145" width="80" height="44" fill="#f1f3f4" stroke="#222"/><text x="50" y="171" text-anchor="middle">Power on</text>
<rect x="110" y="145" width="80" height="44" fill="#e8f0fe" stroke="#222"/><text x="150" y="165" text-anchor="middle">UEFI</text><text x="150" y="180" text-anchor="middle">+ POST</text>
<rect x="210" y="145" width="90" height="44" fill="#e8f0fe" stroke="#222"/><text x="255" y="165" text-anchor="middle">NVRAM boot</text><text x="255" y="180" text-anchor="middle">entries</text>
<rect x="320" y="145" width="90" height="44" fill="#fef7e0" stroke="#222"/><text x="365" y="165" text-anchor="middle">GPT →</text><text x="365" y="180" text-anchor="middle">ESP (FAT32)</text>
<rect x="430" y="145" width="105" height="44" fill="#fef7e0" stroke="#222"/><text x="482" y="165" text-anchor="middle">bootmgfw.efi</text><text x="482" y="180" text-anchor="middle">→ winload.efi</text>
<rect x="555" y="145" width="115" height="44" fill="#e6f4ea" stroke="#222"/><text x="612" y="165" text-anchor="middle">Kernel</text><text x="612" y="180" text-anchor="middle">(ntoskrnl.exe)</text>
<line x1="90" y1="167" x2="108" y2="167" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="190" y1="167" x2="208" y2="167" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="300" y1="167" x2="318" y2="167" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="410" y1="167" x2="428" y2="167" stroke="#222" marker-end="url(#u4-arr1)"/>
<line x1="535" y1="167" x2="553" y2="167" stroke="#222" marker-end="url(#u4-arr1)"/>
<text x="340" y="225" text-anchor="middle">Secure Boot checks signatures of each EFI loader before it runs</text>
</svg>
<div class="cap">Fig: Boot sequence — legacy BIOS/MBR (top) and UEFI/GPT (bottom)</div>
</div>

**Forensic relevance:** (i) never boot the suspect disk — booting writes logs, updates timestamps, may trigger wiping; (ii) to boot a seized machine use a forensic boot USB set in BIOS/UEFI order; (iii) **bootkits/MBR malware** hide in boot code; (iv) record CMOS time.

### MBR vs GPT
**Importance: 8/10** · standard "differentiate" question

In simple words: two ways of writing the partition table at the start of a disk.

| Feature | MBR | GPT |
|---|---|---|
| Firmware | BIOS | UEFI |
| Location | Sector 0 only | LBA 0 protective MBR, LBA 1 GPT header, entries from LBA 2; **backup header + table at end of disk** |
| Partitions | 4 primary (or 3 + extended with logical) | 128 by default (Windows) |
| Address size | 32-bit LBA → **2 TiB** max (512-B sectors) | 64-bit LBA → ~9.4 ZB |
| Integrity | None | **CRC32** checksums on header and table |
| Identifiers | 1-byte partition type code | **GUIDs** for disk and each partition |
| Signature | 0x55AA at end of sector | "EFI PART" in header |

Exam tip: forensic point — GPT's backup copy helps recover a deliberately wiped partition table; unpartitioned gaps between partitions can hide data in both schemes.

### File systems and types — comparison
**Importance: 9/10** · "file systems and types" is a syllabus phrase; table answers score well

In simple words: a file system is the on-disk structure that records where each file's data is and its metadata (name, size, times, permissions).

| FS | OS / use | Key structures | Max file | Journal | Forensic notes |
|---|---|---|---|---|---|
| FAT12 | Floppies | FAT + root dir | — | No | 12-bit cluster entries |
| FAT16 | Old DOS/small media | FAT + root dir | 2 GiB (4 GiB with 64 KiB clusters) | No | 16-bit entries |
| FAT32 | USB, SD, ESP | Two FAT copies, dir entries (32 B) | **4 GiB − 1 B** | No | Deleted file: 1st char of name → **0xE5**; data stays; no permissions; dates in local time |
| exFAT | Large flash (SDXC) | Allocation bitmap, FAT | 16 EiB (theoretical) | No | Large files, cross-platform; no ADS |
| **NTFS** | Windows | **MFT**, $LogFile, $UsnJrnl, $Bitmap | 16 TiB (practical, older Windows) – larger theoretical | **Yes** | ACLs, **ADS**, EFS encryption, compression, resident files, rich timestamps |
| ext2 | Old Linux | Superblock, block groups, **inodes** | 2 TiB | No | Deleted inode pointers often recoverable |
| ext3 | Linux | ext2 + journal | 2 TiB | Yes | Zeroes block pointers on delete — recovery harder |
| ext4 | Modern Linux | **Extents**, inodes | 16 TiB | Yes | Nanosecond times, **crtime** (creation time) |
| HFS+ | macOS ≤ 10.12 | Catalog file (B-tree), extents file | 8 EiB | Yes | Resource forks; times since 1904 |
| **APFS** | macOS 10.13+ / iOS | Copy-on-write B-trees, containers/volumes | 8 EiB | CoW (no classic journal) | **Snapshots**, native **encryption**, clones, nanosecond times |

Exam tip: if asked "types of file systems", group as Windows (FAT/exFAT/NTFS), Linux (ext2/3/4, XFS, Btrfs), Mac (HFS+/APFS), optical (ISO 9660, UDF).

## Unit 5 — Windows, Linux & Mac OS X System Artifacts

### Why system artifacts matter
**Importance: 8/10** · intro line for every Unit-5 answer

In simple words: artifacts are traces the OS leaves automatically while a user works — they answer *who, what, when, where*.

| Question | Windows | Linux | macOS |
|---|---|---|---|
| Who logged in? | Security.evtx 4624/4625, SAM | auth.log/secure, wtmp, btmp | Unified log, user plists |
| What ran? | Prefetch, UserAssist, event 4688 | bash_history | KnowledgeC, zsh_history |
| What files opened? | LNK, Jump Lists, RecentDocs | .viminfo, recently-used.xbel | Recent items (.sfl2) |
| USB used? | USBSTOR, MountedDevices, setupapi.dev.log | syslog / kern.log | FSEvents, unified log |
| Downloaded? | Zone.Identifier ADS | — | com.apple.quarantine, QuarantineEventsV2 |

### NTFS and the Master File Table (MFT)
**Importance: 9/10** · NTFS internals are the base of Windows forensics

In simple words: in NTFS *everything is a file*, and every file has at least one 1 KiB record in the MFT describing it.

- **$MFT** is itself MFT record 0; records **0–15 are system metadata files**: `$MFT`(0), `$MFTMirr`(1), `$LogFile`(2), `$Volume`(3), `$AttrDef`(4), `.` root(5), `$Bitmap`(6), `$Boot`(7), `$BadClus`(8), `$Secure`(9), `$UpCase`(10), `$Extend`(11).
- Each **MFT record = 1024 bytes**, starts with signature **"FILE"**, then attributes, ending with marker 0xFFFFFFFF.
- Key attributes: **$STANDARD_INFORMATION (0x10)** — MACB times, flags; **$FILE_NAME (0x30)** — name, parent, second set of MACB times; **$DATA (0x80)** — content; $INDEX_ROOT/$INDEX_ALLOCATION (directories); $SECURITY_DESCRIPTOR; $OBJECT_ID.
- **Resident vs non-resident:** small files (≈ < 700 bytes) live **inside the MFT record**; larger ones store **data runs** pointing to clusters.
- **Deletion:** record's "in-use" flag cleared and $Bitmap clusters freed — record and data survive until reused → recovery.
- **Timestomping detection:** tools alter $SI times easily but **$FN times are harder to change** → $SI earlier than $FN is a red flag.
- **$LogFile** (transaction journal) and **$UsnJrnl:$J** (change journal: create/delete/rename records) reconstruct file activity.

<div class="fig">
<svg viewBox="0 0 680 170" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="680" height="170" fill="#fff"/>
<text x="340" y="20" text-anchor="middle" font-weight="bold">One MFT record (1024 bytes)</text>
<rect x="10" y="35" width="95" height="60" fill="#f1f3f4" stroke="#222"/><text x="57" y="60" text-anchor="middle">Header</text><text x="57" y="77" text-anchor="middle">"FILE"</text>
<rect x="105" y="35" width="140" height="60" fill="#e8f0fe" stroke="#222"/><text x="175" y="60" text-anchor="middle">$STANDARD_INFO</text><text x="175" y="77" text-anchor="middle">0x10 · MACB, flags</text>
<rect x="245" y="35" width="140" height="60" fill="#e6f4ea" stroke="#222"/><text x="315" y="60" text-anchor="middle">$FILE_NAME</text><text x="315" y="77" text-anchor="middle">0x30 · name, parent</text>
<rect x="385" y="35" width="150" height="60" fill="#fef7e0" stroke="#222"/><text x="460" y="60" text-anchor="middle">$DATA 0x80</text><text x="460" y="77" text-anchor="middle">resident or data runs</text>
<rect x="535" y="35" width="70" height="60" fill="#fce8e6" stroke="#222"/><text x="570" y="60" text-anchor="middle">Free /</text><text x="570" y="77" text-anchor="middle">slack</text>
<rect x="605" y="35" width="65" height="60" fill="#f1f3f4" stroke="#222"/><text x="637" y="60" text-anchor="middle">End</text><text x="637" y="77" text-anchor="middle">FFFFFFFF</text>
<text x="10" y="122">• $SI and $FN each hold 4 times: Modified, Accessed, MFT-changed, Born (MACB)</text>
<text x="10" y="142">• Extra $DATA attributes with a name = Alternate Data Streams</text>
<text x="10" y="162">• Directory records use $INDEX_ROOT (0x90) / $INDEX_ALLOCATION (0xA0) instead of $DATA</text>
</svg>
<div class="cap">Fig: Layout of an NTFS MFT record and its main attributes</div>
</div>

### Windows Registry — hives and on-disk files
**Importance: 10/10** · the single most examinable Windows artifact

In simple words: the Registry is Windows' central hierarchical database of system, software and per-user settings — and it silently logs user activity.

- Structure: **root keys → keys → subkeys → values** (name, type e.g. REG_SZ/REG_DWORD/REG_BINARY, data). Every key has a **LastWrite timestamp**.
- Root keys: HKLM (machine), HKU (all users), HKCU (current user = HKU\<SID>), HKCR (classes), HKCC (current hardware profile).

| Hive | On-disk file | Forensic contents |
|---|---|---|
| SAM | `%SystemRoot%\System32\config\SAM` | Local accounts, RIDs, groups, password hashes, last logon, logon count |
| SECURITY | `...\config\SECURITY` | Security policy, LSA secrets, cached domain credentials |
| SOFTWARE | `...\config\SOFTWARE` | Installed programs, OS version & install date, Run keys, NetworkList, ProfileList |
| SYSTEM | `...\config\SYSTEM` | Computer name, time zone, services, **USBSTOR, MountedDevices**, ControlSets |
| NTUSER.DAT | `C:\Users\<user>\NTUSER.DAT` | Per-user: **UserAssist, RecentDocs, RunMRU, TypedPaths, WordWheelQuery, MountPoints2** |
| USRCLASS.DAT | `C:\Users\<user>\AppData\Local\Microsoft\Windows\UsrClass.dat` | **ShellBags (Win 7+)**, MUICache |
| HARDWARE | none — built in RAM at boot | Only from a live system/memory image |

- Collect the **.LOG1/.LOG2 transaction logs** with each hive (unflushed changes). Older hive copies: `config\RegBack` (disabled by default from Win10 1803) and **Volume Shadow Copies**.
- Tools: RegRipper, Registry Explorer (Eric Zimmerman), FTK Registry Viewer.

<div class="fig">
<svg viewBox="0 0 680 230" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="680" height="230" fill="#fff"/>
<rect x="280" y="10" width="120" height="30" fill="#f1f3f4" stroke="#222"/><text x="340" y="30" text-anchor="middle" font-weight="bold">Registry</text>
<rect x="90" y="70" width="180" height="30" fill="#e8f0fe" stroke="#222"/><text x="180" y="90" text-anchor="middle">HKEY_LOCAL_MACHINE</text>
<rect x="410" y="70" width="180" height="30" fill="#e6f4ea" stroke="#222"/><text x="500" y="90" text-anchor="middle">HKEY_USERS\&lt;SID&gt;</text>
<line x1="340" y1="40" x2="180" y2="70" stroke="#222"/>
<line x1="340" y1="40" x2="500" y2="70" stroke="#222"/>
<rect x="10" y="140" width="62" height="30" fill="#e8f0fe" stroke="#222"/><text x="41" y="160" text-anchor="middle">SAM</text>
<rect x="80" y="140" width="85" height="30" fill="#e8f0fe" stroke="#222"/><text x="122" y="160" text-anchor="middle">SECURITY</text>
<rect x="173" y="140" width="85" height="30" fill="#e8f0fe" stroke="#222"/><text x="215" y="160" text-anchor="middle">SOFTWARE</text>
<rect x="266" y="140" width="75" height="30" fill="#e8f0fe" stroke="#222"/><text x="303" y="160" text-anchor="middle">SYSTEM</text>
<line x1="180" y1="100" x2="41" y2="140" stroke="#222"/>
<line x1="180" y1="100" x2="122" y2="140" stroke="#222"/>
<line x1="180" y1="100" x2="215" y2="140" stroke="#222"/>
<line x1="180" y1="100" x2="303" y2="140" stroke="#222"/>
<rect x="380" y="140" width="120" height="30" fill="#e6f4ea" stroke="#222"/><text x="440" y="160" text-anchor="middle">NTUSER.DAT</text>
<rect x="520" y="140" width="140" height="30" fill="#e6f4ea" stroke="#222"/><text x="590" y="160" text-anchor="middle">UsrClass.dat</text>
<line x1="500" y1="100" x2="440" y2="140" stroke="#222"/>
<line x1="500" y1="100" x2="590" y2="140" stroke="#222"/>
<text x="10" y="192" font-size="11">accounts, hashes</text>
<text x="173" y="192" font-size="11">programs, Run keys</text>
<text x="266" y="208" font-size="11">USBSTOR, MountedDevices</text>
<text x="380" y="192" font-size="11">UserAssist, RecentDocs</text>
<text x="520" y="192" font-size="11">ShellBags</text>
<text x="10" y="225" font-size="11">Machine hives: C:\Windows\System32\config\   ·   User hives: C:\Users\&lt;user&gt;\</text>
</svg>
<div class="cap">Fig: Registry hive tree — machine hives under HKLM, per-user hives under HKU</div>
</div>

### Key forensic registry keys
**Importance: 10/10** · named in the likely 15-mark question

In simple words: specific keys prove program execution, file/folder access, USB use and persistence.

| Key | Hive & path | What it proves |
|---|---|---|
| **UserAssist** | NTUSER `Software\Microsoft\Windows\CurrentVersion\Explorer\UserAssist\{GUID}\Count` | GUI programs launched, **run count, last run time**; names **ROT-13 encoded** |
| **ShellBags** | UsrClass.dat `Local Settings\Software\Microsoft\Windows\Shell\BagMRU` (+ Bags) | Folders browsed in Explorer — **even on removed USB/network drives or deleted folders** |
| **RecentDocs** | NTUSER `...\Explorer\RecentDocs` | Recently opened files, sub-keyed by extension, MRUListEx order |
| RunMRU / TypedPaths / WordWheelQuery | NTUSER `...\Explorer\` | Run-box commands / typed Explorer paths / search terms typed |
| **USBSTOR** | SYSTEM `CurrentControlSet\Enum\USBSTOR\Disk&Ven_&Prod_&Rev_\<serial>` | Every USB storage device ever attached: vendor, product, **serial number** |
| **MountedDevices** | SYSTEM `MountedDevices` | Drive letter / Volume GUID ↔ device mapping |
| MountPoints2 | NTUSER `...\Explorer\MountPoints2\{GUID}` | Ties a mounted volume to a **specific user** |
| **Run keys** | SOFTWARE and NTUSER `Microsoft\Windows\CurrentVersion\Run` / `RunOnce` | Programs auto-starting at logon — **malware persistence** |
| Time zone | SYSTEM `CurrentControlSet\Control\TimeZoneInformation` | Needed to interpret every timestamp |
| ComputerName | SYSTEM `CurrentControlSet\Control\ComputerName\ComputerName` | Machine identity |

Note: in an offline hive `CurrentControlSet` does not exist — read `SYSTEM\Select\Current` and use `ControlSet00N`.

Exam tip: USB proof chain = USBSTOR (serial) → `C:\Windows\INF\setupapi.dev.log` (first connect) → MountedDevices (drive letter/GUID) → user's MountPoints2 (which user) → LNK/ShellBags (what was opened).

### Windows Event Logs
**Importance: 9/10** · event-ID table is a sure MCQ and short note

In simple words: Windows records system, security and application events in binary log files.

- Location: **`C:\Windows\System32\winevt\Logs\*.evtx`** (Vista+; XP used `.evt` in `System32\config`). Main logs: **Security, System, Application**, plus many Operational logs (PowerShell, TerminalServices, etc.). View with Event Viewer, `wevtutil`, EvtxECmd.

| Event ID | Log | Meaning |
|---|---|---|
| **4624** | Security | Successful logon (check **Logon Type**) |
| **4625** | Security | Failed logon (brute force pattern) |
| **4634** | Security | Logoff |
| 4648 | Security | Logon with explicit credentials (runas) |
| **4672** | Security | Special (admin) privileges assigned to new logon |
| 4688 | Security | New process created (if auditing on) |
| **4720** | Security | User account created |
| **1102** | Security | **Audit log cleared** — anti-forensic indicator |
| 104 | System | Event log cleared |
| **7045** | System | **New service installed** (malware/PsExec) |
| 6005 / 6006 | System | Event Log service started / stopped (boot / shutdown) |

Logon types (4624): **2** interactive (console), **3** network (share), 4 batch, 5 service, 7 unlock, **10 RemoteInteractive (RDP)**, 11 cached.

### Shortcut (.lnk) files and Jump Lists
**Importance: 9/10** · syllabus phrase "shortcut files"

In simple words: a LNK file is a small pointer to a target file; Windows creates them automatically whenever a user opens a file.

- Auto-created in **`%AppData%\Microsoft\Windows\Recent\`** (`C:\Users\<u>\AppData\Roaming\Microsoft\Windows\Recent`); also Desktop/Start Menu shortcuts.
- Signature: header size **0x4C** + LNK CLSID.
- Contents: **target path (local or network), target's MAC timestamps, file size, volume serial number, volume label, drive type (fixed/removable/network)**, NetBIOS machine name and often the MAC address (tracker block).
- **Value:** proves a file was opened **even after the target is deleted or the USB is removed**; LNK's own created time ≈ first open, modified time ≈ last open.
- **Jump Lists** (Win 7+): per-application recent/pinned items in `%AppData%\Microsoft\Windows\Recent\AutomaticDestinations\*.automaticDestinations-ms` (OLE compound file containing LNK streams + DestList) and `CustomDestinations\*.customDestinations-ms`. File name prefix = **AppID** of the program.
- Tools: LECmd, JLECmd.

### Prefetch
**Importance: 8/10** · evidence of execution

In simple words: Windows caches info about programs it launches to speed up the next start — which proves they ran.

- Location: **`C:\Windows\Prefetch\<EXENAME>-<HASH>.pf`** (hash of path).
- Contains: executable name, **run count, last run time (Win 8+ up to 8 last run times)**, files and directories loaded in the first ~10 s, volume info.
- Proves **execution** even if the program was deleted (e.g. `CCLEANER.EXE-xxxx.pf`, `SDELETE.EXE`). Usually off on Windows Server. Tool: PECmd.

### Executables — PE format and MZ header
**Importance: 7/10** · syllabus word "executables"; malware analysis base

In simple words: Windows programs (.exe, .dll, .sys) use the Portable Executable format.

- **DOS header** starts with **"MZ" (0x4D 0x5A)**; field `e_lfanew` at offset **0x3C** points to the **PE signature "PE\0\0"**.
- Then **COFF header** (machine type, number of sections, **TimeDateStamp = compile time**), **Optional header** (entry point, image base, subsystem), **section table**: `.text` (code), `.data`, `.rdata`, `.rsrc` (resources, icons, version info), `.reloc`.
- Import table lists DLL functions used (e.g. `CreateRemoteThread` → injection hints).
- Forensic use: **file-signature analysis** — a "holiday.jpg" starting with MZ is a disguised executable; hash and compare with known-bad (VirusTotal, NSRL for known-good).

### Alternate Data Streams (ADS)
**Importance: 10/10** · named in 15-mark question; "write a note on ADS"

In simple words: NTFS lets one file carry extra hidden named data streams besides its main content.

- Every file has an unnamed `$DATA` stream; ADS = additional **named $DATA attributes**. Syntax `file:stream`.
- Create: `echo secret > notes.txt:hidden.txt` ; `type evil.exe > notes.txt:evil.exe`.
- **File size shown by Explorer/`dir` ignores ADS**; hash of the main stream is unchanged.
- Detect: **`dir /r`**, PowerShell `Get-Item file -Stream *`, Sysinternals `streams.exe`, any forensic suite (FTK/Autopsy list them).
- **Zone.Identifier:** browsers/Outlook attach `file:Zone.Identifier` with `[ZoneTransfer] ZoneId=3` (**3 = Internet**) and often HostUrl/ReferrerUrl → **"Mark of the Web" proves a file was downloaded**.
- Legit uses: Zone.Identifier, file-server Macintosh compatibility, thumbnail info.
- ADS exists **only on NTFS** — lost when copied to FAT32/exFAT or uploaded.

### Hidden files and attributes
**Importance: 6/10** · syllabus phrase; short

In simple words: files can be hidden by attribute, by location or by disguise.

- Attributes: **Hidden (H)**, **System (S)**, Read-only, Archive; set with `attrib +h +s file`; list with `attrib` or `dir /a`.
- Other hiding methods: ADS, **renamed extensions** (signature mismatch), slack space, unallocated space, HPA/DCO, encrypted containers, steganography, `$Recycle.Bin`, deep paths.
- Forensic tools ignore the Hidden attribute — they show everything; signature analysis catches renamed files.

### Slack space — RAM slack vs file (drive) slack
**Importance: 10/10** · guaranteed concept; needs a diagram

In simple words: files are stored in whole clusters, so the unused tail of the last cluster ("slack") can hold leftovers of older deleted files.

- **RAM slack:** from the end of the file's data to the end of **that sector**. Old OSes (DOS/Win 95) padded it with whatever was in RAM — hence the name; modern Windows pads with **zeros**.
- **File slack / drive slack:** the remaining **whole unused sectors** of the last cluster — **not overwritten**, so they retain data of previously deleted files.
- **Volume slack:** space between the end of the file system and the end of the partition; **partition/disk slack:** unpartitioned space.
- **Worked example:** cluster = 8 sectors × 512 B = 4096 B; file = 1300 B → uses sectors 1–3 (1536 B). RAM slack = 1536 − 1300 = **236 B**; drive slack = 5 sectors = **2560 B**; total slack = 4096 − 1300 = **2796 B**.
- Can be extracted and keyword-searched / carved (EnCase, FTK, Autopsy, `blkls -s` in Sleuth Kit).

<div class="fig">
<svg viewBox="0 0 680 170" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="680" height="170" fill="#fff"/>
<text x="340" y="18" text-anchor="middle" font-weight="bold">One cluster = 8 sectors × 512 B = 4096 B (file size 1300 B)</text>
<rect x="20" y="40" width="80" height="50" fill="#e6f4ea" stroke="#222"/>
<rect x="100" y="40" width="80" height="50" fill="#e6f4ea" stroke="#222"/>
<rect x="180" y="40" width="43" height="50" fill="#e6f4ea" stroke="#222"/>
<rect x="223" y="40" width="37" height="50" fill="#fef7e0" stroke="#222"/>
<rect x="260" y="40" width="80" height="50" fill="#fce8e6" stroke="#222"/>
<rect x="340" y="40" width="80" height="50" fill="#fce8e6" stroke="#222"/>
<rect x="420" y="40" width="80" height="50" fill="#fce8e6" stroke="#222"/>
<rect x="500" y="40" width="80" height="50" fill="#fce8e6" stroke="#222"/>
<rect x="580" y="40" width="80" height="50" fill="#fce8e6" stroke="#222"/>
<text x="60" y="70" text-anchor="middle">S1 data</text>
<text x="140" y="70" text-anchor="middle">S2 data</text>
<text x="201" y="70" text-anchor="middle">S3</text>
<text x="460" y="70" text-anchor="middle">S4–S8 old data</text>
<line x1="20" y1="105" x2="223" y2="105" stroke="#222"/><text x="121" y="122" text-anchor="middle">File data 1300 B</text>
<line x1="223" y1="105" x2="260" y2="105" stroke="#222"/><text x="241" y="140" text-anchor="middle">RAM slack 236 B</text>
<line x1="260" y1="105" x2="660" y2="105" stroke="#222"/><text x="460" y="122" text-anchor="middle">File / drive slack = 5 sectors = 2560 B</text>
<text x="340" y="162" text-anchor="middle">Total slack = 4096 − 1300 = 2796 B; drive slack may hold fragments of deleted files</text>
</svg>
<div class="cap">Fig: Slack space inside the last cluster of a file</div>
</div>

### Recycle Bin ($I / $R)
**Importance: 8/10** · frequent short note

In simple words: "Delete" in Explorer only moves the file to a hidden folder and records where it came from.

- Vista+: **`C:\$Recycle.Bin\<SID>\`** — the SID folder ties deleted files to a **user**.
- Each deleted item → **`$R<random>.ext`** = the actual content; **`$I<random>.ext`** = metadata: **original path, original size, deletion date/time**. Same random part pairs them.
- XP: `C:\RECYCLER\<SID>\` with a single **INFO2** index file and files renamed `Dc1.ext`, etc.
- Emptying the bin deletes $I/$R entries in the MFT, but data may remain recoverable from unallocated space (HDD). Shift+Delete bypasses the bin. Tool: RBCmd.

### Volume Shadow Copies, pagefile and hiberfil
**Importance: 7/10** · "hidden evidence sources" answers

In simple words: Windows keeps snapshots of the disk and dumps of memory on disk — both hold older or volatile data.

- **Volume Shadow Copies (VSS):** block-level snapshots stored in `\System Volume Information\`, created by System Restore/Windows Backup. Contain **older versions of files and registry hives**, deleted files. List: `vssadmin list shadows`; mount and examine read-only. **`vssadmin delete shadows /all /quiet`** in logs = ransomware/anti-forensics.
- **pagefile.sys** (`C:\pagefile.sys`): virtual-memory swap — fragments of RAM: passwords, chats, URLs, decrypted text. Can be wiped at shutdown (`ClearPageFileAtShutdown`).
- **hiberfil.sys** (`C:\hiberfil.sys`): **compressed copy of RAM** written at hibernation (and Fast Startup) — a "free" memory image from a powered-off machine; analyse with Volatility after decompression.
- **swapfile.sys** (Win 8+): swap for modern/Store apps.

### Linux — file system hierarchy
**Importance: 7/10** · syllabus; MCQ favourite

In simple words: Linux has one tree starting at `/`; every directory has a standard purpose (FHS).

| Dir | Contents | Forensic value |
|---|---|---|
| `/etc` | System configuration | passwd, shadow, group, hosts, crontab, ssh config |
| `/home/<user>` | User files | dotfiles, bash_history, downloads, browser profiles |
| `/root` | root's home | Attacker activity as root |
| `/var/log` | Logs | auth, syslog, wtmp |
| `/tmp`, `/var/tmp`, `/dev/shm` | Temporary | Malware staging (world-writable) |
| `/bin`, `/sbin`, `/usr` | Programs | Trojanised binaries (compare hashes) |
| `/boot` | Kernel, GRUB | Bootkits |
| `/proc`, `/sys` | Virtual, in RAM | Live processes only — volatile |
| `/dev` | Device files | `/dev/sda` (disk) |
| `/media`, `/mnt` | Mount points | Evidence of external media |
| `/opt`, `/lib` | Add-on software, libraries | Rootkit libraries (`/etc/ld.so.preload`) |

- Files are described by **inodes** (owner, permissions, size, MAC times + ctime, block pointers; **no file name** — names live in directory entries).

### Linux ownership and permissions (chmod worked example)
**Importance: 8/10** · numerical-style question; "explain rwx with example"

In simple words: every file has an owner, a group and three permission sets — user, group, others.

- `ls -l` → `-rwxr-xr-- 1 alice staff 2048 Oct 12 10:00 run.sh`. First char: `-` file, `d` dir, `l` link.
- Values: **r = 4, w = 2, x = 1**. For directories: r = list, w = create/delete, x = enter.
- **Worked example — `chmod 754 run.sh`:** 7 = 4+2+1 = **rwx** (owner) · 5 = 4+1 = **r-x** (group) · 4 = **r--** (others) → `-rwxr-xr--`.
- Symbolic: `chmod u+x,g-w,o=r file`. Ownership: `chown alice:staff file`.
- Special bits: **SUID (4000)** run as file owner (`s` in user x), **SGID (2000)**, **sticky (1000)** (`t` on `/tmp`).
- Forensic note: unexpected **SUID-root** binaries (`find / -perm -4000`) = privilege-escalation backdoor; umask sets defaults (022 → files 644).

### Linux hidden dotfiles
**Importance: 6/10** · short note

In simple words: any name beginning with `.` is hidden from plain `ls`; `ls -a` shows it.

- Key dotfiles: `~/.bash_history`, `~/.bashrc`/`.profile` (persistence by adding commands), `~/.ssh/authorized_keys` (attacker backdoor key), `~/.ssh/known_hosts` (hosts the user connected to), `~/.viminfo`, `~/.mozilla/`, `~/.config/`, `~/.local/share/recently-used.xbel` (GNOME recent files), `~/.local/share/Trash/`.
- Attackers hide tools in directories like `...` or `. ` (dot-space).

### Linux user accounts — /etc/passwd and /etc/shadow
**Importance: 9/10** · field-by-field question is very likely

In simple words: `/etc/passwd` lists accounts (world-readable); `/etc/shadow` holds password hashes (root only).

**/etc/passwd — 7 fields:** `alice:x:1001:1001:Alice Rao:/home/alice:/bin/bash`

| # | Field | Note |
|---|---|---|
| 1 | Username | |
| 2 | Password | `x` = hash is in /etc/shadow |
| 3 | UID | **0 = root**; extra UID-0 account = backdoor |
| 4 | GID | Primary group |
| 5 | GECOS | Full name/comment |
| 6 | Home directory | |
| 7 | Login shell | `/usr/sbin/nologin` for service accounts |

**/etc/shadow — 9 fields:** `alice:$6$salt$hash:20000:0:99999:7:::`

| # | Field |
|---|---|
| 1 | Username |
| 2 | Hashed password (`$1$` MD5, `$5$` SHA-256, `$6$` SHA-512, `$y$` yescrypt; `!` or `*` = locked) |
| 3 | Last password change (days since 1 Jan 1970) |
| 4 | Min days between changes |
| 5 | Max days valid |
| 6 | Warning days |
| 7 | Inactive days after expiry |
| 8 | Account expiry date (days since epoch) |
| 9 | Reserved |

Also `/etc/group` (4 fields: name:password:GID:members) and `/etc/sudoers` (who can sudo).

### Linux logs
**Importance: 9/10** · wtmp/btmp/lastlog swap is a classic MCQ

In simple words: Linux logs live in `/var/log`, mostly plain text, some binary.

| Log | Type | Records | Read with |
|---|---|---|---|
| `/var/log/auth.log` (Debian/Ubuntu) / `/var/log/secure` (RHEL/CentOS) | Text | Logins, **SSH success/failure**, sudo, su | `less`, `grep` |
| `/var/log/syslog` (Debian) / `/var/log/messages` (RHEL) | Text | General system messages, USB attach | `less` |
| `/var/log/kern.log` | Text | Kernel messages (USB devices) | |
| **`/var/log/wtmp`** | Binary | All **successful** logins/logouts, reboots | **`last`** |
| **`/var/log/btmp`** | Binary | **Failed** logins | **`lastb`** |
| **`/var/log/lastlog`** | Binary | **Last login of each user** | **`lastlog`** |
| `/var/run/utmp` | Binary | **Currently** logged-in users | `who`, `w` |
| systemd journal (`/var/log/journal/`) | Binary | Everything | `journalctl` |
| `~/.bash_history` | Text | Commands typed by the user | `cat` |

- **bash_history:** written at shell exit; no timestamps unless `HISTTIMEFORMAT` set. Anti-forensic signs: file empty, linked to `/dev/null`, `unset HISTFILE`, `history -c`.
- Log tampering signs: gaps in time, truncated files, missing rotations (`.1`, `.gz`).

### Mac OS X — startup, launchd and services
**Importance: 8/10** · syllabus phrase "startup, services"

In simple words: on macOS, **launchd (PID 1)** starts everything, using plist files that describe each job.

| Path | Runs as | When |
|---|---|---|
| `/System/Library/LaunchDaemons/` | root | Apple system daemons |
| **`/Library/LaunchDaemons/`** | **root**, at boot | Third-party — **malware persistence** |
| `/Library/LaunchAgents/` | logged-in user, any user | Third-party per-login agents |
| **`~/Library/LaunchAgents/`** | that user, at login | **Per-user malware persistence** |
| `/Library/StartupItems` | root | Legacy (deprecated) |

- **Daemon** = background, no GUI, runs without login; **Agent** = runs in a user session.
- Plist keys: `Label`, `ProgramArguments`, `RunAtLoad`, `KeepAlive`, `StartInterval`.
- **Plists** = XML or **binary ("bplist00" magic)**; convert with `plutil -convert xml1 file.plist`. Services control: `launchctl list`.
- Boot outline: firmware (EFI / Apple Silicon iBoot) → `boot.efi` → XNU kernel → launchd → loginwindow.

### Mac OS X — network configuration
**Importance: 6/10** · syllabus phrase

In simple words: macOS keeps network settings in system plists.

- `/Library/Preferences/SystemConfiguration/preferences.plist` — interfaces, DNS, proxies, computer name.
- Wi-Fi known networks (SSIDs, last-joined times): `/Library/Preferences/SystemConfiguration/com.apple.airport.preferences.plist` (older) / `com.apple.wifi.known-networks.plist` (newer) — locates the Mac over time.
- DHCP leases: `/private/var/db/dhcpclient/leases/`; firewall: `/Library/Preferences/com.apple.alf.plist`; Wi-Fi passwords in the **System keychain**.

### Mac OS X — hidden directories
**Importance: 7/10** · MCQ (do not swap .fseventsd and .Spotlight-V100)

| Item | Meaning |
|---|---|
| **`.Trashes`** (per volume) / `~/.Trash` (user) | macOS Trash — deleted-but-not-emptied files |
| **`.fseventsd`** | **File-system events journal** — records create/modify/rename/delete of paths, **also on USB volumes** |
| **`.Spotlight-V100`** | **Spotlight metadata index** — names, paths, metadata; may retain entries of deleted files |
| `.DS_Store` | Finder view settings per folder — proves folder was opened and lists its file names |
| `.DocumentRevisions-V100` | Saved earlier versions of documents |
| `._file` (AppleDouble) | Mac metadata left on FAT/exFAT USB drives — shows a Mac touched the drive |

- Hidden also via `chflags hidden`; Finder shortcut ⌘⇧. shows hidden files.

### Mac OS X — system logs and user artifacts
**Importance: 8/10** · syllabus phrase "system logs, user artifacts"

In simple words: macOS logs to a binary unified log; per-user evidence sits in `~/Library` SQLite databases and plists.

- **Unified Logging** (macOS 10.12 Sierra+): `/private/var/db/diagnostics/*.tracev3` + `/private/var/db/uuidtext/`; read with `log show` / `log collect`; short retention.
- **ASL** (Apple System Log, older): `/private/var/log/asl/*.asl`; text logs `/private/var/log/system.log`, **`install.log`** (software installs with times).

| User artifact | Location | Value |
|---|---|---|
| `~/Library` | User home (hidden in Finder) | Preferences, caches, app data — main store |
| **Recent items** | `~/Library/Application Support/com.apple.sharedfilelist/*.sfl2` | Recent documents, apps, servers, **volumes** |
| **Safari** | `~/Library/Safari/History.db` (SQLite), `Downloads.plist`, `Bookmarks.plist` | Browsing and downloads |
| **KnowledgeC** | `~/Library/Application Support/Knowledge/knowledgeC.db` (user) and `/private/var/db/CoreDuet/Knowledge/knowledgeC.db` | App usage, screen/device activity timeline (pattern of life) |
| **Quarantine events** | `~/Library/Preferences/com.apple.LaunchServices.QuarantineEventsV2` (SQLite) | Every downloaded file with **URL and time** |
| `com.apple.quarantine` xattr | On the downloaded file | macOS "Mark of the Web" (≈ Zone.Identifier) |
| Keychain | `~/Library/Keychains/login.keychain-db` | Stored passwords (needs login password) |
| Messages | `~/Library/Messages/chat.db` | iMessage/SMS |
| Shell history | `~/.zsh_history` (default since Catalina), `~/.bash_history` | Commands |
| User accounts | `/private/var/db/dslocal/nodes/Default/users/*.plist` | ≈ /etc/passwd + shadow |

### Likely questions with model answers

**Q. Explain the booting process of a computer. What is its forensic relevance?** *(5 marks · Likelihood 9/10)*

Booting is the sequence that loads the operating system after power-on. In a **BIOS** system: (1) power on — CPU runs BIOS firmware from ROM; (2) **POST** tests CPU, RAM and devices; (3) BIOS reads the boot order from **CMOS**; (4) it loads **sector 0, the MBR** (446 B boot code, 64 B partition table, 0x55AA signature); (5) MBR code loads the active partition's **VBR**; (6) VBR starts the **boot loader** (bootmgr/winload.exe or GRUB); (7) the loader starts the **kernel**, which launches init/systemd or smss/winlogon. In **UEFI** systems the firmware reads the **GPT**, opens the **EFI System Partition** and runs `bootmgfw.efi`, with **Secure Boot** verifying signatures. **Forensic relevance:** the suspect disk must never be booted (it alters timestamps and logs and may trigger wiping); the examiner records the CMOS clock against real time and sets the boot order to a forensic boot medium; boot-sector malware (bootkits) hides in the MBR/VBR.

**Q. How do SSDs affect digital forensic investigation? Explain TRIM and wear levelling.** *(5 marks · Likelihood 8/10)*

SSDs store data in NAND flash, written in pages but erased in whole blocks, under a controller with a **Flash Translation Layer** mapping logical to physical addresses. **Wear levelling** spreads writes evenly across cells so they wear out uniformly; old copies of data move to locations not reachable through the normal interface. **TRIM** is a command by which the OS tells the SSD which blocks belong to deleted files; the controller's **garbage collection** then erases them in the background. Forensic impact: (1) deleted files are usually unrecoverable — reads of trimmed blocks return zeros, so carving finds little; (2) garbage collection can run whenever the drive is powered, even behind a write-blocker, so **two acquisitions may produce different hashes** — this must be documented; (3) slack and unallocated analysis yields less. Countermeasures: image immediately, keep power-on time short, record TRIM status, use chip-off or vendor tools in advanced labs. HDDs, by contrast, keep deleted data until it is overwritten.

**Q. Differentiate between MBR and GPT.** *(5 marks · Likelihood 7/10)*

MBR (Master Boot Record) is the legacy partitioning scheme used with BIOS; GPT (GUID Partition Table) is the modern scheme used with UEFI. MBR lives in **sector 0 only** (446 B boot code, 64 B table of four 16-byte entries, 0x55AA signature), allows **4 primary partitions** (or 3 + one extended) and uses 32-bit LBA, limiting disks to **2 TiB** with 512-byte sectors. It has no checksum and no backup, so a damaged sector 0 loses the partition map. GPT keeps a **protective MBR at LBA 0**, the **GPT header at LBA 1** and partition entries after it, plus a **backup header and table at the end of the disk**. It supports 128 partitions by default, 64-bit LBA (~9.4 ZB), **CRC32** integrity checks and **GUIDs** for the disk and each partition. Forensically, GPT's backup helps reconstruct a wiped table, and in both schemes gaps between partitions can conceal data.

**Q. Write a note on Alternate Data Streams.** *(5 marks · Likelihood 9/10)*

An Alternate Data Stream is an extra **named $DATA attribute** attached to a file or folder on **NTFS**. Every file has an unnamed main stream; additional streams are addressed as `file:stream`, e.g. `type evil.exe > notes.txt:evil.exe`. Windows Explorer and `dir` show only the main stream's size, and the file's hash is unchanged, so an ADS can hide data or malware inside an innocent file. Legitimate use: browsers add a **`Zone.Identifier`** stream with `ZoneId=3` (Internet) and often the source URL — this "Mark of the Web" proves a file was downloaded. Detection: `dir /r`, PowerShell `Get-Item -Stream *`, Sysinternals `streams`, and forensic suites which list all streams. ADS exist only on NTFS and are stripped when the file is copied to FAT32/exFAT or uploaded. In a report, the examiner lists each stream found, its size, hash and content type.

**Q. Explain the fields of /etc/passwd and /etc/shadow.** *(5 marks · Likelihood 8/10)*

`/etc/passwd` is world-readable and has **seven** colon-separated fields, e.g. `alice:x:1001:1001:Alice:/home/alice:/bin/bash`: username, password placeholder (`x` = stored in shadow), **UID** (0 = root), primary GID, GECOS comment (full name), home directory and login shell. `/etc/shadow` is readable only by root and has **nine** fields: username, **hashed password** (`$6$` = SHA-512, `$5$` SHA-256, `$1$` MD5, `$y$` yescrypt; `!`/`*` = locked), date of last change (days since 1 Jan 1970), minimum days, maximum days, warning days, inactivity days, account-expiry date and a reserved field. Forensic points: an unexpected **second UID-0 account** or a service account with a real shell indicates a backdoor; the last-change date dates a password change; hashes can be tested against wordlists with lawful authority.

**Q. Explain Linux file permissions with the example chmod 754.** *(5 marks · Likelihood 7/10)*

Each Linux file has an owner, a group and three permission sets — **user, group, others** — each made of read (r = 4), write (w = 2) and execute (x = 1). `ls -l` shows them as a 10-character string, e.g. `-rwxr-xr--`, where the first character is the type (`-` file, `d` directory, `l` link). Octal digits are the sum of the bits: in **`chmod 754 run.sh`**, 7 = 4+2+1 = rwx for the owner, 5 = 4+1 = r-x for the group, 4 = r-- for others, giving `-rwxr-xr--`. For directories, r lists contents, w creates/deletes entries and x allows entry. Ownership is changed with `chown user:group`. Special bits are SUID (4000), SGID (2000) and sticky (1000, used on `/tmp`). Forensically, unexpected SUID-root binaries or world-writable system files point to compromise; `find / -perm -4000` lists them.

**Q. Explain slack space. Differentiate RAM slack and file slack with an example.** *(10 marks · Likelihood 9/10)*

File systems allocate storage in **clusters** (groups of sectors), not bytes. A file rarely fills its last cluster exactly, so the unused remainder — **slack space** — exists at the end of almost every file. Because the file system does not clear it, slack often contains fragments of earlier deleted files, making it a valuable evidence source and also a hiding place.

**RAM slack** is the area from the end of the file's actual data to the end of the **sector** that contains it. Older systems (DOS, Windows 95) filled it with whatever happened to be in memory, so it could leak passwords or document text — hence "RAM" slack. Modern Windows fills it with zeros.

**File slack (drive slack)** is the set of **whole unused sectors** after that sector up to the end of the cluster. The OS never writes to them, so they keep whatever data a previously deleted file left there.

Example: cluster = 8 sectors × 512 B = 4096 B; file size = 1300 B. The file occupies 3 sectors (1536 B). RAM slack = 1536 − 1300 = 236 B. File slack = 5 sectors = 2560 B. Total slack = 4096 − 1300 = 2796 B.

| Point | RAM slack | File / drive slack |
|---|---|---|
| Extent | End of data → end of sector | Remaining sectors → end of cluster |
| Content | RAM contents (old OS) / zeros (modern) | Remnants of older deleted files |
| Size | < 1 sector | 0 to (sectors per cluster − 1) sectors |

Related areas: **volume slack** (end of file system to end of partition), **partition/disk slack** (unpartitioned space) and **unallocated clusters**. Examiners use EnCase, FTK, Autopsy/Sleuth Kit (`blkls -s`) to extract slack, then keyword-search and carve it. Suspects may deliberately hide data in slack with special tools; wiping tools may clean it. Because slack is outside the file system, its content is reported as "fragments" and cannot by itself be tied to a file name or date — it must be corroborated (see Fig: slack space).

**Q. Discuss the forensic value of the Windows Registry. Name the hives and important keys.** *(10 marks · Likelihood 9/10)*

The Registry is Windows' hierarchical configuration database of **keys, subkeys and values**; every key has a **LastWrite time**, so it acts as a hidden activity log. It is stored in hive files: **SAM, SECURITY, SOFTWARE, SYSTEM** in `C:\Windows\System32\config\` and per-user **NTUSER.DAT** (`C:\Users\<u>\`) and **UsrClass.dat** (`AppData\Local\Microsoft\Windows\`). Hives are locked on a live system and are acquired from an image (with their `.LOG1/.LOG2` files) or via FTK Imager; older copies come from Volume Shadow Copies.

Forensic value:
1. **System profile** — computer name, OS version and install date (SOFTWARE `Windows NT\CurrentVersion`), **time zone** (SYSTEM `TimeZoneInformation`) for correct timestamps, last shutdown.
2. **User accounts** — SAM: usernames, RIDs, last logon, logon counts, password-change times.
3. **USB history** — SYSTEM `Enum\USBSTOR` lists each storage device's vendor, product and **serial number**; `MountedDevices` maps it to a drive letter/volume GUID; NTUSER `MountPoints2` attributes it to a user; `setupapi.dev.log` gives first connection.
4. **Program execution** — NTUSER **UserAssist** (ROT-13 names, run count, last run); MUICache.
5. **File and folder access** — **RecentDocs**, OpenSavePidlMRU, TypedPaths, RunMRU, **WordWheelQuery** (search terms); **ShellBags** in UsrClass.dat prove folders were browsed even on removed drives.
6. **Persistence / malware** — **Run/RunOnce** keys in SOFTWARE and NTUSER, Services, Winlogon Shell/Userinit.
7. **Networks** — SOFTWARE `NetworkList` profiles (SSIDs, first/last connected), mapped drives.

Tools: RegRipper, Registry Explorer, FTK Registry Viewer. Deleted keys can be recovered from unallocated hive cells. Findings should be corroborated with event logs, LNK files and prefetch.

**Q. Describe Linux system artifacts of forensic importance.** *(10 marks · Likelihood 7/10)*

1. **File system hierarchy:** evidence concentrates in `/etc` (configuration), `/home` and `/root` (user data), `/var/log` (logs), `/tmp`, `/var/tmp`, `/dev/shm` (malware staging) and `/boot`. `/proc` and `/sys` exist only in RAM and must be captured live. Metadata is in **inodes** (owner, permissions, size, atime/mtime/ctime and crtime on ext4).
2. **User accounts:** `/etc/passwd` (7 fields: user, x, UID, GID, GECOS, home, shell), `/etc/shadow` (9 fields incl. SHA-512 hash and last-change date), `/etc/group`, `/etc/sudoers`. Extra UID-0 users or new sudoers are backdoors.
3. **Permissions:** rwx bits (r4 w2 x1), e.g. `chmod 754` = `rwxr-xr--`; SUID/SGID/sticky bits; unexpected SUID-root files show privilege escalation.
4. **Logs:** `/var/log/auth.log` or `secure` (SSH, sudo, su), `syslog`/`messages`, `kern.log` (USB), binary **wtmp** (`last`, successful logins), **btmp** (`lastb`, failed), **lastlog** (last login per user), utmp (`who`), the systemd journal (`journalctl`).
5. **Shell history:** `~/.bash_history` shows commands; empty or `/dev/null`-linked history signals anti-forensics.
6. **Hidden dotfiles:** `.ssh/authorized_keys` (attacker keys), `.ssh/known_hosts`, `.bashrc` (persistence), `.local/share/Trash`, `recently-used.xbel`.
7. **Scheduled tasks:** `/etc/crontab`, `/var/spool/cron/`, systemd timers — persistence.
These artifacts together give a timeline of logins, commands and file changes.

**Q. Explain Windows system artifacts of forensic value: registry, event logs, LNK files, ADS and slack space.** *(15 marks · Likelihood 9/10)*

Windows automatically records user and system activity in many places. An examiner works on a write-blocked forensic image and correlates these artifacts to answer who did what, when.

**1. Registry.** A hierarchical database of keys and values with LastWrite times. Hives: SAM, SECURITY, SOFTWARE, SYSTEM (`C:\Windows\System32\config\`), NTUSER.DAT and UsrClass.dat (per user). Key evidence:
- **UserAssist** (NTUSER) — GUI programs run, run count, last time (ROT-13 encoded).
- **RecentDocs, RunMRU, TypedPaths, WordWheelQuery** — files opened, commands and searches.
- **ShellBags** (UsrClass.dat) — folders browsed, even on removed media.
- **USBSTOR** (SYSTEM) — every USB storage device with serial number; **MountedDevices** gives drive letter; MountPoints2 links to user.
- **Run/RunOnce keys** — autostart persistence of malware.
- SYSTEM TimeZoneInformation — needed to read all timestamps correctly.

**2. Event logs.** Stored as `.evtx` in `C:\Windows\System32\winevt\Logs\` (Security, System, Application). Important IDs: **4624** successful logon (logon type 2 console, 3 network, 10 RDP), **4625** failed logon, **4634** logoff, **4672** admin privileges assigned, **4720** user account created, **1102** security log cleared (anti-forensics), **7045** new service installed. They build a timeline of logons, brute-force attempts and intrusions.

**3. LNK (shortcut) files and Jump Lists.** Created automatically in `%AppData%\Microsoft\Windows\Recent\` when a file is opened. Each holds the target's full path, size and MAC times, the **volume serial number, label and drive type**, and the machine name. They prove a file was opened even after it is deleted or the USB drive is gone. Jump Lists (AutomaticDestinations) keep per-application recent files.

**4. Alternate Data Streams.** NTFS allows extra named $DATA streams (`file:stream`) that do not change the displayed size or main-stream hash, so data or executables can be hidden. Detect with `dir /r` or `Get-Item -Stream *`. The **Zone.Identifier** stream (ZoneId=3) proves a file was downloaded from the Internet.

**5. Slack space.** Files occupy whole clusters; the unused end of the last cluster is slack. **RAM slack** (end of data to end of sector) — zero-filled on modern Windows; **file/drive slack** (remaining sectors of the cluster) keeps fragments of previously deleted files. Example: 4096-B cluster, 1300-B file → 236 B RAM slack + 2560 B drive slack. Examined by keyword search and carving.

**Supporting artifacts:** **Prefetch** (`C:\Windows\Prefetch\*.pf`) proves execution with run count and times; **Recycle Bin** `$Recycle.Bin\<SID>\` $I (original path, deletion time) and $R (content); **Volume Shadow Copies** keep earlier file and registry versions; **pagefile.sys/hiberfil.sys** hold RAM fragments; the **MFT** ($SI vs $FN times) reveals timestomping; the PE "MZ" header exposes disguised executables.

**Correlation example:** USBSTOR shows a pen drive (serial X) first connected at 10:02; MountPoints2 links it to user "ravi"; a LNK file for `E:\salary.xlsx` with the same volume serial was created at 10:05; ShellBags show `E:\HR` was browsed; event 4624 (type 2) shows ravi logged on at 09:58. Together these prove, with timestamps corrected for the registry time zone, that ravi copied/opened the file from that drive.

Conclusion: no single artifact is conclusive; the examiner documents each artifact's path, hash and parsed value, corroborates across sources, preserves chain of custody and reports findings objectively.

## Unit 6 — Logic, Digital Circuits & Number Representation

### 6.1 Propositional Logic and Connectives
**Importance: 7/10** · syllabus phrase "propositional logic"; quick 5-mark or MCQ

In simple words: a proposition is a statement that is either true or false; connectives join propositions.

| p | q | ¬p | p ∧ q | p ∨ q | p → q | p ↔ q | p ⊕ q |
|---|---|---|---|---|---|---|---|
| T | T | F | T | T | T | T | F |
| T | F | F | F | T | F | F | T |
| F | T | T | F | T | T | F | T |
| F | F | T | F | F | T | T | F |

- **p → q is false only when p = T and q = F.** p → q ≡ ¬p ∨ q ≡ ¬q → ¬p (contrapositive).
- Converse q → p and inverse ¬p → ¬q are *not* equivalent to p → q.
- "Kohima is in Nagaland" is a proposition; "Close the door" and "x > 5" (x unknown) are not.

### 6.2 Predicate Logic, Quantifiers and WFF
**Importance: 6/10** · syllabus phrase; definitions-level questions

In simple words: predicate logic adds variables, predicates and "for all / there exists" to propositional logic.

- **Predicate** P(x): a statement with a variable, e.g. P(x): "x is a suspect". Becomes a proposition when x is fixed or quantified.
- **Universal quantifier** ∀x P(x): true if P(x) holds for every x in the domain.
- **Existential quantifier** ∃x P(x): true if P(x) holds for at least one x.
- **Negation rules:** ¬∀x P(x) ≡ ∃x ¬P(x) ; ¬∃x P(x) ≡ ∀x ¬P(x).
- Example: "Every student passed" = ∀x (Student(x) → Passed(x)); "Some student passed" = ∃x (Student(x) ∧ Passed(x)).
- **Well-formed formula (WFF):** built by rules — (1) every atom/predicate is a WFF; (2) if A, B are WFFs, so are ¬A, (A ∧ B), (A ∨ B), (A → B), (A ↔ B); (3) if A is a WFF, ∀x A and ∃x A are WFFs; (4) nothing else. e.g. (p ∧ q) → r is a WFF; p ∧ ∨ q is not.

### 6.3 Tautology, Contradiction, Satisfiable
**Importance: 7/10** · classic MCQ + 5-mark "define with examples"

| Term | Meaning | Example |
|---|---|---|
| Tautology (valid) | true for every assignment | p ∨ ¬p ; (p ∧ q) → p |
| Contradiction (unsatisfiable) | false for every assignment | p ∧ ¬p |
| Contingency | sometimes true, sometimes false | p → q |
| Satisfiable | true for at least one assignment | p ∧ q (true when both T) |

- Every tautology is satisfiable; a formula is a tautology iff its negation is a contradiction.
- Check by truth table: e.g. ((p → q) ∧ p) → q (modus ponens) is a tautology — all four rows give T.

### 6.4 Logic Gates (incl. Universal Gates)
**Importance: 8/10** · guaranteed MCQ; often a 5-mark "explain universal gates"

| Gate | Expression | Output 1 when |
|---|---|---|
| AND | Y = A·B | all inputs 1 |
| OR | Y = A + B | any input 1 |
| NOT | Y = A' | input 0 |
| NAND | Y = (A·B)' | any input 0 |
| NOR | Y = (A + B)' | all inputs 0 |
| XOR | Y = A ⊕ B = A'B + AB' | inputs differ (odd number of 1s) |
| XNOR | Y = (A ⊕ B)' | inputs equal |

- **Universal gates: NAND and NOR** — any Boolean function can be built from only NANDs (or only NORs).
- From NAND: NOT A = (A·A)'; AND = NOT(NAND); OR = (A'·B')' (NAND of inverted inputs).
- From NOR: NOT A = (A+A)'; OR = NOT(NOR); AND = (A' + B')'.
- Exam tip: XOR needs 4 NAND gates; XNOR needs 4 NOR gates.

### 6.5 Boolean Laws and De Morgan's Theorem
**Importance: 7/10** · simplification MCQs

| Law | AND form | OR form |
|---|---|---|
| Identity | A·1 = A | A + 0 = A |
| Null | A·0 = 0 | A + 1 = 1 |
| Idempotent | A·A = A | A + A = A |
| Complement | A·A' = 0 | A + A' = 1 |
| Commutative | AB = BA | A + B = B + A |
| Distributive | A(B + C) = AB + AC | A + BC = (A + B)(A + C) |
| Absorption | A(A + B) = A | A + AB = A |
| De Morgan | (AB)' = A' + B' | (A + B)' = A'B' |

- Useful: A + A'B = A + B ; involution (A')' = A ; consensus AB + A'C + BC = AB + A'C.
- **Duality:** swap · ↔ + and 0 ↔ 1 to get the dual of any identity.

### 6.6 Karnaugh Map Simplification (worked 4-variable)
**Importance: 8/10** · standard 5/10-mark numerical

In simple words: a K-map arranges minterms in Gray-code order so adjacent cells differ by one variable; group 1s in blocks of 1, 2, 4, 8, 16.

**Simplify F(A,B,C,D) = Σm(0, 1, 2, 5, 8, 9, 10).**

| AB \ CD | 00 | 01 | 11 | 10 |
|---|---|---|---|---|
| 00 | 1 (m0) | 1 (m1) | 0 (m3) | 1 (m2) |
| 01 | 0 (m4) | 1 (m5) | 0 (m7) | 0 (m6) |
| 11 | 0 (m12) | 0 (m13) | 0 (m15) | 0 (m14) |
| 10 | 1 (m8) | 1 (m9) | 0 (m11) | 1 (m10) |

- Quad m0, m1, m8, m9 (rows 00 & 10, cols 00 & 01) → **B'C'**.
- Quad m0, m2, m8, m10 (four corners) → **B'D'**.
- Pair m1, m5 (col 01, rows 00 & 01) → **A'C'D**.
- **F = B'C' + B'D' + A'C'D** (verified by evaluating all 16 input combinations with python3).
- Rules: groups must be powers of 2, rectangular, may wrap around edges; make groups as large as possible and as few as possible; don't-cares (X) may be used as 1 when helpful.

### 6.7 Combinational Circuits — Adders, MUX, Decoder, Encoder
**Importance: 8/10** · "explain with diagram" 5/10-mark; adder expressions are MCQ staples

In simple words: output depends only on the present inputs — no memory.

- **Half adder:** Sum S = A ⊕ B ; Carry C = A·B. (1 XOR + 1 AND.)
- **Full adder** (inputs A, B, Cin): S = A ⊕ B ⊕ Cin ; Cout = AB + Cin(A ⊕ B) = AB + BCin + ACin. Built from 2 half adders + 1 OR gate.
- **Multiplexer (2ⁿ:1):** selects one of 2ⁿ inputs using n select lines. 4:1 MUX: Y = S1'S0'I0 + S1'S0 I1 + S1 S0' I2 + S1 S0 I3. A MUX is a "universal" function generator.
- **Demultiplexer (1:2ⁿ):** routes one input to one of 2ⁿ outputs.
- **Decoder (n:2ⁿ):** activates exactly one of 2ⁿ outputs for each input code (e.g. 3:8 decoder; used for memory address decoding).
- **Encoder (2ⁿ:n):** reverse of decoder; **priority encoder** outputs the code of the highest-priority active input.
- Others: comparator, parity generator, code converters (BCD ↔ Excess-3, binary ↔ Gray).

<div class="fig">
<svg viewBox="0 0 660 230" width="660" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<text x="150" y="18" text-anchor="middle" font-weight="bold">Half adder</text>
<text x="20" y="64">A</text><text x="20" y="134">B</text>
<line x1="35" y1="60" x2="150" y2="60" stroke="#222"/><line x1="35" y1="130" x2="150" y2="130" stroke="#222"/>
<line x1="70" y1="60" x2="70" y2="160" stroke="#222"/><line x1="70" y1="160" x2="150" y2="160" stroke="#222"/>
<line x1="95" y1="130" x2="95" y2="80" stroke="#222"/><line x1="95" y1="80" x2="150" y2="80" stroke="#222"/>
<circle cx="70" cy="60" r="2.5" fill="#222"/><circle cx="95" cy="130" r="2.5" fill="#222"/>
<rect x="150" y="50" width="70" height="40" fill="#e8f0fe" stroke="#222"/><text x="185" y="75" text-anchor="middle">XOR</text>
<rect x="150" y="120" width="70" height="50" fill="#e6f4ea" stroke="#222"/><text x="185" y="150" text-anchor="middle">AND</text>
<line x1="220" y1="70" x2="270" y2="70" stroke="#222"/><text x="275" y="74">S = A⊕B</text>
<line x1="220" y1="145" x2="270" y2="145" stroke="#222"/><text x="275" y="149">C = AB</text>
<line x1="345" y1="10" x2="345" y2="220" stroke="#999" stroke-dasharray="4,3"/>
<text x="505" y="18" text-anchor="middle" font-weight="bold">Full adder = 2 half adders + OR</text>
<text x="360" y="54">A</text><text x="360" y="84">B</text><text x="360" y="174">Cin</text>
<line x1="375" y1="50" x2="400" y2="50" stroke="#222"/><line x1="375" y1="80" x2="400" y2="80" stroke="#222"/>
<rect x="400" y="35" width="70" height="60" fill="#e8f0fe" stroke="#222"/><text x="435" y="62" text-anchor="middle">HA 1</text>
<text x="435" y="78" text-anchor="middle" font-size="11">A⊕B, AB</text>
<line x1="470" y1="50" x2="490" y2="50" stroke="#222"/><line x1="490" y1="50" x2="490" y2="140" stroke="#222"/>
<line x1="490" y1="140" x2="510" y2="140" stroke="#222"/>
<line x1="395" y1="170" x2="510" y2="170" stroke="#222"/>
<rect x="510" y="125" width="70" height="60" fill="#e8f0fe" stroke="#222"/><text x="545" y="152" text-anchor="middle">HA 2</text>
<text x="545" y="168" text-anchor="middle" font-size="11">S, Cin(A⊕B)</text>
<line x1="580" y1="140" x2="600" y2="140" stroke="#222"/><text x="603" y="144">S</text>
<line x1="470" y1="85" x2="590" y2="85" stroke="#222"/>
<line x1="545" y1="185" x2="545" y2="205" stroke="#222"/><line x1="545" y1="205" x2="590" y2="205" stroke="#222"/>
<rect x="590" y="70" width="44" height="30" fill="#fef7e0" stroke="#222"/><text x="612" y="90" text-anchor="middle">OR</text>
<line x1="590" y1="205" x2="600" y2="205" stroke="#222"/><line x1="600" y1="205" x2="600" y2="100" stroke="#222"/>
<line x1="634" y1="85" x2="650" y2="85" stroke="#222"/><text x="615" y="62" font-size="11">Cout</text>
</svg>
<div class="cap">Fig: Half adder (XOR + AND) and full adder built from two half adders and an OR gate; Cout = AB + Cin(A⊕B)</div>
</div>

### 6.8 Flip-Flops (SR, JK, D, T) and Race-Around
**Importance: 8/10** · characteristic tables + race-around are a classic 10-mark

In simple words: a flip-flop is a 1-bit memory element that changes state on a clock edge.

| SR: S R | Q(n+1) | JK: J K | Q(n+1) | D | Q(n+1) | T | Q(n+1) |
|---|---|---|---|---|---|---|---|
| 0 0 | Q (hold) | 0 0 | Q (hold) | 0 | 0 | 0 | Q (hold) |
| 0 1 | 0 (reset) | 0 1 | 0 (reset) | 1 | 1 | 1 | Q' (toggle) |
| 1 0 | 1 (set) | 1 0 | 1 (set) | | | | |
| 1 1 | invalid | 1 1 | Q' (toggle) | | | | |

- Characteristic equations: SR: Q⁺ = S + R'Q (SR = 0) · JK: Q⁺ = JQ' + K'Q · D: Q⁺ = D · T: Q⁺ = T ⊕ Q.
- **Race-around condition:** in a level-triggered JK flip-flop with J = K = 1, if the clock pulse width is longer than the propagation delay, the output toggles repeatedly during one pulse and the final state is unpredictable.
- **Cures:** (1) **master–slave JK** (master enabled on high clock, slave on low — output changes once per pulse); (2) edge-triggering; (3) clock pulse width < propagation delay.
- Latch = level-sensitive; flip-flop = edge-triggered.

### 6.9 Sequential Circuits, Registers and Counters
**Importance: 7/10** · ring/Johnson/mod-N are MCQ favourites

In simple words: output depends on present inputs **and** past state (memory) — built from combinational logic + flip-flops.

- **Synchronous:** all flip-flops share one clock (fast, no ripple). **Asynchronous (ripple):** each flip-flop clocks the next (simple, cumulative delay).
- **Registers:** group of flip-flops storing n bits. Shift registers: SISO, SIPO, PISO, PIPO; universal shift register (shift left/right, parallel load).
- **Ring counter:** n flip-flops, output of last fed to first; a single 1 circulates → **n states** (e.g. 4-bit: 1000→0100→0010→0001).
- **Johnson (twisted-ring) counter:** complement of last fed back → **2n states** (4-bit: 0000→1000→1100→1110→1111→0111→0011→0001).
- **Mod-N counter:** counts 0…N−1 then resets; needs ⌈log₂N⌉ flip-flops (mod-10 / decade counter = 4 flip-flops, reset at 1010).
- n-bit ripple counter = mod-2ⁿ; up/down counters.

### 6.10 Integrated Circuits and Memory Unit
**Importance: 5/10** · short MCQ/definitions

| Scale | Gates per chip (approx.) | Example |
|---|---|---|
| SSI | < 10 (up to ~12) | basic gates (7400 quad NAND) |
| MSI | 10–100 | MUX, decoder, counter, adder |
| LSI | 100–10,000 | early microprocessors, ROM/RAM chips |
| VLSI | > 10,000 | modern CPUs, large memories |

- Logic families: TTL, CMOS (low power, most used), ECL (fastest).
- **Memory unit:** collection of storage cells with address lines (k lines → 2ᵏ words), data lines (n bits/word) and control (Read/Write). A 2ᵏ × n memory.
- **RAM** (volatile): SRAM (flip-flops, fast, cache) vs DRAM (capacitor, needs refresh, main memory). **ROM** (non-volatile): Mask ROM, PROM, EPROM (UV-erasable), EEPROM/Flash (electrically erasable).

### 6.11 Number Systems and Conversions (worked)
**Importance: 8/10** · numericals in MCQ every year

- Bases: binary 2, octal 8, decimal 10, hexadecimal 16. Octal = 3 bits per digit, hex = 4 bits per digit.
- **Decimal → binary:** repeated division by 2 (integer), repeated multiplication by 2 (fraction).
- **156₁₀:** 156 → 78 r0 → 39 r0 → 19 r1 → 9 r1 → 4 r1 → 2 r0 → 1 r0 → 0 r1 → read upward = **10011100₂**. Group by 3 → 010 011 100 = **234₈**; by 4 → 1001 1100 = **9C₁₆**.
- **101101.101₂ → decimal:** 32 + 8 + 4 + 1 = 45; .101 = 0.5 + 0.125 = 0.625 → **45.625₁₀**.
- **7A₁₆ → decimal:** 7×16 + 10 = **122₁₀**.
- (All verified with python3.)

### 6.12 1's and 2's Complement Arithmetic (worked)
**Importance: 8/10** · standard numerical

- **1's complement:** invert every bit. **2's complement:** 1's complement + 1. Range of n-bit 2's complement: −2ⁿ⁻¹ to 2ⁿ⁻¹ − 1 (8-bit: −128 to +127). 2's complement has a single zero, 1's complement has +0 and −0.
- Example: 28 = 00011100 → 1's = 11100011 → 2's = 11100100.

**Compute 25 − 37 in 8 bits (= 25 + (−37)).** 25 = 00011001 ; 37 = 00100101.

- **2's complement:** −37 = 11011010 + 1 = 11011011. Add: 00011001 + 11011011 = **11110100**. No carry out → result negative; take 2's complement: 00001100 = 12 → **−12** ✓.
- **1's complement:** −37 = 11011010. Add: 00011001 + 11011010 = **11110011**. No end-around carry → negative; invert: 00001100 = 12 → **−12** ✓.
- If there is a carry out: in 2's complement discard it; in 1's complement add it back to the LSB (end-around carry).
- **Overflow:** adding two numbers of the same sign gives a result of opposite sign (carry into MSB ≠ carry out of MSB).

### 6.13 IEEE-754 Single Precision (worked)
**Importance: 7/10** · syllabus "number representation"; layout is a frequent MCQ

In simple words: a float is stored as sign × 1.mantissa × 2^(exponent − 127) in 32 bits.

<div class="fig">
<svg viewBox="0 0 660 120" width="660" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="20" y="30" width="40" height="40" fill="#fce8e6" stroke="#222"/><text x="40" y="55" text-anchor="middle" font-weight="bold">S</text>
<rect x="60" y="30" width="160" height="40" fill="#fef7e0" stroke="#222"/><text x="140" y="55" text-anchor="middle" font-weight="bold">Exponent (8 bits)</text>
<rect x="220" y="30" width="420" height="40" fill="#e8f0fe" stroke="#222"/><text x="430" y="55" text-anchor="middle" font-weight="bold">Mantissa / fraction (23 bits)</text>
<text x="20" y="22" font-size="11">bit 31</text><text x="60" y="22" font-size="11">30</text><text x="205" y="22" font-size="11">23</text>
<text x="225" y="22" font-size="11">22</text><text x="625" y="22" font-size="11">0</text>
<text x="40" y="90" text-anchor="middle" font-size="11">0 = +</text><text x="40" y="104" text-anchor="middle" font-size="11">1 = −</text>
<text x="140" y="90" text-anchor="middle" font-size="11">biased: E = e + 127</text>
<text x="430" y="90" text-anchor="middle" font-size="11">fraction after the hidden leading 1</text>
<text x="330" y="112" text-anchor="middle" font-size="11">Value = (−1)^S × 1.F × 2^(E − 127)</text>
</svg>
<div class="cap">Fig: IEEE-754 single-precision (32-bit) layout — 1 sign, 8 exponent (bias 127), 23 fraction bits</div>
</div>

**Convert −13.625 to IEEE-754 single precision.**

1. Sign: negative → S = 1.
2. 13 = 1101 ; 0.625 = .101 → 13.625 = 1101.101₂.
3. Normalise: 1.101101 × 2³ → e = 3, E = 3 + 127 = 130 = **10000010**.
4. Fraction (bits after the leading 1, padded to 23): **10110100000000000000000**.
5. Result: **1 10000010 10110100000000000000000** = **0xC15A0000** (verified: `struct.pack('>f', -13.625).hex()` → c15a0000).

- Special values: E = 0 & F = 0 → ±0; E = 255 & F = 0 → ±∞; E = 255 & F ≠ 0 → NaN; E = 0 & F ≠ 0 → denormal.
- Double precision: 1 + 11 + 52 bits, bias 1023.

### Likely questions with model answers (Unit 6)

**Q. What are universal gates? Realise NOT, AND and OR using only NAND gates.** *(5 marks · Likelihood 8/10)*

A universal gate is one from which every other gate, and hence any Boolean function, can be built. NAND and NOR are universal. Using NAND only: (1) **NOT** — tie both inputs together: (A·A)' = A'. (2) **AND** — a NAND followed by a NAND-inverter: ((AB)')' = AB, two gates. (3) **OR** — invert each input with a NAND-inverter, then NAND them: (A'·B')' = A + B by De Morgan, three gates. Similarly with NOR: NOT = (A+A)', OR = NOR + inverter, AND = NOR of inverted inputs (A' + B')' = AB. Universal gates are preferred in IC fabrication because a whole circuit can be made from one standard gate type, which simplifies manufacturing and lowers cost.

**Q. Define tautology, contradiction and satisfiability with examples.** *(5 marks · Likelihood 7/10)*

A **tautology** is a compound proposition that is true for every truth assignment of its variables, e.g. p ∨ ¬p or ((p → q) ∧ p) → q. A **contradiction** is false for every assignment, e.g. p ∧ ¬p. A formula that is neither is a **contingency**, e.g. p → q. A formula is **satisfiable** if at least one assignment makes it true, e.g. p ∧ q (true when p = q = T); it is **unsatisfiable** if it is a contradiction. Relations: every tautology is satisfiable; A is a tautology iff ¬A is unsatisfiable. These can be checked with a truth table (2ⁿ rows for n variables). Satisfiability (SAT) of propositional formulas is the first known NP-complete problem.

**Q. Explain the race-around condition in a JK flip-flop. How is it eliminated?** *(5 marks · Likelihood 8/10)*

The JK flip-flop's characteristic equation is Q⁺ = JQ' + K'Q; with J = K = 1 it toggles. In a level-triggered JK flip-flop the inputs act for the whole time the clock is high. If the clock pulse width tp is greater than the propagation delay Δt of the flip-flop, the output toggles, the new output feeds back to the input gates, and it toggles again — repeatedly — while the clock is still high. At the end of the pulse the state is unpredictable. This is the **race-around condition**. Remedies: (1) keep tp < Δt (hard to guarantee); (2) use **edge-triggered** flip-flops, which sample the inputs only at the clock edge; (3) use a **master–slave JK flip-flop** — two latches in cascade, the master enabled when the clock is high and the slave when it is low, so the output can change only once per clock cycle.

**Q. Simplify F(A,B,C,D) = Σm(0,1,2,5,8,9,10) using a K-map and draw the realisation.** *(10 marks · Likelihood 7/10)*

Plot the 1s on a 4-variable K-map (rows AB and columns CD in Gray order 00, 01, 11, 10). 1s fall at m0, m1, m2 (row 00), m5 (row 01), m8, m9, m10 (row 10). Grouping: (i) the quad m0, m1, m8, m9 — rows 00 and 10 are adjacent by wrap-around, columns 00 and 01 — has B = 0 and C = 0 constant → B'C'. (ii) the four corners m0, m2, m8, m10 have B = 0 and D = 0 → B'D'. (iii) m5 is left; pair it with m1 (A = 0, C = 0, D = 1) → A'C'D. All 1s are covered with the fewest, largest groups, so **F = B'C' + B'D' + A'C'D**. Realisation: three AND gates (2-input, 2-input, 3-input) fed by inverted literals and one 3-input OR gate; or, converting to NAND–NAND form, replace every gate by NAND (two-level AND–OR ≡ NAND–NAND). Check: any minterm not in the list, e.g. m3 (A'B'CD), gives B'C' = 0, B'D' = 0, A'C'D = 0 → F = 0, correct. Explain rules: groups are of size 2ᵏ, rectangular, may wrap around edges, overlapping is allowed, and don't-cares may be included if they enlarge a group.

**Q. Represent −13.625 in IEEE-754 single precision. Explain the format.** *(10 marks · Likelihood 6/10)*

Use the worked conversion in 6.13 (S = 1, E = 130 = 10000010, F = 1011010…0, hex C15A0000), draw the field layout, explain the bias of 127 and the hidden 1 bit, and list the special values (0, ∞, NaN, denormals) and the double-precision format (1/11/52, bias 1023).

## Unit 7 — Computer Networks

### 7.1 Types of Networks — LAN, MAN, WAN, Wireless, Internetworks
**Importance: 7/10** · basic 5-mark "classify networks"

| Type | Span | Typical technology | Owner |
|---|---|---|---|
| PAN | ~10 m | Bluetooth | individual |
| LAN | room / building / campus (≤ ~1 km) | Ethernet (IEEE 802.3), Wi-Fi (802.11) | private |
| MAN | city (~10–50 km) | cable TV networks, WiMAX (802.16), metro Ethernet | ISP / city |
| WAN | country / continent | leased lines, MPLS, satellite, (historically) X.25, Frame Relay, ATM | telecom carriers |

- **Wireless networks:** system interconnection (Bluetooth), wireless LAN (802.11), wireless WAN (cellular 2G–5G).
- **Internetwork (internet):** a collection of interconnected networks joined by routers/gateways; the Internet is the largest example.
- WAN parts (Tanenbaum): hosts and a **subnet** of transmission lines + switching elements (routers).

### 7.2 OSI and TCP/IP Reference Models
**Importance: 9/10** · asked in almost every CN paper

In simple words: layered models split network communication into independent jobs; each layer serves the one above.

| # | OSI layer | Function | PDU / devices |
|---|---|---|---|
| 7 | Application | user services (HTTP, FTP, SMTP, DNS) | data / gateway |
| 6 | Presentation | translation, encryption, compression | data |
| 5 | Session | dialog control, synchronisation (checkpoints) | data |
| 4 | Transport | end-to-end delivery, segmentation, flow & error control, ports (TCP/UDP) | segment |
| 3 | Network | logical (IP) addressing, routing, fragmentation | packet / router |
| 2 | Data link | framing, MAC addressing, error detection, medium access | frame / switch, bridge |
| 1 | Physical | bits on the medium, signals, connectors | bits / hub, repeater |

<div class="fig">
<svg viewBox="0 0 560 300" width="560" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<text x="110" y="20" text-anchor="middle" font-weight="bold">OSI (7)</text>
<text x="430" y="20" text-anchor="middle" font-weight="bold">TCP/IP (4)</text>
<rect x="20" y="30" width="180" height="36" fill="#fce8e6" stroke="#222"/><text x="110" y="53" text-anchor="middle">7 Application</text>
<rect x="20" y="66" width="180" height="36" fill="#fce8e6" stroke="#222"/><text x="110" y="89" text-anchor="middle">6 Presentation</text>
<rect x="20" y="102" width="180" height="36" fill="#fce8e6" stroke="#222"/><text x="110" y="125" text-anchor="middle">5 Session</text>
<rect x="20" y="138" width="180" height="36" fill="#e8f0fe" stroke="#222"/><text x="110" y="161" text-anchor="middle">4 Transport</text>
<rect x="20" y="174" width="180" height="36" fill="#e6f4ea" stroke="#222"/><text x="110" y="197" text-anchor="middle">3 Network</text>
<rect x="20" y="210" width="180" height="36" fill="#fef7e0" stroke="#222"/><text x="110" y="233" text-anchor="middle">2 Data link</text>
<rect x="20" y="246" width="180" height="36" fill="#fef7e0" stroke="#222"/><text x="110" y="269" text-anchor="middle">1 Physical</text>
<rect x="340" y="30" width="180" height="108" fill="#fce8e6" stroke="#222"/><text x="430" y="80" text-anchor="middle" font-weight="bold">Application</text>
<text x="430" y="97" text-anchor="middle" font-size="11">HTTP, FTP, SMTP, DNS</text>
<rect x="340" y="138" width="180" height="36" fill="#e8f0fe" stroke="#222"/><text x="430" y="155" text-anchor="middle" font-weight="bold">Transport</text>
<text x="430" y="169" text-anchor="middle" font-size="11">TCP, UDP</text>
<rect x="340" y="174" width="180" height="36" fill="#e6f4ea" stroke="#222"/><text x="430" y="191" text-anchor="middle" font-weight="bold">Internet</text>
<text x="430" y="205" text-anchor="middle" font-size="11">IP, ICMP, ARP</text>
<rect x="340" y="210" width="180" height="72" fill="#fef7e0" stroke="#222"/><text x="430" y="243" text-anchor="middle" font-weight="bold">Network Access</text>
<text x="430" y="260" text-anchor="middle" font-size="11">Ethernet, Wi-Fi (Link)</text>
<g stroke="#222" stroke-dasharray="4,3">
<line x1="200" y1="30" x2="340" y2="30"/><line x1="200" y1="138" x2="340" y2="138"/>
<line x1="200" y1="174" x2="340" y2="174"/><line x1="200" y1="210" x2="340" y2="210"/>
<line x1="200" y1="282" x2="340" y2="282"/>
</g>
</svg>
<div class="cap">Fig: OSI layers (7→1 top-down) mapped onto the 4-layer TCP/IP model</div>
</div>

| OSI | TCP/IP |
|---|---|
| 7 layers; model came before protocols | 4 layers; protocols came first, model describes them |
| clear service / interface / protocol distinction | less clear distinction |
| network layer: connection-oriented & connectionless | Internet layer connectionless (IP) only |
| transport: connection-oriented only | transport: both (TCP and UDP) |
| reference/teaching model | the model the Internet actually runs on |

**IP address vs MAC address**

| IP address | MAC address |
|---|---|
| logical, network layer (L3) | physical/hardware, data-link layer (L2) |
| IPv4 32-bit (dotted decimal), IPv6 128-bit | 48-bit, hex (e.g. 00:1A:2B:3C:4D:5E) |
| assigned by admin/DHCP; changes with network | burned into NIC by manufacturer (OUI + serial) |
| used for routing end to end | used for delivery on the local link (hop to hop) |
| mapped to MAC by **ARP** | mapped to IP by RARP (old) |

### 7.3 Channel Capacity — Nyquist and Shannon (worked)
**Importance: 7/10** · small numericals

- **Nyquist (noiseless channel):** C = 2B log₂ L bit/s (B = bandwidth in Hz, L = number of signal levels).
- **Shannon (noisy channel):** C = B log₂(1 + S/N) bit/s, with S/N as a ratio (SNR in dB = 10 log₁₀ S/N).
- **Worked (Shannon):** telephone line B = 3000 Hz, SNR = 30 dB → S/N = 10³ = 1000. C = 3000 × log₂(1001) ≈ 3000 × 9.967 ≈ **29,900 bit/s ≈ 30 kbit/s**.
- **Worked (Nyquist):** B = 3000 Hz, L = 4 levels → C = 2 × 3000 × log₂4 = **12,000 bit/s**. (Both verified with python3.)
- Shannon gives the upper limit; Nyquist tells how many levels are needed to approach it.

### 7.4 Transmission Media — Guided and Unguided
**Importance: 8/10** · syllabus lists radio/microwave/infrared/lightwave explicitly

| Guided (wired) | Key points |
|---|---|
| Twisted pair (UTP/STP) | twisting cancels interference; Cat-5e/6 for Ethernet; telephone local loop |
| Coaxial cable | central conductor + shield; cable TV, older Ethernet; better bandwidth than twisted pair |
| Optical fibre | light by total internal reflection; single-mode (long distance, laser) vs multimode (LED); huge bandwidth, immune to EMI, hard to tap |

| Unguided (wireless) | Frequency / behaviour | Uses |
|---|---|---|
| Radio waves | ~3 kHz–1 GHz; omnidirectional; pass through walls | AM/FM radio, mobile, Wi-Fi bands |
| Microwaves | 1–300 GHz; line of sight, unidirectional, dish antennas; towers every ~50 km | long-distance telephone, satellite, cellular backhaul |
| Infrared | 300 GHz–400 THz; short range, cannot pass walls | TV remotes, IrDA |
| Lightwave (free-space optics) | lasers between rooftops; very high bandwidth, unlicensed | but affected by fog, rain, heat convection |

### 7.5 The Telephone System — Local Loop, Trunks, Multiplexing, Switching
**Importance: 8/10** · syllabus phrase verbatim; good 10-mark

In simple words: the PSTN has three parts — local loops (homes to end office), trunks (office to office) and switching offices.

- **Local loop:** analog twisted pair from subscriber to the end office ("last mile"); DSL reuses it for data.
- **Trunks:** high-capacity digital fibre/microwave links between switching offices, carrying many calls by multiplexing.
- **Switching offices:** end offices → toll offices → intermediate switching offices (hierarchy).
- **Codec/PCM:** voice sampled 8000 times/s × 8 bits = **64 kbit/s** per channel (DS0).

**Multiplexing**

| FDM | TDM | WDM |
|---|---|---|
| bandwidth split into frequency bands with guard bands | each user gets a time slot in turn | FDM for light — different wavelengths on one fibre |
| analog; radio/TV, old telephony | digital; T1 = 24 × 64 kbit/s + framing = 1.544 Mbit/s; E1 = 32 slots = 2.048 Mbit/s | DWDM on long-haul fibre |

**Switching**

| Circuit switching | Message switching | Packet switching |
|---|---|---|
| dedicated path set up before data (call setup) | whole message stored and forwarded hop by hop | message split into packets, each stored and forwarded |
| reserved bandwidth, no congestion after setup, wasted when idle | no size limit; long delays; large buffers | efficient sharing, pipelining; possible congestion/out-of-order |
| telephone network | old telegraph, early e-mail | Internet |

### 7.6 Narrowband ISDN, Broadband ISDN and ATM
**Importance: 7/10** · syllabus phrases; numbers (2B+D, 53 bytes) are MCQ bait

- **ISDN (Integrated Services Digital Network):** end-to-end digital network carrying voice and data together over existing telephone lines.
- **B channel** = 64 kbit/s (bearer, user data/voice); **D channel** = signalling (16 kbit/s in BRI, 64 kbit/s in PRI).
- **BRI (Basic Rate Interface): 2B + D** = 2×64 + 16 = 144 kbit/s (192 kbit/s with framing) — homes/small offices.
- **PRI (Primary Rate Interface): 23B + D** (North America/Japan, T1 1.544 Mbit/s) or **30B + D** (Europe/India, E1 2.048 Mbit/s).
- Devices: NT1 (network termination), TE1 (ISDN terminal), TE2 + TA (terminal adapter for non-ISDN devices).
- **Broadband ISDN (B-ISDN):** ITU successor offering 155 Mbit/s and higher for video, data, voice; its transfer technology is **ATM**.
- **ATM (Asynchronous Transfer Mode):** connection-oriented, cell switching using **fixed 53-byte cells (5-byte header + 48-byte payload)** over virtual circuits (VPI/VCI). Fixed small cells → fast hardware switching and low jitter for voice/video. ATM reference model: physical, ATM layer, ATM Adaptation Layer (AAL1–AAL5).

### 7.7 High-Speed LANs, Cellular and Radio Networks
**Importance: 5/10** · listed in syllabus; short notes

- **Fast Ethernet** (100 Mbit/s, 802.3u), **Gigabit Ethernet** (1 Gbit/s, 802.3z/ab), 10 GbE and above; **FDDI** (100 Mbit/s dual counter-rotating fibre token ring).
- **Cellular radio:** area divided into cells, each with a base station; **frequency reuse** in non-adjacent cells; **handoff** when a mobile moves between cells; MSC (mobile switching centre) connects to the PSTN.
- Generations: 1G analog (AMPS, FDMA) · 2G digital GSM (TDMA), CDMA · 3G UMTS/WCDMA (data) · 4G LTE (all-IP, OFDMA) · 5G (mmWave, very low latency).
- Paging systems, cordless phones, satellite (GEO ~36,000 km, MEO, LEO) are other radio systems.

### 7.8 Internetworking Devices
**Importance: 9/10** · "differentiate hub, switch, bridge, router, gateway" is a top question

| Device | OSI layer | What it does |
|---|---|---|
| Repeater | 1 Physical | regenerates signal to extend distance |
| Hub | 1 Physical | multi-port repeater; broadcasts every bit to all ports; one collision domain |
| Bridge | 2 Data link | connects two LAN segments; filters by MAC address; separate collision domains |
| Switch | 2 Data link | multi-port bridge; MAC table; forwards frame only to destination port; full duplex |
| Router | 3 Network | connects different networks; forwards packets by IP address using routing tables; separates broadcast domains |
| Gateway | up to 7 (all layers) | protocol converter between dissimilar networks/applications (e.g. e-mail gateway) |

- Layer-3 switch = switch with routing capability. Brouter = bridge + router.

### 7.9 Concatenated Virtual Circuits, Tunnelling, Fragmentation
**Importance: 7/10** · syllabus phrases verbatim (Tanenbaum internetworking)

- **Concatenated virtual circuits:** when all networks along the path are connection-oriented, a VC is built from the source to a multiprotocol router/gateway on the first network's border, then another VC to the next gateway, and so on. Each gateway keeps a table mapping incoming VC to outgoing VC; packets stay in order. Works badly if any network is datagram-only.
- **Connectionless internetworking (datagram):** each packet routed independently across networks (IP model) — robust, but no ordering guarantee.
- **Tunnelling:** used when source and destination are on the same type of network but a different network lies between them. The packet is **encapsulated** as payload inside a packet of the intermediate network's protocol, carried across, then decapsulated. Examples: IPv6-over-IPv4, VPNs (IPsec, GRE).
- **Fragmentation:** each network has a maximum packet size (MTU, Ethernet 1500 bytes). A large packet is broken into fragments. **Transparent** fragmentation: reassembled at the exit gateway of the small-MTU network. **Non-transparent** (IPv4): reassembled only at the destination host. IPv4 header fields: Identification, DF/MF flags, Fragment offset (in 8-byte units). IPv6 routers do not fragment (source does, using path-MTU discovery).

### 7.10 Firewalls
**Importance: 8/10** · security + networking overlap; good 5/10-mark

In simple words: a firewall sits between a trusted internal network and an untrusted one and enforces an access policy on traffic.

| Type | Works at | How |
|---|---|---|
| Packet-filtering (stateless) | Network/Transport (L3–L4) | checks each packet's source/destination IP, ports, protocol against rules (ACL); fast, but no context |
| Stateful inspection | L3–L4 + connection state | tracks connection state table (e.g. allows replies only to established TCP sessions) |
| Application-level gateway (proxy) | Application (L7) | per-service proxy (HTTP, FTP, SMTP) relays traffic, can inspect content, authenticate users and log; slower |
| Circuit-level gateway | Session (L5) | validates TCP handshake, then relays without content inspection (e.g. SOCKS) |

- **Proxy server:** client connects to the proxy, which makes the request on its behalf — hides internal addresses, caches content, filters URLs.
- **DMZ:** a screened subnet between two firewalls for public servers (web, mail).
- Limitations: cannot stop insider attacks or traffic that bypasses it; encrypted traffic is hard to inspect.

### 7.11 Routing — Virtual Circuits vs Datagrams
**Importance: 7/10** · classic comparison

| Issue | Datagram subnet | Virtual-circuit subnet |
|---|---|---|
| Circuit setup | not needed | required |
| Addressing | each packet carries full source and destination address | each packet carries a short VC number |
| State in routers | none per connection | each VC needs a table entry |
| Routing | each packet routed independently | route fixed at setup; all packets follow it |
| Router failure | only packets lost in that router | all VCs through it terminated |
| QoS / congestion control | difficult | easy if resources reserved in advance |
| Examples | IP (Internet) | ATM, X.25, Frame Relay, MPLS |

- **Routing** decides the path (builds routing tables); **forwarding** sends each packet out the correct interface.
- Properties wanted: correctness, simplicity, robustness, stability, fairness, optimality. Static (non-adaptive) vs dynamic (adaptive) routing.

### 7.12 Routing Algorithms — Distance Vector, Link State, Dijkstra
**Importance: 8/10** · 10-mark candidate, with Dijkstra worked

| Distance vector (Bellman-Ford) | Link state |
|---|---|
| each router sends its whole distance table to **neighbours only**, periodically | each router floods **link-state packets** (its neighbours and costs) to **all** routers |
| knows only next hop and distance | every router has the complete topology map |
| slow convergence; **count-to-infinity** problem (fixes: split horizon, poison reverse, hold-down) | fast convergence, no count-to-infinity; more CPU and memory |
| RIP (hop count, max 15) | OSPF, IS-IS (Dijkstra's shortest path) |

**Dijkstra's algorithm (link state):** start from source with distance 0 and all others ∞; repeatedly pick the unvisited node with the smallest tentative distance, mark it permanent, and relax its neighbours (d[v] = min(d[v], d[u] + w(u,v))); stop when all nodes are permanent. Complexity O(V²) or O((V+E) log V) with a heap.

- Example: A–B 2, A–C 5, B–C 1, B–D 4, C–D 1. From A: B = 2 (A→B), C = 3 (A→B→C), D = 4 (A→B→C→D).
- Other: flooding, hierarchical routing, broadcast/multicast routing; BGP (path vector) between autonomous systems.

### 7.13 Network Security and Cryptography
**Importance: 9/10** · core of a forensic post; "symmetric vs public key", "digital signature" likely

In simple words: cryptography transforms plaintext into ciphertext with a key so only authorised parties can read it.

- Security goals: **confidentiality, integrity, authentication, non-repudiation** (+ availability).
- Classical ciphers: substitution (Caesar, monoalphabetic) and transposition.

| Symmetric (secret key) | Public key (asymmetric) |
|---|---|
| same key encrypts and decrypts | key pair: public key (shared) and private key (secret) |
| fast; bulk data | slow; key exchange, signatures |
| key distribution problem; n(n−1)/2 keys for n users | 2n keys for n users |
| DES, 3DES, AES, Blowfish | RSA, Diffie-Hellman, ECC |

- **DES:** 64-bit block, **56-bit key**, 16 Feistel rounds; now insecure (brute force). 3DES = three DES passes (EDE).
- **AES (Rijndael):** 128-bit block, 128/192/256-bit keys, 10/12/14 rounds; current standard.
- **RSA idea:** pick large primes p, q; n = pq; φ = (p−1)(q−1); choose e coprime to φ; d = e⁻¹ mod φ. Public (e, n), private (d, n). Encrypt C = Mᵉ mod n; decrypt M = Cᵈ mod n. Security rests on difficulty of factoring n. (Toy: p = 3, q = 11, n = 33, φ = 20, e = 3, d = 7; M = 4 → C = 4³ mod 33 = 31 → 31⁷ mod 33 = 4.)
- **Hash function:** fixed-length digest, one-way and collision-resistant — MD5 (128-bit, broken), SHA-1 (160-bit, deprecated), SHA-256. Used for integrity (and in forensics to verify evidence images).
- **Digital signature:** sender hashes the message and encrypts the hash with **sender's private key**; receiver decrypts with the **sender's public key** and compares with its own hash → authentication, integrity, non-repudiation.
- **Public key certificates / PKI:** a CA signs a binding of identity to public key (X.509).

<div class="fig">
<svg viewBox="0 0 660 250" width="660" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u7-pk-arr" markerWidth="10" markerHeight="10" refX="9" refY="5" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker></defs>
<text x="330" y="16" text-anchor="middle" font-weight="bold">(a) Confidentiality: encrypt with receiver's public key</text>
<rect x="10" y="30" width="90" height="36" fill="#f1f3f4" stroke="#222"/><text x="55" y="53" text-anchor="middle">Plaintext</text>
<rect x="150" y="30" width="120" height="36" fill="#e8f0fe" stroke="#222"/><text x="210" y="53" text-anchor="middle">Encrypt</text>
<rect x="320" y="30" width="100" height="36" fill="#fce8e6" stroke="#222"/><text x="370" y="53" text-anchor="middle">Ciphertext</text>
<rect x="470" y="30" width="100" height="36" fill="#e8f0fe" stroke="#222"/><text x="520" y="53" text-anchor="middle">Decrypt</text>
<rect x="590" y="30" width="64" height="36" fill="#f1f3f4" stroke="#222"/><text x="622" y="53" text-anchor="middle">Plain</text>
<line x1="100" y1="48" x2="148" y2="48" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<line x1="270" y1="48" x2="318" y2="48" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<line x1="420" y1="48" x2="468" y2="48" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<line x1="570" y1="48" x2="588" y2="48" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<text x="210" y="86" text-anchor="middle" font-size="11">Bob's PUBLIC key</text>
<text x="520" y="86" text-anchor="middle" font-size="11">Bob's PRIVATE key</text>
<line x1="5" y1="105" x2="655" y2="105" stroke="#999" stroke-dasharray="4,3"/>
<text x="330" y="126" text-anchor="middle" font-weight="bold">(b) Digital signature: sign hash with sender's private key</text>
<rect x="10" y="140" width="90" height="36" fill="#f1f3f4" stroke="#222"/><text x="55" y="163" text-anchor="middle">Message</text>
<rect x="130" y="140" width="80" height="36" fill="#fef7e0" stroke="#222"/><text x="170" y="163" text-anchor="middle">Hash</text>
<rect x="240" y="140" width="110" height="36" fill="#e8f0fe" stroke="#222"/><text x="295" y="163" text-anchor="middle">Sign (encrypt)</text>
<rect x="380" y="140" width="100" height="36" fill="#fce8e6" stroke="#222"/><text x="430" y="163" text-anchor="middle">Msg + sig</text>
<rect x="510" y="140" width="144" height="36" fill="#e6f4ea" stroke="#222"/><text x="582" y="157" text-anchor="middle" font-size="11">Verify: decrypt sig,</text>
<text x="582" y="171" text-anchor="middle" font-size="11">compare hashes</text>
<line x1="100" y1="158" x2="128" y2="158" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<line x1="210" y1="158" x2="238" y2="158" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<line x1="350" y1="158" x2="378" y2="158" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<line x1="480" y1="158" x2="508" y2="158" stroke="#222" marker-end="url(#u7-pk-arr)"/>
<text x="295" y="196" text-anchor="middle" font-size="11">Alice's PRIVATE key</text>
<text x="582" y="196" text-anchor="middle" font-size="11">Alice's PUBLIC key</text>
<text x="330" y="232" text-anchor="middle" font-size="11">(a) gives confidentiality; (b) gives authentication, integrity and non-repudiation</text>
</svg>
<div class="cap">Fig: Public-key encryption (Alice → Bob) and digital signature (signed by Alice)</div>
</div>

### 7.14 DNS — Domain Name System
**Importance: 8/10** · syllabus phrase; resource records are MCQ favourites

In simple words: DNS is the distributed, hierarchical database that maps host names to IP addresses.

- **Name space hierarchy:** root (.) → top-level domains (generic .com .org .gov; country .in) → second level (co.in) → hosts (www.npsc.co.in). Each label ≤ 63 chars, full name ≤ 255.
- **Zones and name servers:** the tree is divided into non-overlapping zones; each zone has a primary (master) and secondary name servers. Root servers (13 logical, A–M), TLD servers, authoritative servers; local (resolver) servers cache answers (TTL).
- **Queries:** recursive (server returns final answer) vs iterative (server returns a referral). Uses **UDP port 53** (TCP 53 for zone transfers/large replies).

| Record | Meaning |
|---|---|
| A | host name → IPv4 address |
| AAAA | host name → IPv6 address |
| MX | mail exchanger for the domain (with priority) |
| CNAME | alias → canonical name |
| NS | authoritative name server for the zone |
| PTR | IP → name (reverse lookup, in-addr.arpa) |
| SOA | start of authority: primary server, admin e-mail, serial, refresh/retry/expire timers |
| TXT / HINFO | text (SPF etc.) / host info |

<div class="fig">
<svg viewBox="0 0 640 260" width="640" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u7-dns-arr" markerWidth="10" markerHeight="10" refX="9" refY="5" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker></defs>
<rect x="10" y="110" width="110" height="44" fill="#e8f0fe" stroke="#222"/>
<text x="65" y="129" text-anchor="middle" font-weight="bold">Client</text>
<text x="65" y="145" text-anchor="middle" font-size="11">(browser)</text>
<rect x="200" y="110" width="130" height="44" fill="#fef7e0" stroke="#222"/>
<text x="265" y="129" text-anchor="middle" font-weight="bold">Local DNS</text>
<text x="265" y="145" text-anchor="middle" font-size="11">resolver (ISP)</text>
<rect x="470" y="15" width="160" height="40" fill="#fce8e6" stroke="#222"/>
<text x="550" y="40" text-anchor="middle">Root server (.)</text>
<rect x="470" y="110" width="160" height="40" fill="#e6f4ea" stroke="#222"/>
<text x="550" y="135" text-anchor="middle">TLD server (.in)</text>
<rect x="470" y="205" width="160" height="40" fill="#f1f3f4" stroke="#222"/>
<text x="550" y="223" text-anchor="middle">Authoritative server</text>
<text x="550" y="238" text-anchor="middle" font-size="11">(npsc.co.in)</text>
<line x1="120" y1="122" x2="198" y2="122" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<text x="160" y="116" text-anchor="middle" font-size="11">1</text>
<line x1="200" y1="144" x2="122" y2="144" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<text x="160" y="160" text-anchor="middle" font-size="11">8 (IP)</text>
<line x1="320" y1="110" x2="468" y2="35" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<line x1="470" y1="48" x2="335" y2="116" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<text x="380" y="62" font-size="11">2 / 3</text>
<line x1="330" y1="125" x2="468" y2="125" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<line x1="470" y1="140" x2="332" y2="140" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<text x="400" y="118" text-anchor="middle" font-size="11">4 / 5</text>
<line x1="320" y1="154" x2="468" y2="218" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<line x1="470" y1="232" x2="305" y2="156" stroke="#222" marker-end="url(#u7-dns-arr)"/>
<text x="370" y="215" font-size="11">6 / 7</text>
</svg>
<div class="cap">Fig: Resolving www.npsc.co.in — client asks local resolver (recursive); resolver queries root, TLD and authoritative servers iteratively</div>
</div>

### 7.15 Electronic Mail — Architecture and Protocols
**Importance: 8/10** · syllabus phrase; forensic relevance (e-mail headers)

In simple words: user agents compose and read mail; message transfer agents move it between servers.

- **User Agent (UA):** mail client (Outlook, Thunderbird, webmail) — compose, read, reply, forward, manage mailboxes.
- **Message Transfer Agent (MTA):** mail server (Postfix, Sendmail, Exchange) that relays mail using **SMTP** (TCP port 25; 587 for submission). SMTP is push-only, 7-bit ASCII; **MIME** extends it for attachments, non-ASCII text and images.
- **Mailbox / Message Access Agent:** **POP3** (port 110) downloads and usually deletes from server — offline, single device. **IMAP** (port 143, 993 over TLS) keeps mail on server, folders, sync across devices, partial download.
- Message = **envelope** (used by MTAs) + **header** (From, To, Cc, Subject, Date, Message-ID, Received lines) + **body**. "Received:" headers trace the path — key in e-mail forensics.
- DNS **MX** record tells the sending MTA which server accepts mail for the domain.

<div class="fig">
<svg viewBox="0 0 660 170" width="660" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u7-mail-arr" markerWidth="10" markerHeight="10" refX="9" refY="5" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker></defs>
<rect x="10" y="50" width="100" height="50" fill="#e8f0fe" stroke="#222"/><text x="60" y="72" text-anchor="middle" font-weight="bold">Alice UA</text>
<text x="60" y="88" text-anchor="middle" font-size="11">(mail client)</text>
<rect x="170" y="50" width="120" height="50" fill="#fef7e0" stroke="#222"/><text x="230" y="72" text-anchor="middle" font-weight="bold">Sender MTA</text>
<text x="230" y="88" text-anchor="middle" font-size="11">(mail server)</text>
<rect x="370" y="50" width="120" height="50" fill="#fef7e0" stroke="#222"/><text x="430" y="72" text-anchor="middle" font-weight="bold">Receiver MTA</text>
<text x="430" y="88" text-anchor="middle" font-size="11">+ Bob's mailbox</text>
<rect x="550" y="50" width="100" height="50" fill="#e8f0fe" stroke="#222"/><text x="600" y="72" text-anchor="middle" font-weight="bold">Bob UA</text>
<text x="600" y="88" text-anchor="middle" font-size="11">(mail client)</text>
<line x1="110" y1="75" x2="168" y2="75" stroke="#222" marker-end="url(#u7-mail-arr)"/>
<text x="139" y="44" text-anchor="middle" font-size="11">SMTP</text>
<line x1="290" y1="75" x2="368" y2="75" stroke="#222" marker-end="url(#u7-mail-arr)"/>
<text x="329" y="44" text-anchor="middle" font-size="11">SMTP (MX)</text>
<line x1="548" y1="75" x2="492" y2="75" stroke="#222" marker-end="url(#u7-mail-arr)"/>
<text x="520" y="44" text-anchor="middle" font-size="11">POP3 / IMAP</text>
<text x="139" y="125" text-anchor="middle" font-size="11">push</text>
<text x="329" y="125" text-anchor="middle" font-size="11">push (port 25)</text>
<text x="520" y="125" text-anchor="middle" font-size="11">pull (110 / 143)</text>
<text x="330" y="158" text-anchor="middle" font-size="11">Arrow on the right points to the server: Bob's UA requests (pulls) mail from his mailbox</text>
</svg>
<div class="cap">Fig: E-mail architecture — UAs, MTAs, SMTP for sending/relaying, POP3/IMAP for retrieval</div>
</div>

### 7.16 World Wide Web
**Importance: 6/10** · short note

- WWW = distributed hypertext system on the Internet (Tim Berners-Lee, CERN, 1989). Pages written in **HTML**, identified by **URL** (protocol://host:port/path), transferred by **HTTP** (port 80) / **HTTPS** (443, TLS).
- **Client–server:** browser sends HTTP request (GET, POST, HEAD, PUT, DELETE); server returns a response with status code (200 OK, 301 moved, 404 not found, 500 server error).
- HTTP is **stateless**; state kept with **cookies** and sessions. HTTP/1.1 persistent connections; HTTP/2 multiplexing.
- Static vs dynamic pages (server-side PHP/ASP/JSP; client-side JavaScript). Proxy/web caching speeds access.

### Likely questions with model answers (Unit 7)

**Q. Differentiate between hub, switch, bridge, router and gateway.** *(5 marks · Likelihood 9/10)*

A **hub** works at the physical layer; it is a multi-port repeater that copies every incoming bit to all other ports, so all ports share one collision domain. A **bridge** works at the data-link layer; it joins two LAN segments and forwards a frame only if the destination MAC address is on the other side, separating collision domains. A **switch** is a multi-port bridge: it learns MAC addresses into a table and sends each frame only to the port of the destination, allowing full-duplex, collision-free links. A **router** works at the network layer; it connects different networks and forwards packets using IP addresses and routing tables, and it blocks broadcasts (separate broadcast domains). A **gateway** may operate at all seven layers; it translates between completely different protocols or architectures (e.g. an e-mail gateway between two mail systems). In short, hub and repeater = L1, bridge and switch = L2, router = L3, gateway = L4–L7.

**Q. Explain narrowband ISDN. Distinguish BRI and PRI.** *(5 marks · Likelihood 7/10)*

ISDN (Integrated Services Digital Network) is an ITU standard for an end-to-end digital telephone network carrying voice, data and fax together over the existing copper local loop. Channels: the **B (bearer) channel** of 64 kbit/s carries user voice or data; the **D (delta) channel** carries out-of-band signalling (call setup) and can carry low-rate packet data. **Basic Rate Interface (BRI) = 2B + D** — two 64 kbit/s B channels and one 16 kbit/s D channel = 144 kbit/s of user capacity (192 kbit/s with framing), for homes and small offices. **Primary Rate Interface (PRI) = 23B + D** in North America/Japan (fits a T1 of 1.544 Mbit/s) or **30B + D** in Europe/India (fits an E1 of 2.048 Mbit/s), with a 64 kbit/s D channel — for organisations and PBXs. Equipment includes NT1, TE1 and terminal adapters. Narrowband ISDN was succeeded by broadband ISDN based on ATM (53-byte cells) and later by DSL.

**Q. What is a firewall? Explain its types.** *(5 marks · Likelihood 8/10)*

A firewall is hardware or software placed between a trusted internal network and an untrusted network (Internet) that permits or blocks traffic according to a security policy; all traffic must pass through it. Types: (1) **Packet-filtering firewall** (L3/L4) inspects each packet's source and destination IP, protocol and port numbers against an access-control list; fast and cheap, but stateless and unable to see application content. (2) **Stateful inspection firewall** additionally keeps a table of active connections, allowing only packets that belong to an established session. (3) **Application-level gateway / proxy firewall** (L7) runs a proxy for each service (HTTP, FTP, SMTP); the client talks to the proxy, which inspects content, authenticates users and logs activity before forwarding — most secure but slowest. (4) **Circuit-level gateway** (L5) validates the TCP handshake and then relays bytes. Firewalls are often deployed with a DMZ for public servers. They cannot stop insider attacks or traffic that bypasses them.

**Q. Explain DNS and its resource records.** *(5 marks · Likelihood 8/10)*

The Domain Name System is a distributed, hierarchical naming database that translates domain names into IP addresses. The name space is a tree: root, top-level domains (.com, .org, .in), second-level domains and hosts. The tree is divided into zones, each served by primary and secondary authoritative name servers; root and TLD servers provide referrals, and local resolvers cache results for the TTL. A client sends a recursive query to its local resolver, which queries root, TLD and authoritative servers iteratively, over UDP port 53. Each zone stores **resource records** (Domain, TTL, Class, Type, Value): **A** (name → IPv4), **AAAA** (name → IPv6), **MX** (mail server with priority), **CNAME** (alias → canonical name), **NS** (name server of the zone), **PTR** (reverse IP → name), and **SOA** (zone authority with serial number and refresh, retry, expire timers).

**Q. Compare symmetric-key and public-key cryptography. How does a digital signature work?** *(5 marks · Likelihood 9/10)*

In **symmetric** cryptography sender and receiver share one secret key used both to encrypt and decrypt (DES with 56-bit key, AES with 128/192/256-bit keys). It is fast and suits bulk data, but the key must be distributed secretly and n users need n(n−1)/2 keys. In **public-key** cryptography each user has a key pair; anything encrypted with the public key can be decrypted only with the matching private key (RSA, based on the difficulty of factoring n = pq; Diffie-Hellman). It solves key distribution and needs only 2n keys, but is slow, so in practice it is used to exchange a symmetric session key (hybrid, e.g. TLS). **Digital signature:** the sender computes a hash (SHA-256) of the message and encrypts the hash with her private key; the signature is sent with the message. The receiver decrypts the signature with the sender's public key and compares it with a freshly computed hash; a match proves authenticity, integrity and non-repudiation.

**Q. Explain internetworking: concatenated virtual circuits, tunnelling and fragmentation.** *(10 marks · Likelihood 7/10)*

Internetworking joins networks that differ in addressing, packet size, service type (connection-oriented or connectionless), and quality of service, using multiprotocol routers or gateways. **Concatenated virtual circuits:** if every network on the path offers connection-oriented service, the source sets up a virtual circuit to a gateway at the edge of its network; that gateway records the circuit and sets up a VC through the next network to the next gateway, and so on until the destination. Each gateway keeps a table mapping (incoming VC → outgoing VC). Data packets then traverse the same path, in order, and resources can be reserved, giving QoS; the drawbacks are table space in every gateway and vulnerability to gateway failure, and it cannot be used if a network on the path is datagram-only. The alternative is the **connectionless (datagram) model** used by IP, where each packet is routed independently. **Tunnelling:** used when the source and destination networks are of the same type but the network in between is different, e.g. two IPv6 islands joined by an IPv4 backbone, or two offices of an organisation joined across the Internet. The entry router encapsulates the whole original packet as the payload of a packet of the middle network; the exit router strips the outer header and delivers the original. The middle network sees only ordinary packets. VPNs (IPsec, GRE) work this way; the analogy is a car carried on a train through a tunnel. **Fragmentation:** every network has a maximum transfer unit (Ethernet 1500 bytes) due to hardware, protocol or standards limits. A packet larger than the next network's MTU must be split into fragments. In **transparent fragmentation** the exit gateway of the small-packet network reassembles fragments, so later networks never see them (requires all fragments to leave by the same gateway). In **non-transparent fragmentation** (IPv4) fragments travel independently and only the destination host reassembles them; IPv4 uses the 16-bit Identification, the DF and MF flags and the 13-bit Fragment Offset (units of 8 bytes). Example: a 4000-byte datagram (20-byte header + 3980 data) over 1500-byte MTU → fragments with 1480, 1480 and 1020 data bytes, offsets 0, 185, 370, MF = 1, 1, 0. IPv6 forbids router fragmentation and relies on path-MTU discovery.

**Q. Compare distance-vector and link-state routing. Explain Dijkstra's algorithm with an example.** *(10 marks · Likelihood 7/10)*

Use 7.11–7.12: definition of routing; distance-vector (Bellman-Ford update D(x,y) = min over neighbours v of {c(x,v) + Dv(y)}, exchanged with neighbours only, RIP, count-to-infinity and its cures); link-state (hello packets to learn neighbours, measure cost, build and flood LSPs with sequence numbers and age, each router runs Dijkstra; OSPF); a comparison table; then Dijkstra steps on the A-B-C-D example with a table of tentative and permanent labels at each step and the resulting shortest-path tree (B = 2, C = 3, D = 4).

**Q. Describe the structure of the telephone system: local loop, trunks, multiplexing and switching.** *(15 marks · Likelihood 7/10)*

The public switched telephone network (PSTN) was designed for voice and is the backbone over which much data has historically been carried. It has three major components: **local loops**, **trunks** and **switching offices**. **Local loop:** the two-wire copper twisted pair linking each subscriber's telephone to the nearest **end office** (central office), often called the "last mile". It carries analog signals; at the end office a **codec** digitises voice by PCM — 8000 samples per second (twice the 4 kHz voice band, Nyquist) × 8 bits = 64 kbit/s. For data, modems convert digital bits to analog tones (limited by Shannon to about 30–56 kbit/s on a 3 kHz line with 30 dB SNR: 3000 × log₂ 1001 ≈ 29.9 kbit/s), while **DSL** uses the full copper bandwidth (above 4 kHz) for broadband. **Trunks:** digital, high-bandwidth links (optical fibre, microwave) between switching offices — end office to toll office to intermediate switching offices. Because laying cables is costly, many conversations share one trunk by **multiplexing**. (a) **FDM** divides the bandwidth into frequency bands, one per channel, separated by guard bands — e.g. 12 voice channels of 4 kHz grouped in 60–108 kHz; used in analog systems, radio and TV. (b) **TDM** gives each channel a fixed time slot in a repeating frame; it suits digital signals. The North American **T1** carrier multiplexes 24 PCM channels: 24 × 8 bits + 1 framing bit = 193 bits every 125 µs = **1.544 Mbit/s**; the European/Indian **E1** has 32 slots of 8 bits = **2.048 Mbit/s** (30 voice + 2 control). Higher levels form the digital hierarchy (T2, T3) and SONET/SDH (OC-3 = 155.52 Mbit/s). (c) **WDM** is FDM at optical frequencies: several wavelengths (colours) of light share one fibre, combined by a prism/grating and separated at the far end; DWDM puts dozens of channels each at 10–100 Gbit/s on a fibre. **Switching:** the end and toll offices contain switches that connect calls. In **circuit switching** (the telephone system) a dedicated end-to-end physical path is set up before communication (call setup delay), and the bandwidth is reserved for the whole call whether used or not; after setup there is no congestion and delay is constant. In **message switching** no path is set up; the whole message is stored at each switch and forwarded (store-and-forward), so there is no size limit but delays and buffer requirements are large; it suits telegraphy. In **packet switching** messages are cut into small packets with an upper size limit; each is stored and forwarded independently, so lines are shared efficiently, transmission is pipelined and delay is low, but packets may be reordered or lost under congestion; the Internet works this way, either as datagrams or as virtual circuits. Comparison: circuit switching — setup required, dedicated path, fixed bandwidth, charged by time, no store-and-forward; packet switching — no setup, shared path, dynamic bandwidth, charged by volume, store-and-forward. Draw a sketch of subscriber → local loop → end office → trunk → toll office → trunk → end office → local loop → subscriber, and a TDM frame of slots 1…n. The telephone system has evolved into an all-digital core (ISDN: BRI 2B+D, PRI 23B+D/30B+D), with only the local loop still analog in many places, and is now migrating to IP (VoIP) networks.

## Unit 8 — Operating Systems, UNIX & Windows

### Main functions of an Operating System
**Importance: 9/10** · first syllabus phrase of the unit — classic 5-marker
In simple words: the OS is the manager between user programs and hardware — it shares the hardware fairly and safely.

| Function | What it does |
|---|---|
| Process management | create/delete, schedule, suspend/resume processes; synchronisation; deadlock handling |
| Memory management | track which memory is used by whom; allocate/free; virtual memory |
| File management | create/delete files & directories, map files to disk, backup |
| Device (I/O) management | device drivers, buffering, caching, spooling |
| Secondary-storage management | free-space management, allocation, disk scheduling |
| Protection & security | control access to resources; defend against attacks |
| User interface | CLI (shell), GUI, batch |
| Accounting & error detection | usage statistics, logs, error handling |

Exam tip: say "OS acts as a **resource allocator** and a **control program**" (Silberschatz). Logs/accounting = forensic artifacts.

### Multiprogramming vs Multiprocessing vs Multitasking
**Importance: 8/10** · "differentiate" bait; also MCQ

| Aspect | Multiprogramming | Multitasking (time-sharing) | Multiprocessing |
|---|---|---|---|
| Idea | several jobs in memory; CPU switches when a job waits for I/O | CPU switched among tasks by time slice so each user feels interactive | two or more CPUs in one system |
| CPUs | 1 | 1 (or more) | ≥ 2 |
| Goal | maximise CPU utilisation | minimise response time | throughput, reliability (graceful degradation) |
| Switch trigger | I/O wait (non-preemptive) | timer interrupt (preemptive) | true parallel execution |
| Example | early batch mainframes | UNIX, Windows desktop | SMP servers, multicore PCs |

Multiprocessing types: **symmetric (SMP)** — every CPU runs OS & user code; **asymmetric** — one master CPU controls slaves.

### Memory management — virtual memory, paging, fragmentation
**Importance: 9/10** · syllabus phrase; paging diagram is a frequent 10-marker
In simple words: chop programs and RAM into equal pieces so a program need not sit in one contiguous block, and keep only needed pieces in RAM.

- **Paging:** logical memory → fixed **pages**; physical memory → same-size **frames**. Logical address = (page number p, offset d). Page table maps p → frame f; physical address = f × page size + d.
- **Virtual memory:** only part of a program is in RAM; the rest on disk (swap). **Demand paging** loads a page only on a **page fault**. Lets programs larger than RAM run and raises multiprogramming degree.
- **Page replacement:** FIFO, Optimal (replace page used farthest in future), LRU. FIFO suffers **Belady's anomaly**.
- **Thrashing:** too many page faults, CPU busy swapping → fix with working-set model / fewer processes.
- **TLB:** small associative cache of page-table entries; EAT = h(t+m) + (1−h)(t+2m).


<div class="fig">
<svg viewBox="0 0 680 260" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u8-arr1" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="260" fill="#fff"/>
<rect x="10" y="90" width="56" height="40" fill="#f1f3f4" stroke="#222"/><text x="38" y="115" text-anchor="middle">CPU</text>
<line x1="66" y1="110" x2="98" y2="110" stroke="#222" marker-end="url(#u8-arr1)"/>
<rect x="100" y="90" width="40" height="40" fill="#e8f0fe" stroke="#222"/><text x="120" y="115" text-anchor="middle">p</text>
<rect x="140" y="90" width="40" height="40" fill="#e6f4ea" stroke="#222"/><text x="160" y="115" text-anchor="middle">d</text>
<text x="114" y="152" text-anchor="end" font-size="11">logical address</text>
<rect x="240" y="60" width="80" height="32" fill="#fff" stroke="#222"/>
<rect x="240" y="92" width="80" height="32" fill="#fff" stroke="#222"/>
<rect x="240" y="124" width="80" height="32" fill="#fef7e0" stroke="#222"/><text x="280" y="145" text-anchor="middle">f</text>
<rect x="240" y="156" width="80" height="32" fill="#fff" stroke="#222"/>
<rect x="240" y="188" width="80" height="32" fill="#fff" stroke="#222"/>
<text x="280" y="240" text-anchor="middle" font-size="11">page table</text>
<path d="M120,130 L120,170 L200,170 L200,140 L238,140" fill="none" stroke="#222" marker-end="url(#u8-arr1)"/>
<text x="160" y="185" text-anchor="middle" font-size="11">index by p</text>
<path d="M320,140 L400,140 L400,132" fill="none" stroke="#222" marker-end="url(#u8-arr1)"/>
<path d="M160,90 L160,45 L440,45 L440,88" fill="none" stroke="#222" marker-end="url(#u8-arr1)"/>
<text x="300" y="40" text-anchor="middle" font-size="11">offset d copied unchanged</text>
<rect x="380" y="90" width="40" height="40" fill="#fef7e0" stroke="#222"/><text x="400" y="115" text-anchor="middle">f</text>
<rect x="420" y="90" width="40" height="40" fill="#e6f4ea" stroke="#222"/><text x="440" y="115" text-anchor="middle">d</text>
<text x="420" y="160" text-anchor="middle" font-size="11">physical address</text>
<line x1="460" y1="110" x2="538" y2="110" stroke="#222" marker-end="url(#u8-arr1)"/>
<rect x="540" y="30" width="120" height="32" fill="#fff" stroke="#222"/>
<rect x="540" y="62" width="120" height="32" fill="#fff" stroke="#222"/>
<rect x="540" y="94" width="120" height="32" fill="#fef7e0" stroke="#222"/><text x="600" y="115" text-anchor="middle">frame f</text>
<rect x="540" y="126" width="120" height="32" fill="#fff" stroke="#222"/>
<rect x="540" y="158" width="120" height="32" fill="#fff" stroke="#222"/>
<rect x="540" y="190" width="120" height="32" fill="#fff" stroke="#222"/>
<text x="600" y="240" text-anchor="middle" font-size="11">physical memory</text>
</svg>
<div class="cap">Fig: Paging hardware — page number p indexes the page table to get frame f; offset d is appended unchanged</div>
</div>

| Fragmentation | Cause | Remedy |
|---|---|---|
| **Internal** | fixed-size block bigger than request (last page partly unused) | smaller pages / variable partitions |
| **External** | free memory is enough in total but not contiguous (variable partitions, segmentation) | compaction, paging |

Exam tip (forensic angle): pagefile.sys / swap and hiberfil.sys hold RAM contents → valuable evidence of passwords, keys, chats.

### Concurrent processing — mutual exclusion, critical regions, lock/unlock, semaphores
**Importance: 9/10** · four syllabus phrases in one line → certain question
In simple words: when processes share data, only one at a time may touch it, otherwise results get corrupted (race condition).

- **Race condition:** outcome depends on order of execution of concurrent processes accessing shared data.
- **Critical section/region:** code segment that accesses shared data. Solution must give **mutual exclusion**, **progress**, **bounded waiting**.
- **Mutual exclusion:** at most one process in its critical section at a time.
- **Lock/unlock:** a shared lock variable; `lock()` before entering, `unlock()` after. Must be **atomic** (hardware TestAndSet / Swap), otherwise two processes can both see "free".
- **Critical region (high-level construct, Brinch Hansen/Hoare):** `region v when B do S;` — compiler guarantees S runs with exclusive access to shared variable v, only when condition B holds.
- **Semaphore (Dijkstra):** integer S accessed only through atomic `wait (P)` and `signal (V)`. **Binary** (0/1, mutex lock) and **counting** (number of resource instances).

```
wait(S):   while (S <= 0) ;  /* busy wait */   S--;
signal(S): S++;

do {  wait(mutex);   /* critical section */   signal(mutex);   /* remainder */ } while (1);
```

Blocking version: if S < 0 the process is put on the semaphore queue (no busy wait); signal wakes one. Misuse → deadlock or starvation. Classic problems: producer–consumer (bounded buffer), readers–writers, dining philosophers.

### Scheduling — CPU, I/O and resource scheduling
**Importance: 8/10** · syllabus phrase; Gantt numericals are standard 10-markers
In simple words: deciding who gets the CPU (or disk, or a resource) next.

- **Schedulers:** long-term (job, controls degree of multiprogramming), short-term (CPU), medium-term (swapping).
- **Criteria:** CPU utilisation, throughput, turnaround time (TAT = completion − arrival), waiting time (WT = TAT − burst), response time.
- **Algorithms:** FCFS (convoy effect), SJF (optimal average WT, starvation), SRTF (preemptive SJF), Priority (aging fixes starvation), Round Robin (time quantum), Multilevel (feedback) queue.
- **I/O (disk) scheduling:** FCFS, SSTF, SCAN (elevator), C-SCAN, LOOK, C-LOOK — minimise head movement.
- **Resource scheduling:** allocating printers, tapes, memory etc. among processes — queues per device, spooling, avoiding deadlock and starvation.

**Worked example — SJF (non-preemptive), verified**

| Process | Arrival | Burst |
|---|---|---|
| P1 | 0 | 7 |
| P2 | 2 | 4 |
| P3 | 4 | 1 |
| P4 | 5 | 4 |

At t=0 only P1 → runs 0–7. At t=7 ready: P2(4), P3(1), P4(4) → P3 (7–8), then P2 (8–12, earlier arrival breaks tie), P4 (12–16).

<div class="fig">
<svg viewBox="0 0 680 90" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="680" height="90" fill="#fff"/>
<rect x="40" y="20" width="280" height="36" fill="#e8f0fe" stroke="#222"/><text x="180" y="43" text-anchor="middle">P1</text>
<rect x="320" y="20" width="40" height="36" fill="#e6f4ea" stroke="#222"/><text x="340" y="43" text-anchor="middle">P3</text>
<rect x="360" y="20" width="160" height="36" fill="#fef7e0" stroke="#222"/><text x="440" y="43" text-anchor="middle">P2</text>
<rect x="520" y="20" width="160" height="36" fill="#fce8e6" stroke="#222"/><text x="600" y="43" text-anchor="middle">P4</text>
<text x="40" y="74" text-anchor="middle">0</text><text x="320" y="74" text-anchor="middle">7</text><text x="360" y="74" text-anchor="middle">8</text><text x="520" y="74" text-anchor="middle">12</text><text x="672" y="74" text-anchor="end">16</text>
</svg>
<div class="cap">Fig: Gantt chart — SJF non-preemptive (scale 40 px per time unit)</div>
</div>

| Process | Completion | TAT = C − A | WT = TAT − B |
|---|---|---|---|
| P1 | 7 | 7 | 0 |
| P2 | 12 | 10 | 6 |
| P3 | 8 | 4 | 3 |
| P4 | 16 | 11 | 7 |
| **Average** | | **32/4 = 8** | **16/4 = 4** |

### Deadlock — four conditions and handling
**Importance: 9/10** · evergreen; "conditions + methods" is a standard 10-marker
In simple words: a set of processes each holding something and waiting for something another one holds — nobody moves.

| Coffman condition (all four needed) | Meaning |
|---|---|
| Mutual exclusion | at least one resource non-sharable |
| Hold and wait | process holds one resource while waiting for another |
| No preemption | resource released only voluntarily |
| Circular wait | P0 → P1 → … → Pn → P0 waiting chain |

**Handling:** (1) **Prevention** — deny one condition (e.g. total ordering of resources kills circular wait; request all at once kills hold-and-wait). (2) **Avoidance** — grant only if the system stays in a **safe state** (Banker's algorithm; RAG with claim edges). (3) **Detection & recovery** — wait-for graph / detection algorithm, then kill processes or preempt resources (rollback). (4) **Ignore** — ostrich approach (UNIX, Windows).

### Disk management — formatting, boot block, free-space management
**Importance: 9/10** · forensic examiners love formatting/boot block (evidence recovery)
In simple words: preparing a raw disk to hold files, starting the computer from it, and tracking free blocks.

| | Low-level (physical) formatting | High-level (logical) formatting |
|---|---|---|
| Done by | manufacturer | OS (format, mkfs) |
| Creates | sectors: header + data area (512 B / 4 KB) + trailer with **ECC**, sector numbers | file system: boot sector, FAT/MFT/inodes, root directory, free-space map |
| Data effect | overwrites everything | quick format only rewrites metadata — **old data remains recoverable** (file carving) |

Before high-level format the disk is **partitioned** (MBR or GPT).
**Boot block:** a tiny **bootstrap loader in ROM** (BIOS/UEFI firmware) reads the **boot block** (MBR sector 0 — 446 B boot code + 64 B partition table + 0x55AA signature) from the boot disk, which loads the OS kernel. Disk holding the boot partition = **boot disk / system disk**. Bad blocks are handled by **sector sparing** (remapping) or slipping.

**Free-space management:**

| Method | Idea | Pro / Con |
|---|---|---|
| Bit vector (bitmap) | 1 bit per block; 1 = free, 0 = allocated (Silberschatz) | easy to find contiguous free blocks; map needs memory (1 TB/4 KB blocks → 32 MB map) |
| Linked list | free blocks chained, head pointer kept | no waste; traversal slow |
| Grouping | first free block stores addresses of n free blocks; last of them points to next group | finds many free blocks fast |
| Counting | store (first free block, count of contiguous free blocks) | compact when free space is contiguous |

### RAID levels
**Importance: 8/10** · syllabus item + forensic acquisition twist
In simple words: combine several disks for speed (striping) and/or safety (mirroring/parity).

| Level | Technique | Min disks | Usable capacity | Survives | Use |
|---|---|---|---|---|---|
| RAID 0 | block striping, no redundancy | 2 | n | 0 failures | speed (video editing) |
| RAID 1 | mirroring | 2 | n/2 | 1 disk (per mirror) | OS disks, reliability |
| RAID 5 | block striping + **distributed parity** | 3 | n − 1 | 1 disk | file servers |
| RAID 6 | striping + **dual parity (P+Q)** | 4 | n − 2 | 2 disks | large arrays |
| RAID 10 (1+0) | stripe of mirrors | 4 | n/2 | 1 per mirror pair | databases |

**Forensic note — acquiring a RAID:** (1) photograph and label each disk with its **slot/order**, controller model, cables; (2) image **every member disk separately** through a write-blocker and hash each image; (3) record RAID level, stripe (block) size, disk order, parity rotation from the controller BIOS; (4) reconstruct the logical volume in the forensic tool (EnCase/FTK/X-Ways), or, if reconstruction is impossible (hardware RAID, encryption, server cannot be shut down), do a **live/logical acquisition** of the mounted volume and document why. Never let the controller "rebuild/initialise" the array — it overwrites data.

### Protection & security — domain, access matrix, threats, authentication
**Importance: 9/10** · forensic-heavy; malware definitions are certain MCQs
In simple words: protection = internal rules on who may access what; security = defence against outside attacks.

- **Protection domain:** set of <object, rights> pairs (e.g. <file F, {read, write}>). A process executes in a domain; in UNIX the domain = user-id; switching via setuid.
- **Access matrix:** rows = domains, columns = objects, entry = rights. Stored as **ACL** (column-wise: per object, list of domains+rights — used by Windows NTFS, UNIX rwx) or **capability list** (row-wise: per domain, list of objects+rights).

| Threat | Definition |
|---|---|
| **Trojan horse** | program that appears useful but secretly performs malicious action (e.g. fake login steals passwords) |
| **Virus** | code fragment that attaches to a host program/file and replicates when host runs; needs user action |
| **Worm** | standalone program that self-replicates over the network without a host (Morris worm 1988) |
| **Logic bomb** | code that triggers damage when a condition occurs (date, employee removed from payroll) |
| **Trap door (backdoor)** | secret entry point bypassing normal authentication, left by the programmer |
| **Rootkit** | toolkit that hides attacker presence (files, processes, registry keys) by modifying OS/kernel; detect with offline/memory analysis |

Others: spyware, ransomware, keylogger, DoS/DDoS, port scanning, buffer overflow, man-in-the-middle.

**User authentication:** (1) **something you know** — password (store as salted hash, one-time passwords, aging); (2) **something you have** — smart card, token, OTP device; (3) **something you are** — **biometrics** (fingerprint, iris, face, voice; FAR vs FRR trade-off). **MFA / two-factor** = combine two or more different categories (password + OTP).

### UNIX architecture
**Importance: 8/10** · UNIX section is half of this unit — layered diagram expected
In simple words: an onion — hardware in the middle, kernel around it, shell around the kernel, user commands outside.

<div class="fig">
<svg viewBox="0 0 680 320" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="680" height="320" fill="#fff"/>
<ellipse cx="340" cy="160" rx="320" ry="150" fill="#f1f3f4" stroke="#222"/>
<ellipse cx="340" cy="160" rx="230" ry="108" fill="#e6f4ea" stroke="#222"/>
<ellipse cx="340" cy="160" rx="145" ry="68" fill="#e8f0fe" stroke="#222"/>
<ellipse cx="340" cy="160" rx="70" ry="32" fill="#fef7e0" stroke="#222"/>
<text x="340" y="165" text-anchor="middle" font-weight="bold">Hardware</text>
<text x="340" y="115" text-anchor="middle" font-weight="bold">Kernel</text>
<text x="340" y="215" text-anchor="middle" font-size="11">process, memory, file, device mgmt</text>
<text x="340" y="70" text-anchor="middle" font-weight="bold">Shell (sh, bash, csh, ksh)</text>
<text x="340" y="250" text-anchor="middle" font-size="11">command interpreter / system-call interface</text>
<text x="340" y="32" text-anchor="middle" font-weight="bold">Utilities &amp; application programs</text>
<text x="340" y="292" text-anchor="middle" font-size="11">ls, cp, grep, vi, cc, sort, awk, user programs</text>
</svg>
<div class="cap">Fig: Layered UNIX architecture — hardware, kernel, shell, utilities/applications</div>
</div>

- **Kernel:** core resident program — process scheduling, memory management, file system, device drivers, system calls.
- **Shell:** reads a command, interprets it, invokes programs via system calls (fork/exec).
- **Utilities:** small tools that "do one thing well" and combine with pipes.
- UNIX features: multiuser, multitasking, portable (written in C), hierarchical file system, "everything is a file".

### UNIX file system — inode & directory tree
**Importance: 9/10** · inode is the #1 UNIX forensic concept (timestamps, deleted files)
In simple words: every file has an inode — an ID card holding all info about the file except its name, plus pointers to its data blocks.

- Disk layout: **boot block | super block** (FS size, free-block list, inode count) **| inode list | data blocks**.
- **Inode** holds: type & permissions (mode), owner UID/GID, size, link count, timestamps **atime, mtime, ctime**, and **block pointers** (classically 12 direct, 1 single, 1 double, 1 triple indirect). **File name is not in the inode** — it is in the directory entry (name → inode number).
- Max file (4 KB blocks, 4-byte pointers → 1024 ptrs/block): 12×4 KB + 1024×4 KB + 1024²×4 KB + 1024³×4 KB ≈ 48 KB + 4 MB + 4 GB + 4 TB.

<div class="fig">
<svg viewBox="0 0 680 300" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u8-arr2" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="300" fill="#fff"/>
<rect x="20" y="10" width="170" height="280" fill="#e8f0fe" stroke="#222"/>
<text x="105" y="28" text-anchor="middle" font-weight="bold">inode</text>
<text x="30" y="48">mode / permissions</text><text x="30" y="66">owner UID, GID</text><text x="30" y="84">size, link count</text><text x="30" y="102">atime, mtime, ctime</text>
<rect x="30" y="112" width="150" height="80" fill="#fff" stroke="#222"/><text x="105" y="140" text-anchor="middle">direct 0 … 11</text><text x="105" y="160" text-anchor="middle" font-size="11">(12 pointers)</text>
<rect x="30" y="198" width="150" height="26" fill="#fff" stroke="#222"/><text x="105" y="216" text-anchor="middle">single indirect</text>
<rect x="30" y="228" width="150" height="26" fill="#fff" stroke="#222"/><text x="105" y="246" text-anchor="middle">double indirect</text>
<rect x="30" y="258" width="150" height="26" fill="#fff" stroke="#222"/><text x="105" y="276" text-anchor="middle">triple indirect</text>
<rect x="560" y="120" width="100" height="40" fill="#e6f4ea" stroke="#222"/><text x="610" y="145" text-anchor="middle">data blocks</text>
<line x1="180" y1="150" x2="556" y2="140" stroke="#222" marker-end="url(#u8-arr2)"/>
<rect x="250" y="198" width="90" height="26" fill="#fef7e0" stroke="#222"/><text x="295" y="216" text-anchor="middle" font-size="11">ptr block</text>
<line x1="180" y1="211" x2="246" y2="211" stroke="#222" marker-end="url(#u8-arr2)"/>
<line x1="340" y1="211" x2="556" y2="150" stroke="#222" marker-end="url(#u8-arr2)"/>
<rect x="250" y="234" width="90" height="26" fill="#fef7e0" stroke="#222"/><text x="295" y="252" text-anchor="middle" font-size="11">ptr block</text>
<rect x="380" y="234" width="90" height="26" fill="#fef7e0" stroke="#222"/><text x="425" y="252" text-anchor="middle" font-size="11">ptr block</text>
<line x1="180" y1="241" x2="246" y2="246" stroke="#222" marker-end="url(#u8-arr2)"/>
<line x1="340" y1="247" x2="376" y2="247" stroke="#222" marker-end="url(#u8-arr2)"/>
<line x1="470" y1="247" x2="560" y2="160" stroke="#222" marker-end="url(#u8-arr2)"/>
<text x="250" y="288" font-size="11">triple indirect: three levels of pointer blocks → data</text>
<line x1="180" y1="271" x2="246" y2="280" stroke="#222" marker-end="url(#u8-arr2)"/>
</svg>
<div class="cap">Fig: UNIX inode — 12 direct pointers plus single, double and triple indirect pointer blocks</div>
</div>

**Directory tree:** single rooted hierarchy `/` → `/bin` (commands), `/etc` (config, passwd, shadow), `/home` (users), `/dev` (device files), `/tmp`, `/var` (logs — `/var/log`), `/usr`, `/boot`. Paths are absolute (`/home/ram/a.txt`) or relative (`../a.txt`). **Hard link** = another name for the same inode; **soft (symbolic) link** = small file containing a path.
Forensic tip: deleting a file removes the directory entry and decrements link count; data blocks stay until reused → recoverable.

### UNIX process management
**Importance: 7/10** · syllabus phrase; fork/exec is a favourite 5-marker

- Every process has a **PID**, parent **PPID**; `init`/`systemd` (PID 1) is the ancestor.
- **fork()** creates a child (copy of parent); returns 0 in child, child's PID in parent, −1 on error. **exec()** replaces the process image with a new program. **wait()** parent waits for child; **exit()** terminates. Dead child not yet waited for = **zombie**; child whose parent died = **orphan** (adopted by init).

| Command | Purpose |
|---|---|
| `ps -ef` / `ps aux` | list processes |
| `top` | live process view |
| `kill -9 PID` | send signal (9 = SIGKILL, 15 = SIGTERM default) |
| `nice -n 10 cmd` / `renice` | run with lower priority (nice −20 highest … 19 lowest) |
| `cmd &` | run in background; `jobs`, `fg`, `bg` manage it |
| `nohup cmd &` | keep running after logout |

### Shell variables & command-line programming
**Importance: 7/10** · syllabus phrase; MCQ on `$?`, `$$`, `$#`

| Variable | Meaning |
|---|---|
| `PATH` | directories searched for commands |
| `HOME` | user's home directory |
| `PS1` | primary prompt; `SHELL`, `USER`, `PWD` |
| `$?` | exit status of last command (0 = success) |
| `$$` | PID of current shell |
| `$#` | number of positional arguments |
| `$0`, `$1…$9` | script name, arguments; `$*` / `$@` all arguments |

```sh
#!/bin/sh
# count.sh — report lines in each file given as argument
if [ $# -eq 0 ]; then
    echo "usage: $0 file..."; exit 1
fi
for f in "$@"; do
    if [ -f "$f" ]; then
        n=$(wc -l < "$f")
        echo "$f : $n lines"
    else
        echo "$f : not found"
    fi
done
echo "script PID = $$, last status = $?"
```

Run: `chmod +x count.sh; ./count.sh a.txt b.txt`. Variables: `name=value` (no spaces), `export name` makes it an environment variable.

### UNIX filters & commands
**Importance: 8/10** · filters + pipes are high-yield MCQs and 5-markers
In simple words: a **filter** reads standard input, transforms it, writes standard output — so commands chain with pipes.

| Command | Use | Example |
|---|---|---|
| `grep` | search lines matching pattern | `grep -i "error" /var/log/syslog` |
| `sort` | sort lines | `sort -n -r marks.txt` |
| `cut` | extract columns | `cut -d: -f1 /etc/passwd` |
| `wc` | count lines/words/chars | `wc -l file` |
| `head` / `tail` | first / last lines | `tail -f log` (follow) |
| `uniq` | remove adjacent duplicates | `sort f | uniq -c` |
| `tr` | translate characters | `tr 'a-z' 'A-Z' < f` |
| `sed` | stream editor | `sed 's/old/new/g' f` |
| `awk` | pattern–action field processing | `awk -F: '{print $1,$3}' /etc/passwd` |
| `find` | search files by attributes | `find / -mtime -2 -name "*.jpg"` |
| `chmod` | change permissions | `chmod 754 f` = rwx r-x r-- |

**Redirection & pipes:** `>` overwrite stdout, `>>` append, `<` stdin, `2>` stderr, `2>&1` merge, `|` pipe stdout of one into stdin of next. Example: `cut -d: -f7 /etc/passwd | sort | uniq -c` → count users per login shell.
Forensic tip: `find / -newer x`, `grep -r`, `md5sum/sha256sum`, `dd if=/dev/sdb of=img.dd` are typical examiner commands.

### Windows OS — design principles
**Importance: 7/10** · syllabus copies Silberschatz "Windows XP" chapter verbatim

| Principle | How Windows achieves it |
|---|---|
| **Extensibility** | layered, modular executive; environmental subsystems in user mode; new subsystems/drivers added without kernel change |
| **Portability** | written in C/C++; hardware-dependent code isolated in **HAL** |
| **Reliability** | hardware memory protection, user/kernel mode, NTFS recovery (logging), driver verification |
| **Compatibility** | runs POSIX, Win16/MS-DOS (via VDM) and Win32 apps through subsystems |
| **Performance** | preemptive priority scheduling, threads, SMP support, fast LPC message passing |
| **Security** | ACL-based discretionary access control, Security Reference Monitor, auditing (C2 certification) |
| International support | Unicode, National Language Support API |

### Windows system components
**Importance: 8/10** · layered diagram + executive components = likely 10-marker

<div class="fig">
<svg viewBox="0 0 680 330" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<rect x="0" y="0" width="680" height="330" fill="#fff"/>
<text x="10" y="22" font-weight="bold">User mode</text>
<rect x="20" y="30" width="140" height="40" fill="#e6f4ea" stroke="#222"/><text x="90" y="55" text-anchor="middle">Logon process</text>
<rect x="175" y="30" width="150" height="40" fill="#e6f4ea" stroke="#222"/><text x="250" y="55" text-anchor="middle">Security subsys (LSA)</text>
<rect x="340" y="30" width="150" height="40" fill="#e6f4ea" stroke="#222"/><text x="415" y="55" text-anchor="middle">Win32 subsystem</text>
<rect x="505" y="30" width="155" height="40" fill="#e6f4ea" stroke="#222"/><text x="582" y="55" text-anchor="middle">POSIX / applications</text>
<line x1="10" y1="85" x2="670" y2="85" stroke="#222" stroke-dasharray="6,4"/>
<text x="10" y="103" font-weight="bold">Kernel mode</text>
<rect x="20" y="110" width="640" height="110" fill="#e8f0fe" stroke="#222"/>
<text x="340" y="127" text-anchor="middle" font-weight="bold">Executive</text>
<rect x="30" y="135" width="150" height="34" fill="#fff" stroke="#222"/><text x="105" y="157" text-anchor="middle">Object manager</text>
<rect x="190" y="135" width="150" height="34" fill="#fff" stroke="#222"/><text x="265" y="157" text-anchor="middle">Process manager</text>
<rect x="350" y="135" width="150" height="34" fill="#fff" stroke="#222"/><text x="425" y="157" text-anchor="middle">Virtual memory mgr</text>
<rect x="510" y="135" width="140" height="34" fill="#fff" stroke="#222"/><text x="580" y="157" text-anchor="middle">I/O manager</text>
<rect x="30" y="177" width="150" height="34" fill="#fff" stroke="#222"/><text x="105" y="199" text-anchor="middle" font-size="11">Security ref. monitor</text>
<rect x="190" y="177" width="150" height="34" fill="#fff" stroke="#222"/><text x="265" y="199" text-anchor="middle" font-size="11">LPC facility</text>
<rect x="350" y="177" width="150" height="34" fill="#fff" stroke="#222"/><text x="425" y="199" text-anchor="middle" font-size="11">Cache manager</text>
<rect x="510" y="177" width="140" height="34" fill="#fff" stroke="#222"/><text x="580" y="199" text-anchor="middle" font-size="11">PnP / power, registry</text>
<rect x="20" y="228" width="640" height="34" fill="#fef7e0" stroke="#222"/><text x="340" y="250" text-anchor="middle">Kernel (thread scheduling, interrupts/exceptions, synchronisation)  ·  device drivers</text>
<rect x="20" y="268" width="640" height="26" fill="#fce8e6" stroke="#222"/><text x="340" y="286" text-anchor="middle">Hardware Abstraction Layer (HAL)</text>
<rect x="20" y="298" width="640" height="26" fill="#f1f3f4" stroke="#222"/><text x="340" y="316" text-anchor="middle">Hardware</text>
</svg>
<div class="cap">Fig: Windows (NT/XP family) layered architecture — user-mode subsystems over executive, kernel and HAL</div>
</div>

- **HAL:** hides chipset/hardware differences → portability.
- **Kernel:** thread scheduling (32 priority levels), interrupt & exception handling, low-level synchronisation; never paged out.
- **Executive:** **Object manager** (names, handles, all resources as objects), **Process manager** (create/delete processes & threads), **Virtual memory manager** (paging, page file), **I/O manager** (drivers, file systems, IRPs), **Security reference monitor** (checks every access against ACL, auditing), LPC (local procedure call), cache manager, PnP & power manager, registry (configuration manager).
- **User-mode environmental subsystems:** Win32 (main), POSIX, MS-DOS/Win16 emulation; **logon process (winlogon)** and **security subsystem (LSA)** authenticate users.

### Windows — Terminal Services, Fast User Switching, NTFS, networking
**Importance: 8/10** · named syllabus phrases; NTFS is forensic gold

- **Terminal Services (Remote Desktop):** many users run separate GUI sessions on one server remotely over **RDP**; each session has its own desktop, kernel session space.
- **Fast User Switching:** a second user logs on while the first user's session (programs, files) keeps running in background; switch without logging off. Built on the same session technology as Terminal Services.

**NTFS features:** everything stored in the **Master File Table (MFT)** (each file = MFT record of attributes: $STANDARD_INFORMATION, $FILE_NAME, $DATA); small files **resident** inside MFT; **journaling** ($LogFile) for recovery; **ACL security** per file; **compression** & **EFS encryption**; **Alternate Data Streams (ADS)** — can hide data; hard links, sparse files, disk quotas, volume shadow copies; 64-bit cluster addresses (huge volumes); B+-tree directories. Forensic artifacts: MFT timestamps (MACB), $UsnJrnl, $Recycle.Bin, ADS.

**Networking:** layered — NDIS drivers, transport protocols (TCP/IP, NetBEUI), TDI. **SMB (Server Message Block)** — file & printer sharing protocol (CIFS). **NetBIOS** — API/name service for session-level communication (NetBIOS names, NBT over TCP/IP). Named pipes, mailslots, RPC. **Domains:** group of machines sharing a common security policy and user database managed by a **domain controller**. **Active Directory:** LDAP-based directory service (Windows 2000+) storing users, computers, groups, policies in a hierarchy of domains/trees/forests; Kerberos authentication.

### Likely questions with model answers — Unit 8

**Q. Differentiate between low-level and high-level formatting. What is a boot block?** *(5 marks · Likelihood 8/10)*
**Low-level (physical) formatting** is done by the manufacturer. It divides each track into sectors and writes each sector's header (sector number), data area (512 B or 4 KB) and trailer containing an error-correcting code (ECC). It overwrites the entire surface. **High-level (logical) formatting** is done by the OS after partitioning (MBR/GPT). It writes file-system structures — boot sector, FAT or MFT or inode tables, root directory and free-space map. A quick high-level format only rewrites these structures; user data stays on disk and can be recovered forensically by carving.
The **boot block** holds the bootstrap program. A small loader in ROM (BIOS/UEFI) reads the boot block — on BIOS systems the MBR in sector 0 (446 bytes boot code, 64-byte partition table, signature 0x55AA) — which in turn locates the boot partition and loads the OS kernel. A disk with a boot partition is called a boot disk or system disk.

**Q. Explain Trojan horse, virus, worm, logic bomb and trap door.** *(5 marks · Likelihood 9/10)*
**Trojan horse:** a program that looks legitimate but secretly does something harmful, e.g. a fake login screen that records passwords. **Virus:** a fragment of code embedded in a host program or document that replicates when the host is executed and infects other files; it needs user action to spread. **Worm:** a standalone program that copies itself across a network using vulnerabilities, without a host or user action (e.g. Morris worm 1988), often consuming bandwidth. **Logic bomb:** malicious code inside a legitimate program that activates when a condition becomes true — a date or a programmer's name removed from payroll. **Trap door (backdoor):** a hidden entry point deliberately left by a programmer that bypasses normal authentication. Related: a **rootkit** hides an intruder's files and processes by modifying the OS. Defences: least privilege, code signing, antivirus, patching, auditing and logs.

**Q. Explain inode structure in UNIX with a diagram.** *(5 marks · Likelihood 8/10)*
Every UNIX file is described by an **inode** stored in the inode list (after boot block and super block). It contains the file type and permission bits, owner UID/GID, size, link count, three timestamps (atime – last access, mtime – last content modification, ctime – last inode change) and data-block pointers: 12 direct pointers, one single-indirect, one double-indirect and one triple-indirect pointer (draw the inode figure). The file name is not in the inode; a directory entry maps name → inode number, so hard links are multiple names for one inode. With 4 KB blocks and 4-byte pointers, an indirect block holds 1024 pointers, giving a maximum file of about 48 KB + 4 MB + 4 GB + 4 TB. Small files are reached quickly through direct pointers; large files through indirection. Forensically, inode timestamps reconstruct a timeline and deleted files leave data blocks until reused.

**Q. Explain any five UNIX filters with examples.** *(5 marks · Likelihood 7/10)*
A filter reads standard input, processes it and writes to standard output, so filters can be joined with pipes (`|`). **grep** prints lines matching a pattern: `grep -n "fail" auth.log`. **sort** orders lines: `sort -t: -k3 -n /etc/passwd`. **cut** extracts fields: `cut -d: -f1 /etc/passwd` lists user names. **wc** counts lines, words, characters: `wc -l file`. **uniq** removes adjacent duplicate lines, `-c` counts them. **tr** translates characters: `tr 'a-z' 'A-Z'`. **head/tail** show first/last n lines; `tail -f` follows a growing log. **sed** edits a stream: `sed 's/2025/2026/g'`. **awk** processes fields: `awk -F: '$3>=1000 {print $1}' /etc/passwd`. Combined example: `grep "Failed password" auth.log | awk '{print $11}' | sort | uniq -c | sort -nr | head` lists the IPs trying most brute-force logins.

**Q. What are semaphores? How are they used for mutual exclusion?** *(5 marks · Likelihood 8/10)*
A **semaphore** S is an integer variable that, apart from initialisation, is accessed only through two atomic operations: `wait(S)` (P): while S ≤ 0 wait; then S−−; and `signal(S)` (V): S++. A **binary semaphore** (values 0/1, also called a mutex lock) gives mutual exclusion; a **counting semaphore** controls access to a resource with N instances (initialised to N). For mutual exclusion, processes share `mutex = 1` and execute `wait(mutex); critical section; signal(mutex); remainder section`. The first process makes mutex 0 and enters; others block until it signals. To avoid busy waiting, wait() puts the process in a queue attached to the semaphore and signal() wakes one. Incorrect order (e.g. two semaphores taken in opposite orders) can cause deadlock; unfair wake-up can cause starvation.

**Q. Explain RAID levels. How would you acquire a RAID array as a forensic examiner?** *(10 marks · Likelihood 8/10)*
RAID (Redundant Array of Independent Disks) combines several physical disks into one logical unit for performance and/or reliability, using **striping** (spreading blocks across disks for parallel I/O), **mirroring** (duplicate copies) and **parity** (XOR information to rebuild a lost disk).
- **RAID 0** — block striping without redundancy; min 2 disks; full capacity, best speed; one disk failure loses all data.
- **RAID 1** — mirroring; min 2 disks; 50 % capacity; survives a disk failure; reads faster.
- **RAID 5** — block striping with **distributed parity**; min 3 disks; capacity n−1; survives one failure; write penalty (read-modify-write of parity).
- **RAID 6** — two independent parity blocks (P and Q); min 4 disks; capacity n−2; survives two simultaneous failures.
- **RAID 10 (1+0)** — mirrored pairs then striped; min 4 disks; 50 % capacity; fast and fault tolerant.
(Insert the RAID table.)
**Forensic acquisition:** (1) Before removing anything, photograph the server, label each drive with its bay/slot number and note controller make/model, firmware settings, RAID level, stripe size and disk order. (2) If the system can be shut down, remove each member disk and image it **individually** through a hardware write-blocker into E01/dd images, computing MD5/SHA-256 hashes; record everything in the chain-of-custody form. (3) Rebuild the array virtually in the forensic tool (EnCase, X-Ways, FTK, Linux mdadm on read-only images) using the recorded parameters; verify by finding a valid partition table/file system. (4) If reconstruction is not feasible (proprietary controller, full-disk encryption, critical live server) perform a **live logical acquisition** of the mounted volume, with justification documented. (5) Never allow the controller to initialise, rebuild or "resync" the array, and never boot the original disks — this would overwrite evidence.

**Q. Explain the architecture of UNIX. Describe process management commands.** *(10 marks · Likelihood 7/10)*
UNIX has a layered structure (draw the onion figure). **Hardware** is at the centre. The **kernel** directly controls hardware and provides process management (creation, scheduling, IPC, signals), memory management (paging, swapping), the file system (inodes, buffer cache) and device drivers (character and block devices). Programs access it only through **system calls** (open, read, write, fork, exec). The **shell** (sh, bash, csh, ksh) is the command interpreter: it reads a command line, expands variables and wild cards, sets up redirection and pipes, then forks a child and execs the program. The outer layer contains **utilities and applications** (ls, cp, grep, editors, compilers) designed as small tools combined via pipes. Key features: multiuser, multitasking, portability (C), hierarchical file system, everything-is-a-file, security via user/group permissions.
**Process management:** each process has a PID and PPID; `init`/`systemd` is PID 1. `fork()` duplicates the caller (returns 0 to child, child PID to parent); `exec()` loads a new program into the process; `wait()` lets the parent collect the exit status; `exit()` terminates. A finished child not yet waited for is a **zombie**; one whose parent died is an **orphan** adopted by init. Commands: `ps -ef` lists processes; `top` shows live CPU/memory usage; `kill -15 PID` politely terminates, `kill -9 PID` forces; `nice -n 10 cmd` starts at lower priority (range −20 high to +19 low), `renice` changes it; `cmd &` runs in background, `jobs`, `fg %1`, `bg` control jobs; `nohup` survives logout.

**Q. Describe the design principles and system components of Windows.** *(10 marks · Likelihood 7/10)*
Design goals (Silberschatz): **Extensibility** — layered modular executive; personalities as user-mode subsystems; drivers loadable. **Portability** — written in C/C++; processor-dependent code in the kernel and chipset-dependent code in the **HAL**. **Reliability** — kernel/user mode separation, per-process virtual memory, NTFS journaling, driver verification. **Compatibility** — runs Win32, POSIX, MS-DOS and 16-bit Windows applications. **Performance** — preemptive priority-based threads, SMP, fast LPC message passing, caching. **Security** — logon authentication, ACLs, security reference monitor, auditing. Also international support (Unicode).
Components (draw the layered figure): **HAL** — hides hardware differences. **Kernel** — thread scheduling with 32 priority levels, interrupt/exception dispatch, synchronisation primitives; object-oriented (dispatcher and control objects). **Executive** — Object manager (naming, handles, reference counts for all resources), Process manager (create/terminate processes and threads), Virtual-memory manager (paging, page file, working sets), I/O manager (driver stack, IRPs, file systems, cache manager), Security reference monitor (checks access tokens against ACLs, generates audit records), LPC facility, Plug-and-Play and power managers, registry. **User-mode subsystems** — Win32 environment, POSIX, logon process (winlogon) and Local Security Authority, which authenticate users and create access tokens.

**Q. Explain deadlock: necessary conditions and methods of handling.** *(10 marks · Likelihood 8/10)*
A deadlock is a state where each process in a set waits for a resource held by another process of the set, so none can proceed. Four necessary (Coffman) conditions must hold simultaneously: mutual exclusion, hold and wait, no preemption and circular wait (explain each). It can be modelled by a resource-allocation graph: a cycle with single-instance resources means deadlock.
Handling: (1) **Prevention** — break a condition: spool printers (mutual exclusion), request all resources before starting (hold & wait; low utilisation), preempt resources of a waiting process (no preemption), number resource types and request only in increasing order (circular wait). (2) **Avoidance** — each process declares its maximum need; the OS grants a request only if the resulting state is **safe** (a safe sequence exists). Banker's algorithm computes Need = Max − Allocation and repeatedly finds a process whose Need ≤ Work. (3) **Detection and recovery** — allow deadlock, periodically run a wait-for-graph/detection algorithm, then recover by aborting all or one deadlocked process at a time, or preempting resources with rollback and preventing starvation of the victim. (4) **Ignore** — UNIX and Windows assume deadlocks are rare (ostrich algorithm). Compare: prevention is simple but wasteful, avoidance needs advance information, detection has run-time cost.

**Q. Explain disk management in an operating system: formatting, boot block, bad blocks, free-space management and RAID, with forensic significance.** *(15 marks · Likelihood 7/10)*
**1. Disk formatting.** A new disk is a blank magnetic platter (or flash array). **Low-level formatting** (by manufacturer) creates sectors on each track — each has a header and trailer with sector number and ECC, and a data area of 512 bytes or 4 KB. The OS then **partitions** the disk into one or more logical disks using an **MBR** (up to 4 primary partitions, 2 TB) or **GPT** (128 partitions, GUIDs, backup header). **High-level (logical) formatting** creates a file system: boot sector, allocation structures (FAT, NTFS MFT, ext inode tables), root directory and free-space map. Raw partitions without a file system are used by some databases and swap.
**2. Boot block.** At power-on the CPU runs firmware (BIOS/UEFI) from ROM. This tiny bootstrap reads the **boot block** — MBR sector 0 (446 B code + 64 B partition table + 0x55AA) or the EFI system partition — which loads the boot loader (GRUB, Windows Boot Manager) and then the kernel. The disk with the boot partition is the boot/system disk.
**3. Bad blocks.** Sectors fail over time. Controllers maintain a list of bad sectors and use **sector sparing** (remap to a spare sector) or **sector slipping**; the OS can mark bad clusters in the file system.
**4. Free-space management.** The OS tracks free blocks: **bit vector** (1 bit/block, 1 = free; simple, fast to find runs, but a 1 TB disk with 4 KB blocks needs a 32 MB map), **linked list** (each free block points to the next; no extra space but slow traversal), **grouping** (first free block stores addresses of n free blocks), **counting** (stores start address and count of contiguous free blocks — compact for extents).
**5. RAID.** Levels 0, 1, 5, 6, 10 provide striping, mirroring and parity (table). RAID 5 survives one disk failure with capacity n−1; RAID 6 two failures with n−2.
**6. Disk scheduling (brief).** FCFS, SSTF, SCAN, C-SCAN, LOOK reduce seek time.
**Forensic significance.** Quick formatting and deletion only change metadata — unallocated space, slack space (end of last cluster) and unpartitioned space still hold data recoverable by carving; therefore examiners image the **entire physical disk** (bit-stream copy, including unallocated and slack) through a write-blocker and verify with hashes. Partition tables and the boot block reveal hidden partitions, deleted partitions and boot-sector malware (bootkits). HPA/DCO areas can hide data. Free-space bitmaps tell which blocks are unallocated. For RAID, each member disk is imaged separately, configuration documented, and the array rebuilt virtually; the original array is never rebuilt on the controller. SSD TRIM and wear levelling can erase deleted data quickly, so SSDs should be acquired promptly.

## Unit 9 — Computer Organization & Architecture

### Basic structure & operational concepts
**Importance: 7/10** · first syllabus phrase — easy 5-marker
In simple words: a computer = input + memory + ALU + control + output, and the CPU repeatedly fetches and executes instructions stored in memory (von Neumann stored-program concept).

- **Functional units:** Input, Output, Memory (primary + secondary), ALU, Control unit (ALU + CU + registers = CPU).
- **Key registers:** **PC** (address of next instruction), **IR** (current instruction), **MAR** (address to memory), **MDR/MBR** (data to/from memory), general-purpose registers R0…Rn, status/flag register.
- **Operational concept:** PC → MAR; Read; MDR → IR; PC ← PC + 1; decode; fetch operands; execute in ALU; store result; check interrupts; repeat.

### Instruction formats (0/1/2/3-address)
**Importance: 8/10** · classic "evaluate X = (A+B)*(C+D)" question

| Format | Example for X = (A+B)×(C+D) | Note |
|---|---|---|
| 3-address | `ADD R1,A,B` · `ADD R2,C,D` · `MUL X,R1,R2` | short programs, long instructions |
| 2-address | `MOV R1,A` · `ADD R1,B` · `MOV R2,C` · `ADD R2,D` · `MUL R1,R2` · `MOV X,R1` | most common (x86) |
| 1-address (accumulator) | `LOAD A` · `ADD B` · `STORE T` · `LOAD C` · `ADD D` · `MUL T` · `STORE X` | AC implied |
| 0-address (stack) | `PUSH A` · `PUSH B` · `ADD` · `PUSH C` · `PUSH D` · `ADD` · `MUL` · `POP X` | operands on stack top (postfix) |

Instruction = opcode + mode + address field(s).

### Instruction execution & sequencing; register transfers; fetch/store word
**Importance: 7/10** · syllabus phrases; micro-operation sequence for a full instruction

- **Sequencing:** instructions run in sequence (PC incremented) unless a **branch/jump** loads a new value into PC; condition codes (N, Z, V, C) decide conditional branches.
- **Register transfer notation:** `R2 ← R1` (copy), `MAR ← [PC]`, `[R1] ← [R1] + [R2]`; with control signal: `P: R2 ← R1`.
- **Fetch a word from memory:** `MAR ← address; Read; wait MFC (memory function complete); R ← MDR`.
- **Store a word:** `MAR ← address; MDR ← data; Write; wait MFC`.

**Execution of a complete instruction `ADD R1, (R3)`** (single-bus organisation, Hamacher):

| Step | Micro-operations / control signals |
|---|---|
| 1 | PCout, MARin, Read, Select4, Add, Zin (PC → MAR, start read, compute PC+4) |
| 2 | Zout, PCin, Yin, WMFC (PC ← PC+4, wait for memory) |
| 3 | MDRout, IRin (instruction → IR) |
| 4 | R3out, MARin, Read (operand address) |
| 5 | R1out, Yin, WMFC |
| 6 | MDRout, SelectY, Add, Zin (R1 + operand) |
| 7 | Zout, R1in, End (result → R1) |

Steps 1–3 = **fetch phase**; 4–7 = **execute phase**.

### Addressing modes
**Importance: 9/10** · near-certain MCQ + 5-marker

| Mode | Example | Effective address / operand |
|---|---|---|
| Immediate | `MOV R1, #5` | operand = 5 (in instruction) |
| Register | `ADD R1, R2` | operand in R2 |
| Direct (absolute) | `LOAD 2000` | EA = 2000 |
| Indirect (memory) | `LOAD (2000)` | EA = M[2000] |
| Register indirect | `LOAD (R1)` | EA = [R1] |
| Indexed | `LOAD 20(R1)` | EA = 20 + [R1] (arrays) |
| Base register | `LOAD 4(BP)` | EA = [base] + displacement |
| Relative (PC-relative) | `BR 50` | EA = [PC] + 50 (branches, relocatable code) |
| Auto-increment | `(R1)+` | EA = [R1], then R1 ← R1 + size |
| Auto-decrement | `−(R1)` | R1 ← R1 − size, then EA = [R1] (stack push) |
| Implied | `CLC`, `PUSH` | operand implicit |

### Stacks, queues & subroutines
**Importance: 7/10** · syllabus phrase; "call/return using stack" 5-marker

- **Stack:** LIFO; stack pointer SP. Push: `SP ← SP − 1; M[SP] ← item` (stack grows downward). Pop: `item ← M[SP]; SP ← SP + 1`.
- **Queue:** FIFO with two pointers (IN/rear, OUT/front), usually circular buffer — used for I/O buffers.
- **Subroutine CALL:** push return address (PC) onto stack, PC ← subroutine address. **RETURN:** PC ← pop. Using a stack allows **nested** and **recursive** calls (link register alone cannot).
- **Stack frame (activation record):** parameters, return address, saved old frame pointer (FP), saved registers, local variables. FP points to a fixed place in the frame; locals at negative offsets, parameters at positive offsets.

### Memory — RAM/ROM types and characteristics
**Importance: 7/10** · MCQ favourite

| Type | Characteristics |
|---|---|
| SRAM | flip-flop cells (6 transistors), fast, no refresh, costly → cache |
| DRAM | capacitor + transistor, needs **refresh**, dense, cheap → main memory (SDRAM, DDR) |
| ROM (mask) | programmed at manufacture |
| PROM | programmed once by user |
| EPROM | erased by UV light |
| EEPROM | erased electrically, byte-wise |
| Flash | electrically erased in blocks; SSD, pen drive, BIOS chip |

RAM is volatile (lost on power off — hence **live RAM acquisition** in forensics); ROM non-volatile.
Characteristics of memory: capacity, access time, cycle time, transfer rate, cost/bit, volatility, access method (random, sequential, direct).

### Memory hierarchy, cache & interleaving
**Importance: 9/10** · cache mapping + AMAT numerical very likely

<div class="fig">
<svg viewBox="0 0 680 260" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u9-arr1" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="260" fill="#fff"/>
<polygon points="300,15 360,15 400,65 260,65" fill="#fce8e6" stroke="#222"/><text x="330" y="45" text-anchor="middle">Registers</text>
<polygon points="260,65 400,65 440,110 220,110" fill="#fef7e0" stroke="#222"/><text x="330" y="93" text-anchor="middle">Cache (L1/L2/L3, SRAM)</text>
<polygon points="220,110 440,110 480,155 180,155" fill="#e6f4ea" stroke="#222"/><text x="330" y="138" text-anchor="middle">Main memory (DRAM)</text>
<polygon points="180,155 480,155 520,200 140,200" fill="#e8f0fe" stroke="#222"/><text x="330" y="183" text-anchor="middle">Secondary: SSD / magnetic disk</text>
<polygon points="140,200 520,200 560,245 100,245" fill="#f1f3f4" stroke="#222"/><text x="330" y="228" text-anchor="middle">Tertiary: tape, optical (backup)</text>
<line x1="80" y1="240" x2="80" y2="25" stroke="#222" marker-end="url(#u9-arr1)"/>
<text x="20" y="130" font-size="11">faster,</text><text x="20" y="145" font-size="11">costlier</text><text x="20" y="160" font-size="11">per bit</text>
<line x1="590" y1="25" x2="590" y2="240" stroke="#222" marker-end="url(#u9-arr1)"/>
<text x="600" y="130" font-size="11">larger,</text><text x="600" y="145" font-size="11">slower,</text><text x="600" y="160" font-size="11">cheaper</text>
</svg>
<div class="cap">Fig: Memory hierarchy — speed and cost rise towards the top, capacity towards the bottom</div>
</div>

- Works because of **locality of reference**: temporal (reuse soon) and spatial (nearby addresses).
- **Cache mapping:** **Direct** — block j → line (j mod number of lines); simple, conflict misses. Address = Tag | Line | Word. **Fully associative** — any block in any line; tags compared in parallel; costly. **Set-associative (k-way)** — block → set (j mod sets), any line within set; compromise. Address = Tag | Set | Word.
- **Replacement:** LRU, FIFO, random. **Write policies:** write-through (update memory every write) vs write-back (dirty bit, write on eviction).
- **Hit ratio** h = hits / total accesses.
- **AMAT = hit time + miss rate × miss penalty.**

**Worked (verified):** hit time 1 ns, miss rate 5 %, miss penalty 100 ns → AMAT = 1 + 0.05 × 100 = **6 ns**.
Alternative (two-level formula): Tc = 10 ns, Tm = 100 ns, h = 0.9. Simultaneous access: T = h·Tc + (1−h)·Tm = 9 + 10 = **19 ns**. Hierarchical (look in cache first): T = Tc + (1−h)·Tm = 10 + 10 = **20 ns**.

**Memory interleaving:** main memory split into n modules (banks). **Low-order interleaving** — consecutive addresses in consecutive modules (module = address mod n), so a block of n words is fetched in parallel → higher bandwidth. **High-order interleaving** — high bits select module; consecutive words in same module (good for expansion, not speed).

### Virtual memory & address translation (TLB); secondary memory
**Importance: 7/10** · overlaps Unit 8 paging

- CPU generates virtual address = (virtual page number, offset). **MMU** translates via page table (page-table base register) to physical frame. Missing page → page fault → OS loads from disk.
- **TLB** (translation look-aside buffer): small associative cache of recent page-table entries; TLB hit avoids extra memory access. Example: TLB 20 ns, memory 100 ns, hit 80 % → EAT = 0.8 × 120 + 0.2 × 220 = 96 + 44 = **140 ns**.
- **Secondary memory:** magnetic disk — platters, tracks, sectors, cylinders; access time = **seek time + rotational latency + transfer time** (avg latency = half a rotation: 7200 rpm → 60/7200/2 s ≈ 4.17 ms). SSD (flash, no moving parts, TRIM, wear levelling), optical (CD/DVD/Blu-ray), magnetic tape (sequential, backup).

### I/O organisation — addressing I/O devices
**Importance: 8/10** · syllabus phrase "memory-mapped, standard, linear selection"

| | Memory-mapped I/O | Isolated (standard / I/O-mapped) I/O | Linear selection |
|---|---|---|---|
| Address space | I/O registers share memory address space | separate I/O address space | each address line directly enables one device/chip |
| Instructions | ordinary load/store (`MOV`) | special `IN`/`OUT` | normal, no full decoder |
| Control lines | MEMR/MEMW | IOR/IOW (IO/M̅ signal in 8085) | — |
| Pro | all addressing modes usable; flexible | full memory space for memory; small I/O addresses (8-bit in 8085) | cheapest, simple hardware |
| Con | reduces memory space | fewer instructions for I/O | wastes address space, few devices, multiple (fold-back) addresses |

### Programmed I/O vs Interrupt-driven I/O vs DMA
**Importance: 9/10** · near-certain 5/10-marker; DMA diagram

| Aspect | Programmed I/O | Interrupt-driven I/O | DMA |
|---|---|---|---|
| CPU role | polls status flag continuously (busy wait) | does other work; device interrupts when ready | only sets up transfer; DMA controller moves block |
| Data path | via CPU registers | via CPU (ISR moves each word) | device ↔ memory directly |
| CPU overhead | highest | moderate (interrupt per word) | lowest (one interrupt per block) |
| Suits | simple, slow devices | keyboard, mouse | disk, network, high-speed block transfer |

<div class="fig">
<svg viewBox="0 0 680 230" width="680" xmlns="http://www.w3.org/2000/svg" font-family="DejaVu Sans, Arial" font-size="12">
<defs><marker id="u9-arr2" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse"><path d="M0,0 L10,5 L0,10 z" fill="#222"/></marker></defs>
<rect x="0" y="0" width="680" height="230" fill="#fff"/>
<rect x="30" y="20" width="120" height="60" fill="#e8f0fe" stroke="#222"/><text x="90" y="55" text-anchor="middle">CPU</text>
<rect x="280" y="20" width="160" height="60" fill="#fef7e0" stroke="#222"/><text x="360" y="45" text-anchor="middle">DMA controller</text><text x="360" y="63" text-anchor="middle" font-size="11">addr reg, count reg</text>
<rect x="520" y="20" width="130" height="60" fill="#e6f4ea" stroke="#222"/><text x="585" y="55" text-anchor="middle">I/O device (disk)</text>
<rect x="30" y="150" width="120" height="50" fill="#f1f3f4" stroke="#222"/><text x="90" y="180" text-anchor="middle">Main memory</text>
<line x1="20" y1="125" x2="660" y2="125" stroke="#222" stroke-width="4"/><text x="420" y="145" font-size="11">system bus (address / data / control)</text>
<line x1="152" y1="35" x2="276" y2="35" stroke="#c5221f" marker-end="url(#u9-arr2)"/><text x="160" y="30" font-size="11">BG (bus grant)</text>
<line x1="276" y1="62" x2="152" y2="62" stroke="#c5221f" marker-end="url(#u9-arr2)"/><text x="160" y="76" font-size="11">BR (bus request)</text>
<line x1="442" y1="40" x2="516" y2="40" stroke="#222" marker-end="url(#u9-arr2)"/><text x="450" y="33" font-size="11">DACK</text>
<line x1="516" y1="65" x2="442" y2="65" stroke="#222" marker-end="url(#u9-arr2)"/><text x="450" y="78" font-size="11">DREQ</text>
<line x1="90" y1="82" x2="90" y2="122" stroke="#222"/><line x1="360" y1="82" x2="360" y2="122" stroke="#222" marker-start="url(#u9-arr2)" marker-end="url(#u9-arr2)"/><line x1="585" y1="82" x2="585" y2="122" stroke="#222" marker-start="url(#u9-arr2)" marker-end="url(#u9-arr2)"/>
<line x1="90" y1="128" x2="90" y2="147" stroke="#222" marker-start="url(#u9-arr2)" marker-end="url(#u9-arr2)"/>
<text x="190" y="215" font-size="11">Data flows device ↔ memory over the bus while the CPU is disconnected; interrupt at end of block</text>
</svg>
<div class="cap">Fig: DMA transfer — device raises DREQ, DMAC raises BR, CPU grants bus (BG), DMAC acknowledges (DACK) and moves the block</div>
</div>

DMA modes: **burst** (whole block, CPU held off), **cycle stealing** (one word per bus cycle), **transparent** (only when CPU not using bus).
**I/O processor (IOP / channel):** a dedicated processor that executes its own I/O programs (channel command words) from memory, handling many devices and multiple DMA transfers, interrupting the CPU only on completion — selector, multiplexer and block-multiplexer channels (IBM mainframes).

### Buses — synchronous vs asynchronous; standard interfaces
**Importance: 7/10** · syllabus phrase; handshaking diagram/explanation

| | Synchronous bus | Asynchronous bus |
|---|---|---|
| Timing | common clock; every transfer in fixed clock cycles | no clock; **handshaking** control signals |
| Speed | fast, simple | adapts to devices of different speed |
| Limitation | clock set by slowest device; clock skew limits length | extra delay from handshake |

**Handshaking (asynchronous read):** master places address & command, raises **Master-ready**; slave decodes, places data, raises **Slave-ready**; master latches data, drops Master-ready; slave drops Slave-ready (full handshake).

| Bus | Key facts |
|---|---|
| PCI / **PCIe** | PCI: parallel, 32/64-bit, 33/66 MHz, plug-and-play. PCIe: serial point-to-point lanes (x1…x16), full duplex, used for GPUs, NVMe SSDs |
| **USB** | serial, hot-pluggable, tiered star, up to 127 devices; 1.1 (12 Mb/s), 2.0 (480 Mb/s), 3.x (5–20 Gb/s); powers devices |
| **SATA** | serial ATA for disks/SSDs, point-to-point; 1.5/3/6 Gb/s; hot-swap; AHCI |
| **SCSI** | parallel bus for disks/tapes in servers, daisy-chained devices with IDs, terminators; successor SAS (serial) |

Forensic note: write-blockers exist for SATA, SAS/SCSI, USB, PCIe/NVMe interfaces.

### Likely questions with model answers — Unit 9

**Q. Compare programmed I/O, interrupt-driven I/O and DMA.** *(5 marks · Likelihood 9/10)*
In **programmed I/O** the CPU issues a command and then repeatedly checks (polls) the device status register until the device is ready, moving every word itself; the CPU is wasted in busy-waiting. In **interrupt-driven I/O** the CPU issues the command and continues other work; when the device is ready it sends an interrupt, the CPU saves its state, runs the interrupt service routine to transfer the word and resumes — better, but each word still costs an interrupt and passes through the CPU. In **DMA** the CPU programs the DMA controller with memory address, word count and direction; the controller requests the bus (BR), receives bus grant (BG) and transfers the whole block directly between device and memory (burst or cycle stealing), interrupting the CPU only once at the end. DMA gives lowest CPU overhead and is used for disks and network cards; programmed I/O suits very simple devices; interrupts suit low-rate devices like keyboards.

**Q. Explain addressing modes with examples.** *(5 marks · Likelihood 8/10)*
The addressing mode tells how the effective address (EA) of an operand is obtained. **Immediate:** operand in the instruction (`MOV R1,#5`). **Register:** operand in a register (`ADD R1,R2`). **Direct/absolute:** address field is the EA (`LOAD 2000`). **Indirect:** address field points to a location holding the EA (`LOAD (2000)`). **Register indirect:** register holds EA (`LOAD (R1)`). **Indexed:** EA = constant + index register (`LOAD 20(R1)`) — for arrays. **Relative:** EA = PC + offset — for branches and position-independent code. **Base:** EA = base register + displacement — for relocation. **Auto-increment/decrement:** EA = [R] then R incremented, or R decremented then used — for stacks and array scanning. **Implied:** operand implicit in opcode (`CLC`). Modes reduce instruction length and support high-level constructs (pointers, arrays, stacks).

**Q. Distinguish memory-mapped I/O and isolated I/O.** *(5 marks · Likelihood 7/10)*
In memory-mapped I/O, device registers are assigned addresses in the same address space as memory; the CPU accesses them with ordinary load/store instructions using all addressing modes and the same MEMR/MEMW control lines. It is flexible but reduces addressable memory. In isolated (standard, I/O-mapped) I/O, devices have a separate address space selected by an IO/M̅ signal; special IN/OUT instructions with IOR/IOW lines are used (8085/8086). The full memory space remains for memory and I/O decoding is simpler, but fewer instructions/addressing modes are available for I/O. In linear selection, individual address lines enable devices directly without a full decoder — cheapest but wastes address space and gives multiple addresses per device.

**Q. Explain cache memory mapping techniques. A cache has hit time 1 ns, miss rate 5 % and miss penalty 100 ns; find AMAT.** *(10 marks · Likelihood 8/10)*
Cache is a small fast SRAM between CPU and main memory, exploiting temporal and spatial locality. Main memory is divided into blocks, cache into lines of equal size. **Direct mapping:** block j goes to line j mod m (m lines). Address = Tag | Line | Word. Only one tag comparison — cheap and fast — but two blocks mapping to the same line keep evicting each other (conflict misses). **Associative mapping:** any block in any line; address = Tag | Word; all tags compared in parallel using associative memory — flexible, highest hit ratio, expensive. **k-way set-associative:** cache has m/k sets of k lines; block j goes to set j mod (m/k) and any line within it; address = Tag | Set | Word — balances cost and hit ratio (2-/4-/8-way common). Example: 64 KB cache, 16-byte blocks, 32-bit address, direct mapped → 4096 lines → word 4 bits, line 12 bits, tag 16 bits.
Replacement (associative/set): LRU, FIFO, random. Write policy: write-through vs write-back with dirty bit.
**AMAT** = hit time + miss rate × miss penalty = 1 + 0.05 × 100 = **6 ns**. If instead Tc = 10 ns, Tm = 100 ns, h = 0.9 with hierarchical access: T = 10 + 0.1 × 100 = 20 ns.

**Q. What is DMA? Explain with block diagram. What is an I/O processor?** *(10 marks · Likelihood 8/10)*
Direct Memory Access lets an I/O device transfer a block of data to/from main memory without the CPU moving each word. **Components** of the DMA controller: address register (next memory address), word-count register, control register (read/write, mode), data buffer and control logic (draw figure). **Operation:** (1) CPU initialises the DMAC with starting address, count, direction and device; (2) device raises DREQ; (3) DMAC raises Bus Request (BR/HOLD); (4) CPU finishes current bus cycle, tri-states its buses and raises Bus Grant (BG/HLDA); (5) DMAC sends DACK to the device and places addresses on the bus, transferring words directly, decrementing count and incrementing address; (6) when count = 0 it releases the bus and interrupts the CPU. **Modes:** burst (block at once — fastest, CPU stalled), cycle stealing (one word per stolen cycle, CPU slowed slightly), transparent (only idle cycles). Advantage: high-speed block transfers with minimal CPU overhead. 
**I/O processor (channel):** a special-purpose processor with its own instruction set that fetches and executes **channel programs** (command words) from memory, controls several devices, performs code conversion/error checks and DMA transfers, and interrupts the CPU only on completion. Types: selector channel (one high-speed device at a time), multiplexer channel (many slow devices interleaved), block-multiplexer.

**Q. Discuss memory hierarchy, cache, interleaving and virtual memory in a computer system.** *(15 marks · Likelihood 6/10)*
Draw the hierarchy figure: registers → cache → main memory → secondary storage → tertiary. Moving down, capacity increases and speed and cost per bit decrease. The goal is memory as fast as the top level at the cost of the bottom, made possible by **locality of reference**.
**Cache:** SRAM, L1/L2/L3; mapping (direct, associative, set-associative) as above; hit ratio; AMAT = hit time + miss rate × penalty (1 + 0.05 × 100 = 6 ns); write-through vs write-back; replacement LRU/FIFO.
**Main memory:** DRAM (refreshing capacitor cells, dense), ROM family for firmware. **Interleaving** splits memory into n banks; low-order interleaving places consecutive addresses in successive banks so n words can be accessed in an overlapped fashion, multiplying bandwidth for cache-block fills; high-order interleaving uses top address bits for the module.
**Virtual memory:** gives each program a large private address space backed by disk. The MMU translates virtual page numbers to physical frames through page tables; a **TLB** caches recent translations (TLB 20 ns, memory 100 ns, 80 % hit → EAT = 0.8 × 120 + 0.2 × 220 = 140 ns). A page fault traps to the OS which loads the page from disk, using replacement (LRU, FIFO). Benefits: programs larger than RAM, protection, sharing, easier relocation. Segmentation gives variable-size logical units.
**Secondary memory:** disk access time = seek + rotational latency + transfer; SSDs remove mechanical delays; tape for archives.
**Forensic relevance:** volatile levels (registers, cache, RAM) are lost on power-off, so order of volatility dictates capturing RAM first (live acquisition); virtual memory leaves RAM contents in the page/swap file and hibernation file on disk, which are imaged with the drive.
