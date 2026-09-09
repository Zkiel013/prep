# FOR_05 — MCQ Bank + Descriptive Question Bank (Computer Forensic, NPSC CTSE 2026)

> **No CTSE past paper exists for Computer Forensic** — this elective is new to the CTSE pattern
> and no previous-year question paper is available anywhere (official or coaching-circulated).
> This file is therefore your **main practice source**, built directly from the official syllabus
> (`OFFICIAL_SYLLABUS.md`, TP-I units 1–9 and TP-II units 1–8) and from `FOR_01`–`FOR_04`. Treat
> every question here as a rehearsal for the *shape* the real exam will take, not as a leaked
> paper. Where a fact is legally/historically uncertain it is marked **⚠️ verify** — do not treat
> those as settled; do not quote them as certainties in the exam without your own check.

---

## 0. How to use the negative marking (MCQ paper: 100 × 2 = 200, −1/3 per wrong answer)

**The arithmetic first.** Each question is worth **+2** if correct, **−2/3 (−0.667)** if wrong,
**0** if left blank.

| Strategy | Expected value per question | Verdict |
|---|---|---|
| **Leave blank** (no guess) | 0 | Safe floor |
| **Blind guess among 4 options** (25% chance correct) | 0.25×2 + 0.75×(−0.667) = 0.5 − 0.5 = **≈0** | **Break-even** — no better or worse than skipping, pure noise either way |
| **Guess after eliminating 1 wrong option** (3 left, 33% chance) | 0.33×2 + 0.67×(−0.667) ≈ 0.667 − 0.445 = **+0.22** | **Worth it** |
| **Guess after eliminating 2 wrong options** (2 left, 50% chance) | 0.5×2 + 0.5×(−0.667) = 1 − 0.33 = **+0.67** | **Strongly worth it** |
| **Guess with full confidence in 1 option (no real doubt)** | ≈ +2 | Just answer it — this isn't really a "guess" |

**Rule of thumb for the exam hall:**
1. Never blind-guess with zero elimination — it is exactly break-even in theory, but in practice
   your "gut feel" 4-option guesses tend to run *worse* than 25% on badly-worded distractor
   questions (this bank is full of paired traps like Locard vs Gross, virus vs worm, MBR vs GPT
   precisely so you learn to eliminate, not gamble).
2. The instant you can honestly rule out **even one** option, guessing among the rest has
   positive expected value — do it.
3. Budget your first pass to **answer everything you know cold**, second pass to **eliminate and
   guess** on partial-knowledge questions, and only leave truly blank the ones where you have
   *zero* basis to eliminate anything.
4. This syllabus rewards elimination unusually well because so many MCQs are **paired traps**
   (two named people/two similar acronyms/two similar numbers) — half the option set is usually
   eliminable on a moment's recall of *which one is which*, even if you can't recall the exact
   fact being tested.

---

## 1. MCQ Bank (127 questions, spanning the whole syllabus)

Numbering is continuous 1–127. Grouped by topic block for study convenience; the real exam will
shuffle order and blocks freely, so do not expect this ordering on the paper.

### Block A — Forensic Science Fundamentals, Physical Evidence, Crime Scene (Q1–Q20)

**Q1.** Who is regarded as the "Father of Criminalistics"?
A) Edmond Locard  B) Hans Gross  C) Alphonse Bertillon  D) Mathieu Orfila

**Q2.** "Every contact leaves a trace" is a statement of:
A) Law of Individuality  B) Locard's Exchange Principle  C) Principle of Comparison  D) Law of Progressive Change

**Q3.** The world's first fingerprint bureau was established in:
A) Scotland Yard, 1901  B) Calcutta, 1897  C) Shimla, 1904  D) Lyon, 1910

**Q4.** The first Central Forensic Science Laboratory (CFSL) in India was set up at:
A) New Delhi  B) Hyderabad  C) Kolkata (Calcutta)  D) Chandigarh

**Q5.** CFSL New Delhi functions under the administrative control of:
A) DFSS/MHA  B) NCRB  C) CBI  D) BPR&D

**Q6.** The Government Examiner of Questioned Documents (GEQD) has its principal office at:
A) Kolkata  B) Hyderabad  C) New Delhi  D) Shimla

**Q7.** Which North-East India CFSL is regionally relevant to Nagaland?
A) CFSL Kolkata  B) CFSL Guwahati  C) CFSL Bhopal  D) CFSL Pune

**Q8.** NAFIS (fingerprint database) and CCTNS are operated by:
A) BPR&D  B) NCRB  C) DFSS  D) NFSU

**Q9.** A property shared by an entire manufactured batch/class of objects (e.g., shoe brand and size) is called a:
A) Individual characteristic  B) Class characteristic  C) Associative evidence  D) Transient evidence

**Q10.** Which of these is an example of an individual characteristic?
A) Shoe brand and size  B) Blood ABO group  C) Striations on a fired bullet from a specific barrel  D) Calibre of a firearm

**Q11.** A mismatch in class characteristics between a suspect item and crime-scene evidence results in:
A) Individualisation  B) Inconclusive result  C) Exclusion of the source  D) Automatic conviction

**Q12.** Evidence that is lost quickly if not recorded immediately (odour, temperature, wet stains) is called:
A) Pattern evidence  B) Conditional evidence  C) Transient evidence  D) Associative evidence

**Q13.** A search pattern in which the area is searched twice at 90° to each other is the:
A) Strip search  B) Grid search  C) Spiral search  D) Wheel/ray search

**Q14.** The search pattern best suited to a single body in an open field, searched by one person, is:
A) Zone search  B) Grid search  C) Spiral search  D) Strip search

**Q15.** The main weakness of the wheel/ray search pattern is:
A) It requires many searchers  B) Gaps diverge/widen towards the periphery  C) It cannot be used outdoors  D) It always takes the longest time

**Q16.** The zone/quadrant search pattern is best suited to:
A) Large open fields  B) Indoor scenes divided into rooms  C) Underwater searches  D) Circular blast craters

**Q17.** The documentary record of who held a piece of evidence, when, and what was done to it, from seizure to court, is called the:
A) Panchnama  B) Chain of custody  C) Forensic linkage triangle  D) Order of volatility

**Q18.** "Drylabbing" in forensic ethics means:
A) Testing in a low-humidity lab  B) Reporting results of tests never actually performed  C) Working without air conditioning  D) Refusing to testify

**Q19.** Which bias occurs when an analyst is told irrelevant case facts (e.g., suspect's prior convictions) before comparing evidence?
A) Confirmation bias  B) Contextual bias  C) Anchoring  D) Observer effect

**Q20.** The primary duty of a forensic expert witness in court is to:
A) The party who engaged them  B) The investigating officer  C) The court  D) The victim

### Block B — Computer Hardware, OS Basics, File Systems (Q21–Q30)

**Q21.** The component that holds instructions and data currently being processed and loses content on power-off is:
A) ROM  B) RAM  C) HDD  D) SSD

**Q22.** The firmware that performs POST and initiates the boot process on legacy systems is the:
A) BIOS  B) UEFI only  C) Bootloader  D) Kernel

**Q23.** The file system historically native to Windows NT/2000/XP and later, supporting permissions, journaling and large volumes, is:
A) FAT32  B) NTFS  C) ext4  D) HFS+

