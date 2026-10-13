# Computer Forensic MCQ Bank — 200 Questions with Answers

**NPSC CTSE 2026 · Computer Forensic · MCQ (OMR) paper: 100 Qs × 2 marks, 2 hours · Tue 13 Oct 2026, 13:00 IST · covers TP-I and TP-II mixed**

- **Marking:** +2 correct, 0 blank. A wrong answer costs **−⅓** (the 2025 booklet's wording) or −⅔ (the stricter reading). Check the instructions page. Under either rule, **guess whenever you can rule out one option**.
- **Time:** about 70 seconds per question. Do one fast pass on what you know, then a second pass with eliminations.
- **Weighting:** forensic-only topics get about 60% of this bank, since this elective's examiner is a forensic specialist. CS-core topics get the rest.
- **How to use:** the answer is in the green box under each question. Cover it, answer, then reveal. Every hex value, conversion and numerical was checked by computing it.

| § | Topic | Qs | § | Topic | Qs |
|---|---|---|---|---|---|
| F1 | Forensic science, principles, history, FSLs | 1–20 | F8 | OS, UNIX, Windows | 111–125 |
| F2 | Physical evidence, chain of custody | 21–32 | F9 | COA | 126–133 |
| F3 | Scene of crime | 33–50 | F10 | Cyber crime, seizure, imaging | 134–153 |
| F4 | Hardware, booting, file systems | 51–65 | F11 | Browsers, e-mail, VM/cloud | 154–163 |
| F5 | Windows/Linux/Mac artifacts | 66–85 | F12 | SE, C/C++, web, DBMS/SQL, DS | 164–178 |
| F6 | Logic & number systems | 86–95 | F13 | Mobile computing | 179–185 |
| F7 | Networks, DNS, e-mail, crypto | 96–110 | F14 | Digital evidence, hashing, law | 186–200 |



## F1. Forensic science: intro, principles, history, FSLs, ethics

**1.** "Every contact leaves a trace" is the statement of which principle?  
(a) Law of Individuality (b) Locard's Exchange Principle (c) Principle of Comparison (d) Law of Progressive Change

> **Ans: (b) Locard's Exchange Principle** — Edmond Locard: when two objects come into contact, material is transferred both ways.

**2.** Who is regarded as the "Father of Criminalistics"?  
(a) Edmond Locard (b) Alphonse Bertillon (c) Hans Gross (d) Mathieu Orfila

> **Ans: (c) Hans Gross** — Austrian jurist, author of *Criminal Investigation*; Orfila = toxicology, Bertillon = anthropometry, Locard = exchange principle.

**3.** Mathieu Orfila is known as the father of which branch?  
(a) Forensic toxicology (b) Fingerprinting (c) Ballistics (d) Questioned documents

> **Ans: (a) Forensic toxicology** — His 1814 treatise on poisons founded scientific toxicology.

**4.** The world's first fingerprint bureau was established at:  
(a) Scotland Yard, 1901 (b) Shimla, 1904 (c) Lyon, 1910 (d) Calcutta, 1897

> **Ans: (d) Calcutta, 1897** — Under Edward Henry, with Azizul Haque and Hem Chandra Bose.

**5.** India's first Central Forensic Science Laboratory (CFSL) was set up in 1957 at:  
(a) Kolkata (Calcutta) (b) New Delhi (c) Hyderabad (d) Chandigarh

> **Ans: (a) Kolkata (Calcutta)** — CFSL Kolkata (1957) is the oldest CFSL.

**6.** CFSL New Delhi functions under the administrative control of:  
(a) DFSS, MHA (b) NCRB (c) CBI (d) BPR&D

> **Ans: (c) CBI** — Standard trick: the other CFSLs are under DFSS/MHA, but CFSL New Delhi is under the CBI.

**7.** The principal office of the Government Examiner of Questioned Documents (GEQD) is at:  
(a) Kolkata (b) Shimla (c) Hyderabad (d) New Delhi

> **Ans: (b) Shimla** — GEQD units are at Shimla (principal), Kolkata and Hyderabad.

**8.** Since 2002, the CFSLs (other than CFSL Delhi) and GEQDs are controlled by:  
(a) BPR&D (b) NCRB (c) NFSU (d) Directorate of Forensic Science Services (DFSS), MHA

> **Ans: (d) DFSS, MHA** — Directorate of Forensic Science was carved out of BPR&D in 2002, later renamed DFSS.

**9.** The National Forensic Sciences University (NFSU), an Institution of National Importance (2020), is headquartered at:  
(a) Gandhinagar (b) New Delhi (c) Hyderabad (d) Kolkata

> **Ans: (a) Gandhinagar** — GFSU (Gandhinagar) was converted into NFSU by an Act of Parliament in 2020.

**10.** The Indian officers who did the substantive work on the Henry fingerprint classification system were:  
(a) J.C. Bose and C.V. Raman (b) P.C. Mahalanobis and S.N. Bose (c) Azizul Haque and Hem Chandra Bose (d) Lalji Singh and V.K. Kashyap

> **Ans: (c) Azizul Haque and Hem Chandra Bose** — Worked under Edward Henry at the Calcutta bureau.

**11.** "Everything changes with the passage of time" is the:  
(a) Law of Individuality (b) Law of Progressive Change (c) Principle of Analysis (d) Locard's Principle

> **Ans: (b) Law of Progressive Change** — Evidence, scenes and suspects change over time, so speed of examination matters.

**12.** "Only like can be compared with like" is the:  
(a) Principle of Analysis (b) Law of Individuality (c) Law of Probability (d) Principle of Comparison

> **Ans: (d) Principle of Comparison** — Questioned samples must be compared with known samples of the same kind.

**13.** "Every object, natural or man-made, has a unique identity" is the:  
(a) Law of Individuality (b) Principle of Comparison (c) Law of Progressive Change (d) Principle of Exchange

> **Ans: (a) Law of Individuality** — Basis of individualisation (fingerprints, tool marks).

**14.** "Facts do not lie, men can and do" expresses the:  
(a) Law of Probability (b) Principle of Analysis (c) Principle of Circumstantial Facts (d) Law of Individuality

> **Ans: (c) Principle of Circumstantial Facts** — Physical evidence is more reliable than eyewitness testimony.

**15.** DNA fingerprinting was discovered in 1984 by:  
(a) Karl Landsteiner (b) Alec Jeffreys (c) Kary Mullis (d) Leone Lattes

> **Ans: (b) Alec Jeffreys** — UK, 1984; first used in the Colin Pitchfork case. Landsteiner = ABO groups; Mullis = PCR.

**16.** The comparison microscope used in firearms identification is associated with:  
(a) Albert Osborn (b) Francis Galton (c) Edward Henry (d) Calvin Goddard

> **Ans: (d) Calvin Goddard** — 1920s; Osborn = questioned documents.

**17.** Alphonse Bertillon is best known for:  
(a) Anthropometry (Bertillonage) (b) Blood grouping (c) DNA profiling (d) Toxicology

> **Ans: (a) Anthropometry** — Body-measurement identification system, later replaced by fingerprints.

**18.** In forensic ethics, "drylabbing" means:  
(a) Testing samples in a low-humidity lab (b) Refusing to testify in court (c) Reporting results of tests that were never actually performed (d) Sharing case data with the media

> **Ans: (c) Reporting results of tests never performed** — A grave form of scientific misconduct.

**19.** The primary duty of a forensic expert witness is owed to:  
(a) The party that engaged the expert (b) The court (c) The investigating officer (d) The victim

> **Ans: (b) The court** — The expert must be impartial and assist the court, not either side.

**20.** Edmond Locard established the first police crime laboratory in 1910 at:  
(a) Paris (b) London (c) Vienna (d) Lyon

> **Ans: (d) Lyon** — Locard's lab in Lyon, France, is regarded as the first police crime lab.

## F2. Physical evidence & chain of custody

**21.** A property shared by a whole group or batch of items (e.g. shoe brand and size) is a:  
(a) Individual characteristic (b) Class characteristic (c) Transient evidence (d) Associative evidence

> **Ans: (b) Class characteristic** — It narrows the source to a group, not a single item.

**22.** Which is an example of an individual characteristic?  
(a) Calibre of a firearm (b) ABO blood group (c) Striations on a bullet fired from a specific barrel (d) Shoe size

> **Ans: (c) Striations from a specific barrel** — Unique, random marks allow individualisation; the others are class traits.

**23.** Evidence that is lost quickly if not recorded immediately (odour, temperature, a wet footprint) is:  
(a) Pattern evidence (b) Associative evidence (c) Trace evidence (d) Transient evidence

> **Ans: (d) Transient evidence** — Temporary by nature; must be documented first.

**24.** The documented chronological record of everyone who handled an exhibit, when and why, from seizure to court, is the:  
(a) Chain of custody (b) Order of volatility (c) Case diary (d) Forwarding note

> **Ans: (a) Chain of custody** — Proves the exhibit's integrity and continuity.

**25.** If the class characteristics of crime-scene evidence and a suspect's item do NOT match, the result is:  
(a) Individualisation (b) Inconclusive (c) Exclusion of that source (d) Automatic identification

> **Ans: (c) Exclusion** — A class mismatch rules out the suspect item as the source.

**26.** Which of the following is trace evidence?  
(a) A firearm (b) A few fibres and hairs (c) A motor vehicle (d) A dead body

> **Ans: (b) Fibres and hairs** — Trace evidence is small/microscopic material transferred on contact.

**27.** A break in the chain of custody primarily affects the evidence's:  
(a) Weight in kilograms (b) Chemical composition (c) File size (d) Integrity and admissibility in court

> **Ans: (d) Integrity and admissibility** — Unaccounted custody lets the defence argue tampering or substitution.

**28.** A chain-of-custody form must record, at minimum:  
(a) Each person handling the item, date/time, and purpose of transfer (b) Only the IO's name (c) Only the lab's name (d) Only the market value of the item

> **Ans: (a) Each handler, date/time, purpose** — Every transfer must be signed and accounted for.

**29.** Bloodstain spatter, tyre marks and glass fracture patterns are examples of:  
(a) Transient evidence (b) Trace evidence (c) Pattern evidence (d) Biological evidence only

> **Ans: (c) Pattern evidence** — Their shape/arrangement reveals how events happened.

**30.** Evidence that links a suspect to a victim or to the scene is called:  
(a) Corpus delicti (b) Associative evidence (c) Conditional evidence (d) Hearsay

> **Ans: (b) Associative evidence** — e.g. victim's fibres on the suspect (Locard transfer).

**31.** A fingerprint ridge pattern with its minutiae is a:  
(a) Class characteristic (b) Transient evidence (c) Conditional evidence (d) Individual characteristic

> **Ans: (d) Individual characteristic** — Ridge minutiae are unique to one finger.

**32.** An ABO blood group result is a:  
(a) Class characteristic (b) Individual characteristic (c) Transient evidence (d) Digital evidence

> **Ans: (a) Class characteristic** — Millions of people share each blood group; DNA is needed to individualise.

## F3. Scene of crime: protection, documentation, search, packaging

**33.** A search in which the area is covered twice, the second pass at 90° to the first, is the:  
(a) Strip search (b) Spiral search (c) Grid search (d) Wheel search

> **Ans: (c) Grid search** — A double-strip search; most thorough but takes twice the time and manpower.

**34.** For a single searcher covering a small open area around one focal point, the most suitable pattern is:  
(a) Spiral search (b) Grid search (c) Zone search (d) Strip search with many searchers

> **Ans: (a) Spiral search** — Inward or outward spiral from/to a focal point needs only one person.

**35.** The zone (quadrant/sector) search method is best suited to:  
(a) Large open fields (b) Underwater scenes (c) Circular blast craters (d) Indoor scenes such as a house with rooms

> **Ans: (d) Indoor scenes** — The area is divided into zones/rooms, each assigned to a searcher.

**36.** The main weakness of the wheel (ray) search method is that:  
(a) It needs a helicopter (b) Gaps between the spokes widen towards the periphery (c) It cannot be used outdoors (d) It always needs 50 searchers

> **Ans: (b) Gaps widen towards the periphery** — Searchers move along radii, so outer areas are covered poorly.

**37.** The strip (line/lane) search is most suitable for:  
(a) A car interior (b) A single room (c) Large open outdoor areas with many searchers (d) A computer hard disk

> **Ans: (c) Large open outdoor areas** — Searchers walk parallel lanes shoulder to shoulder.

**38.** The highest priority of the first officer arriving at a crime scene is:  
(a) Ensuring safety and giving aid to any injured person (b) Collecting fingerprints (c) Interviewing the media (d) Packaging evidence

> **Ans: (a) Safety and aid to the injured** — Preservation of life comes first, then securing and protecting the scene.

**39.** The correct sequence of crime-scene photography is:  
(a) Close-up → mid-range → overall (b) Overall → mid-range → close-up (c) Mid-range → overall → close-up (d) Close-up only

> **Ans: (b) Overall → mid-range → close-up** — Establishes context first, then the relationship of objects, then detail.

**40.** Close-up photographs of evidence are taken:  
(a) Only in colour, never with a scale (b) Only after the item is packed (c) Only by the defence (d) Both without and with a scale/ruler

> **Ans: (d) Without and with a scale** — First without (shows nothing was altered), then with a scale for size.

**41.** A rough crime-scene sketch is:  
(a) Drawn to exact scale in the lab (b) A photograph (c) Drawn at the scene, not to scale, but with accurate measurements noted (d) Made by the court

> **Ans: (c) Drawn at the scene, not to scale, with measurements** — The finished (final) sketch is drawn to scale later.

**42.** Locating an object by measuring its distance from two fixed reference points is the:  
(a) Triangulation method (b) Baseline method (c) Polar method (d) Cross-projection method

> **Ans: (a) Triangulation** — Two measurements from two fixed points fix the object's position.

**43.** Locating objects by perpendicular measurements from a single straight reference line is the:  
(a) Triangulation method (b) Baseline method (c) Polar coordinate method (d) Exploded view

> **Ans: (b) Baseline method** — Distance along the baseline plus perpendicular offset.

**44.** Dried biological evidence (e.g. bloodstained cloth) should be packed in:  
(a) Airtight plastic bags (b) Sealed glass bottles with water (c) Metal tins (d) Paper bags/envelopes after air-drying

> **Ans: (d) Paper packaging after air-drying** — Plastic traps moisture and causes bacterial/fungal degradation.

**45.** Fire debris suspected to contain petrol/kerosene residues should be packed in:  
(a) Paper envelopes (b) Cloth bags (c) Airtight clean metal cans or glass jars (d) Cardboard boxes

> **Ans: (c) Airtight metal cans/glass jars** — Volatile accelerants evaporate from porous packaging.

**46.** Hard disks and other electronic storage media should be packed in:  
(a) Anti-static bags (b) Ordinary plastic bags near a magnet (c) Wet cloth (d) Aluminium-foil-free paper soaked in water

> **Ans: (a) Anti-static bags** — Prevent electrostatic discharge damage; keep away from magnets, heat and moisture.

**47.** When sealing an evidence packet, the collecting officer should:  
(a) Leave it unsealed for the lab (b) Seal it and sign/initial across the seal (c) Staple it open (d) Seal it without any label

> **Ans: (b) Sign/initial across the seal** — Any later opening becomes visible (tamper evidence).

**48.** The 3-D scanning technique of crime-scene documentation produces:  
(a) A hand-drawn sketch (b) A polygraph chart (c) A DNA profile (d) A measurable point-cloud model of the scene (laser scanning)

> **Ans: (d) A point-cloud 3-D model** — Allows accurate measurement and virtual walk-throughs later.

**49.** A place where a body was dumped after the murder was committed elsewhere is a:  
(a) Primary crime scene (b) Macroscopic scene only (c) Secondary crime scene (d) Mock scene

> **Ans: (c) Secondary crime scene** — The primary scene is where the original offence occurred.

**50.** The crime-scene entry log (security log) records:  
(a) Every person entering and leaving the cordoned scene, with times (b) Only the weather (c) Only exhibits seized (d) Only the accused's statements

> **Ans: (a) Every entry/exit with times** — Controls contamination and supports chain of custody.

## F4. Computer hardware, booting, file systems

**51.** Which of these is performed first when a computer is switched on?  
(a) Loading the OS kernel (b) POST by the BIOS/UEFI firmware (c) User login (d) Starting services

> **Ans: (b) POST** — Power-On Self-Test checks hardware before the boot loader is located.

**52.** The Master Boot Record (MBR) is located in:  
(a) The last sector, 1 KB (b) The MFT (c) The first sector (LBA 0), 512 bytes (d) The BIOS chip

> **Ans: (c) First sector, 512 bytes** — 446 bytes boot code + 64-byte partition table + 2-byte signature.

**53.** An MBR partition table can hold at most how many primary partitions?  
(a) 4 (b) 8 (c) 16 (d) 128

> **Ans: (a) 4** — Four 16-byte entries in a 64-byte table (an extended partition works around this).

**54.** The partitioning scheme used with UEFI that supports 128 partitions by default is:  
(a) MBR (b) FAT (c) CHS (d) GPT

> **Ans: (d) GPT** — GUID Partition Table; also supports disks far beyond 2 TiB.

**55.** The boot signature at the end of a valid MBR is:  
(a) FF D8 (b) 55 AA (c) 4D 5A (d) 50 4B

> **Ans: (b) 55 AA** — Bytes 510–511 of sector 0 (0xAA55 read as a little-endian word).

**56.** With 512-byte sectors, the maximum disk size addressable by MBR is about:  
(a) 32 GB (b) 128 GB (c) 2 TiB (d) 16 EiB

> **Ans: (c) 2 TiB** — 32-bit LBA: 2^32 × 512 B = 2^41 B = 2 TiB.

**57.** In NTFS, every file and directory has an entry in the:  
(a) Master File Table ($MFT) (b) File Allocation Table (c) Inode table (d) Superblock only

> **Ans: (a) $MFT** — FAT uses the File Allocation Table; ext uses inodes.

**58.** The maximum size of a single file on FAT32 is:  
(a) 2 GB (b) 16 TB (c) 256 TB (d) 4 GB minus 1 byte

> **Ans: (d) 4 GB − 1 byte** — File size field is 32 bits.

**59.** The default file system on most modern Linux distributions is:  
(a) NTFS (b) ext4 (c) APFS (d) HFS+

> **Ans: (b) ext4** — NTFS = Windows; APFS (successor of HFS+) = Apple.

**60.** Apple's current file system for macOS/iOS is:  
(a) ReFS (b) exFAT (c) APFS (d) ext3

> **Ans: (c) APFS** — Apple File System replaced HFS+ (2017).

**61.** Which memory loses its contents when power is switched off?  
(a) RAM (b) ROM (c) Hard disk (d) SSD

> **Ans: (a) RAM** — Volatile; hence RAM must be captured before shutdown in forensics.

**62.** The smallest unit of disk space a file system allocates to a file is the:  
(a) Bit (b) Byte (c) Track (d) Cluster (block)

> **Ans: (d) Cluster** — A group of sectors; unused tail of the last cluster becomes slack space.

**63.** The correct boot order is:  
(a) Kernel → POST → boot loader → init (b) POST → boot loader (MBR/GPT) → kernel → init/services → login (c) Login → kernel → POST (d) Boot loader → POST → login

> **Ans: (b) POST → boot loader → kernel → init → login** — Firmware → loader → OS.

**64.** The common boot loader used by Linux systems is:  
(a) NTLDR (b) launchd (c) GRUB (d) BIOS

> **Ans: (c) GRUB** — GRand Unified Bootloader; NTLDR = old Windows; launchd = macOS init.

**65.** A networking device that forwards frames using MAC addresses (Layer 2) is a:  
(a) Switch (b) Hub (c) Router (d) Repeater

> **Ans: (a) Switch** — Hub/repeater = Layer 1; router = Layer 3 (IP).

## F5. Windows, Linux and macOS artifacts

**66.** The NTFS feature that lets hidden data be attached to a file without appearing in a normal directory listing is:  
(a) Slack space (b) Alternate Data Streams (ADS) (c) Prefetch (d) Shadow copy

> **Ans: (b) ADS** — e.g. `file.txt:secret.exe`; detect with `dir /r` or forensic tools.

**67.** The registry key recording GUI program execution, with value names ROT-13 encoded, is:  
(a) UserAssist (b) ShellBags (c) MountedDevices (d) RunMRU

> **Ans: (a) UserAssist** — Stored in the user's NTUSER.DAT; gives run counts and last-run times.

**68.** The USBSTOR key, which records USB storage devices ever connected, is in which hive?  
(a) SAM (b) NTUSER.DAT (c) SYSTEM (d) SECURITY

> **Ans: (c) SYSTEM** — HKLM\SYSTEM\CurrentControlSet\Enum\USBSTOR.

**69.** Local user accounts and their password hashes are stored in which hive?  
(a) SOFTWARE (b) SYSTEM (c) NTUSER.DAT (d) SAM

> **Ans: (d) SAM** — Security Account Manager.

**70.** The system registry hive files (SAM, SYSTEM, SOFTWARE, SECURITY) are located in:  
(a) C:\Windows\System32\config (b) C:\Users\Public (c) C:\Program Files (d) C:\Windows\Prefetch

> **Ans: (a) C:\Windows\System32\config** — Per-user NTUSER.DAT is in C:\Users\<user>.

**71.** NTUSER.DAT is:  
(a) The system boot file (b) The per-user registry hive (HKEY_CURRENT_USER) (c) The page file (d) An event log

> **Ans: (b) Per-user hive** — Holds UserAssist, RecentDocs, typed paths, MRU lists.

**72.** Windows Security Event ID 4624 indicates:  
(a) Failed logon (b) Log cleared (c) Successful logon (d) Service installed

> **Ans: (c) Successful logon** — Check the Logon Type (2 = interactive, 10 = RemoteInteractive/RDP).

**73.** Windows Security Event ID 4625 indicates:  
(a) Successful logon (b) Logoff (c) User account created (d) Failed logon attempt

> **Ans: (d) Failed logon** — Repeated 4625s suggest password guessing/brute force.

**74.** Security Event ID 1102 is an anti-forensic red flag because it means:  
(a) The audit log was cleared (b) A USB was inserted (c) The system was rebooted (d) A file was printed

> **Ans: (a) Audit log cleared** — Someone erased the Security log.

**75.** Windows Prefetch files (.pf in C:\Windows\Prefetch) are evidence of:  
(a) Deleted e-mails (b) Program execution (name, run count, last run times) (c) Network shares only (d) Printer jobs

> **Ans: (b) Program execution** — Created when an application is run, even if it is later deleted.

**76.** Windows shortcut (.lnk) files are valuable because they:  
(a) Are always malware (b) Contain the system password (c) Preserve the target's path, timestamps and volume details even if the target is deleted (d) Only exist on servers

> **Ans: (c) Preserve target path/times/volume info** — Proves a file (or USB volume) was accessed.

**77.** The unused space between the logical end of a file and the end of its last allocated cluster is:  
(a) Unallocated space (b) Alternate Data Stream (c) Swap space (d) File slack

> **Ans: (d) File slack** — May hold remnants of previously deleted data.

**78.** In the Windows registry, the LastWrite timestamp is maintained for:  
(a) Registry keys (b) Individual values (c) Only the SAM hive (d) Only data of type REG_SZ

> **Ans: (a) Registry keys** — Values do not carry their own timestamps.

**79.** On Linux, hashed user passwords are stored in:  
(a) /etc/passwd in plain text (b) /etc/shadow (c) /var/log/syslog (d) /etc/hosts

> **Ans: (b) /etc/shadow** — Readable only by root; /etc/passwd shows `x` in the password field.

**80.** A hidden file in Linux/macOS is indicated by:  
(a) A ".hid" extension (b) The sticky bit (c) A file name beginning with a dot (.) (d) A registry flag

> **Ans: (c) Leading dot** — e.g. `.bash_history`; shown with `ls -a`.

**81.** `chmod 754 file` gives the permission string:  
(a) rwxrwxr-- (b) rw-r-xr-- (c) rwxr--r-x (d) rwxr-xr--

> **Ans: (d) rwxr-xr--** — 7 = rwx (owner), 5 = r-x (group), 4 = r-- (others). (Verified with python `stat.filemode`.)

**82.** On Debian/Ubuntu Linux, authentication events (logins, sudo) are logged in:  
(a) /var/log/auth.log (b) /etc/shadow (c) /boot/grub (d) /tmp/auth

> **Ans: (a) /var/log/auth.log** — On Red Hat/CentOS the equivalent is /var/log/secure.

**83.** Which of the following is NOT stored in a Linux ext inode?  
(a) File size (b) File name (c) Owner UID and permissions (d) Timestamps and block pointers

> **Ans: (b) File name** — Names are kept in directory entries that map name → inode number.

**84.** macOS system startup and background services are managed by:  
(a) The Windows registry (b) systemd unit files (c) launchd with property list (.plist) files (d) GRUB

> **Ans: (c) launchd and .plist files** — LaunchDaemons/LaunchAgents folders hold plist configuration.

**85.** In the Windows Recycle Bin ($Recycle.Bin, Vista onwards), the $I file of a deleted item contains:  
(a) The full file content (b) The registry hive (c) The prefetch data (d) Metadata — original path/name, size and deletion time

> **Ans: (d) Metadata** — The paired $R file holds the actual content.

## F6. Logic, number systems, digital circuits

**86.** Hexadecimal 2F equals decimal:  
(a) 45 (b) 46 (c) 47 (d) 32

> **Ans: (c) 47** — 2×16 + 15 = 47.

**87.** The 8-bit 2's complement representation of −5 is:  
(a) 10000101 (b) 11111011 (c) 11111010 (d) 00000101

> **Ans: (b) 11111011** — 5 = 00000101 → invert 11111010 → +1 = 11111011. (11111010 is the 1's complement.)

**88.** Which of the following is a tautology?  
(a) p ∧ ¬p (b) p → ¬p (c) p ∧ q (d) p ∨ ¬p

> **Ans: (d) p ∨ ¬p** — True for every truth value of p; p ∧ ¬p is a contradiction.

**89.** Which gate is a universal gate?  
(a) NAND (b) XOR (c) AND (d) OR

> **Ans: (a) NAND** — NAND (and NOR) alone can implement any Boolean function.

**90.** The range of an 8-bit signed 2's complement number is:  
(a) −127 to +127 (b) −255 to +255 (c) −128 to +127 (d) 0 to 255

> **Ans: (c) −128 to +127** — −2^7 to 2^7 − 1.

**91.** Octal 157 equals decimal:  
(a) 157 (b) 111 (c) 109 (d) 103

> **Ans: (b) 111** — 1×64 + 5×8 + 7 = 111.

**92.** A multiplexer with 8 data inputs needs how many select lines?  
(a) 8 (b) 2 (c) 4 (d) 3

> **Ans: (d) 3** — 2^3 = 8.

**93.** A decoder with 4 input lines has how many output lines?  
(a) 16 (b) 8 (c) 4 (d) 32

> **Ans: (a) 16** — n inputs → 2^n outputs; 2^4 = 16.

**94.** In a JK flip-flop, when J = K = 1 and a clock edge occurs, the output:  
(a) Resets to 0 (b) Sets to 1 (c) Toggles (d) Holds its value

> **Ans: (c) Toggles** — J=K=0 hold, J=1 K=0 set, J=0 K=1 reset, J=K=1 toggle.

**95.** IEEE 754 single-precision format has sign / exponent / mantissa bits of:  
(a) 1 / 11 / 52 (b) 1 / 8 / 23 (c) 1 / 7 / 24 (d) 2 / 8 / 22

> **Ans: (b) 1 / 8 / 23** — 32 bits, exponent bias 127; 1/11/52 is double precision.

## F7. Networks, DNS, e-mail architecture, cryptography

**96.** In the OSI model, routing of packets between networks is the job of the:  
(a) Data link layer (b) Transport layer (c) Session layer (d) Network layer

> **Ans: (d) Network layer** — Layer 3 (IP addressing, routers).

**97.** A MAC address is how many bits long?  
(a) 48 (b) 32 (c) 64 (d) 128

> **Ans: (a) 48** — 6 bytes, e.g. 00:1A:2B:3C:4D:5E; first 3 bytes = OUI (vendor).

**98.** An IPv4 address is how many bits long?  
(a) 16 (b) 48 (c) 32 (d) 128

> **Ans: (c) 32** — IPv6 is 128 bits.

**99.** DNS normally uses which transport and port for queries?  
(a) TCP 25 (b) UDP 53 (c) UDP 69 (d) TCP 80

> **Ans: (b) UDP 53** — TCP 53 is used for zone transfers and large responses.

**100.** The DNS resource record mapping a host name to an IPv4 address is the:  
(a) MX record (b) PTR record (c) CNAME record (d) A record

> **Ans: (d) A record** — AAAA = IPv6, MX = mail server, PTR = reverse lookup.

**101.** The DNS record that identifies the mail server for a domain is the:  
(a) MX record (b) A record (c) NS record (d) SOA record

> **Ans: (a) MX** — Mail eXchanger; used by SMTP to route mail.

**102.** A reverse DNS lookup (IP address → host name) uses the:  
(a) A record (b) MX record (c) PTR record (d) TXT record

> **Ans: (c) PTR** — Under the in-addr.arpa domain; useful when tracing an e-mail's IP.

**103.** SMTP (sending/relaying e-mail) uses default port:  
(a) 110 (b) 25 (c) 143 (d) 21

> **Ans: (b) 25** — 110 = POP3, 143 = IMAP, 21 = FTP.

**104.** The default port for IMAP is:  
(a) 25 (b) 110 (c) 53 (d) 143

> **Ans: (d) 143** — IMAP keeps mail on the server; POP3 (110) usually downloads and deletes.

**105.** To send a confidential message using public-key cryptography, the sender encrypts with:  
(a) The receiver's public key (b) The sender's private key (c) The receiver's private key (d) A shared hash

> **Ans: (a) Receiver's public key** — Only the receiver's private key can decrypt.

**106.** A digital signature is created using the:  
(a) Receiver's public key (b) Receiver's private key (c) Sender's private key (d) Sender's public key

> **Ans: (c) Sender's private key** — Verified with the sender's public key; gives authenticity and non-repudiation.

**107.** Which is a symmetric (secret-key) algorithm?  
(a) RSA (b) AES (c) Diffie–Hellman (d) ECC

> **Ans: (b) AES** — Same key for encryption and decryption; RSA/ECC are public-key.

**108.** By Nyquist, a noiseless channel of bandwidth 3000 Hz using 4 signal levels has maximum bit rate:  
(a) 6000 bps (b) 3000 bps (c) 24000 bps (d) 12000 bps

> **Ans: (d) 12000 bps** — 2B log2 L = 2 × 3000 × log2 4 = 2 × 3000 × 2 = 12000.

**109.** A device that connects networks using different protocols by translating between them is a:  
(a) Gateway (b) Hub (c) Repeater (d) Bridge

> **Ans: (a) Gateway** — Works up to the application layer; bridge/switch = L2, router = L3.

**110.** A /24 (255.255.255.0) network provides how many usable host addresses?  
(a) 256 (b) 255 (c) 254 (d) 252

> **Ans: (c) 254** — 2^8 − 2 (network and broadcast addresses excluded).

## F8. Operating systems, UNIX commands, Windows OS

**111.** Belady's anomaly (more frames → more page faults) can occur with which page-replacement algorithm?  
(a) LRU (b) FIFO (c) Optimal (d) LFU-stack algorithms

> **Ans: (b) FIFO** — LRU and Optimal are stack algorithms and never show it.

**112.** Which is NOT one of the four necessary conditions for deadlock?  
(a) Mutual exclusion (b) Hold and wait (c) Preemption (d) Circular wait

> **Ans: (c) Preemption** — The condition is *no* preemption.

**113.** The Banker's algorithm is used for deadlock:  
(a) Avoidance (b) Prevention (c) Detection only (d) Recovery

> **Ans: (a) Avoidance** — Grants a request only if the system remains in a safe state.

**114.** Thrashing in a virtual-memory system means:  
(a) Disk head crash (b) Too many processes in the ready queue (c) CPU overheating (d) The system spends more time paging than executing

> **Ans: (d) Excessive paging** — Occurs when processes lack enough frames for their working sets.

**115.** RAID 1 provides:  
(a) Striping without redundancy (b) Mirroring (c) Striping with distributed parity (d) Byte-level parity disk

> **Ans: (b) Mirroring** — RAID 0 = striping; RAID 5 = distributed parity.

**116.** RAID 5 uses:  
(a) Mirroring only (b) Striping only, no fault tolerance (c) Block-level striping with distributed parity (d) A single dedicated parity disk at bit level

> **Ans: (c) Striping with distributed parity** — Survives one disk failure; needs at least 3 disks.

**117.** Which CPU scheduling algorithm gives the minimum average waiting time for a given set of jobs?  
(a) Shortest Job First (SJF) (b) FCFS (c) Round Robin (d) Priority with aging

> **Ans: (a) SJF** — Provably optimal for average waiting time (needs burst lengths in advance).

**118.** The UNIX command used to search files for lines matching a pattern is:  
(a) find (b) cat (c) ls (d) grep

> **Ans: (d) grep** — `find` searches for files by name/attributes, not content.

**119.** The UNIX command that lists all files including hidden (dot) files is:  
(a) ls -l (b) ls -a (c) ls -h (d) ls -r

> **Ans: (b) ls -a** — `-l` = long format; `-h` = human-readable sizes.

**120.** The UNIX command that displays running processes is:  
(a) df (b) du (c) ps (d) wc

> **Ans: (c) ps** — df = disk free, du = disk usage, wc = word count.

**121.** In UNIX, the `|` operator in `ls | wc -l`:  
(a) Sends the output of one command as input to the next (pipe) (b) Runs both in background (c) Redirects output to a file (d) Comments out the second command

> **Ans: (a) Pipe** — `>` redirects to a file; `&` runs in background.

**122.** Malicious code that self-replicates across a network WITHOUT attaching to a host program is a:  
(a) Trojan horse (b) Virus (c) Logic bomb (d) Worm

> **Ans: (d) Worm** — A virus needs a host file; a Trojan pretends to be useful software.

**123.** In Windows NT-family architecture, the layer that hides hardware differences from the kernel is the:  
(a) Win32 subsystem (b) Hardware Abstraction Layer (HAL) (c) Registry (d) Explorer shell

> **Ans: (b) HAL** — Enables portability across hardware platforms.

**124.** Windows "Fast User Switching" allows:  
(a) Faster booting (b) Faster network switching (c) Several users to stay logged on and switch without logging off (d) Automatic password reset

> **Ans: (c) Multiple logged-on sessions** — Built on Terminal Services session technology.

**125.** Paging eliminates external fragmentation but can cause:  
(a) Internal fragmentation (b) Deadlock (c) Belady's anomaly always (d) Starvation

> **Ans: (a) Internal fragmentation** — The last page of a process may be partly empty.

## F9. Computer organization & architecture

**126.** Cache access time is 10 ns, hit ratio 0.9, and a miss costs 100 ns in total. Average memory access time is:  
(a) 110 ns (b) 20 ns (c) 10 ns (d) 19 ns

> **Ans: (d) 19 ns** — 0.9×10 + 0.1×100 = 9 + 10 = 19 ns (miss cost given as total time).

**127.** In immediate addressing mode, the operand is:  
(a) Part of the instruction itself (b) In a register (c) At the address given in the instruction (d) At the address held in a register

> **Ans: (a) In the instruction** — e.g. `MOV R1, #5`.

**128.** DMA (Direct Memory Access) is used to:  
(a) Increase the clock rate (b) Encrypt memory (c) Transfer data between I/O and memory without the CPU handling each word (d) Replace the cache

> **Ans: (c) Transfer without CPU per-word involvement** — CPU only sets up and is interrupted at the end.

**129.** The Program Counter (PC) holds:  
(a) The current instruction's opcode (b) The address of the next instruction to be fetched (c) The result of the ALU (d) The stack top value

> **Ans: (b) Address of the next instruction** — IR holds the current instruction.

**130.** In memory-mapped I/O:  
(a) I/O uses separate IN/OUT instructions (b) I/O devices have no addresses (c) DMA is mandatory (d) I/O registers share the memory address space and use normal memory instructions

> **Ans: (d) Shared address space** — Isolated (standard) I/O uses a separate address space and IN/OUT.

**131.** On a subroutine call, the return address is normally saved on the:  
(a) Stack (b) Queue (c) Cache (d) Hard disk

> **Ans: (a) Stack** — LIFO order supports nested calls.

**132.** Memory interleaving is used to:  
(a) Reduce memory size (b) Encrypt memory contents (c) Increase memory bandwidth by accessing several modules in parallel (d) Convert RAM into ROM

> **Ans: (c) Increase bandwidth** — Consecutive addresses lie in different modules.

**133.** A ROM that can be erased electrically and reprogrammed byte-wise is:  
(a) PROM (b) EEPROM (c) Mask ROM (d) EPROM

> **Ans: (b) EEPROM** — EPROM is erased by UV light; PROM is one-time programmable.

## F10. Cyber crime, attacks, first responder, search & seizure, imaging, recovery

**134.** Fraudulent e-mails that imitate a bank to steal credentials are called:  
(a) Phishing (b) Spamming (c) Salami attack (d) Sniffing

> **Ans: (a) Phishing** — Vishing = by voice call; smishing = by SMS.

**135.** Capturing and analysing packets travelling on a network (e.g. with Wireshark) is:  
(a) Spoofing (b) Phishing (c) Packet sniffing (d) Defacement

> **Ans: (c) Packet sniffing** — Passive capture; unencrypted passwords can be read.

**136.** Forging the source IP address of packets to hide identity or impersonate a host is:  
(a) Sniffing (b) IP spoofing (c) Port scanning (d) Phishing

> **Ans: (b) IP spoofing** — Common in DoS reflection attacks.

**137.** An attacker who sends fake ARP replies linking his MAC address to the gateway's IP is performing:  
(a) DNS tunnelling (b) SQL injection (c) Brute force (d) ARP spoofing / poisoning (man-in-the-middle)

> **Ans: (d) ARP spoofing** — Traffic for the gateway is redirected through the attacker.

**138.** A data theft by a disgruntled employee using legitimate access is an example of:  
(a) An internal (insider) attack (b) An external attack (c) A DDoS attack (d) Cyber squatting

> **Ans: (a) Internal attack** — Insider with authorised access; external attacks come from outside the organisation.

**139.** Copying card magnetic-stripe data with a device fitted on an ATM slot is:  
(a) Phishing (b) Vishing (c) Skimming (d) Pharming

> **Ans: (c) Skimming** — Often combined with a hidden camera to capture the PIN.

**140.** "Vishing" refers to:  
(a) Virus-based hacking (b) Fraud through voice/phone calls (c) Video piracy (d) Visual steganography

> **Ans: (b) Voice phishing** — e.g. fake "bank KYC" calls asking for OTP.

**141.** A Distributed Denial of Service (DDoS) attack typically uses:  
(a) A single dial-up machine (b) Social engineering only (c) Steganography (d) A botnet of many compromised machines

> **Ans: (d) A botnet** — Many sources flood the target simultaneously.

**142.** If a computer is found switched OFF at the scene, the first responder should:  
(a) Leave it off and not switch it on (b) Switch it on to check contents (c) Format the disk (d) Log in with the suspect's password

> **Ans: (a) Leave it off** — Powering on changes timestamps and data; image it later via write blocker.

**143.** Which item belongs in a digital-evidence first responder toolkit?  
(a) A strong magnet (b) Write blocker, Faraday bags, camera, anti-static bags (c) A compiler and a game CD (d) A soldering iron for the suspect's disk

> **Ans: (b) Write blocker, Faraday bags, camera, anti-static bags** — Magnets can damage media.

**144.** A seized mobile phone is placed in a Faraday bag mainly to:  
(a) Charge it (b) Make it waterproof (c) Speed up acquisition (d) Block network signals and prevent remote wiping or new data

> **Ans: (d) Block signals / prevent remote wipe** — Also preserves the state of the device.

**145.** Which is volatile digital evidence?  
(a) Data on a DVD (b) Data on a backup tape (c) Contents of RAM (running processes, network connections) (d) Data on a hard disk

> **Ans: (c) RAM contents** — Lost on power-off; must be captured during live acquisition.

**146.** A forensic (bit-stream) image differs from an ordinary file copy because it:  
(a) Copies every sector, including unallocated space and slack (b) Copies only visible files (c) Compresses only documents (d) Deletes the original

> **Ans: (a) Copies every sector** — Deleted and hidden data are preserved; a logical copy misses them.

**147.** Hashing the original and the image after acquisition is done to:  
(a) Encrypt the evidence (b) Prove the image is identical to the original (integrity) (c) Compress the image (d) Recover deleted files

> **Ans: (b) Prove integrity** — Matching hash values show no change occurred.

**148.** When a file is deleted on FAT, the file system:  
(a) Overwrites the data with zeros (b) Moves it to the MFT (c) Encrypts it (d) Replaces the first character of its directory entry with 0xE5 and frees its clusters

> **Ans: (d) 0xE5 in the first name byte** — Data stays until overwritten, so it is recoverable.

**149.** Recovering files from raw data using header/footer signatures, without file-system metadata, is called:  
(a) Defragmentation (b) Hashing (c) File carving (d) Formatting

> **Ans: (c) File carving** — e.g. carve JPEGs from FF D8 FF … FF D9.

**150.** When a file is deleted on NTFS (bypassing the Recycle Bin), typically:  
(a) Its MFT record is marked unused but the data remains until overwritten (b) The disk is wiped (c) The file name changes to 0xE5 (d) The MBR is erased

> **Ans: (a) MFT record marked unused** — 0xE5 renaming is a FAT behaviour.

**151.** A suspect renames `photo.exe` to `photo.jpg`. This is best detected by:  
(a) Sorting by file name (b) File signature (magic number) analysis (c) Checking file size only (d) Defragmenting

> **Ans: (b) Signature analysis** — Header `4D 5A` ("MZ") reveals an executable despite the .jpg extension.

**152.** In Linux/UNIX file timestamps, "ctime" means:  
(a) Creation time (b) Copy time (c) Close time (d) Inode (metadata) change time

> **Ans: (d) Inode change time** — mtime = content modified, atime = accessed; classic exam trap.

**153.** Stealing very small amounts from a large number of accounts so that each loss goes unnoticed is a:  
(a) Logic bomb (b) Trojan (c) Salami attack (d) Phishing attack

> **Ans: (c) Salami attack** — "Thin slices" of money.

## F11. Browsers, e-mail headers & tracing, VM and cloud forensics

**154.** Browser cookies are:  
(a) Executable plug-ins (b) Small text data stored by a website on the client to maintain state/session (c) Cached images only (d) Server log files

> **Ans: (b) Small client-side text data** — Reveal sites visited, logins and session IDs.

**155.** Google Chrome stores browsing history in a file named "History", which is a:  
(a) Plain XML file (b) Registry hive (c) SQLite database (d) .pst file

> **Ans: (c) SQLite database** — Tables such as `urls` and `visits`.

**156.** When tracing an e-mail, the "Received:" header lines should be read:  
(a) From bottom to top (the lowest is closest to the sender) (b) From top to bottom (c) Only the first one (d) They are irrelevant

> **Ans: (a) Bottom to top** — Each server prepends its line, so the earliest hop is at the bottom.

**157.** A strong indication of a spoofed e-mail is:  
(a) A long subject line (b) An attachment (c) A Message-ID present (d) A mismatch between From and Return-Path/originating server, with SPF failing

> **Ans: (d) From/Return-Path mismatch, SPF fail** — The sender's domain did not authorise that server.

**158.** The e-mail authentication method that adds a cryptographic signature to the message header is:  
(a) SPF (b) DKIM (c) POP3 (d) MIME

> **Ans: (b) DKIM** — DomainKeys Identified Mail; SPF checks authorised sending IPs.

**159.** Private/incognito browsing mainly prevents:  
(a) The ISP from seeing traffic (b) The website from logging the IP (c) Local storage of history and cookies after the session closes (d) All forensic recovery from RAM

> **Ans: (c) Local history/cookie storage** — Traces may still exist in RAM, DNS cache, ISP and server logs.

**160.** The e-mail header field giving a globally unique identifier for a message is:  
(a) Message-ID (b) Subject (c) X-Mailer (d) Reply-To

> **Ans: (a) Message-ID** — Useful for matching with server logs.

**161.** The virtual disk file format of VMware is:  
(a) .vdi (b) .vhdx (c) .qcow2 (d) .vmdk

> **Ans: (d) .vmdk** — .vdi = VirtualBox, .vhd/.vhdx = Hyper-V, .qcow2 = QEMU/KVM.

**162.** In a suspended VMware virtual machine, the guest's RAM contents are stored in the:  
(a) .vmx file (b) .vmem file (c) .log file (d) .nvram file

> **Ans: (b) .vmem** — .vmx is the configuration file; .vmem can be analysed like a memory dump.

**163.** A major challenge specific to cloud forensics is:  
(a) Data too small to analyse (b) No need for hashing (c) Multi-tenancy, lack of physical access and cross-border jurisdiction (d) Absence of logs by design

> **Ans: (c) Multi-tenancy, no physical access, jurisdiction** — Investigators depend on the cloud provider.

## F12. Software engineering, C/C++/OOP, web, DBMS & SQL, data structures

**164.** The Waterfall model is most suitable when:  
(a) Requirements are well understood and stable (b) Requirements change daily (c) Risk is the main concern (d) No documentation is needed

> **Ans: (a) Stable, clear requirements** — Phases are sequential; going back is costly.

**165.** The Spiral model (Boehm) is mainly:  
(a) Code-and-fix (b) Purely sequential (c) Risk-driven and iterative (d) Testing-only

> **Ans: (c) Risk-driven, iterative** — Each loop includes risk analysis.

**166.** The Cleanroom approach to software development relies on:  
(a) Debugging by trial and error (b) Formal specification/verification and statistical usage testing (c) No testing at all (d) Only unit testing by developers

> **Ans: (b) Formal methods + statistical testing** — Aims at defect prevention rather than removal.

**167.** Analysing existing code to recover its design and specification is called:  
(a) Forward engineering (b) Refactoring (c) Prototyping (d) Reverse engineering

> **Ans: (d) Reverse engineering** — Also used in malware analysis.

**168.** A control-flow graph has 9 edges and 7 nodes (one connected component). Its cyclomatic complexity is:  
(a) 4 (b) 2 (c) 3 (d) 16

> **Ans: (a) 4** — V(G) = E − N + 2 = 9 − 7 + 2 = 4.

**169.** Entering `' OR '1'='1` in a login form's password box is an example of:  
(a) Cross-site scripting (b) Buffer overflow (c) SQL injection (d) Session fixation

> **Ans: (c) SQL injection** — Makes the WHERE clause always true and bypasses authentication.

**170.** The most effective defence against SQL injection is:  
(a) Longer passwords (b) Parameterised queries / prepared statements (c) Hiding the login page (d) Using HTTP instead of HTTPS

> **Ans: (b) Prepared statements** — User input is bound as data, never executed as SQL.

**171.** Which SQL command is a DDL (Data Definition Language) command?  
(a) SELECT (b) INSERT (c) UPDATE (d) CREATE

> **Ans: (d) CREATE** — DDL: CREATE/ALTER/DROP; DML: SELECT/INSERT/UPDATE/DELETE.

**172.** The ACID property guaranteeing that committed changes survive a system crash is:  
(a) Durability (b) Atomicity (c) Consistency (d) Isolation

> **Ans: (a) Durability** — Ensured by logs and recovery techniques.

**173.** Second Normal Form (2NF) removes:  
(a) Multivalued attributes (b) Transitive dependencies (c) Partial dependencies on part of a composite key (d) All redundancy

> **Ans: (c) Partial dependencies** — 1NF = atomic values; 3NF removes transitive dependencies.

**174.** Function calls and recursion are implemented using a:  
(a) Queue (b) Stack (c) Graph (d) Hash table

> **Ans: (b) Stack** — LIFO order; queue is FIFO.

**175.** In a B+ tree:  
(a) Data pointers are in internal nodes only (b) Leaves are unlinked (c) It is always unbalanced (d) All data records are at the leaves, which are linked for sequential access

> **Ans: (d) Records at linked leaves** — Supports both indexed and sequential (range) access.

**176.** In C, the size of a union is:  
(a) At least the size of its largest member (b) The sum of all members (c) Always 4 bytes (d) The size of its first member only

> **Ans: (a) Size of the largest member (plus any padding)** — All members share the same memory.

**177.** Function overloading in C++ is an example of:  
(a) Run-time polymorphism (b) Inheritance (c) Compile-time (static) polymorphism (d) Encapsulation only

> **Ans: (c) Compile-time polymorphism** — Virtual functions give run-time polymorphism.

**178.** A Java Servlet runs on:  
(a) The client browser (b) The web server (servlet container) (c) The DNS server (d) The user's GPU

> **Ans: (b) Web server** — Applets ran in the client browser.

## F13. Mobile computing & mobile databases

**179.** The 15-digit number that uniquely identifies a mobile handset is the:  
(a) IMSI (b) ICCID (c) MSISDN (d) IMEI

> **Ans: (d) IMEI** — Displayed by dialling *#06#; IMSI identifies the subscriber.

**180.** The IMSI (subscriber identity) is stored on the:  
(a) SIM card (b) Handset ROM (c) Base station only (d) Memory card

> **Ans: (a) SIM** — Links the subscriber to the network operator.

**181.** Cellular networks reuse the same frequencies in non-adjacent cells. This concept is:  
(a) Handoff (b) Roaming (c) Frequency reuse (d) Multiplexing

> **Ans: (c) Frequency reuse** — Increases capacity; cells are usually modelled as hexagons.

**182.** Transferring an ongoing call from one cell's base station to another as the user moves is:  
(a) Roaming (b) Handoff (handover) (c) Paging (d) Hoarding

> **Ans: (b) Handoff** — Roaming = using another operator's network.

**183.** GPRS added which capability to GSM?  
(a) Analog voice (b) Circuit-switched SMS only (c) Satellite links (d) Packet-switched data

> **Ans: (d) Packet-switched data** — Basis of 2.5G mobile internet.

**184.** In mobile databases, pre-loading data onto the device before an expected disconnection is called:  
(a) Hoarding (b) Handoff (c) Paging (d) Sniffing

> **Ans: (a) Hoarding** — Supports disconnected operation; changes are reintegrated on reconnection.

**185.** The protocol suite designed for web access on early mobile devices, using WML, is:  
(a) SMTP (b) FTP (c) WAP (d) SNMP

> **Ans: (c) WAP** — Wireless Application Protocol.

## F14. Digital evidence: volatility, acquisition, hashing, signatures, steganography, law

**186.** According to RFC 3227, which should be collected FIRST (most volatile)?  
(a) Hard disk (b) CPU registers and cache (c) Archival media (d) Remote logs

> **Ans: (b) Registers and cache** — Order: registers/cache → routing/ARP/process tables, memory → temp files → disk → remote logs → physical config → archival media.

**187.** Which IT Act, 2000 section deals with cyber terrorism (punishable up to life imprisonment)?  
(a) 66C (b) 66E (c) 67 (d) 66F

> **Ans: (d) Section 66F** — 66C = identity theft; 66E = privacy violation; 67 = obscene material.

**188.** RFC 3227 is titled:  
(a) Guidelines for Evidence Collection and Archiving (b) Hypertext Transfer Protocol (c) Simple Mail Transfer Protocol (d) Domain Names — Concepts

> **Ans: (a) Guidelines for Evidence Collection and Archiving** — Source of the order of volatility.

**189.** A hardware write blocker is used during acquisition to:  
(a) Speed up copying (b) Encrypt the suspect drive (c) Allow reading but prevent any writes to the source drive (d) Wipe the drive

> **Ans: (c) Prevent writes to the source** — Preserves original evidence.

**190.** An MD5 hash value is how many bits long?  
(a) 64 (b) 128 (c) 160 (d) 256

> **Ans: (b) 128** — 32 hex characters. (Verified with python hashlib.)

**191.** A SHA-1 hash is 160 bits. Written in hexadecimal it has:  
(a) 32 characters (b) 64 characters (c) 20 characters (d) 40 characters

> **Ans: (d) 40** — 160 / 4 bits per hex digit = 40. (20 is the byte count.)

**192.** A SHA-256 digest written in hexadecimal has how many characters?  
(a) 64 (b) 32 (c) 40 (d) 256

> **Ans: (a) 64** — 256 bits / 4 = 64 hex digits.

**193.** A JPEG file begins with the signature bytes:  
(a) 25 50 44 46 (b) 4D 5A (c) FF D8 FF (d) 50 4B 03 04

> **Ans: (c) FF D8 FF** — JPEG ends with FF D9.

**194.** A file starting with hex 25 50 44 46 ("%PDF") is a:  
(a) ZIP archive (b) PDF document (c) Windows executable (d) PNG image

> **Ans: (b) PDF** — '%'=25, 'P'=50, 'D'=44, 'F'=46. (Verified with python.)

**195.** A .docx file has the same signature as a ZIP archive, because it is a ZIP container. That signature is:  
(a) 4D 5A ("MZ") (b) 89 50 4E 47 (c) 47 49 46 38 ("GIF8") (d) 50 4B 03 04 ("PK")

> **Ans: (d) 50 4B 03 04 ("PK")** — Initials of Phil Katz (PKZIP); also .xlsx, .pptx, .apk, .jar.

**196.** Windows executables (.exe/.dll) begin with:  
(a) 4D 5A ("MZ") (b) FF D8 FF (c) 25 50 44 46 (d) 7F 45 4C 46

> **Ans: (a) 4D 5A ("MZ")** — Initials of Mark Zbikowski; 7F 45 4C 46 = Linux ELF.

**197.** A file beginning 89 50 4E 47 0D 0A 1A 0A is a:  
(a) GIF image (b) JPEG image (c) PNG image (d) BMP image

> **Ans: (c) PNG** — 0x89 followed by "PNG"; GIF begins "GIF8" (47 49 46 38), BMP begins "BM".

**198.** Hiding a message in the least significant bits of image pixels is:  
(a) Encryption with AES (b) LSB steganography (c) Hashing (d) Compression

> **Ans: (b) LSB steganography** — Visual change is imperceptible; detected by steganalysis (statistical/histogram tests).

**199.** Fraudulently using another person's password or electronic signature is punishable under IT Act, 2000 section:  
(a) 43 (b) 65 (c) 66F (d) 66C

> **Ans: (d) Section 66C (identity theft)** — 66D = cheating by personation using a computer resource; 65 = tampering with source documents; 43 = civil penalty for damage.

**200.** The certificate for admissibility of electronic records, formerly under Section 65B of the Indian Evidence Act, 1872, is now under which provision of the Bharatiya Sakshya Adhiniyam, 2023?  
(a) Section 63 (b) Section 45 (c) Section 79A (d) Section 3

> **Ans: (a) Section 63** — BSA in force from 1 July 2024; certificate under §63(4) as per the Schedule. (Safe to write "§65B IEA, now §63 BSA".)
