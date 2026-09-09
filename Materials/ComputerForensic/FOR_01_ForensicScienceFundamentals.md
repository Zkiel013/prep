# FOR_01 — Forensic Science Fundamentals
### Covers TP-I Unit 1 (Introduction to Forensic Science), Unit 2 (Physical Evidence), Unit 3 (Scene of Crime)

> This is the block a computer-science graduate knows least and the examiner knows best.
> It is also the *easiest* block to score full marks in, because the answers are lists and
> principles rather than reasoning. Treat it as the highest-return chunk in TP-I.

---

# §1. Introduction to Forensic Science

## 1.1 Concept — the intuition first

Think of a crime as an event that happened in the past and cannot be replayed. A court has two
ways of learning what happened: **people tell it** (witness testimony), or **things tell it**
(physical evidence). People lie, forget, misperceive and are intimidated. Things do none of
those. Forensic science is the discipline of making *things* testify.

The word comes from Latin *forum* — the public place where Roman legal disputes were argued.
"Forensic" therefore literally means "pertaining to the court". So forensic science is not a
science in itself; it is **the application of every science to the questions the law asks.**
Chemistry becomes forensic chemistry when a chemist is asked "is this powder heroin, and is it
from the same batch as the packet in the accused's house?"

Two consequences flow from that "for the court" part, and they explain almost everything else
in this syllabus:

1. **The conclusion must survive cross-examination.** Hence the obsession with documented
   method, validated techniques, and reproducibility.
2. **The evidence must be provably the same object that was at the scene.** Hence the
   **chain of custody** — see §4.5.

## 1.2 Definitions (write one of these, then expand)

- **Forensic Science**: the application of scientific principles, techniques and methods to
  the investigation of crime and to matters of law, for the purpose of establishing facts
  admissible in a court of justice.
- **Criminalistics**: the branch of forensic science concerned with the recognition,
  collection, identification, individualisation and interpretation of *physical evidence*.
  (Often used interchangeably with forensic science, but strictly it is the physical-evidence
  subset — the laboratory side.)
- **Digital / Computer Forensics**: the branch dealing with the identification, preservation,
  extraction, analysis, documentation and presentation of **digital evidence** in a legally
  admissible manner.

## 1.3 History and development

### International milestones

| Period / person | Contribution |
|---|---|
| **c. 250 BC, Archimedes** | The crown/buoyancy problem — often cited as the first "forensic" application of a physical principle to a question of fraud |
| **1248, China — *Xi Yuan Ji Lu* ("Washing Away of Wrongs") by Song Ci** | Earliest known treatise on forensic medicine; distinguishing drowning from strangulation |
| **1814, Mathieu Orfila (Spain/France)** | **"Father of Forensic Toxicology"** — *Traité des poisons*; established toxicology as a discipline |
| **1823, Jan Evangelista Purkinje** | First classification of fingerprint patterns |
| **1879, Alphonse Bertillon (France)** | **Anthropometry / Bertillonage** — the first systematic personal-identification system (body measurements). "Father of Criminal Identification". Superseded by fingerprints. |
| **1880, Henry Faulds & William Herschel** | Published on the use of fingerprints for identification |
| **1892, Francis Galton** | *Finger Prints* — established individuality and permanence of ridge patterns; Galton details (minutiae) |
| **1893, Hans Gross (Austria)** | *Handbuch für Untersuchungsrichter* (Criminal Investigation) — **"Father of Criminalistics"**; coined the term |
| **1901, Karl Landsteiner** | ABO blood groups → forensic serology |
| **1901, Edward Henry** | **Henry Classification System** for fingerprints (developed in Bengal, India — see below) |
| **1910, Edmond Locard (France)** | Established the first police crime laboratory (Lyon); **Locard's Exchange Principle**. "Sherlock Holmes of France" |
| **1915, Leone Lattes** | Method of determining blood group from a dried bloodstain |
| **1920s, Calvin Goddard** | Comparison microscope → modern **firearms/ballistics** identification |
| **1930s, Albert Osborn** | *Questioned Documents* — founded scientific document examination |
| **1932, FBI Laboratory (USA)** | Establishment of a national forensic laboratory model |
| **1984, Alec Jeffreys (UK)** | Discovery of **DNA fingerprinting**; first used in the Colin Pitchfork case (1986–88) |
| **1990s–present** | PCR, STR profiling, CODIS-style databases, and the rise of **digital forensics** |

### Indian milestones

| Year (⚠️ verify exact years where marked) | Development |
|---|---|
| 1849 | Chemical Examiner's Laboratory established in the erstwhile **Madras Presidency** — one of the earliest Indian forensic facilities. Similar labs followed in Calcutta (1853) and Agra/Bombay (1870s). ⚠️ verify years |
| **1897** | **Anthropometric Bureau, Calcutta** → renamed the **Finger Print Bureau** — widely described as the **world's first fingerprint bureau**, set up under Edward Henry with Indian officers **Azizul Haque** and **Hem Chandra Bose**, who did the substantive classification work |
| 1904 | Government Examiner of Questioned Documents (GEQD) work begins in Shimla; the **GEQD** office is later established at **Shimla**, with additional GEQD units at **Kolkata** and **Hyderabad** |
| 1910 | Serology department, Calcutta |
| 1915 | Note Forgery Section, CID Bengal |
| 1930 | Ballistics Laboratory, Calcutta |
| **1952** | **First State Forensic Science Laboratory in India — Calcutta (West Bengal)** ⚠️ verify (some sources credit the first *full-service* State FSL to West Bengal, 1952) |
| **1957** | **Central Forensic Science Laboratory (CFSL), Calcutta** — the first CFSL |
| 1959 | Central Detective Training School, Calcutta |
| **1970** | **Bureau of Police Research & Development (BPR&D)** established |
| **1972** | **Directorate of Forensic Science** work begins to be consolidated under MHA/BPR&D |
| **1986** | **National Crime Records Bureau (NCRB)** established |
| **1995** | Information Technology consciousness begins; DNA fingerprinting introduced in India by **CDFD, Hyderabad** and **CCMB** (Dr. Lalji Singh — "Father of DNA fingerprinting in India") ⚠️ verify year |
| **2000** | **Information Technology Act, 2000** enacted — creates the legal basis for electronic evidence and cybercrime |
| **2002** | **Directorate of Forensic Science (DFS)** created as a separate directorate under the **Ministry of Home Affairs**, taking the CFSLs and GEQDs out of BPR&D. Later renamed **Directorate of Forensic Science Services (DFSS)** |
| **2009** | **National Forensic Sciences University** precursor — Gujarat Forensic Sciences University (GFSU) established in Gandhinagar |
| **2020** | GFSU converted by Act of Parliament into the **National Forensic Sciences University (NFSU)** — an Institution of National Importance under MHA |
| **2023–24** | **Bharatiya Nyaya Sanhita, Bharatiya Nagarik Suraksha Sanhita and Bharatiya Sakshya Adhiniyam 2023** replace IPC, CrPC and the Indian Evidence Act (in force **1 July 2024**). BNSS makes **forensic examination mandatory for offences punishable with 7 years or more** ⚠️ verify the exact BNSS section (commonly cited as **BNSS §176(3)**) |

> **Exam tip:** For a 5-mark "history of forensic science" question, give 6–8 milestones in a
> table with a clear split into international and Indian. For a 10-mark question add the
> Indian institutional evolution (1897 Finger Print Bureau → 1957 CFSL Calcutta → 2002 DFS →
> 2020 NFSU → 2024 BNSS mandating forensics).

## 1.4 Scope of forensic science in India

**Scope = the range of questions it can answer + the range of disciplines it uses.**

| Domain | Typical questions answered |
|---|---|
| Forensic **Physics** | Glass fracture, paint, soil, tool marks, restoration of erased numbers, tyre/footwear marks |
| Forensic **Chemistry** | Explosives, petroleum products, fire debris, adulteration, trap cases (phenolphthalein) |
| **Toxicology** | Poisons, alcohol, drugs in viscera and body fluids |
| **Biology / Serology** | Blood, semen, saliva, hair, fibre, wildlife, diatoms (drowning) |
| **DNA** | Identification, paternity/maternity, mass-disaster victim identification, sexual assault |
| **Ballistics** | Firearms, cartridge cases, bullet-to-weapon matching, range of firing, GSR |
| **Questioned Documents** | Handwriting, signatures, forgery, alterations, ink dating, counterfeit currency |
| **Fingerprints (Dactyloscopy)** | Individual identification; AFIS/NAFIS database matching |
| **Forensic Medicine** | Autopsy, cause/manner/time of death, injuries |
| **Forensic Psychology** | Polygraph, narco-analysis, brain electrical oscillation signature (BEOS) — note the *Selvi v. State of Karnataka* (2010) restriction that these cannot be conducted **without consent** ⚠️ verify citation before quoting |
| **Cyber / Digital Forensics** | Computers, mobiles, networks, cloud, CCTV/audio-video authentication |
| **Forensic Anthropology / Odontology** | Skeletal remains, age/sex estimation, bite marks, superimposition |

**Growth drivers in India**: rising cybercrime, the 2024 criminal-law overhaul mandating forensic
teams for serious offences, NAFIS rollout, expansion of DNA facilities, and NFSU-driven manpower.
**Constraints**: pendency and backlog in FSLs, shortage of trained examiners, uneven State
capacity, delays affecting admissibility.

## 1.5 Basic principles of forensic science — **the core of Unit 1**

These six (some books say seven) principles are near-certain exam material. Learn each as
**Statement → Meaning in plain English → Example → Digital-forensics analogue**. The digital
analogue is a strong differentiator in the answer sheet for *this* elective.

---

### (i) Locard's Exchange Principle — "Every contact leaves a trace"

**Statement:** When any two objects come into contact, there is always a **mutual exchange of
material** between them.

**Plain English:** You cannot walk into a room without both leaving something behind and taking
something away. The criminal brings something to the scene and carries something from it.
The exchange may be too small to find, but it always occurs.

**Example:** A burglar breaking a window leaves fingerprints and fibres on the sill, and carries
away glass fragments in his shoe soles and trouser turn-ups.

**Digital analogue:** A user cannot open a file without leaving traces — an MFT timestamp
change, a prefetch entry, an LNK file, a registry MRU entry, a browser cache entry. This is the
single most quotable line you can put in a digital-forensics answer.

**Corollary / limitation:** the trace's *detection* depends on the time elapsed, the medium and
the analyst's skill. Absence of trace evidence is not proof of absence of contact.

---

### (ii) Law of Individuality — "Every object, natural or man-made, is unique"

**Statement:** Every object, natural or artificial, has an individuality which is not duplicated
in any other object. No two objects, **not even two grains of sand or two identical twins'
fingerprints**, are exactly alike.

**Plain English:** Manufacturing tolerances, wear, growth and random processes make every item
one-of-a-kind at a fine enough level of examination.

**Example:** Two bullets fired from the *same* barrel bear the same striations; bullets from two
"identical" barrels of the same model do not, because the rifling tools wear differently.
Identical twins share DNA but **not** fingerprints (ridge detail is formed by random foetal
pressures).

**Digital analogue:** Cryptographic hash values — two different files essentially never produce
the same SHA-256. Also MAC addresses, IMEI numbers, hardware serial numbers.

**Exception to note in the answer:** DNA of monozygotic twins is (practically) identical — the
usual exception cited against this law for DNA evidence.

---

### (iii) Principle of Comparison — "Only like can be compared with like"

**Statement:** Only comparable samples/standards can be compared with the questioned evidence.
A questioned sample must be compared against a **control/standard/known** sample of the same
type, collected under comparable conditions.

**Plain English:** You cannot identify a suspect's handwriting by comparing his printed capitals
to a cursive ransom note. You must obtain a specimen in the same script, same writing
instrument, same posture.