**Q24.** The default file system on modern Linux distributions is typically:
A) NTFS  B) exFAT  C) ext4  D) APFS

**Q25.** Apple's current file system (successor to HFS+) is:
A) APFS  B) exFAT  C) ext4  D) ReFS

**Q26.** In the standard boot sequence, which happens first?
A) OS kernel loads  B) POST (Power-On Self-Test)  C) User login  D) Application launch

**Q27.** A motherboard component that houses the CPU is the:
A) DIMM slot  B) Processor socket  C) PCI slot  D) SATA port

**Q28.** RAID is primarily used for:
A) Encrypting data  B) Redundancy and/or performance across multiple disks  C) Compressing files  D) Formatting partitions

**Q29.** The part of a computer that performs arithmetic and logic operations is the:
A) Control Unit  B) ALU  C) Cache  D) Register file

**Q30.** Non-volatile memory used to store firmware that is not (normally) rewritten by the user is:
A) RAM  B) ROM  C) L1 cache  D) Virtual memory

### Block C — Windows / Linux / macOS Artifacts (Q31–Q45)

**Q31.** Which Windows feature allows a file to hide additional data streams attached to it, invisible in normal directory listings?
A) Slack space  B) Alternate Data Streams (ADS)  C) Shadow copy  D) Prefetch

**Q32.** The Windows registry key associated with recording GUI program execution history (values stored ROT-13 encoded) is:
A) UserAssist  B) ShellBags  C) MountedDevices  D) RunMRU

**Q33.** Windows Registry keys that record USB device connection history (device IDs, first/last connected) are found under:
A) UserAssist  B) USBSTOR  C) TypedPaths  D) WordWheelQuery

**Q34.** In the NTFS/Windows registry, which of the following carries a LastWrite timestamp?
A) Individual registry values  B) Registry keys  C) Only the SAM hive  D) Only the SYSTEM hive

**Q35.** Windows ".lnk" shortcut files are forensically significant because they:
A) Are always malicious  B) Record evidence of file/program access even if the target is later deleted  C) Cannot be analysed  D) Only exist on servers

**Q36.** The unused space between the logical end of a file and the end of the last allocated disk cluster is called:
A) RAM slack / file slack  B) Alternate Data Stream  C) Unallocated space  D) Registry hive

**Q37.** In Linux, file and directory access rights are primarily controlled through:
A) NTFS ACLs only  B) Ownership (user/group/other) and permission bits (read/write/execute)  C) Alternate Data Streams  D) The Windows Registry

**Q38.** A hidden file in Linux is conventionally indicated by:
A) A ".hidden" extension  B) A leading dot (.) in the filename  C) A registry flag  D) An ADS marker

**Q39.** Linux user account and authentication information (hashed passwords) is stored in:
A) /etc/passwd only, in plaintext  B) /etc/shadow  C) The Windows SAM hive  D) /var/log/syslog only

**Q40.** In macOS forensics, hidden system directories (e.g., containing caches and system state) are analogous in purpose to which Windows artifact category?
A) Prefetch and hidden AppData folders  B) The MBR  C) The BIOS  D) DNS cache only

**Q41.** macOS system startup and background services are managed primarily through:
A) The Windows Registry  B) launchd and property list (.plist) files  C) systemd only  D) The Bootcamp partition

**Q42.** Linux system logs recording authentication attempts are typically found in:
A) /var/log/auth.log or /var/log/secure  B) C:\Windows\System32\config  C) /Applications/Logs  D) UserAssist

**Q43.** Windows Event Logs are forensically valuable primarily because they record:
A) Only network packet captures  B) System, security and application events with timestamps (logons, errors, service starts)  C) Only browser history  D) Only file hashes

**Q44.** A ".exe" file whose true file signature (magic bytes) begins with "MZ" but has been renamed with a ".jpg" extension is an example of:
A) A legitimate JPEG  B) Extension–signature mismatch (masquerading)  C) A registry artifact  D) An ADS

**Q45.** Which of the following is NOT typically a Windows artifact category examined in Windows system forensics?
A) Registry  B) Event logs  C) launchd plist files  D) Prefetch files

### Block D — Logic, Number Systems, Boolean Algebra, COA basics (Q46–Q55)

**Q46.** The decimal number 25 in binary is:
A) 11001  B) 11010  C) 10101  D) 11101

**Q47.** In 2's complement representation, the negative of a binary number is obtained by:
A) Reversing the bit order  B) Inverting all bits and adding 1  C) Inverting all bits only (1's complement)  D) Adding 1 to the original number

**Q48.** A logic gate that outputs 1 only when all its inputs are 1 is the:
A) OR gate  B) NAND gate  C) AND gate  D) NOR gate

**Q49.** A Karnaugh map (K-map) is used to:
A) Encrypt data  B) Simplify Boolean expressions  C) Design network topologies  D) Manage memory paging

**Q50.** A well-formed formula (WFF) that is true under every possible interpretation is called a:
A) Contradiction  B) Tautology  C) Contingency  D) Satisfiable-only formula

**Q51.** A circuit whose output depends only on the current inputs (no memory of past state) is a:
A) Sequential circuit  B) Combinational circuit  C) Flip-flop  D) Counter

**Q52.** A flip-flop is a basic building block of:
A) Combinational circuits only  B) Sequential circuits  C) ROM only  D) The ALU exclusively

**Q53.** In computer organisation, the memory hierarchy from fastest/smallest to slowest/largest is typically:
A) Main memory → Cache → Registers → Secondary storage  B) Registers → Cache → Main memory → Secondary storage  C) Secondary storage → Main memory → Cache → Registers  D) Cache → Registers → Secondary storage → Main memory

**Q54.** DMA (Direct Memory Access) is used primarily to:
A) Slow down I/O for accuracy  B) Allow I/O devices to transfer data to/from memory without continuous CPU intervention  C) Encrypt memory contents  D) Replace the ALU

**Q55.** The hexadecimal representation of decimal 255 is:
A) FF  B) F0  C) 1FF  D) FE

### Block E — Computer Networks (Q56–Q65)

**Q56.** The OSI model has how many layers?
A) 4  B) 5  C) 7  D) 8

**Q57.** In the TCP/IP model, IP addressing and routing occur at the:
A) Application layer  B) Transport layer  C) Internet (network) layer  D) Physical layer

**Q58.** A MAC address is:
A) A logical, changeable software address  B) A hardware address burned into the network interface card  C) The same as an IP address  D) Assigned by DNS

**Q59.** A device that connects multiple networks and makes forwarding decisions based on IP addresses is a:
A) Hub  B) Switch  C) Router  D) Repeater

**Q60.** DNS primarily provides the function of:
A) Encrypting web traffic  B) Translating domain names to IP addresses  C) Assigning MAC addresses  D) Managing firewall rules

**Q61.** A network topology in which all devices connect to a single central cable is called:
A) Star  B) Bus  C) Ring  D) Mesh

**Q62.** Which transmission medium offers the highest bandwidth and immunity to electromagnetic interference?
A) Twisted pair  B) Coaxial cable  C) Fibre-optic cable  D) Radio wireless

**Q63.** A firewall's primary function is to:
A) Speed up DNS resolution  B) Filter network traffic based on defined security rules  C) Store website cookies  D) Assign IP addresses dynamically