**Example:** To match a tyre mark you need a test impression from the suspect tyre on similar
substrate. To match a bullet you fire test bullets from the seized weapon into a recovery tank.

**Digital analogue:** Compare the hash of the *working copy* to the hash of the *original* image;
compare a carved JPEG against a known-good exemplar from the same camera model.

---

### (iv) Principle of Analysis — "The analysis is only as good as the sample"

**Statement:** The result of an analysis can be no better than the **sample analysed**, the
**method used** and the **person who performs** it. Incorrect sampling, contaminated sampling or
an unqualified analyst destroys the value of even a perfect instrument.

**Plain English:** Garbage in, garbage out. This is the principle that makes crime-scene
collection technique legally important.

**Example:** A blood sample collected into an unsterile container and left in a hot vehicle
yields a useless DNA result no matter how good the lab is.

**Digital analogue:** Imaging a live disk without a write blocker corrupts timestamps; the
subsequent analysis is worthless. Also: analysis of a *logical* copy cannot recover deleted
files, because the sample never contained them.

---

### (v) Law of Progressive Change — "Everything changes with the passage of time"

**Statement:** Everything changes with time. The rate of change varies with the object and the
conditions. The criminal changes (appearance, memory), the scene changes (weather, traffic,
contamination), and the evidence changes (decomposition, evaporation, corrosion).

**Plain English:** Evidence has a shelf life. Delay is the enemy.

**Example:** A body decomposes; a bloodstain degrades; a footprint in mud dries and cracks;
volatile accelerants evaporate from fire debris within hours.

**Digital analogue:** This is precisely why the **order of volatility** exists — RAM contents
vanish on power-off, ARP caches age out in minutes, DHCP leases and ISP logs are overwritten in
days or weeks. Cite this link in the exam; it directly connects TP-I §1 to TP-II §1.

---

### (vi) Principle of Circumstantial Facts / "Facts do not lie, men can and do"

**Statement:** Physical/circumstantial evidence does not lie, cannot be wholly absent, and is not
subject to the frailties of human memory or motive — but it **must be interpreted correctly**.
Oral testimony can be false, mistaken, coerced or retracted; physical evidence cannot.

**Plain English:** A witness may turn hostile in court; a fingerprint will not.

**Example:** In a case where all eyewitnesses turn hostile, the recovered weapon bearing the
accused's fingerprints and the victim's blood can still sustain a conviction.

**Digital analogue:** Log files and hash values do not change their story on cross-examination —
provided integrity is proved (§65B / BSA §63 certificate).

**Caveat:** physical evidence is only as truthful as its *interpretation*; wrongful convictions
arise from over-claimed forensic conclusions (bite marks, hair microscopy, arson "indicators").

---

> Some texts add a seventh: **Principle of Presentation** — the finding must be presented in a
> form the court can understand. Mention it as an add-on, not as a core principle.

### Memory hook

**L-I-C-A-P-C**: **L**ocard, **I**ndividuality, **C**omparison, **A**nalysis, **P**rogressive
change, **C**ircumstantial facts.
Or a sentence: "**L**ittle **I**tems **C**an **A**lways **P**rove **C**rime."

## 1.6 Significance of forensic science

1. **Objective, scientific proof** independent of witness reliability.
2. **Links** the four corners of a crime: the **victim**, the **suspect**, the **scene**, and the
   **weapon/instrument** — the "forensic linkage triangle/quadrangle" (draw it, see below).
3. **Excludes the innocent** as often as it convicts the guilty (exculpatory value; DNA
   exonerations).
4. **Reconstructs** the sequence of events (bloodstain pattern analysis, trajectory analysis, log
   timeline reconstruction).
5. **Identifies** persons and objects (fingerprints, DNA, IMEI, hashes).
6. **Deterrent effect** and increased conviction rate.
7. **Corroborates or contradicts** the confession/testimony on record.
8. Handles crimes where there **are no witnesses at all** — the normal case in cybercrime.

**Limitations (add these for a 10-mark answer):** backlog and delay; contamination risk;
dependence on the quality of scene work; interpretive/expert bias; cost and infrastructure;
absence of statutory forensic standards in some domains; over-reliance leading to the "CSI
effect" in courts.

### Diagram to hand-draw: the Linkage Triangle

```
                    SUSPECT
                    /      \
       transfer of /        \ transfer of
        evidence  /          \  evidence
                 /            \
            SCENE ──────────── VICTIM
                  transfer of
                    evidence

  (Weapon/instrument sits in the middle, connecting all three)
```
Draw three labelled circles — SUSPECT, VICTIM, SCENE — joined by double-headed arrows labelled
"exchange of trace material (Locard)". Put WEAPON in the centre with lines to all three. One
extra mark, every time.

---

## §1.7 Likely exam questions (Unit 1, part A)

| Marks | Question |
|:--:|---|
| 5 | State and explain Locard's Exchange Principle with two examples. |
| 5 | Distinguish between the Law of Individuality and the Principle of Comparison. |
| 5 | What is forensic science? Discuss its scope in India. |
| 10 | Explain the basic principles of forensic science with suitable examples and their relevance to digital evidence. |
| 10 | Trace the historical development of forensic science in India. |
| 15 | "Physical evidence does not lie." Discuss the principles, significance and limitations of forensic science in the Indian criminal justice system. |

### MCQ traps (Unit 1)
- "Father of **Forensic Toxicology**" = **Orfila**; "Father of **Criminalistics**" = **Hans Gross**;
  "Father of **Criminal Identification / Anthropometry**" = **Bertillon**; first crime lab = **Locard, Lyon 1910**;
  DNA fingerprinting = **Alec Jeffreys 1984**. These four are constantly swapped in options.
- The first **CFSL** was at **Calcutta (1957)** — options will offer Delhi or Hyderabad.
- The world's first **fingerprint bureau** was at **Calcutta (1897)** — options will offer Scotland Yard.
- Locard's principle is about **mutual/two-way** exchange, not one-way transfer.
- "Every contact leaves a trace" → Locard, **not** Gross.

---

# §2. Organisation and Functioning of Forensic Science Laboratories in India

> **This section is the single most likely "you either know it or you don't" question in TP-I.**
> A CS graduate will lose these marks by default. Learn the hierarchy as a picture.

## 2.1 The intuition

India has a federal police structure: **"Police" and "Public Order" are State subjects**
(State List, Seventh Schedule). So most forensic work is done by **State** laboratories serving
State police. The **Centre** maintains a parallel set of laboratories that (a) serve central
agencies like the CBI, NIA and paramilitary forces, (b) handle inter-State and sensational cases,
(c) act as referral/appellate laboratories when a State result is challenged, and (d) do R&D and
standard-setting. That is the whole architecture in two sentences.

## 2.2 The hierarchy — diagram to hand-draw

```
              MINISTRY OF HOME AFFAIRS (MHA), Government of India
                                 │
        ┌────────────────┬───────┴────────┬───────────────────┐
        │                │                │                   │
  DIRECTORATE OF     BPR&D          NCRB              NFSU (Gandhinagar,
  FORENSIC SCIENCE  (research,   (crime & criminal     Institution of
  SERVICES (DFSS)    training,    data, NAFIS,         National Importance)
   New Delhi         policy)      CCTNS)
        │
   ┌────┴──────────────────────────┬──────────────────────┐
   │                               │                      │
 CENTRAL FORENSIC SCIENCE     GOVERNMENT EXAMINER OF   Central Fingerprint
 LABORATORIES (CFSLs)         QUESTIONED DOCUMENTS     Bureau (CFPB) — under
 Kolkata, Hyderabad, Chandigarh,    (GEQD)             NCRB
 Guwahati, Bhopal, Pune, Delhi   Shimla, Kolkata,
 (CFSL-Delhi under CBI)          Hyderabad

        ─────────────── STATE SIDE ───────────────
        STATE HOME DEPARTMENT / STATE POLICE
                    │
            STATE FSL (one per State, at the capital)
                    │
        ┌───────────┴────────────┐
        │                        │
  REGIONAL FSLs (RFSL)     MOBILE FSL UNITS (MFSU)
  (zonal, 2–5 per State)   (vehicle-based, go to the scene)
                    │
            DISTRICT MOBILE FORENSIC UNITS / District Clue Teams
```

## 2.3 Directorate of Forensic Science Services (DFSS)

| Attribute | Detail |
|---|---|
| Parent | **Ministry of Home Affairs, Government of India** |
| Created | **2002** (as Directorate of Forensic Science, carved out of BPR&D); later renamed DFSS |
| Headquarters | **New Delhi** |
| Head | Director-cum-Chief Forensic Scientist |
| Controls | The **CFSLs** and the **GEQD** offices |

**Functions of DFSS**
1. Administrative and technical control of CFSLs and GEQDs.
2. Provides forensic services to **central investigating agencies** (CBI, NIA, ED, NCB, CAPFs)
   and to State police in referred/sensational/inter-State cases.
3. **Referral laboratory** function — second opinion where a State FSL report is disputed.
4. Formulates **standards, protocols, SOPs and quality-assurance** norms for the country.
5. Research & development in forensic techniques.
6. **Training** of forensic scientists, police officers, judicial officers and prosecutors.
7. Advises MHA on forensic policy and on new legislation.
8. Coordinates the national forensic infrastructure and manpower planning.

## 2.4 Central Forensic Science Laboratories (CFSLs)

Full-fledged multidisciplinary central laboratories. The classical list (⚠️ verify the current
count — the network has been expanded in recent years and new CFSLs/NFSU campuses have been
sanctioned):

| CFSL | Notable speciality / note |
|---|---|
| **Kolkata (1957)** | **The oldest CFSL.** Historically the centre for **Questioned Documents / handwriting**; also serology, ballistics |
| **Hyderabad** | Chemistry, toxicology, **narcotics**, DNA; serves southern region |
| **Chandigarh** | Broad multidisciplinary; serves northern region |
| **Guwahati** | Serves the **North-East**, including Nagaland — *know this one, it is the regionally relevant answer* |
| **Bhopal** | Multidisciplinary (central region) |
| **Pune** | Multidisciplinary (western region) |
| **New Delhi (CFSL, CBI)** | **Under the administrative control of the CBI**, not DFSS — the standard exam trick. Strong in DNA, cyber, documents |

> Under the National Forensic Infrastructure Enhancement Scheme (NFIES) further CFSLs/NFSU
> campuses have been sanctioned across States ⚠️ verify current status and list.

**Functions of a CFSL**
1. Examination of exhibits referred by central agencies, courts, and State police in important cases.
2. Referral/second-opinion analysis.
3. Crime-scene attendance in sensational cases.
4. Expert testimony in court by the examining scientist.
5. R&D and method validation.
6. Training and internships.

## 2.5 Government Examiner of Questioned Documents (GEQD)

- **Statutory expert offices** for the examination of **questioned documents**: handwriting,
  signatures, typescripts, printing, forgery, alterations, obliterations, ink and paper
  examination, **counterfeit currency**, and (increasingly) computer-printed/digital documents.
- Located at **Shimla (the principal office), Kolkata and Hyderabad**; under **DFSS/MHA**.
- The GEQD is a **"Government Scientific Expert"** whose report has special statutory standing —
  under the Indian Evidence Act 1872 the report of certain named government scientific experts
  could be used in evidence **without calling the expert** (the old **§293 CrPC** list, now
  carried into the **BNSS** ⚠️ verify the corresponding new section number). Note that the list
  of such experts also includes the Chemical Examiner, the Chief Inspector of Explosives, the
  Director of a Fingerprint Bureau, the Director of a Central/State FSL, the Serologist, and the
  Director of the Haffkine Institute. ⚠️ verify the exact composition of the list before quoting.

## 2.6 State Forensic Science Laboratories (SFSL)

| Attribute | Detail |
|---|---|
| Control | **State Home Department / State Police** (Police is a State subject) |
| Location | Normally the State capital; one per State/UT |
| Head | Director, SFSL |
| Users | State police, State courts, State agencies |

**Functions**: routine casework for the entire State; crime-scene visits in serious cases;
expert testimony in State courts; supervising the RFSLs and mobile units; training State police
in evidence collection; maintaining State-level databases.

**Nagaland-relevant note:** the North-East is served centrally by **CFSL Guwahati**; State-level
work in Nagaland is handled by the State FSL under the Nagaland Police ⚠️ verify current status
and location before writing it as a fact.

## 2.7 Regional FSLs (RFSL)

- **Zonal branches of the State FSL**, set up because a single capital laboratory cannot serve a
  whole State without unacceptable delay.
- Typically handle the **high-volume, routine** disciplines — toxicology (viscera), excise/liquor,
  narcotics screening, biology/serology, general chemistry, photography.
- **Reduce turnaround time and transport risk** (shorter chain of custody, less degradation —
  connect this to the Law of Progressive Change).
- Complex or specialised work (DNA, cyber, ballistics, documents) is escalated to the SFSL or CFSL.

## 2.8 Mobile FSL Units (MFSU) / District Mobile Forensic Vans

- **A laboratory on wheels** — a specially fitted vehicle that reaches the **scene of crime**
  rather than waiting for the exhibits to reach the laboratory.
- Typical kit: crime-scene kit, photography and videography equipment, lighting, forensic light
  sources, fingerprint development kit, casting materials, presumptive test reagents (blood,
  semen, narcotics), collection and packaging materials, sometimes a portable digital-forensics
  kit (write blocker, imaging device).
- **Purpose:** immediate scene examination, on-the-spot presumptive testing, correct collection
  and packaging, and preventing loss/contamination of evidence.
- Under the **BNSS 2023 requirement** of mandatory forensic visits for offences punishable with
  **7 years or more**, mobile forensic vans have become the operational backbone in the districts
  ⚠️ verify the exact BNSS section.

## 2.9 Divisions inside a full-service forensic science laboratory

**This is a very common 5- or 10-mark question: "Describe the various divisions of a Forensic
Science Laboratory and their functions."** Answer as a table.