**Q64.** Public-key (asymmetric) cryptography differs from secret-key (symmetric) cryptography in that:
A) It uses the same key for encryption and decryption  B) It uses a mathematically related key pair — one public, one private  C) It cannot be used for encryption, only signing  D) It is always faster than symmetric cryptography

**Q65.** ARP (Address Resolution Protocol) is used to:
A) Resolve domain names to IP addresses  B) Resolve IP addresses to MAC addresses on a local network  C) Encrypt email  D) Route packets across the internet

### Block F — Operating Systems Concepts (Q66–Q72)

**Q66.** Virtual memory allows a system to:
A) Run without any RAM  B) Use disk space to extend the effective size of main memory  C) Encrypt the file system  D) Bypass the CPU scheduler

**Q67.** The OS technique of dividing memory into fixed-size blocks to reduce external fragmentation is:
A) Segmentation  B) Paging  C) Swapping  D) Caching

**Q68.** A situation where two or more processes are each waiting for a resource held by the other, and none can proceed, is called:
A) Starvation  B) Deadlock  C) Thrashing  D) Race condition

**Q69.** Round Robin is a type of:
A) Memory management technique  B) CPU scheduling algorithm  C) File system  D) Network protocol

**Q70.** Which of these is a malicious program that disguises itself as legitimate software and does not self-replicate?
A) Worm  B) Trojan horse  C) Virus  D) Logic bomb (as commonly distinguished)

**Q71.** A worm differs from a virus mainly in that a worm:
A) Requires a host file and user execution  B) Self-replicates and spreads across networks without needing a host file or user action  C) Cannot spread across a network  D) Only affects mobile devices

**Q72.** RAID and disk formatting are primarily discussed under which OS management function?
A) Process management  B) Disk management  C) Memory paging  D) User authentication

### Block G — Cyber Crime & First Responder (Q73–Q85)

**Q73.** Classifying cyber crime by the role of the computer, an attack where the computer itself is the victim (e.g., hacking, DDoS) is called:
A) Computer as tool  B) Computer as target  C) Computer as incidental  D) Computer-associated crime

**Q74.** Cyber-stalking and identity theft are examples of cyber crime classified against:
A) Property  B) The individual/person  C) Government  D) Society at large

**Q75.** Compared to external attacks, internal (insider) attacks are generally considered harder to detect because:
A) Insiders never have legitimate access  B) Insider activity blends in with normal, already-authorised work  C) Insiders always use malware  D) Firewalls block insiders automatically

**Q76.** ARP spoofing operates primarily at which layer/scope?
A) Application layer, across the internet  B) Layer 2, within a local broadcast domain  C) Physical cabling only  D) DNS resolution only

**Q77.** DNS spoofing/cache poisoning that redirects victims to a fake website is also known as:
A) Phishing  B) Pharming  C) Smishing  D) Vishing

**Q78.** SQL Injection succeeds primarily because:
A) The web server uses HTTPS  B) User input is concatenated unsanitised into an executable SQL query  C) The database is encrypted  D) DNS records are misconfigured

**Q79.** Cross-Site Scripting (XSS) differs fundamentally from Cross-Site Request Forgery (CSRF) in that:
A) XSS injects and runs script in the victim's browser; CSRF rides on the victim's already-authenticated session without injecting script  B) CSRF injects script; XSS does not  C) They are the same attack  D) Only CSRF can steal cookies

**Q80.** The single greatest cause of retail banking/UPI fraud in India is generally attributed to:
A) Advanced technical hacking of bank servers  B) Social engineering (phishing/vishing/smishing) tricking victims into sharing OTP/PIN/CVV  C) EMV chip cloning  D) SIM manufacturing defects

**Q81.** The first responder's most important immediate duty at a digital crime scene is to:
A) Immediately run antivirus on the machine  B) Secure the scene and avoid altering the evidence  C) Reboot the system to check for errors  D) Open suspicious files to assess damage

**Q82.** For a machine found powered OFF at the scene, the correct first-responder action is to:
A) Boot it to check what is on it  B) Leave it off and image the disk later using a write blocker  C) Immediately connect it to the internet  D) Remove the RAM before imaging

**Q83.** For a machine found powered ON with an unlocked encrypted volume, the recommended priority is to:
A) Pull the plug immediately  B) Capture volatile memory / the encryption key first, before any power decision  C) Perform a graceful shutdown immediately  D) Ignore RAM entirely and proceed straight to disk imaging

**Q84.** A key risk of a "graceful" (normal) OS shutdown on a compromised machine is that it may:
A) Preserve all volatile evidence  B) Trigger shutdown scripts that delete temp files, clear the pagefile, or run anti-forensic wipers  C) Always corrupt the file system  D) Have no effect on evidence

**Q85.** To prevent a suspect's phone from being remotely wiped after seizure, the first responder should:
A) Turn on Wi-Fi to back it up  B) Place it in a Faraday bag / enable airplane mode and isolate it from the network  C) Fully charge it while connected to the internet  D) Restart it repeatedly

### Block H — Order of Volatility, Imaging & Hashing (Q86–Q93)

**Q86.** In the order of volatility, which of these should be collected FIRST?
A) Archival backups  B) CPU registers and cache  C) Hard disk contents  D) Printed documents

**Q87.** In the order of volatility, RAM contents rank as more volatile than:
A) Network connection state / ARP cache  B) Registers and cache  C) Disk (hard drive) contents  D) Nothing — RAM is the most volatile of all

**Q88.** A hardware write blocker is used during acquisition to:
A) Speed up imaging  B) Prevent any write operation from reaching the original evidence disk  C) Compress the disk image  D) Decrypt the disk

**Q89.** A "physical" or bit-stream disk image, as opposed to a "logical" acquisition, captures:
A) Only active/visible files  B) Every sector including unallocated space and slack — enabling deleted-file recovery  C) Only the registry  D) Only RAM

**Q90.** Hashing an acquired forensic image is done primarily to:
A) Compress the image for storage  B) Prove and later verify the integrity of the image against the original  C) Encrypt the evidence  D) Speed up file carving

**Q91.** Which hash algorithm produces a 256-bit digest and is currently preferred for forensic defensibility over MD5/SHA-1?
A) MD5  B) SHA-1  C) SHA-256  D) CRC32

**Q92.** MD5 and SHA-1 are considered forensically weaker today mainly because:
A) They are too slow to compute  B) Cryptographic collisions have been demonstrated against them  C) They cannot be used on Windows  D) They produce no fixed-length output

**Q93.** Imaging a live (running) system's disk without proper care primarily risks:
A) No risk at all — live imaging is always safe  B) Altering timestamps and other metadata compared to a dead-box (powered-off) image  C) Automatically encrypting the disk  D) Deleting the registry

### Block I — File Carving, Signatures, Recovery (Q94–Q99)

**Q94.** File carving is the technique of recovering files by:
A) Reading file system metadata only  B) Searching unallocated space for known file signatures/structures, without relying on file system metadata  C) Reading the registry  D) Reformatting the disk

**Q95.** The file signature (magic bytes) for a JPEG file typically begins with:
A) 25 50 44 46  B) FF D8 FF  C) 50 4B 03 04  D) 4D 5A

**Q96.** The file signature "MZ" at the start of a file indicates it is (most likely) a:
A) PDF document  B) Windows executable (EXE)  C) ZIP archive  D) PNG image