| Division | What it examines / does |
|---|---|
| **Biology** | Hair, fibre, wood, pollen, diatoms (drowning), botanical material, wildlife material |
| **Serology** | Blood, semen, saliva, sweat, urine; species of origin; blood grouping; stain identification |
| **DNA / Molecular Biology** | STR profiling, paternity/maternity, sexual-assault cases, disaster victim identification, DNA databanking |
| **Chemistry** | Explosives and post-blast residue, petroleum products, fire debris/accelerants, dyes, adulterants, trap-case (phenolphthalein) analysis, general unknowns |
| **Toxicology** | Poisons, pesticides, alcohol, drugs of abuse in viscera, blood and body fluids |
| **Narcotics / NDPS** | Identification and quantification of narcotic drugs and psychotropic substances |
| **Physics** | Glass, paint, soil, cement, tool marks, tyre and footwear marks, restoration of erased serial numbers, accident reconstruction |
| **Ballistics** | Firearms, ammunition, cartridge cases, bullets, range and direction of fire, gunshot residue (GSR) |
| **Documents / Questioned Documents** | Handwriting, signatures, forgery, alterations, erasures, indented writing, ink and paper analysis, counterfeit currency, typewriting/printing |
| **Fingerprint / Dactyloscopy** | Development, lifting, comparison and identification of latent prints; AFIS/**NAFIS** searching (usually under the Finger Print Bureau) |
| **Cyber Forensics / Computer Forensics** | Computers, hard disks, mobile phones, memory cards, network and cloud data, CCTV, audio-video authentication, malware analysis |
| **Photography / Imaging** | Crime-scene and exhibit photography, photomicrography, infrared/UV imaging, image enhancement |
| **Lie Detection / Forensic Psychology** | Polygraph, narco-analysis, BEOS — subject to consent requirements |
| **Prohibition & Excise** | Liquor, illicit spirits, methanol |
| **Anthropology / Odontology** (where present) | Skeletal remains, age/sex/stature estimation, superimposition, bite marks |

## 2.10 Other institutions to name-drop correctly

| Body | Role |
|---|---|
| **BPR&D** (Bureau of Police Research & Development, 1970, MHA) | Police research, modernisation, training, correctional administration; publishes standards/manuals. **Not** the operator of CFSLs since 2002. |
| **NCRB** (National Crime Records Bureau, 1986, MHA) | Crime statistics (*Crime in India*), **CCTNS**, **NAFIS** (National Automated Fingerprint Identification System), Central Finger Print Bureau |
| **NICFS / NICFS-LNJN** (National Institute of Criminology & Forensic Science, Delhi) | Training and academic institution — now part of **NFSU** ⚠️ verify current status |
| **NFSU** (National Forensic Sciences University, Gandhinagar, 2020) | Institution of National Importance under MHA; education, research, campuses across India and abroad |
| **CDFD, Hyderabad** | Centre for DNA Fingerprinting and Diagnostics — DNA casework and research (Dept. of Biotechnology) |
| **I4C** (Indian Cyber Crime Coordination Centre, MHA) | Cybercrime coordination; **National Cyber Crime Reporting Portal (cybercrime.gov.in)**; **1930** helpline; CFMC |
| **CERT-In** (Indian Computer Emergency Response Team, MeitY) | National nodal agency for cyber-security incidents; statutory basis in **IT Act §70B** |
| **NCIIPC** | National Critical Information Infrastructure Protection Centre — **IT Act §70A** |
| **Cyber Crime Cells / Cyber Police Stations** | State-level cybercrime investigation |

## §2.11 Likely exam questions (Unit 1, part B)

| Marks | Question |
|:--:|---|
| 5 | Write a note on the Directorate of Forensic Science Services (DFSS). |
| 5 | What is a Mobile Forensic Science Unit? State its functions. |
| 5 | Distinguish between Central and State Forensic Science Laboratories. |
| 10 | Describe the organisation and functioning of forensic science laboratories in India with a diagram. |
| 10 | Enumerate the divisions of a full-service FSL and state the functions of each. |
| 15 | Discuss the structure of forensic science services in India from the Ministry of Home Affairs down to the district level, and evaluate the adequacy of this structure for handling cybercrime. |

### MCQ traps (Unit 1, part B)
- **CFSL New Delhi is under the CBI**, the other CFSLs are under DFSS/MHA.
- CFSLs are under **DFSS**, *not* BPR&D (true only before 2002) and *not* NCRB.
- **GEQD principal office = Shimla.**
- **NCRB** runs NAFIS and CCTNS; **BPR&D** does research and training; do not swap.
- Police is a **State** subject → SFSLs are under the **State** government, not MHA.
- NFSU is at **Gandhinagar, Gujarat**.

---

# §3. Ethics in Forensic Science

## 3.1 Concept

A forensic scientist is not a member of the prosecution team. He is an **officer of the court
who happens to be paid by the State**. The whole evidentiary weight of forensic science depends
on the court believing the analyst was indifferent to the outcome. Ethics is therefore not a
soft topic here — it is the load-bearing wall.

## 3.2 Code of conduct — exam-ready bullets

1. **Objectivity and impartiality** — report what the evidence shows, whether it helps the
   prosecution or the defence. Disclose **exculpatory** findings.
2. **Competence** — undertake only examinations for which you are trained and qualified; do not
   opine outside your field.
3. **Use of validated methods** — accepted, peer-reviewed, validated techniques; documented SOPs.
4. **Complete and contemporaneous documentation** — all case notes, worksheets, raw data
   retained; another expert must be able to reproduce the work.
5. **Integrity of evidence** — maintain the chain of custody; do not consume the whole sample if
   avoidable (preserve a portion for re-examination by the defence).
6. **Confidentiality** — no disclosure of case information outside authorised channels; no press
   comment on a pending case.
7. **No overstatement** — state limitations, error rates and the degree of certainty. Never claim
   "100% match" where the science supports only "consistent with" or "cannot be excluded".
8. **Independence** — resist pressure from investigators, superiors, the accused or the media.
9. **Disclosure of conflicts of interest** — prior involvement, relationship to a party, financial
   interest in a technique or company.
10. **Continuing professional development** and participation in proficiency testing.
11. **Correct errors promptly** — report a mistake even after the report is issued.
12. **Do not accept a fee contingent on the outcome.**

## 3.3 Duties of an expert witness

- Assist the **court**, not the party that called him — this duty **overrides** any obligation to
  the party paying.
- Give evidence within his field of expertise only.
- Explain in language the court can follow; avoid jargon or explain it.
- State the facts and assumptions the opinion is based on, and what would change the opinion.
- Disclose any material that detracts from the opinion.
- Answer cross-examination honestly, including conceding valid limitations.
- Be prepared to produce case notes, raw data, instrument logs and SOPs.

> Under Indian law, expert opinion is admissible under the **Indian Evidence Act §45**
> (now **BSA 2023 §39** ⚠️ verify), and expert opinion is **advisory** — the court is not bound
> by it and must apply its own mind. Reports of certain government scientific experts may be
> used without examining the expert (old **CrPC §293**, now the corresponding **BNSS** provision
> ⚠️ verify number).

## 3.4 Bias — the types (very examinable)

| Type of bias | What it is | Forensic example |
|---|---|---|
| **Confirmation bias** | Seeing what you expect to see | Analyst told "the suspect confessed" then finds a fingerprint "match" |
| **Contextual bias** | Irrelevant case information influences the analysis | Being told the suspect has prior convictions before comparing handwriting |
| **Expectation bias** | The investigator's stated hypothesis shapes interpretation | "We need this to be blood" |
| **Motivational / role bias** | Seeing oneself as part of the prosecution team | "My job is to help police convict" |
| **Anchoring** | Over-weighting the first piece of information | Fixing on an initial time-of-death estimate |
| **Reverse-reasoning / target-driven comparison** | Working *from* the suspect's exemplar *to* the crime-scene mark instead of the other way round | Fingerprint circular reasoning |
| **Observer effect** | The examiner's awareness of the desired outcome affects a subjective measurement | Interpretation of an ambiguous bloodstain pattern |

**Countermeasures:** *Linear Sequential Unmasking* (analyse the questioned sample fully **before**
looking at the known); **context management** (give the analyst only task-relevant information);
**blind verification** by a second examiner who does not know the first conclusion; documented
SOPs; proficiency testing; accreditation (ISO/IEC 17025 for testing laboratories, ISO/IEC 17020
for scene work) ⚠️ verify the standard numbers before quoting.

## 3.5 Common ethical failures

1. **Drylabbing** — reporting results of tests never actually performed.
2. **Overstating conclusions** — "an absolute match", "to the exclusion of all others" where the
   discipline cannot support it.
3. **Falsification / fabrication** of data or credentials (inflated CV, non-existent degrees).
4. **Selective reporting** — omitting inconclusive or exculpatory results.
5. **Testifying beyond expertise** — a chemist opining on cause of death.
6. **Failure to disclose limitations, error rates, or contamination events.**
7. **Breaking the chain of custody** and concealing it.
8. **Contamination through poor practice** and failure to report it.
9. **Leaking information to the media**; commenting on a sub-judice matter.
10. **Consuming the entire sample**, denying the defence any re-examination.
11. **Acting as a hired gun** for whichever side pays.
12. **Backlog-driven shortcuts** — signing reports on work done by unqualified juniors.

## §3.6 Likely exam questions
| Marks | Question |
|:--:|---|
| 5 | What is confirmation bias? How can a laboratory minimise it? |
| 5 | State the duties of an expert witness. |
| 10 | Discuss ethics in forensic science. What are the common ethical failures and their consequences? |
| 15 | "Forensic evidence is only as trustworthy as the analyst." Discuss with reference to bias, ethical failures and quality-assurance measures. |

### MCQ traps
- The expert's **primary duty is to the court**, not to the party engaging him.
- Expert opinion is **advisory/not binding** on the court.
- "Drylabbing" = reporting tests not performed (not "testing in a dry environment").
- Linear Sequential Unmasking is a *bias-control* technique, not an analytical technique.

---

# §4. Physical Evidence (TP-I Unit 2)

## 4.1 Concept

**Physical evidence is any material object that can establish that a crime has been committed,
or can provide a link between a crime and its victim or between a crime and its perpetrator.**

Intuition: it is the "silent witness". It cannot be intimidated, does not forget and has no
motive — but it also cannot speak for itself. It requires a competent examiner to translate it.

**Value/functions of physical evidence — memorise this six-item list:**
1. **Corpus delicti** — proves that a crime actually occurred (e.g., a jemmy-marked door proves
   housebreaking).
2. **Modus operandi** — reveals the method used, linking serial offences.
3. **Linking** the suspect to the scene/victim (Locard).
4. **Disproving / supporting** an alibi or a statement.
5. **Identifying** the accused, victim or object (fingerprints, DNA, IMEI, hash).
6. **Providing investigative leads** where none exist; and **exonerating** the innocent.

## 4.2 Types of physical evidence

Two useful classifications — give **both** in a 5-mark answer.

**(a) By nature/origin**

| Category | Examples |
|---|---|
| **Biological** | Blood, semen, saliva, urine, hair, tissue, bone, botanical material |
| **Chemical** | Drugs, poisons, explosives, petroleum products, paints, dyes, fibres |
| **Physical** | Glass, soil, metal, tool marks, tyre and footwear marks, firearms and bullets |
| **Documentary** | Handwriting, signatures, printed and typed documents, currency |
| **Impression / pattern** | Fingerprints, footprints, tool marks, tyre marks, bite marks, bloodstain patterns |
| **Electronic / digital** | Computers, hard disks, mobile phones, memory cards, CCTV footage, logs, cloud data |
| **Miscellaneous** | Anything else — clothing, jewellery, rope, cigarette ends |

**(b) By evidential value (the important one)**

| Type | Meaning |
|---|---|
| **Transient evidence** | Temporary; lost quickly — odour, temperature, wet stains, smoke. Record first. |
| **Pattern evidence** | Produced by physical contact — bloodstain patterns, glass fracture, tyre marks |
| **Conditional evidence** | Produced by an event/action — lights on/off, doors locked, TV channel, body position |
| **Transfer / trace evidence** | Material exchanged between persons/objects — hair, fibre, soil, paint |
| **Associative evidence** | Personal property linking a suspect to a scene — wallet, ID card, phone |

> **Digital note for this elective:** digital evidence is simultaneously *transient* (RAM, network
> connections), *transfer* (log entries created by an intrusion) and *associative* (a phone at
> the scene). Say this in the exam — it shows you connected the two halves of the syllabus.

## 4.3 **Class characteristics vs individual characteristics** — the classic question

### The intuition first

Ask: **"How many objects in the world could have produced this evidence?"**

- If the answer is **"a whole group / batch / model"** → the feature is a **class characteristic**.
- If the answer is **"only this one specific object, and no other in existence"** → it is an
  **individual characteristic**.

Class characteristics come from the **design/manufacture** of the object — they are shared by
every item made to the same specification. Individual characteristics come from **random events**
that happened only to that one object: manufacturing imperfections, wear, damage, growth, or
random biological variation. Randomness is what creates uniqueness.

### Formal definitions

- **Class characteristic:** a property of physical evidence that can be associated only with a
  **group** (a class) of objects or persons, never with a single source. It permits
  **identification** (this is glass; this is a Bata sole, size 9) and **exclusion**, but never
  individualisation.
- **Individual characteristic:** a property that can be attributed to a **single, unique source**
  with an extremely high degree of certainty. It permits **individualisation**.

### Comparison table (reproduce this)

| Aspect | Class characteristic | Individual characteristic |
|---|---|---|
| Source | Design / manufacture / species | Random wear, damage, imperfection, random biology |
| Points to | A **group** of possible sources | **One** source |
| Conclusion possible | "Consistent with / cannot be excluded"; **exclusion** | "Identified to the exclusion of all others" |
| Evidential weight | Corroborative | Conclusive / individualising |
| Statistical basis | Frequency of the class in the population | Practical uniqueness |
| Result of a mismatch | **Exclusion** (a mismatch in class characteristics eliminates the source outright) | Exclusion |

### Examples — learn six of each

| Evidence | Class characteristic | Individual characteristic |
|---|---|---|
| **Footwear** | Brand, model, size, sole tread design | Cuts, nicks, wear pattern, embedded stone in the sole |
| **Fingerprint** | Pattern type — loop, whorl, arch; ridge count | **Minutiae / Galton details** — ridge endings, bifurcations, their relative positions |
| **Firearm/bullet** | Calibre, number of lands and grooves, direction and width of twist | **Striations** from tool marks unique to that barrel |
| **Tool marks** | Type and width of the tool (screwdriver, 12 mm) | Striae from nicks and imperfections on that tool's edge |
| **Blood** | ABO group, Rh type, species of origin | **DNA STR profile** (except identical twins) |
| **Hair** | Species, race, body area, colour, treatment (dye) | Nuclear **DNA from the root sheath** (the shaft alone gives only mitochondrial DNA → maternal lineage, still not individualising) |
| **Glass** | Type (float, tempered), colour, thickness, **refractive index**, density | **Physical fit** of a fracture edge — jigsaw match |
| **Paint** | Layer sequence, colour, chemical composition, make/model of vehicle | Physical fit of a paint chip to the damaged area |
| **Handwriting** | Copybook style, general slant | Individual writing habits, letter formations, pen lifts |
| **Fibre** | Type (cotton/nylon), colour, dye, cross-section | Almost never individualising (physical fit of a torn fabric edge is the exception) |
| **Typewriting / printer** | Typeface, font, model of machine | Defects — worn or misaligned characters, printer banding/artefacts |
| **Digital analogue** | File **type/extension**, MIME type, camera model from EXIF | **Hash value (SHA-256)**, MAC address, IMEI, serial number, GUID |

### Key insight to write down in the answer

> A **mismatch in class characteristics is conclusive of exclusion**, even though a *match* in
> class characteristics is not conclusive of identity. This asymmetry is why class evidence is
> still valuable: it eliminates suspects cheaply.

> Also: enough class characteristics *in combination* can approach individualisation
> statistically (e.g. blood group A + Rh− + a rare enzyme variant narrows the population to a
> fraction of a percent) — but it is **cumulative probability**, not true individualisation.

### Likely exam framing
- 5 marks: "Distinguish between class and individual characteristics with examples." → table + 4 examples.
- 10 marks: add the exclusion asymmetry, the cumulative-probability point, and a digital analogue.

## 4.4 Search methods for locating physical evidence at the scene

**Concept:** a scene search must be **systematic, exhaustive and documented**. The method chosen
depends on the **size** of the area, the **terrain**, the **number of searchers** available and
whether the area is **indoor or outdoor**. Never search randomly; never let searchers cross
uncleared ground.

Draw all five patterns. Each is a simple sketch — practise until you can draw all five in
90 seconds.

---

### (1) Strip / Line (Lane) search

```
  START →  ●───────────────────────────→
           ←───────────────────────────●
           ●───────────────────────────→
           ←───────────────────────────●
   (searcher walks parallel lanes, back and forth)
```
- The area is divided into **parallel strips/lanes**. One or more searchers walk each lane end to
  end, then turn and take the adjacent lane.
- With several searchers they stand in a **line, arm's length apart**, and advance together on a
  command ("line search").
- **Best for:** large **open outdoor** areas — fields, roadsides, parks; also for searching a
  route for a discarded weapon.
- **Advantages:** simple, easy to supervise, scales to many searchers.
- **Limitation:** in tall vegetation, items can be stepped over.

---

### (2) Grid (Double-strip) search

```
   ═╬═╬═╬═╬═╬═   pass 1: lanes north–south
   ═╬═╬═╬═╬═╬═   pass 2: lanes east–west (over the same ground)
```
- **A strip search performed twice, the second time at 90° to the first.** Each point of ground is
  therefore examined from two different directions and lighting angles.
- **Best for:** large outdoor areas where thoroughness matters more than speed — bomb-blast sites,
  aircraft crash sites, searching for a small item like a cartridge case.
- **Advantage:** the **most thorough** of all patterns; a second look from a different angle finds
  what the first missed.
- **Limitation:** roughly **twice the time and manpower**.

---

### (3) Spiral search (inward or outward)

```
      ┌─────────────┐
      │ ┌─────────┐ │
      │ │  ┌───┐  │ │
      │ │  │ ✕ │  │ │      ✕ = focal point (body / point of impact)
      │ │  └───┘  │ │
      │ └─────────┘ │
      └─────────────┘
```
- The searcher moves in a **circular/spiral path**, either **outward** from a central focal point
  (the body, the seat of the fire) to the perimeter, or **inward** from the perimeter to the
  centre.
- **Inward spiral** is used when the centre is the most important area and you must avoid
  disturbing the periphery on the way in; **outward spiral** is used when the investigator is
  already at the centre (e.g. arriving at a body).
- **Best for:** **small, confined or barrier-free areas**, a single body in the open, **underwater**
  searches by a diver on a fixed line, and large open areas with no reference features.
- **Advantage:** good for a **single searcher**; simple around a focal point.
- **Limitation:** hard to maintain an even spiral; risk of missed gaps; not easily supervised.

---

### (4) Zone / Quadrant / Sector search

```
   ┌───────┬───────┐
   │   A   │   B   │       Each zone assigned to a team;
   ├───────┼───────┤       zones may be sub-divided (A1, A2 …)
   │   C   │   D   │
   └───────┴───────┘
```
- The scene is divided into **zones/quadrants**, each assigned to a searcher or team; each zone
  may be sub-divided and searched using any of the other patterns internally.
- **Best for:** **indoor scenes** — a house is naturally divided into rooms; also large complex
  outdoor scenes and multi-storey buildings.
- **Advantage:** clear allocation of responsibility and accountability; allows **cross-checking**
  (teams swap zones for a second pass); scales well.
- **Limitation:** boundaries between zones can be neglected; requires coordination.

---

### (5) Wheel / Ray / Pie search

```
              │
          ＼  │  ／
       ＼     ✕     ／      Searchers move outward from the centre
          ／  │  ＼         along radii ("spokes"), then return
              │
```
- Searchers begin at a central point and move **outward along radii (spokes/rays)**, like the
  spokes of a wheel; or move inward along the spokes.
- **Best for:** **small, circular or roughly circular** scenes with an obvious focal point —
  e.g. a body in an open field, a small explosion crater.
- **Advantage:** fast; focuses effort near the centre.
- **Limitation:** **major gaps develop as the searchers move outward** (the spokes diverge) — so
  it is *not* thorough for large areas. This limitation is a favourite MCQ point.

---

### Summary table (reproduce this)

| Pattern | Best used for | Searchers | Thoroughness | Key weakness |
|---|---|---|---|---|
| **Strip / Line** | Large open outdoor areas | Many | Good | Single viewing angle |
| **Grid** | Critical outdoor scenes; small items | Many | **Highest** | Time and manpower ×2 |
| **Spiral** | Small confined areas; single body; underwater | **One** | Moderate | Gaps; hard to keep even |
| **Zone / Quadrant** | **Indoor** scenes, buildings, complex scenes | Teams | Good, cross-checkable | Zone boundaries missed |
| **Wheel / Ray** | Small circular scenes with a focal point | Few | Poor at the periphery | **Diverging gaps** |

**General rules for any search**
- Search **from the general to the specific**, and from the **periphery inward to the body** where
  approach paths must be preserved.
- Establish a **single common entry/exit path** and search it first.
- Photograph and document *before* anything is moved.
- Search **three-dimensionally** — floor, walls, ceiling, above eye level, under furniture, drains.
- **Search twice** — a second search by different personnel finds what the first missed.
- Note **negative evidence** too (the absence of something that should be there — no blood where
  there should be, a missing knife from a block, a wiped hard disk).

## 4.5 **Chain of Custody** — guaranteed exam material

### Concept

The court will only accept an exhibit if the prosecution can prove that the object produced in
court is **the very object collected at the scene**, and that it was **not altered, substituted,
tampered with or contaminated** at any point in between. The chain of custody is the documentary
proof of that.

**Definition:** The **chronological documentation** (paper and/or electronic) recording the
**seizure, custody, control, transfer, analysis and disposition** of physical or electronic
evidence — i.e. an unbroken record of *who* had the evidence, *when*, *where*, *why* and *what
they did to it*, from the moment of collection until its production in court and final disposal.

Also called the **"paper trail"** or **chain of evidence**.

### Why it matters

1. Establishes **authenticity** — the exhibit is what it is claimed to be (Evidence Act / BSA
   requirement of proving a document/object).
2. Establishes **integrity** — it has not been altered.
3. Establishes **accountability** — a named person is answerable for every period of custody.
4. Prevents **contamination, substitution and planting** allegations.
5. Enables **reconstruction of handling** if a problem is later discovered.
6. It is the **first thing the defence attacks** in cross-examination.

### What the chain-of-custody form records

| Field | Detail |
|---|---|
| Case / FIR number, police station, section of law | Identifies the case |
| **Unique exhibit number** | e.g. "Ex-A/3" |
| **Description** of the item | Make, model, colour, **serial number/IMEI**, capacity, visible damage |
| **Date, time and exact place of collection** | GPS/room/position |
| **Name, designation and signature of the collector** | Who seized it |
| **Names and signatures of independent witnesses (*panchas*)** | The *panchnama*/seizure memo requirement in India |
| **Method of collection and packaging** | Container type, sealing details, **seal number/impression** |
| **Hash value** (for digital evidence) | MD5/SHA-256 of the acquired image — the digital equivalent of a seal |
| **Every transfer**: released by (name, sign, date, time) → received by (name, sign, date, time), and **purpose** | The core of the chain |
| **Storage location and conditions** | Malkhana/property room, refrigerated, sealed cupboard, safe |
| **Examination record** | Who examined it, when, what was done, whether the seal was intact on receipt and re-sealed after |
| **Final disposition** | Returned, retained, destroyed (with court order) |

### The rule in one line

> **Every person who handles the evidence must sign for it, and there must be no unexplained gap
> in time or custody between one signature and the next.**

### How the chain breaks — and the consequence

| How it breaks | Consequence |
|---|---|
| An unexplained **gap** in the record (item unaccounted for for hours/days) | Defence argues opportunity for tampering |
| A **broken, missing or mismatched seal** on receipt at the laboratory | Report may be rejected outright |
| **No independent witnesses** to the seizure / defective *panchnama* | Seizure itself challenged |
| **Missing signature** at a transfer | That link cannot be proved |
| Evidence left **unattended or in an unsecured place** (a car boot, an open desk) | Integrity in doubt |
| **Improper storage** — biological sample not refrigerated, drive near a magnet | Degradation; result unreliable |
| **Original examined instead of a working copy** (digital) | Alteration of the original; hash mismatch |
| **Hash mismatch** between acquisition and analysis | Conclusive proof of alteration — evidence discarded |
| **Absence of the §65B / BSA §63 certificate** for electronic evidence | **Inadmissible** (see §6) |
| No record of who **opened and re-sealed** the packet | Contamination/substitution argument |

**Legal consequence:** a broken chain does not automatically make evidence inadmissible in India
in every case, but it **destroys its evidentiary weight**; courts routinely discard exhibits where
the chain is doubtful, and in the case of electronic records the statutory certificate requirement
makes the defect fatal. In the exam write: *"a break in the chain of custody renders the evidence
liable to be excluded, or at minimum deprives it of evidentiary value, and can collapse the entire
prosecution case."*

### Digital-specific chain of custody

- Record the **hash at acquisition** and re-verify at every subsequent stage; the hash is the
  digital seal.
- Use **write blockers** so that the mere act of examination cannot alter the original.
- Work on a **verified working copy**, never the original.
- Maintain **tamper-evident, anti-static, Faraday** packaging (Faraday bag for live phones, to
  prevent remote wipe and network changes).
- **Photograph** the device, its screen state, its ports and its serial/IMEI before seizure.
- Log every tool used, with version number.

### §4.6 Likely exam questions (Unit 2)
| Marks | Question |
|:--:|---|
| 5 | Define physical evidence and state its importance in criminal investigation. |
| 5 | Distinguish between class and individual characteristics with examples. |
| 5 | Describe any three crime-scene search methods with diagrams. |
| 5 | What is chain of custody? Why is it important? |
| 10 | Describe the various searching methods for locating physical evidence at a scene of crime, with diagrams, stating the suitability of each. |
| 10 | Explain chain of custody. What does the chain-of-custody form record, and what are the consequences of a break in the chain? |
| 15 | Discuss physical evidence — its types, characteristics and value — and explain how its integrity is maintained from the scene to the court. |

### MCQ traps (Unit 2)
- **Grid = double strip**, and is the **most thorough**; **wheel/ray** is the *least* suitable for
  large areas.
- **Zone** search is the standard **indoor** method.
- Fingerprint **pattern type (loop/whorl/arch) is a CLASS characteristic**; minutiae are individual.
- Blood **group is class**, **DNA is individual**.
- Refractive index of glass = **class**; a **physical (jigsaw) fit** = individual.
- Chain of custody documents **possession**, not analysis results.
- A mismatch in class characteristics → **exclusion** is valid.

---

# §5. Scene of Crime (TP-I Unit 3)

## 5.1 Meaning and types

**Scene of crime:** the **place where the offence was committed**, together with the surrounding
area over which physical evidence may be distributed — including approach routes, escape routes,
and any place where evidence of the crime may be found.

**Types**