**Q97.** A file renamed from ".exe" to ".txt" to disguise it will still be detected as an executable by:
A) Checking only the file extension  B) Checking the file's true signature/magic bytes  C) Checking only the file's creation date  D) Checking the antivirus name

**Q98.** On NTFS, when a file is deleted (not securely wiped), typically:
A) The data is instantly and irrecoverably overwritten  B) The file's metadata entry is marked free but the underlying data often remains recoverable until overwritten  C) The disk is automatically reformatted  D) Only the registry is affected

**Q99.** SSD TRIM commands are forensically significant because they:
A) Improve deleted-file recovery chances  B) Can autonomously and irreversibly erase "deleted" data blocks, defeating recovery  C) Only affect RAM, not SSDs  D) Encrypt all deleted data instead of erasing it

### Block J — Browser & Email Forensics (Q100–Q106)

**Q100.** Small text files stored by websites in a browser to remember session/preference data are called:
A) Bookmarks  B) Cookies  C) Cache  D) Plugins

**Q101.** Browser cache primarily stores:
A) A list of favourite/bookmarked sites  B) Locally saved copies of web page resources for faster reloading  C) The user's saved passwords only  D) DNS server addresses only

**Q102.** To trace the true originating server of an email, an investigator reads the "Received:" headers:
A) Top to bottom  B) Bottom to top (oldest/originating hop first)  C) In random order  D) Only the last "Received:" header

**Q103.** SPF, DKIM and DMARC are email-security mechanisms primarily designed to combat:
A) Slow email delivery  B) Email spoofing  C) Large attachment sizes  D) Spam folders only

**Q104.** In a spoofed/phishing email, forensic examiners often find a mismatch between the visible "From:" address and the:
A) Subject line  B) "Return-Path" / "Reply-To" / originating IP in the headers  C) Font used in the body  D) Email client version only

**Q105.** Virtual machine forensics is important because:
A) VMs never contain user data  B) A VM can hold an entire independent evidential file system/OS inside a single host, requiring its own acquisition approach  C) VMs cannot be imaged  D) VMs are identical to physical disks in every respect

**Q106.** Cloud forensics is distinctively challenging mainly due to:
A) Cloud data is always encrypted and therefore irrelevant  B) Data may be distributed across jurisdictions and controlled by a third-party provider rather than the suspect directly  C) Cloud providers never retain any logs  D) Cloud data cannot be legally obtained under any circumstance

### Block K — Digital Evidence, ACPO, Process Model (Q107–Q114)

**Q107.** Digital evidence is generally described as "latent" because:
A) It never changes  B) It is not visible to the naked eye and needs tools/software to be perceived  C) It is always encrypted  D) It cannot be duplicated

**Q108.** ACPO Principle 1 states that:
A) An audit trail must be created  B) No action taken by law enforcement should change data held on a computer that may later be relied upon in court  C) Only senior officers may examine evidence  D) All evidence must be destroyed after the case closes

**Q109.** Under ACPO Principle 2, if an examiner must access original data, they must:
A) Never document their actions  B) Be competent and able to explain the relevance and implications of their actions  C) Get a second opinion before acting  D) Refuse access under all circumstances

**Q110.** ACPO Principle 4 places overall responsibility for compliance with the principles on:
A) The junior-most officer present  B) The person in charge of the investigation  C) The defence lawyer  D) The manufacturer of the forensic tool

**Q111.** The six-phase digital forensic process model is typically ordered as:
A) Analysis → Collection → Identification → Preservation → Examination → Presentation  B) Identification → Preservation → Collection → Examination → Analysis → Presentation  C) Collection → Identification → Analysis → Presentation → Examination → Preservation  D) Presentation → Analysis → Examination → Collection → Preservation → Identification

**Q112.** NIST SP 800-86 condenses the forensic process to how many core phases?
A) Two  B) Three  C) Four (Collection, Examination, Analysis, Reporting)  D) Six

**Q113.** Comparing MBR and GPT partitioning, which statement is correct?
A) MBR supports more partitions than GPT  B) GPT supports more partitions, larger disks, and keeps a redundant backup table; MBR is limited to ~2 TB and 4 primary partitions  C) MBR is used only on macOS  D) GPT cannot be used with UEFI

**Q114.** The legal requirement in Indian evidence law for certifying an electronic record before it is admissible in court is commonly cited as:
A) IT Act §66  B) §65B Indian Evidence Act 1872 / §63 Bharatiya Sakshya Adhiniyam 2023 (⚠️ verify exact current section)  C) IT Act §43A  D) BNSS §176 only

### Block L — Mobile Forensics (Q115–Q122)

**Q115.** The unique identifier assigned to a mobile handset (hardware) is the:
A) IMSI  B) IMEI  C) ICCID  D) MSISDN

**Q116.** The identifier stored on the SIM card that identifies the subscriber to the network is the:
A) IMEI  B) IMSI  C) MAC address  D) Serial ATA ID

**Q117.** A mobile device state where the passcode has not yet been entered since the last full power-on, and full-disk encryption keys are not derived, is called:
A) AFU (After First Unlock)  B) BFU (Before First Unlock)  C) Airplane mode  D) Roaming mode

**Q118.** To prevent remote wipe and network-based tampering, a seized phone should immediately be placed in a:
A) Anti-static bag only  B) Faraday bag  C) Standard evidence envelope  D) Freezer

**Q119.** GSM networks use which multiple access technique, and identify subscribers via which component?
A) CDMA; handset-bound identity  B) TDMA/FDMA; a removable SIM card  C) Only FDMA; no subscriber identity module  D) OFDMA; a fixed IP address

**Q120.** The default on-device database engine used by both Android and iOS to store SMS, call logs, contacts and chat-app data is:
A) MySQL  B) SQLite  C) Oracle  D) MongoDB

**Q121.** A hard handoff (break-before-make) between cells is characteristic of:
A) CDMA  B) GSM  C) 5G NR only  D) Wi-Fi

**Q122.** Call Detail Records (CDR) are primarily useful in mobile forensics for:
A) Recovering deleted photos  B) Reconstructing call history, duration, and approximate location via cell tower data  C) Decrypting the phone's file system  D) Bypassing the phone's passcode

### Block M — Tools (Q123–Q127)

**Q123.** A widely used open-source packet capture and network protocol analysis tool is:
A) FTK Imager  B) Wireshark  C) Volatility  D) Autopsy

**Q124.** A tool commonly used for memory (RAM) forensic analysis to extract running processes and artifacts from a memory dump is:
A) Wireshark  B) Volatility  C) EnCase Imager only  D) NSRL

**Q125.** FTK Imager and dd/dcfldd are primarily used for:
A) Malware reverse engineering  B) Disk/memory imaging and acquisition  C) Network intrusion detection  D) Mobile app development

**Q126.** The NSRL (National Software Reference Library) hash set is primarily used in forensic examination to:
A) Encrypt evidence  B) Filter out (exclude) known, unmodified operating-system and application files by hash, so examiners focus on relevant data  C) Crack passwords  D) Capture network traffic

**Q127.** Autopsy is best described as:
A) A network sniffer  B) A graphical digital forensics platform (front-end) commonly built on The Sleuth Kit for disk image analysis  C) A mobile-only acquisition tool  D) A cryptographic hashing algorithm

---

## 2. Answer Key with Brief Explanations

| Q | Ans | Why |
|:--:|:--:|---|
| 1 | B | Hans Gross coined "criminalistics" and wrote the foundational *Handbuch für Untersuchungsrichter*. Orfila = toxicology; Bertillon = anthropometry/identification; Locard = exchange principle/first crime lab. |
| 2 | B | Locard's Exchange Principle — the classic quotable line. |
| 3 | B | Calcutta, 1897 (Anthropometric Bureau → Finger Print Bureau) — widely cited as the world's first. |
| 4 | C | CFSL Kolkata, 1957 — the oldest CFSL. |
| 5 | C | CFSL New Delhi is under the CBI, not DFSS — the classic exam trap. |
| 6 | D | GEQD principal office = Shimla; branches at Kolkata and Hyderabad. |
| 7 | B | CFSL Guwahati serves the North-East, including Nagaland. |
| 8 | B | NCRB runs NAFIS and CCTNS; BPR&D does research/training — don't swap these two. |
| 9 | B | Shared by a group/batch → class characteristic. |
| 10 | C | Striations are produced by random tool wear unique to one barrel → individual characteristic. |
| 11 | C | A class-characteristic mismatch is conclusive of exclusion, even though a match is not conclusive of identity. |
| 12 | C | Transient evidence — temporary, must be recorded first (odour, temperature, wet stains). |
| 13 | B | Grid search = strip search repeated at 90°; the most thorough pattern. |
| 14 | C | Spiral search suits a single searcher around one focal point. |
| 15 | B | Wheel/ray search: gaps between spokes widen as you move outward — poor at the periphery. |
| 16 | B | Zone/quadrant search maps naturally onto rooms of a building. |
| 17 | B | Chain of custody — the documented, unbroken handling record. |
| 18 | B | Drylabbing = reporting fictitious/never-performed test results. |
| 19 | B | Contextual bias = irrelevant case information colouring the analysis. |
| 20 | C | The expert's primary duty is to the court, overriding obligation to the engaging party. |
| 21 | B | RAM is volatile working memory. |
| 22 | A | BIOS performs POST and starts the legacy boot process (UEFI is the modern equivalent). |
| 23 | B | NTFS — Windows NT-family native file system with permissions and journaling. |
| 24 | C | ext4 is the common modern Linux default. |
| 25 | A | APFS is Apple's current file system, replacing HFS+. |
| 26 | B | POST happens first in the boot sequence, before the OS kernel loads. |
| 27 | B | The processor socket houses the CPU on the motherboard. |
| 28 | B | RAID's core purpose is redundancy and/or performance across multiple disks. |
| 29 | B | The ALU (Arithmetic Logic Unit) performs arithmetic and logic operations. |
| 30 | B | ROM is non-volatile and holds firmware not normally rewritten by the user. |
| 31 | B | Alternate Data Streams (ADS) — NTFS feature hiding extra data streams on a file. |
| 32 | A | UserAssist records GUI program execution, values ROT-13 encoded. |
| 33 | B | USBSTOR records USB device connection history. |
| 34 | B | Registry keys carry a LastWrite time; individual values do not. |
| 35 | B | LNK shortcut files retain evidence of file/program access even after the target is deleted. |
| 36 | A | File/RAM slack — unused space between logical file end and cluster end. |
| 37 | B | Linux permissions are based on ownership (user/group/other) and read/write/execute bits. |
| 38 | B | A leading dot (.) marks a hidden file/directory in Linux/Unix convention. |
| 39 | B | /etc/shadow stores hashed passwords (not /etc/passwd in modern systems). |
| 40 | A | macOS hidden system directories parallel Windows hidden AppData/cache/prefetch-type artifacts in purpose. |
| 41 | B | launchd and .plist files manage macOS startup and services. |
| 42 | A | /var/log/auth.log (Debian-family) or /var/log/secure (RHEL-family) record authentication attempts. |
| 43 | B | Windows Event Logs record system/security/application events with timestamps. |
| 44 | B | Extension–signature mismatch — the true "MZ" (EXE) signature contradicts the ".jpg" extension. |
| 45 | C | launchd/.plist files are a macOS artifact, not a Windows one. |
| 46 | A | 25 = 16+8+1 = 11001. |
| 47 | B | 2's complement = invert all bits (1's complement) then add 1. |
| 48 | C | AND gate outputs 1 only when all inputs are 1. |
| 49 | B | K-maps simplify Boolean expressions graphically. |
| 50 | B | A tautology is true under every interpretation. |
| 51 | B | Combinational circuits have no memory; output depends only on current inputs. |
| 52 | B | Flip-flops are the storage element underlying sequential circuits. |
| 53 | B | Registers → Cache → Main memory → Secondary storage (fastest/smallest to slowest/largest). |
| 54 | B | DMA lets I/O devices transfer to/from memory without continuous CPU involvement. |
| 55 | A | 255 decimal = FF hex. |
| 56 | C | OSI model has 7 layers. |
| 57 | C | IP addressing/routing happen at the Internet (network) layer. |
| 58 | B | MAC address = hardware address burned into the NIC. |
| 59 | C | A router forwards based on IP addresses across networks. |
| 60 | B | DNS translates domain names to IP addresses. |
| 61 | B | Bus topology — single central cable/backbone. |
| 62 | C | Fibre-optic offers highest bandwidth and immunity to EMI. |
| 63 | B | A firewall filters traffic per defined security rules. |
| 64 | B | Asymmetric/public-key crypto uses a mathematically related public/private key pair. |
| 65 | B | ARP resolves IP addresses to MAC addresses on a local network. |
| 66 | B | Virtual memory extends effective RAM using disk space. |
| 67 | B | Paging divides memory into fixed-size blocks, reducing external fragmentation. |
| 68 | B | Deadlock — circular wait where none of the processes can proceed. |
| 69 | B | Round Robin is a CPU scheduling algorithm. |
| 70 | B | Trojan horse — disguised, does not self-replicate. |
| 71 | B | A worm self-replicates and spreads across networks without needing a host file or user execution. |
| 72 | B | RAID/formatting are part of OS disk management. |
| 73 | B | Computer-as-target — the machine itself is the victim (hacking, DDoS). |
| 74 | B | Cyber-stalking/identity theft target the individual/person. |
| 75 | B | Insiders already have legitimate access, so their activity blends with authorised work — harder to detect. |
| 76 | B | ARP spoofing operates at Layer 2, within a broadcast domain. |
| 77 | B | Pharming = DNS-level redirection to a fake site. |
| 78 | B | SQLi succeeds because unsanitised input is concatenated into an executable SQL query. |
| 79 | A | XSS injects/executes script in the victim's browser; CSRF abuses an already-authenticated session without injecting script. |
| 80 | B | Social engineering (phishing/vishing/smishing) is the dominant cause, not technical hacking. |
| 81 | B | Secure the scene and avoid altering evidence — the first responder's top priority. |
| 82 | B | If OFF, leave it off; image later with a write blocker (dead-box). Do not boot it. |
| 83 | B | Unlocked encrypted volume: capture the key/volatile memory first, or you may permanently lose access. |
| 84 | B | Graceful shutdown can trigger scripts that delete temp files/clear the pagefile/run anti-forensic wipers. |
| 85 | B | Faraday bag / airplane mode isolates the phone from the network, preventing remote wipe. |
| 86 | B | Registers and cache are the most volatile — collect first. |
| 87 | C | Order (most→least volatile, relevant excerpt): registers/cache → network/ARP/process tables → RAM → disk. RAM is more volatile than disk. |
| 88 | B | A write blocker prevents any write reaching the original evidence disk. |
| 89 | B | Physical/bit-stream imaging captures every sector, including unallocated space and slack. |
| 90 | B | Hashing proves and later verifies integrity of the image against the original. |
| 91 | C | SHA-256 produces a 256-bit digest and is currently preferred over MD5/SHA-1. |
| 92 | B | MD5/SHA-1 are weakened by demonstrated cryptographic collisions. |
| 93 | B | Live imaging without care alters timestamps/metadata compared to a dead-box image. |
| 94 | B | File carving searches unallocated space for known signatures/structures, independent of file system metadata. |
| 95 | B | JPEG signature begins FF D8 FF. |
| 96 | B | "MZ" (4D 5A) signature = Windows executable. |
| 97 | B | Signature/magic-byte analysis, not the extension, reveals the true file type. |
| 98 | B | Deleting a file (without secure wipe) frees the metadata entry but the data often remains recoverable until overwritten. |
| 99 | B | SSD TRIM can autonomously and irreversibly erase "deleted" blocks, defeating recovery. |
| 100 | B | Cookies — small text files storing session/preference data. |
| 101 | B | Browser cache stores locally saved copies of page resources for faster reloading. |
| 102 | B | Read "Received:" headers bottom to top to trace back to the originating hop. |
| 103 | B | SPF/DKIM/DMARC are anti-email-spoofing mechanisms. |
| 104 | B | Mismatch between visible "From:" and Return-Path/Reply-To/originating IP reveals spoofing. |
| 105 | B | A VM can be an entire independent evidential OS/file system inside one host file, needing its own acquisition approach. |
| 106 | B | Cloud data may span jurisdictions and sit under third-party provider control, not the suspect's direct custody. |
| 107 | B | "Latent" = not visible to the naked eye; needs tools to perceive. |
| 108 | B | ACPO Principle 1 — no action should change data that may be relied upon in court. |
| 109 | B | ACPO Principle 2 — competent access with documented relevance/implications, when unavoidable. |
| 110 | B | ACPO Principle 4 — overall responsibility rests with the person in charge of the investigation. |
| 111 | B | Identification → Preservation → Collection → Examination → Analysis → Presentation. |
| 112 | C | NIST SP 800-86 condenses to four phases: Collection, Examination, Analysis, Reporting. |
| 113 | B | GPT: more partitions, larger disks, redundant backup table; MBR: ~2 TB limit, max 4 primary partitions. |
| 114 | B | §65B Indian Evidence Act 1872 / §63 Bharatiya Sakshya Adhiniyam 2023 — the electronic-record certificate requirement (⚠️ verify exact current section before quoting in the exam). |
| 115 | B | IMEI identifies the handset (hardware). |
| 116 | B | IMSI identifies the subscriber, stored on the SIM. |
| 117 | B | BFU (Before First Unlock) — passcode not yet entered since power-on; encryption keys not yet derived. |
| 118 | B | Faraday bag blocks radio signals, preventing remote wipe/network tampering. |
| 119 | B | GSM uses TDMA/FDMA and identifies subscribers via a removable SIM card. |
| 120 | B | SQLite is the default on-device database engine on both Android and iOS. |
| 121 | B | Hard handoff (break-before-make) is characteristic of GSM; CDMA uses soft handoff. |
| 122 | B | CDRs reconstruct call history/duration and approximate location via cell tower data. |
| 123 | B | Wireshark — packet capture and protocol analysis. |
| 124 | B | Volatility — memory (RAM) forensic analysis framework. |
| 125 | B | FTK Imager and dd/dcfldd are disk/memory imaging and acquisition tools. |
| 126 | B | NSRL hash sets exclude known-good OS/application files by hash, letting examiners focus on relevant data. |
| 127 | B | Autopsy is a graphical forensics platform commonly built atop The Sleuth Kit. |