| Basis | Types |
|---|---|
| **Location** | **Indoor** (house, office, shop, server room) · **Outdoor** (field, road, forest) · **Conveyance** (vehicle, train, aircraft, vessel) · **Underwater** |
| **Sequence / importance** | **Primary scene** — where the crime actually occurred / the main criminal act took place · **Secondary scene** — any additional scene related to the crime (where the body was dumped, where the weapon was discarded, the suspect's house, the vehicle used) |
| **Size / detail** | **Macroscopic** — the scene as a whole and its large components (the room, the body, the vehicle) · **Microscopic** — the small specific details (a hair, a fibre, a latent print, a droplet) |
| **Condition** | **Original/unaltered** vs **altered/contaminated** (by rescuers, relatives, weather, media) |
| **Nature of offence** | Homicide, burglary, arson, explosion, road accident, sexual assault, **cybercrime scene** |

**The cybercrime scene** is a special case worth a paragraph: it can be **physical** (the room
with the computer), **logical** (the file system, the memory), and **remote/distributed** (a
server abroad, a cloud tenancy). It may be **all three at once**, which is why jurisdiction is
the hardest problem in cyber forensics.

**Comparison: indoor vs outdoor scenes**

| Factor | Indoor | Outdoor |
|---|---|---|
| Boundaries | Defined by walls — easy to fix | Ill-defined — must be decided by the officer |
| Preservation | Easier; can be locked and guarded | Difficult |
| Threat to evidence | People, cleaning, pets | **Weather (rain, wind, sun), animals, traffic, public** — urgency is far higher |
| Lighting | Controllable | Time-limited by daylight |
| Search pattern | Zone/quadrant | Strip, grid, spiral |
| Priority | Systematic thoroughness | **Speed** — protect and collect perishable evidence first |

## 5.2 Protection and securing of the scene

**Concept:** the value of a scene falls the moment anyone walks into it. The first officer's job
is not to investigate but to **freeze** the scene.

**Duties of the first officer at a physical crime scene (in order):**
1. **Assess safety and hazards** — armed suspect, fire, gas, electricity, chemicals, structural
   collapse, biohazard.
2. **Preserve life** — render medical aid; the injured take priority over evidence. If a body must
   be moved, **document its original position first** (chalk/marker + photo).
3. **Detain and separate** any persons present; note names, addresses and their movements at the
   scene.
4. **Establish the boundary and cordon** the scene — "make it bigger than you think you need; you
   can always shrink it, you can never expand it backwards".
5. **Establish a single common approach path (CAP)** — one route in and out, itself searched and
   cleared first.
6. **Maintain an entry/exit log** — name, designation, time in, time out, purpose, for every
   person including senior officers.
7. **Exclude everyone unauthorised** — relatives, media, sightseers, and, crucially, **senior
   officers with no role at the scene**.
8. **Protect perishable evidence** — cover footprints from rain, shelter a bloodstain, note
   transient evidence (odours, temperature, lights on/off) immediately in the notebook.
9. **Do not touch, move, smoke, eat, drink, use the toilet or the telephone** at the scene.
10. **Record initial observations** — time of arrival, weather, lighting, doors/windows open or
    shut, appliances on/off.
11. **Inform** the investigating officer, the FSL/mobile unit, the fingerprint bureau, the
    photographer and the medical officer.
12. **Hand over** formally to the investigating officer, with a briefing and the log.

**The three-layer perimeter (draw it)**
```
   ┌──────────── OUTER cordon (public/media held here) ─────────────┐
   │   ┌──────── INNER cordon (authorised personnel only) ───────┐  │
   │   │        ┌──── CORE / focal scene (only the SOCO team) ─┐ │  │
   │   │        │            ✕ body / focal point              │ │  │
   │   │        └──────────────────────────────────────────────┘ │  │
   │   │   ← Common Approach Path runs from outer to core →      │  │
   │   └─────────────────────────────────────────────────────────┘  │
   │   Command post, vehicles, PPE donning area in this ring        │
   └────────────────────────────────────────────────────────────────┘
```

**For a digital crime scene, add:**
- **Do not switch the computer on if it is off; do not switch it off if it is on** (see the
  pull-the-plug debate in `FOR_03` §3).
- Photograph the **screen** before anything.
- Move suspects **away from keyboards** immediately (risk of a kill command or wipe).
- Isolate mobile devices in a **Faraday bag** or enable airplane mode (remote wipe risk).
- Note and photograph all **cables, ports and connected devices** before disconnecting; label
  each cable and its port.

## 5.3 Crime scene documentation

> **The golden rule: document *before* you disturb.** Notes, photographs, video and sketch are
> **complementary, not alternatives** — a good scene has all four. That sentence alone earns a
> mark.

### (a) Note taking

- **Contemporaneous** — written at the scene as things happen, never reconstructed later.
- Record: date and time of the call, time of arrival, weather and lighting, exact location, who
  was present, who summoned whom, condition of doors/windows/lights/appliances, position and
  condition of the body, transient observations (odours, temperature, wetness), description and
  location of each item of evidence, who collected what and when, time of departure.
- Use a **bound notebook with numbered pages**, ink, no erasures — strike a line through errors and
  initial them (an erasure suggests alteration).
- Note **negative findings** explicitly ("no forced entry observed at the rear door").
- Notes are **disclosable** and can be demanded in cross-examination — write them as if the
  defence will read them, because it will.

### (b) Photography

**Principle:** photographs must show the scene **as it was found**, must not distort, and must be
supported by a photograph log.

**The required sequence — memorise these three levels:**

| Level | What it shows | Purpose |
|---|---|---|
| **1. Overall / long-range** | The entire scene and its surroundings, exterior of the building, street, approach routes, all four walls of a room, ceiling and floor | Establishes **where** the scene is and its general layout — orientation |
| **2. Mid-range / medium** | An item of evidence **together with a recognisable fixed landmark** (a door, a table, a wall) | Establishes the **spatial relationship** of the evidence to the scene |
| **3. Close-up** | The item alone, filling the frame — **twice: once WITHOUT a scale, then again WITH a scale** and an identification label | Records the **detail** of the item; the scale permits later measurement and 1:1 comparison |

**Why "without a scale first"?** Because the defence can argue the scale was placed so as to
obscure or alter something. The unscaled photograph proves the item's appearance before anything
was added to the frame.

**Other photography rules**
- Photograph **before** any item is moved, marked or numbered — then re-photograph with the
  evidence markers in place.
- Photograph the scene from **all four corners / all approaches**, and the **ceiling and floor**.
- Take **eye-level** shots to reflect a witness's viewpoint where relevant.
- Photograph the **entrance and exit points** and any signs of forced entry.
- Photograph the **body** from all sides, plus the surface underneath after removal.
- Maintain a **photograph log**: photo number, subject, direction faced, time, camera settings,
  photographer.
- Do not use filters, do not edit; retain the **original RAW/unaltered files** with hash values.
- **Digital scenes:** photograph the screen, the front and rear of every device, all serial
  numbers/IMEI/service tags, the cable layout, and the surrounding desk (sticky notes with
  passwords are real and common).

### (c) Videography

- Provides a **continuous, contextual walkthrough** that stills cannot — spatial relationships,
  scale, and the sense of moving through the scene.
- Start with a **statement to camera**: case number, date, time, location, name of the operator.
- Move **slowly and steadily**, no zoom-happy jerks, no rapid panning.
- **No commentary of opinions** — narration should be purely factual, or the audio may be turned
  off entirely (a stray speculative remark on the tape is a gift to the defence).
- Do the videography **before** stills and before any evidence markers are placed, and again
  afterwards if required.
- Do not edit; retain the original file and its hash.
- Videography is now increasingly **mandatory in India** for search and seizure in certain
  offences under the BNSS 2023 ⚠️ verify the section.

### (d) Sketching

**Why sketch when you have photographs?** Because a photograph **distorts perspective and does
not give measurements**. A sketch gives **accurate relative distances** and removes irrelevant
clutter. Photograph = appearance; sketch = **dimension**.

| Type | Made | Contents |
|---|---|---|
| **Rough sketch** | **At the scene**, freehand, **not to scale** | All measurements written in, all evidence items numbered, compass north, dimensions of the room, position of doors/windows/furniture/body/evidence. Must **never be altered or destroyed** — it is the original record and is producible in court. |
| **Finished / final sketch** | **Later, in the office**, **drawn to scale** (by hand or with CAD) | Neat, to scale, with a **legend/key**, **scale ratio (e.g. 1:50)**, **north arrow**, case number, date, location, name and signature of the preparer, and a note of who took the measurements. Only relevant items retained. |

**Essential elements of any crime-scene sketch (the "must-have" list):**
1. Case number, date and time
2. Location/address
3. **North arrow (compass direction)**
4. **Scale** (or the words "not to scale" on the rough sketch)
5. **Legend/key** identifying numbered items
6. Names of the sketcher and the measurer, with signatures
7. Names of witnesses present

**Measurement methods — describe these (very examinable):**

| Method | How it works | Best for |
|---|---|---|
| **Rectangular coordinate** | Measure the **perpendicular distance from an object to two fixed walls at right angles** to each other (e.g. 1.2 m from the north wall, 2.4 m from the east wall) | **Indoor** scenes with square rooms — the standard method |
| **Triangulation** | Measure the distance from the object to **two (or three) fixed reference points**; the intersection of the arcs fixes the position | **Outdoor** scenes with no straight walls; irregular areas |
| **Baseline (coordinate)** | Establish a fixed straight line (a tape between two fixed points, or a wall); for each item measure the distance **along** the baseline and the **perpendicular offset** from it | Large **outdoor** scenes, roads, open ground |
| **Polar / azimuth coordinate** | From a single fixed point, record the **distance and the angle (bearing)** to each object | Large open areas, aerial/surveying-style work, **total-station** or **3-D scanner** use |
| **Cross-projection / "exploded" sketch** | The walls and ceiling are drawn as if folded flat outward from the floor plan, so that evidence on the **walls and ceiling** (bullet holes, blood spatter) can be plotted with floor evidence on one sheet | Rooms with evidence on **vertical surfaces** — shootings, blood-spatter scenes |
| **Elevation sketch** | A side/vertical view | Height of a bullet hole, a hanging point |

**Diagram to practise:** draw a rectangular room plan with a door, two windows, a body, and three
numbered evidence items; annotate two of them with rectangular coordinates and one by
triangulation; add a north arrow, scale bar and legend. Do this once a week — it is a ready-made
answer to any sketching question.

### (e) 3-D scanning technique

**Concept:** a laser scanner (LIDAR) or structured-light/photogrammetric system placed at several
positions in the scene records **millions of measured points** (a "point cloud"), each with X, Y, Z
coordinates and often colour. The scans are registered together into a single, dimensionally
accurate **3-D digital model of the entire scene**.

**How it works:**
1. The scanner is placed at a station and rotates through 360°, emitting a laser pulse and timing
   its return (**time-of-flight**) or measuring **phase shift** to compute distance.
2. Reference **targets/spheres** are placed so that scans from different stations can be
   **registered** (aligned) into one coordinate system.
3. Multiple stations are scanned to eliminate "shadows" behind objects.
4. Photographs are mapped onto the point cloud for colour/texture.
5. Software produces measurements, floor plans, sections, walkthrough animations and VR views.

**Advantages**
- **Captures everything, measured, at once** — you can take a measurement months later that nobody
  thought to take at the scene.
- **Non-contact and non-destructive**; nothing is disturbed.
- **Very fast** compared with manual measuring; a room in minutes.
- Extremely **accurate** (millimetre order) and reduces human measurement error.
- Enables **reconstruction**: bullet trajectories, line-of-sight/visibility analysis, blood
  spatter point-of-origin, vehicle-collision reconstruction.
- Produces compelling, easily understood **courtroom visualisations**; the scene can be "revisited"
  virtually after it has been released.
- Permits **virtual walkthroughs** by the judge or jury.

**Limitations**
- **High cost** of equipment and software; specialised training needed.
- Large **data volumes** and processing time.
- Records **geometry, not micro-detail** — it will not show a latent fingerprint or a fibre; it
  supplements, never replaces, photography and physical collection.
- **Line-of-sight limited** — occluded areas need extra stations; poor with transparent, glossy or
  very dark surfaces.
- Weather/vibration sensitive outdoors.
- Requires the court to accept the **validation and authenticity** of the model — and the model is
  itself electronic evidence requiring a §65B/BSA §63 certificate.

## 5.4 Processing of physical evidence — the full lifecycle

Learn this as a **pipeline**; it is an easy 10- or 15-mark answer.

```
DISCOVER → RECOGNISE → DOCUMENT → EXAMINE (in situ) → COLLECT →
PRESERVE → PACKAGE → SEAL → LABEL → FORWARD → (LAB) ANALYSE →
REPORT → STORE → PRODUCE IN COURT → DISPOSE
```

### (a) Discovering physical evidence
Systematic **search** (§4.4) plus enhancement techniques: oblique/grazing **light** to reveal dust
prints and impressions, **forensic light sources / alternate light source (ALS)** in various
wavelengths with goggles to make body fluids, fibres and bruises fluoresce, **UV and IR**
photography, **luminol / BLUESTAR** for latent blood (including washed-away blood),
**ninhydrin/cyanoacrylate/powders** for latent fingerprints, metal detectors for buried
metal, cadaver dogs, ground-penetrating radar for buried remains.

### (b) Recognising physical evidence
The single most important skill and the commonest failure. It requires the investigator to know
what is **relevant to this offence**. Ask: *what would have had to happen for this crime to occur,
and what would that have left behind?* Reconstruct hypothetically, then look for the predicted
traces. Beware of: evidence that looks like rubbish (a cigarette end, a chewing-gum wad, a
discarded receipt), **negative evidence**, and evidence that is **not at the scene but on the
suspect or victim** (fingernail scrapings, clothing, shoes).

### (c) Examination at the scene
Preliminary/**presumptive** tests only — Kastle-Meyer/phenolphthalein for blood, acid phosphatase
for semen, colour tests for narcotics, portable spectrometers. These are **screening** tests:
they can **exclude**, and they guide collection, but they are **not confirmatory** and their
result must never be reported as a conclusion. Confirmatory tests belong in the laboratory.
Do only what cannot be postponed.

### (d) Collection
- Document (notes, photo, sketch) **first**; then collect.
- Collect the item **in its entirety** wherever possible — take the whole cushion, not a cut-out;
  take the whole door lock, not just the marks.
- Collect from **most fragile/transient first** (the crime-scene equivalent of the order of
  volatility).
- Where the item cannot be moved, collect the stain/trace: **swab** (moisten a sterile swab with
  distilled water for a dried stain), **scrape**, **tape-lift** (for fibres and hair),
  **vacuum** (last resort — collects too much), **cast** (dental stone for footwear/tyre marks,
  silicone for tool marks), or **lift** (adhesive lifter for fingerprints).
- **Always collect a CONTROL/reference sample**: unstained substrate next to the stain, soil from
  a nearby unrelated area, a known blood sample from the victim and suspect, a specimen of the
  suspect's handwriting. *Without a control the Principle of Comparison cannot be satisfied.*
- Use **clean, new** tools for each item; change gloves between items.
- Assign a **unique exhibit number** at the moment of collection and start the chain-of-custody
  entry immediately.

### (e) Safety measures for evidence collection

| Hazard | Measure |
|---|---|
| **Biohazard** (blood, body fluids — HIV, hepatitis B/C, TB) | **Universal precautions**: treat all body fluids as infectious. Double **nitrile gloves**, gown/coverall (Tyvek), **N95/FFP2 mask**, eye protection/face shield, shoe covers, hair cover |
| **Sharps** — needles, broken glass, knives | Never place hands where you cannot see; use forceps; **puncture-proof containers**; never recap needles |
| **Chemical** — drug labs, explosives, corrosives, unknown powders | Respirator, chemical-resistant gloves, ventilation; do not open unknown containers; call the bomb squad/chemical team |
| **Fire/explosion, structural collapse, electricity** | Clear the scene until specialists declare it safe |
| **Radiological/CBRN** | Specialist teams only |
| **Cross-contamination between exhibits** | Change gloves and tools between items; package separately; separate personnel for suspect and victim/scene wherever possible |
| **Contamination BY the investigator** | Elimination samples (DNA and fingerprints) from all scene personnel; masks to prevent breath DNA |
| **Digital-specific** | Anti-static wrist strap and **anti-static bags** (not ordinary plastic — static discharge can destroy a drive); keep media away from magnets, radios and heat; **Faraday bag** for live phones; battery/charger for a live phone so it does not power down mid-seizure |
| General | Never eat, drink, smoke or apply cosmetics at the scene; wash hands after; dispose of PPE as biohazard waste |

### (f) Preservation
Keep the evidence in the condition in which it was found, for as long as it may be needed.

| Evidence | Preservation requirement |
|---|---|
| **Wet biological stains (blood, semen)** | **Air-dry completely at room temperature in the shade** before packaging; never dry with heat or sunlight |
| **Dried blood/DNA samples** | Cool and dry; **refrigerate** for medium term, **freeze (−20 °C)** for long term; keep away from humidity |
| **Liquid blood (reference sample)** | In an EDTA vacutainer, **refrigerated (4 °C), never frozen** |
| **Viscera for toxicology** | Preserved in **saturated saline** (and a separate portion in **rectified spirit** for some analytes); a **control of the preservative** must also be sent ⚠️ verify the standard preservative combination against a forensic medicine text |
| **Arson/fire debris** | **Airtight metal cans or nylon bags** — accelerant vapours escape from ordinary plastic and paper |
| **Volatiles / alcohol samples** | Airtight, cool, with preservative (sodium fluoride + potassium oxalate for blood alcohol) ⚠️ verify |
| **Firearms** | Unloaded and made safe, documented; do not clean; package to avoid disturbing residues; **swab hands for GSR within a few hours** |
| **Documents** | Flat, in transparent envelopes/folders; never fold along new lines; never staple, pin, or write on |
| **Soil/glass/paint** | Dry, in paper packets or vials |
| **Impressions** | Cast, or lifted and protected |
| **Digital media** | **Anti-static** bags; away from magnetic fields, heat, moisture and vibration; **never** in ordinary polythene; keep phones charged and network-isolated |

### (g) Packaging — the rules and the classic exam point

**The golden rule: BIOLOGICAL EVIDENCE GOES IN PAPER, NEVER IN PLASTIC.**
*Why?* Plastic is airtight; residual moisture cannot escape; bacteria and fungi grow and
**degrade the DNA**. Paper "breathes" and allows the sample to continue drying.

| Evidence | Correct packaging |
|---|---|
| Dried bloodstained clothing, biological items | **Paper bags, paper bindles, cardboard boxes**, breathable — after air-drying |
| Fibres, hair, glass fragments, paint chips, small trace | **Paper bindle (druggist's fold)** placed inside an envelope or vial |
| Wet/damp items | **Air-dry first**; if impossible, transport in paper and dry at the earliest, documenting the fact |
| **Arson debris / accelerants** | **Clean, unused metal paint cans** (airtight), or special nylon/Kapak bags — **NOT** ordinary plastic (vapour loss and contamination) |
| Liquids | Leak-proof, non-breakable bottles with screw caps, sealed and placed inside a secondary container |
| Sharp items (knives, syringes) | Rigid puncture-resistant container, blade immobilised, with hazard labelling |
| Firearms | Rigid box, secured to prevent movement, muzzle direction noted, unloaded |
| Documents | Flat between card, in a transparent envelope/folder; unfolded, unstapled |
| Impression casts | Rigid box with padding, after full curing |
| **Hard disks, memory cards, USB drives** | **Anti-static (ESD) bags**, then a rigid box with padding; tamper-evident evidence tape |
| **Mobile phones** | **Faraday bag / signal-shielding bag**; if switched on, keep it powered (with a charger inside the shielded bag) or note the decision to power down; document battery level |
| CDs/DVDs | Protective sleeves/jewel cases, avoid scratching the data surface |
| Latent-print items | Handle by edges, package so surfaces are not rubbed; box, do not bag loosely |

**General packaging rules**
1. **One item, one package.** Never mix exhibits — cross-contamination.
2. Package so that the item **cannot move** inside the container.
3. **Do not over-handle** — package at the scene, at the point of collection.
4. Package so that the item can be examined **without breaking the seal in the wrong place** where
   possible.
5. Include the **control samples** in separate packages.
6. **Suspect's and victim's items must be packaged, transported and stored separately**, and
   preferably handled by different personnel.

### (h) Sealing
- The package is closed so that it **cannot be opened without visibly destroying the seal**
  ("tamper-evident").
- Traditional Indian practice: the packet is stitched/wrapped in cloth and sealed with **lac/wax
  bearing a distinctive seal impression**; the **specimen impression of the seal** is separately
  forwarded to the laboratory so it can verify that the seal on receipt matches.
- Modern practice: **tamper-evident evidence tape** signed and dated **across the seam**, so that
  the signature is broken if the tape is lifted.
- The **seal number/description is recorded** on the seizure memo and chain-of-custody form.
- The seal is applied **in the presence of independent witnesses**, who also sign.
- The laboratory records on receipt whether the **seal was intact and matched the specimen**; if
  not, this is noted in the report and is usually fatal to the exhibit.
- **Digital equivalent of a seal = the hash value.**

### (i) Labelling
Every package must bear, on the package itself (not only on a tag that can fall off):
1. **Case/FIR number**, police station, sections of law
2. **Unique exhibit number** ("Ex-4")
3. **Description** of the contents
4. **Date, time and place of collection**
5. **Name and signature of the collecting officer**, and of witnesses
6. **Name of the person from whom / place from which** it was seized
7. **Seal details**
8. **Hazard warnings** (biohazard, sharps, flammable) where applicable
9. Any special handling instruction ("keep refrigerated", "fragile", "anti-static")

### (j) Forwarding
- A **forwarding letter/requisition** from the investigating officer or the court accompanies the
  exhibits, stating: the case details, a **list of exhibits with their seals**, a brief **history
  of the case** (essential — the laboratory needs context to choose the right analysis), and the
  **specific questions to be answered** ("is this human blood and does it match Ex-7?").
- The **specimen seal impression** is enclosed.
- Exhibits are sent by a **responsible officer by hand**, or by an approved secure channel; never
  by ordinary post for critical exhibits.
- **Perishable exhibits are sent first and fastest**; refrigerated transport where required.
- The lab issues an **acknowledgement/receipt** noting the condition and seals — this becomes the
  next link in the chain of custody.
- The **court's order** may be required for forwarding certain exhibits ⚠️ verify the relevant BNSS
  provision (formerly CrPC §§ relating to sending exhibits for examination).

### §5.5 Likely exam questions (Unit 3)
| Marks | Question |
|:--:|---|
| 5 | What is a scene of crime? Distinguish between primary and secondary scenes. |
| 5 | Describe the duties of the first officer at the scene of crime. |
| 5 | Distinguish between a rough sketch and a finished sketch. |
| 5 | Why must biological evidence never be packaged in plastic? |
| 5 | Write a note on 3-D scanning of a crime scene. |
| 10 | Describe crime-scene documentation under the heads of note taking, photography, videography and sketching. |
| 10 | Explain the methods of measurement used in crime-scene sketching, with diagrams. |
| 10 | Describe the processing of physical evidence from collection to forwarding to the laboratory. |
| 15 | Describe in detail the procedure to be followed at a scene of crime from the arrival of the first officer to the forwarding of exhibits to the laboratory, with particular reference to a scene involving computers. |
| 15 | Discuss crime-scene documentation and the packaging, sealing, labelling and forwarding of physical evidence. Why is each step legally significant? |

### MCQ traps (Unit 3)
- Photography sequence is **overall → mid-range → close-up**, and close-ups are taken **without,
  then with**, a scale.
- The **rough sketch** is made at the scene and is **not to scale**; the **finished sketch is to
  scale**. The rough sketch must be preserved.
- **Triangulation** = distances from **two fixed points**; **rectangular coordinates** = perpendicular
  distances from **two walls at right angles**; **baseline** = along-and-offset from a line.
- **Cross-projection sketch** is for evidence on **walls and ceiling**.
- Arson debris goes in **airtight metal cans**, not paper and not ordinary plastic — this is the
  one exception to "biological in paper", and examiners love it.
- Wet bloodstains are **air-dried at room temperature in the shade**, not heated, not sun-dried.
- A **presumptive test is not confirmatory**.
- The first responder's first priority is **safety/preservation of life**, not evidence.

---

# §6. Indian Legal Framework for Electronic Evidence
### (exam-appropriate depth; accuracy flagged where uncertain)

> ⚠️ **Read this whole section with care.** Section numbers are the easiest place to lose marks by
> confidently writing something wrong. Where a number is marked ⚠️, verify it against
> `indiacode.nic.in` before the exam. **In the exam, when unsure of a number, describe the
> provision correctly and name the statute — a correct description without a number scores far
> better than a wrong number.**

## 6.1 The big change: IEA 1872 → BSA 2023

| Old law (until 30 June 2024) | New law (from **1 July 2024**) |
|---|---|
| **Indian Evidence Act, 1872** | **Bharatiya Sakshya Adhiniyam (BSA), 2023** |
| **Indian Penal Code, 1860** | **Bharatiya Nyaya Sanhita (BNS), 2023** |
| **Code of Criminal Procedure, 1973** | **Bharatiya Nagarik Suraksha Sanhita (BNSS), 2023** |

**What changed for digital evidence (the substance, which is safe to state):**
- The BSA **expands the definition of "document"** to expressly include **electronic and digital
  records** — emails, server logs, smartphone messages, locational evidence, voice mail — placing
  them on the same footing as documentary evidence.
- Electronic records are now expressly **primary evidence** in defined circumstances (e.g. where
  a record is stored in multiple files/storage spaces, each is primary evidence).
- The **certificate requirement** for admitting an electronic record produced from a computer is
  **retained** and made more elaborate, now requiring a certificate from **both** the person in
  charge of the device **and** an expert ⚠️ verify this detail.
- The **BNSS** mandates **audio-video recording** of search and seizure, and mandates forensic
  team visits for offences punishable with **seven years or more** ⚠️ verify sections.

**Section-number mapping (⚠️ verify all of these before writing them as facts):**

| Provision | IEA 1872 | BSA 2023 (⚠️ verify) |
|---|---|---|
| Definition of "evidence" / "document" including electronic records | §3 | §2 |
| Opinion of experts | **§45** | §39 |
| Opinion of the Examiner of Electronic Evidence | §45A | §39(2) |
| Primary evidence | §62 | §57 |
| Secondary evidence | §63 | §58 |
| **Admissibility of electronic records + certificate** | **§65B** | **§63** (certificate under §63(4), in the form of the **Schedule**) |
| Presumption as to electronic messages | §88A | §92 |
| Presumption as to electronic records five years old | §90A | §93 |
| Presumption as to electronic signature certificates | §85B/85C | §§90–91 |

> **Safe exam formulation:** *"Electronic evidence is admissible subject to the certificate
> requirement — formerly §65B of the Indian Evidence Act, 1872, and now the corresponding
> provision of the Bharatiya Sakshya Adhiniyam, 2023 (§63, with the certificate under §63(4))."*
> This is correct whichever numbering the examiner has in mind.

## 6.2 Admissibility of electronic evidence — the concept

**The problem:** an electronic record is not a thing; it is a *representation* produced by a
machine from stored bits. It can be perfectly copied, silently altered, and generated by
software the court has never seen. So the law needs a mechanism to satisfy itself that:
1. the record is **authentic** — it is what it claims to be;
2. it is **integral** — it has not been altered;
3. the **computer that produced it was working properly** and was used regularly.

**The solution:** the **§65B (now BSA §63) certificate.** The printout/copy of an electronic
record is admissible **as if it were the original document**, without producing the original
computer, **provided** the statutory conditions are met and a certificate is filed.

### The four conditions (§65B(2) IEA; substantially carried into BSA §63(2) ⚠️ verify)

The computer output must satisfy that:
1. It was produced by a computer **used regularly** to store or process information for activities
   **regularly carried on** by the person having lawful control over it.
2. Information of that kind was **regularly fed** into the computer in the ordinary course of
   those activities.
3. Throughout the material period the computer was **operating properly**; or if not, any
   malfunction did not affect the accuracy/contents of the record.
4. The information in the output **reproduces or is derived from** the information fed into the
   computer in the ordinary course.

### What the certificate must state (§65B(4) IEA; BSA §63(4) ⚠️ verify)

1. **Identify** the electronic record and describe how it was produced.
2. Give **particulars of the device** involved in producing it, so as to show that it was produced
   by a computer.
3. Deal with the matters in the four conditions above.
4. Be **signed by a person occupying a responsible official position** in relation to the
   operation of the relevant device or the management of the relevant activities — and under the
   BSA also by an **expert** ⚠️ verify.
5. It is sufficient that the statement is made **to the best of the signatory's knowledge and
   belief**.

### The case law (state these carefully — do not invent holdings)

| Case | Holding (in substance) |
|---|---|
| **State (NCT of Delhi) v. Navjot Sandhu** ("Parliament attack case"), 2005 | Held that electronic records could be proved under §§63/65 as secondary evidence even without a §65B certificate. **Later overruled on this point.** |
| **Anvar P.V. v. P.K. Basheer**, 2014 | **Overruled Navjot Sandhu.** Held §65B is a **complete code**; a §65B(4) certificate is **mandatory** for admitting secondary electronic evidence. |
| **Shafhi Mohammad v. State of Himachal Pradesh**, 2018 | Took a relaxed view — the certificate could be dispensed with where the party did not possess the device. **Later held to be per incuriam.** |
| **Arjun Panditrao Khotkar v. Kailash Kushanrao Gorantyal**, 2020 | **Settled the law.** Reaffirmed *Anvar P.V.*; the §65B(4) certificate is **mandatory** for secondary electronic evidence; *Shafhi Mohammad* held to be incorrect; a party unable to obtain the certificate may apply to the court to summon it from the person in control. |

> ⚠️ Verify the exact citations before quoting them as "(2020) 7 SCC 1" etc. — **name the case and
> state the holding; you do not need the reporter citation for full marks.**

**Practical exam point:** if the certificate is missing, the electronic record is **inadmissible**
— not merely weak. This makes the certificate the single most important document a digital
forensic examiner must ensure exists. Contrast this with the chain of custody, whose absence
usually goes to *weight* rather than *admissibility*.

**Note on primary evidence:** where the **original device itself** is produced and proved by the
person who owned/operated it, the certificate is not needed — the certificate is required for
**secondary** electronic evidence (a printout, a copy, a forensic image tendered instead of the
device).

## 6.3 The Information Technology Act, 2000 — key provisions

**Scope of the Act:** gives legal recognition to electronic records and digital/electronic
signatures, facilitates e-governance and e-commerce, creates offences and penalties for computer
misuse, provides for the Controller of Certifying Authorities, and amended the IPC, Evidence Act,
Bankers' Books Evidence Act and RBI Act. Substantially **amended in 2008** (in force 2009), which
inserted most of the §66-series offences and §69, §69A, §69B, §70A, §70B, §79 and §43A.

### Offence and penalty sections (learn these; do not invent others)

| Section | Subject |
|---|---|
| **§43** | Penalty and **compensation** for damage to computer, computer system etc. — unauthorised access, downloading, introducing virus, damage, disruption, denial of access, tampering, stealing source code. **Civil liability**, adjudicated by an Adjudicating Officer |
| **§43A** | Compensation for failure to protect **sensitive personal data** by a body corporate (reasonable security practices) ⚠️ note the interaction with the **DPDP Act 2023** |
| **§65** | **Tampering with computer source documents** — concealing, destroying, altering source code required to be kept by law. Up to **3 years** imprisonment and/or fine up to ₹2 lakh ⚠️ verify quantum |
| **§66** | **Computer-related offences** — doing any act referred to in §43 **dishonestly or fraudulently**. Up to **3 years** and/or fine up to ₹5 lakh ⚠️ verify |
| **§66B** | Dishonestly **receiving stolen computer resource** or communication device |
| **§66C** | **Identity theft** — fraudulent use of another's electronic signature, password or other unique identification feature |
| **§66D** | **Cheating by personation using a computer resource** — the section used for **phishing/vishing** and most online frauds |
| **§66E** | **Violation of privacy** — capturing/publishing/transmitting the image of a private area of a person without consent |
| **§66F** | **Cyber terrorism** — punishable with imprisonment which may extend to **imprisonment for life** |
| **§67** | Publishing or transmitting **obscene material** in electronic form |
| **§67A** | Publishing/transmitting material containing **sexually explicit** act |
| **§67B** | **Child sexually abusive material (CSAM)** — publishing/transmitting/browsing etc. |
| **§67C** | **Preservation and retention of information by intermediaries** |
| **§69** | Power to issue directions for **interception, monitoring or decryption** of information |
| **§69A** | Power to issue directions for **blocking public access** to information |
| **§69B** | Power to authorise **monitoring and collection of traffic data** for cyber security |
| **§70** | **Protected system** — unauthorised access punishable up to **10 years** |
| **§70A** | **NCIIPC** — National Critical Information Infrastructure Protection Centre |
| **§70B** | **CERT-In** — national nodal agency for incident response |
| **§72** | Breach of **confidentiality and privacy** by a person with statutory powers |
| **§72A** | Disclosure of information in **breach of a lawful contract** |
| **§79** | **Intermediary liability — safe harbour**, subject to due diligence and the Intermediary Guidelines |
| **§85** | Offences by **companies** |

### Provisions specifically relevant to a forensic examiner

| Section | Relevance |
|---|---|
| **§2(1)(t)** | Definition of **"electronic record"** ⚠️ verify sub-clause letter |
| **§3 / §3A** | **Digital signature** and **electronic signature** |
| **§4, §5** | Legal recognition of electronic records and electronic signatures |
| **§7** | Retention of electronic records |
| **§67C** | Intermediaries must **preserve and retain** specified information — the basis for demanding logs from an ISP or platform |
| **§69** | Legal authority for **interception/decryption** — and the power to require assistance/decryption keys |
| **§76** | **Confiscation** of computers/accessories involved in a contravention |
| **§78** | Investigation power — an officer **not below the rank of Inspector** may investigate offences under the Act ⚠️ verify the current rank after the 2008 amendment |
| **§79A** | Central Government may notify an **"Examiner of Electronic Evidence"** — the statutory expert body for electronic evidence (links to IEA §45A / BSA §39(2)) |
| **§80** | Power of a police officer (not below Inspector) to **enter any public place, search and arrest without warrant** ⚠️ verify |

### Other statutes worth naming
- **Bharatiya Nyaya Sanhita 2023** — general offences (cheating, forgery, criminal breach of
  trust, defamation, extortion) that apply to cyber conduct alongside the IT Act.
- **BNSS 2023** — search and seizure procedure, mandatory audio-video recording of search and
  seizure, mandatory forensic team visit for offences ≥7 years ⚠️ verify sections.
- **Digital Personal Data Protection Act, 2023 (DPDP)** — data-fiduciary obligations, consent,
  breach notification, Data Protection Board. (Implementation staged; rules notified separately
  ⚠️ verify current status.)
- **Indian Telegraph Act 1885 §5(2)** + Rule 419A — lawful interception of telephony.
- **CrPC/BNSS provisions on production of documents** — used to compel service providers.
- **POCSO Act 2012** — child sexual abuse material offences alongside IT Act §67B.
- **Copyright Act 1957 §63/§65A/§65B** — software piracy and circumvention of DRM ⚠️ verify.

## 6.4 The practical rule for a digital forensic examiner in India

For an electronic exhibit to reach the court with full value, **all four** of the following must
exist:

1. **Lawful authority** for the search and seizure (warrant/§ authority; *panchnama* with
   independent witnesses; audio-video recording under BNSS).
2. An **unbroken chain of custody**, documented from seizure onward.
3. **Proof of integrity** — a forensic image acquired with a write blocker, and **matching hash
   values** recorded at acquisition and re-verified at analysis.
4. A **§65B / BSA §63 certificate** accompanying the output tendered in court.

Miss (4) and the evidence is **inadmissible**. Miss (2) or (3) and it is admissible but
**worthless**. Miss (1) and you may face an illegality argument (though in India illegally
obtained evidence is not automatically inadmissible ⚠️ verify before stating as a rule).

### §6.5 Likely exam questions (legal)
| Marks | Question |
|:--:|---|
| 5 | What is a §65B certificate? What must it contain? |
| 5 | State any five offences under the Information Technology Act, 2000 with their sections. |
| 5 | What is meant by "Examiner of Electronic Evidence"? |
| 10 | Discuss the admissibility of electronic evidence in India with reference to the relevant statutory provisions and case law. |
| 10 | Explain the salient features of the Information Technology Act, 2000 relating to cyber offences. |
| 15 | "Digital evidence is fragile and easily challenged." Discuss the legal and procedural safeguards required in India for digital evidence to be admitted and relied upon by a court. |

### MCQ traps (legal)
- **§65B IEA (now BSA §63)** relates to **admissibility of electronic records**, not to expert opinion.
- **§45A IEA** (BSA §39(2)) = opinion of the **Examiner of Electronic Evidence**; **§45** = experts generally.
- **IT Act §66F = cyber terrorism** (life imprisonment); **§66C = identity theft**; **§66D = cheating by
  personation**; **§66E = privacy violation**. These four are the most-swapped options in any MCQ set.
- **§70B = CERT-In**; **§70A = NCIIPC**. Do not swap.
- The IT Act was substantially amended in **2008**.
- *Anvar P.V. (2014)* and *Arjun Panditrao (2020)* → certificate **mandatory**; *Navjot Sandhu (2005)*
  and *Shafhi Mohammad (2018)* → the **discredited** line of authority.
- The BSA/BNS/BNSS came into force on **1 July 2024**.

---

## Appendix — One-page revision sheet for FOR_01

**Six principles:** Locard (mutual exchange) · Individuality (everything unique) · Comparison
(like with like) · Analysis (sample + method + analyst) · Progressive change (everything changes
with time) · Circumstantial facts (facts don't lie, men do).

**Institutions:** MHA → **DFSS** (New Delhi, est. 2002) → **CFSLs** (Kolkata 1957 *oldest*,
Hyderabad, Chandigarh, **Guwahati** for NE, Bhopal, Pune, **Delhi under CBI**) + **GEQD**
(Shimla, Kolkata, Hyderabad). State side: State Home Dept → **SFSL** → **RFSL** → **MFSU**.
Also **BPR&D** (1970, research/training), **NCRB** (1986, NAFIS/CCTNS), **NFSU** (Gandhinagar
2020), **I4C**, **CERT-In** (IT Act §70B), **NCIIPC** (§70A).

**Search patterns:** Strip (open outdoor) · **Grid = double strip, most thorough** · Spiral
(small/confined, single searcher, underwater) · **Zone (indoor)** · Wheel/ray (small circular,
gaps at periphery).

**Photography:** overall → mid-range → close-up **(without scale, then with scale)**.

**Sketch:** rough (at scene, not to scale, preserve it) vs finished (office, to scale, legend,
north arrow). Measurements: rectangular coordinate · triangulation · baseline · polar ·
cross-projection (walls & ceiling).

**Packaging:** biological → **PAPER**, air-dried; arson debris → **airtight metal can**;
digital → **anti-static bag**; phones → **Faraday bag**. One item, one package.

**Chain of custody:** who, when, where, why, what — unbroken signatures; seal + specimen seal
impression; **hash = digital seal**.

**Law:** electronic evidence certificate = **§65B IEA → BSA §63(4)** (mandatory: *Anvar P.V.* 2014,
*Arjun Panditrao* 2020). IT Act: §43 civil · §65 source code · §66 computer offences · §66C ID
theft · §66D personation · §66E privacy · §66F cyber terrorism · §67/67A/67B obscene/explicit/CSAM
· §69 interception · §70 protected system · §70A NCIIPC · §70B CERT-In · §79 intermediary ·
§79A Examiner of Electronic Evidence.