---

## 3. Descriptive Question Bank

Structured to match the real descriptive paper shape observed for CTSE (`OFFICIAL_SYLLABUS.md`
§1): **Section A — any 8 of 10 × 5 marks; Section B — any 3 of 5 × 10 marks; Section C — any 2 of
4 × 15 marks**, per paper (Paper-I and Paper-II are each set out this way — you get *choice*, so
learn breadth over depth: skip your two weakest topics per section on the real paper). Each
question below carries a **model-answer skeleton** — the bullet points an examiner is checking
for, not full prose. Write the prose yourself in practice; do not memorise sentences verbatim.

### 3.1 Five-mark questions (22 — Section A style)

**D1. State and explain Locard's Exchange Principle with two examples.**
- Definition: mutual exchange of material whenever two objects contact.
- One physical example (burglar/window: fibres left, glass taken).
- One digital analogue (opening a file leaves MFT/prefetch/LNK/registry traces).
- Note: absence of detectable trace ≠ absence of contact (detection depends on time/medium/skill).

**D2. Distinguish class characteristics from individual characteristics with examples.**
- Definitions (group-associable vs single-source-associable).
- Table/list: 3 examples of each (shoe brand vs wear pattern; blood group vs DNA STR; calibre vs striations).
- Key line: class mismatch = exclusion; class match ≠ identity.

**D3. What is forensic science? Discuss its scope in India.**
- Definition (application of science to legal questions).
- 5–6 domains with one example question each (physics, chemistry, toxicology, biology/serology, ballistics, QD, fingerprints, digital).
- One line on growth drivers (cybercrime rise, BNSS mandate) and one constraint (backlog).

**D4. Write a note on the Directorate of Forensic Science Services (DFSS).**
- Parent: MHA; created 2002; HQ New Delhi.
- Controls CFSLs and GEQD.
- Functions: standards/SOPs, referral lab, training, R&D, advice to MHA.

**D5. What is a Mobile Forensic Science Unit (MFSU)? State its functions.**
- Definition: vehicle-based lab reaching the crime scene.
- Kit: crime-scene/photography equipment, presumptive tests, collection/packaging materials.
- Purpose: immediate scene examination, prevent contamination/loss, link to BNSS mandatory-forensics requirement.

**D6. What is confirmation bias? How can a laboratory minimise it?**
- Definition: seeing what one expects to see.
- One example (told of a confession, then "finds" a match).
- Countermeasures: Linear Sequential Unmasking, context management, blind verification, accreditation.

**D7. Distinguish between the Central and State Forensic Science Laboratories.**
- Table: control (MHA/DFSS vs State Home Dept/Police), scope (central agencies + referral vs State casework), examples (CFSL Kolkata/Guwahati vs State FSL).

**D8. Distinguish MBR and GPT.**
- Table: firmware era (BIOS/UEFI), location (LBA0 vs LBA1+backup), max partitions (4 vs 128), max size (~2TB vs huge), redundancy (none vs backup+CRC32).

**D9. State the ACPO principles of digital evidence.**
- List all four, one line each (no change; competent+documented access; audit trail/reproducibility; overall responsibility with person in charge).

**D10. List the characteristics of digital evidence.**
- Latent, fragile/volatile, easily duplicated, alterable/time-sensitive, jurisdiction-spanning, voluminous, format-dependent.
- One line on admissibility requirements (authentic, reliable, complete, legally obtained + §65B/§63 certificate).

**D11. Distinguish physical, logical and sparse acquisition.**
- Physical: every sector, enables deleted-file recovery.
- Logical: active files only, no deleted data.
- Sparse: selected data + some deleted fragments, middle ground for very large systems.

**D12. What are the contents of a forensic report?**
- List 6–8 items: case details, authorisation/scope, chain of custody/exhibits with hashes, tools/methods with versions, acquisition + hash verification, findings, analysis/opinion (labelled), declaration/§65B-§63 certificate.

**D13. Distinguish between phishing, vishing and smishing.**
- Same social-engineering goal; channel differs — email (phishing), voice call (vishing), SMS (smishing).
- One example and one artifact/detection point for each.

**D14. Distinguish internal and external attacks.**
- Table: access (already have it vs must gain it), detection difficulty (hard vs easier), typical evidence, typical defence (least privilege/DLP vs firewall/IDS/patching).

**D15. Distinguish a virus, a worm and a trojan horse.**
- Virus: needs host + user execution.
- Worm: self-replicating, no host/user action needed, spreads via network.
- Trojan: disguised as legitimate, does not self-replicate.

**D16. What is packet sniffing? How is it carried out on a switched network?**
- Definition: promiscuous/monitor mode capturing all traffic.
- On a switch (traffic normally isolated per port): ARP spoofing, MAC flooding, or port mirroring/SPAN to defeat isolation.
- Legitimate use (troubleshooting/IDS) vs malicious use (credential/PII theft from unencrypted traffic).

**D17. What is a mobile database and what challenges does mobility create?**
- Definition: DB running on/synced with mobile devices under intermittent connectivity/limited power.
- Challenges: replication/sync, conflict resolution, caching/hoarding, disconnected operation, on-device security.
- Note SQLite as the standard on-device engine — forensic payoff.

**D18. Distinguish hard and soft handoff.**
- Hard (break-before-make) = GSM; soft (make-before-break) = CDMA. One line each on mechanism and network association.

**D19. What is frequency reuse? Why are cells drawn as hexagons?**
- Definition: reusing the same channel set in non-adjacent cells to multiply capacity.
- Hexagon: tessellates without gaps/overlap, models roughly circular coverage efficiently.

**D20. Distinguish IMEI and IMSI.**
- IMEI: unique to the handset (hardware); IMSI: unique to the subscriber, stored on the SIM.
- Forensic use of each (device identification vs subscriber/account identification).

**D21. What is the order of volatility? Why does it matter in digital forensics?**
- List (most→least): registers/cache → network/process state → RAM → disk → remote logs/backups.
- Link to Law of Progressive Change (evidence has a "shelf life"); collect most-volatile data first.

**D22. What is drylabbing? State two other common ethical failures in forensic science.**
- Definition: reporting results of tests never performed.
- Two more: overstating conclusions ("absolute match"); selective/omitted reporting of exculpatory results.

### 3.2 Ten-mark questions (13 — Section B style)

**D23. Explain the basic principles of forensic science with suitable examples and their relevance to digital evidence.**
- List all six (Locard, Individuality, Comparison, Analysis, Progressive Change, Circumstantial Facts).
- One physical example + one digital analogue per principle (see FOR_01 §1.5 table).
- Close with the memory hook and one line tying principles to court admissibility.

**D24. Describe the organisation and functioning of forensic science laboratories in India with a diagram.**
- Draw the hierarchy: MHA → DFSS/BPR&D/NCRB/NFSU; DFSS → CFSLs + GEQD; State side: State Home Dept → SFSL → RFSL/MFSU.
- One function each for DFSS, CFSL, GEQD, SFSL, RFSL, MFSU.
- Nagaland-relevant note: served by CFSL Guwahati (⚠️ verify current State FSL status).

**D25. Explain the different types of spoofing with examples and their defences.**
- Table: IP, MAC, ARP, DNS, email, caller-ID/SMS, website/URL spoofing — what is forged, abuse, defence for each.
- Close with the ARP-vs-DNS-vs-IP layer distinction (a common trap).

**D26. Describe the common ATM and UPI frauds and how each is investigated.**
- List mechanisms: skimming, cloning, trapping, shimming, phishing/vishing/smishing, SIM swap, UPI collect/QR/screen-mirroring scams, money mules.
- For each, name the investigative artifact (CCTV, CDR, UTR/RRN, KYC, device ID).
- Close with the "OTP/PIN never shared" + 1930/cybercrime.gov.in golden-hour point.

**D27. Explain SQL injection, XSS and CSRF, and how each appears in web-server evidence.**
- One paragraph each: mechanism + forensic footprint (payload patterns in logs; injected script tags; foreign Referer/Origin on authenticated request).
- Close with the XSS-vs-CSRF distinction (script injection vs session riding).

**D28. Discuss data acquisition methods (physical/logical/sparse, live/static) and when each is used.**
- Two axes: completeness (physical/logical/sparse/targeted) and system state (live/static).
- One line each on trade-offs and typical use-case.
- Close with "modern standard: RAM live-first, then dead-box disk."

**D29. Explain the phases of the digital forensic process model with a diagram.**
- Draw: Identification → Preservation → Collection → Examination → Analysis → Presentation, with chain of custody running through all.
- One goal + one failure mode per phase.
- Mention NIST's 4-phase condensation and one other named model (Kruse & Heiser / DFRWS).

**D30. Discuss forensic report writing and the duties of an expert witness in an Indian court.**
- Report qualities (accurate, objective, complete, clear, reproducible, defensible, within competence).
- Report contents (see D12 list).
- Expert duties: primary duty to the court, testify within field, disclose limitations, §45 IEA/§39 BSA advisory status (⚠️ verify), old CrPC §293/BNSS provision for certain government experts (⚠️ verify).

**D31. Trace the evolution of cellular networks from 1G to 5G.**
- Table by generation: era, switching (circuit→packet→all-IP), key technology, data capability.
- One line each on GPRS/EDGE as 2.5G/2.75G overlays and VoLTE for 4G/5G voice.

**D32. Explain mobile database synchronisation and its forensic significance.**
- Concept: local storage + replication/sync with server; conflict resolution; caching/hoarding.
- Forensic payoff: SQLite files hold SMS/calls/contacts/chat-app data — name where examiners look.

**D33. Discuss ethics in forensic science. What are the common ethical failures and their consequences?**
- Code-of-conduct bullets (objectivity, competence, validated methods, documentation, integrity, confidentiality, no overstatement).
- Failures list (drylabbing, overstatement, falsification, selective reporting, testifying beyond expertise) with consequence (wrongful conviction/exoneration, case dismissal, professional sanction).

**D34. Enumerate the divisions of a full-service Forensic Science Laboratory and state the functions of each.**
- Table: Biology, Serology, DNA, Chemistry, Toxicology, Narcotics, Physics, Ballistics, Documents, Fingerprint, Cyber/Computer Forensics, Photography, Lie Detection, Prohibition/Excise (mention any 8–10 with one function each).

**D35. Discuss malware taxonomy and explain why rootkits and fileless malware change the forensic acquisition strategy.**
- Table: virus/worm/trojan/ransomware/rootkit/bootkit/keylogger/spyware/botnet/logic bomb/backdoor/fileless/cryptominer/APT — one defining property each.
- Reasoning: rootkits subvert the OS itself → live OS view untrustworthy → dead-box imaging + memory forensics required; fileless malware lives in RAM → RAM capture becomes essential, not optional.

### 3.3 Fifteen-mark questions (9 — Section C style)

**D36. "Physical evidence does not lie." Discuss the principles, significance and limitations of forensic science in the Indian criminal justice system.**
- Six principles (brief, one line each) as the foundation.
- Significance: 6–8 points (objective proof, linkage triangle, exculpatory value, reconstruction, identification, deterrence, corroboration, handles no-witness crimes).
- Limitations: backlog, contamination risk, interpretive/expert bias, cost/infrastructure, CSI effect.
- Close with a balanced conclusion — evidence is only as reliable as its collection and interpretation.

**D37. Discuss the structure of forensic science services in India from the Ministry of Home Affairs down to the district level, and evaluate the adequacy of this structure for handling cybercrime.**
- Full hierarchy diagram (as in D24) plus RFSL/MFSU district layer.
- Adequacy evaluation: strengths (referral system, NFSU training pipeline, mobile units, BNSS mandate) vs weaknesses (backlog, uneven State capacity, shortage of trained cyber examiners, jurisdictional/attribution difficulty in cybercrime).
- Conclusion: structure suits traditional physical evidence better than borderless, fast-moving digital evidence; recommend capacity-building (state cyber labs, NFSU-trained manpower, faster inter-State cooperation).

**D38. "Forensic evidence is only as trustworthy as the analyst." Discuss with reference to bias, ethical failures and quality-assurance measures.**
- Bias table (confirmation, contextual, expectation, motivational/role, anchoring, reverse-reasoning, observer effect) with one example each.
- Ethical failures list (see D33).
- QA measures: Linear Sequential Unmasking, blind verification, documented SOPs, proficiency testing, accreditation (ISO/IEC 17025/17020 — ⚠️ verify numbers).
- Conclusion tying bias-control to admissibility and wrongful-conviction prevention.

**D39. "Attribution is the central problem of cyber-crime investigation." Discuss with reference to spoofing, anonymisation and the classification of cyber crimes.**
- Explain why attribution is hard: volatility/remoteness, anonymity (spoofing/VPN/Tor), scale.
- Both classifications of cyber crime (role-based and victim-based) with examples.
- Spoofing family table (IP/MAC/ARP/DNS/email/caller-ID/URL) as the technical mechanism defeating attribution.
- Conclusion: legal process (ISP/platform records), technical correlation (logs, timestamps, hashes) and international cooperation (MLAT) as partial answers to the attribution problem.

**D40. Describe the complete lifecycle of digital evidence from identification to presentation, referencing ACPO principles, hashing, chain of custody and the §65B/§63 certificate.**
- Six-phase process model diagram.
- Weave in at each phase: ACPO principle invoked, hashing/chain-of-custody action taken, and (at presentation) the §65B IEA/§63 BSA certificate requirement (⚠️ verify exact current section).
- Close with the reproducibility argument (an independent third party should reach the same result).

**D41. Discuss the architecture of a cellular mobile network (cells, base stations, MSC/HLR/VLR, handoff) and explain how mobility and switching evolved from 1G to 5G.**
- Diagram: hexagonal cells, base stations, frequency reuse, MSC/HLR/VLR roles.
- Handoff types (hard/soft) and which generation/technology uses which.
- Generation table (1G→5G) emphasising the circuit→packet→all-IP switching evolution.

**D42. Discuss the various forms of cyber crime targeting individuals, property, government and society, with the applicable legal provisions (verify sections before quoting in the exam).**
- Four-bucket table (person/property/government-terrorism/society) with 2–3 examples each.
- Cite the IT Act sections named in FOR_03 for each bucket, flagged ⚠️ verify.
- Close with one line on the BNS/BNSS/BSA 2023 overlay replacing IPC/CrPC/Evidence Act.

**D43. Explain the digital forensic investigation of a suspected malware/ransomware incident from first response to reporting, integrating order of volatility, imaging, hashing and recovery techniques.**
- First-responder actions (secure scene, assess power state, isolate network).
- Order-of-volatility-driven capture: RAM first (fileless/rootkit risk) → live triage → power-down decision (pull-plug vs live-first reasoning) → dead-box disk imaging with write blocker + hashing.
- Recovery: undelete → carving → journal/shadow-copy recovery; note SSD TRIM caveat.
- Report and testimony stage tying back to ACPO and the §65B/§63 certificate.

**D44. Compare and evaluate physical, logical and sparse data acquisition together with live and static acquisition strategies, and justify the acquisition strategy you would choose for (a) a powered-off desktop, (b) a running server suspected of an active intrusion, and (c) a locked, powered-on smartphone.**
- Definitions/trade-offs table (as in D28).
- (a) Dead-box, physical, write-blocked image — full recovery capability, no volatile risk since machine is already off.
- (b) Live-first: capture RAM/network state/logs before any shutdown decision (server — avoid destructive downtime/data loss); then controlled shutdown or continued live monitoring per ACPO Principle 2, fully documented.
- (c) Mobile-specific: isolate (Faraday/airplane mode), assess AFU/BFU state, use an appropriate mobile acquisition level, document because a hardware write blocker cannot be attached to soldered eMMC/UFS.
- Conclusion: no single "right" method — decision follows from device state, encryption status, and risk of destructive change, always under ACPO Principle 2's competence/documentation requirement.

---

## 4. Quick recap — where each syllabus unit is covered in this bank

| Syllabus unit | MCQ blocks | Descriptive Qs |
|---|---|---|
| TP-I §1 Intro to Forensic Science | A | D1, D3, D23, D36 |
| TP-I §2 Physical Evidence | A | D2, D22 |
| TP-I §3 Scene of Crime | A | (search patterns/chain of custody folded into Block A + D2/D17-style skeletons) |
| TP-I §4 Computer Hardware | B | (hardware facts recur inside D24/D43 skeletons) |
| TP-I §5 Windows/Linux/macOS Artifacts | C | D8 (MBR/GPT is TP-II §8 but tool-adjacent) |
| TP-I §6 Logic/Number Systems | D | — (pure MCQ topic; descriptive coverage lives in the CORE/shared-core notes) |
| TP-I §7 Computer Networks | E | D25 (spoofing), D16 (sniffing) |
| TP-I §8 Operating Systems | F | D35 (malware) |
| TP-I §9 COA | D | — |
| TP-II §1 Cyber Crime + First Responder | G | D14, D15, D16, D26, D27, D39, D42, D43 |
| TP-II §2 Web Browsers / Email / VM-Cloud | J | (folded into D30/D40 report-writing skeletons) |
| TP-II §7 Mobile Computing / Mobile Forensics | L | D5 (MFSU relates), D17–D20, D31, D32, D41 |
| TP-II §8 Digital Evidences | H, I, K | D9–D13, D21, D28, D29, D30, D40, D44 |

**Reminder:** no official CTSE Computer Forensic past paper exists as of this writing — every
question above is a constructed practice item mapped to the official syllabus, not a leaked or
recalled paper. Use it to build pattern-recognition (paired traps, table-shaped answers,
skeleton-first writing), not to memorise a "final" answer key.
