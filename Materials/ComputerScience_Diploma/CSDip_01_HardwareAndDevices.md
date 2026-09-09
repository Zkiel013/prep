# CS (Diploma) — Hardware, Devices, Storage and the Motherboard

> Elective 3: **Computer Science / Computer Engineering (Diploma)**, NPSC CTSE 2026.
> Covers **Paper-I units 1, 2, 3 and 4**. Companion to `CSDip_00_OVERVIEW.md`.
> Drill questions for this material are in `CSDip_04_MCQ_and_QuestionBank.md`.

---

## Why this file matters

This is the **most MCQ-dense file in the whole set**, and it is the one where a B.Tech CS
graduate is most likely to be quietly under-prepared.

Here is the awkward truth about your position. Your degree taught you *computer architecture* —
pipelines, cache coherence, addressing modes, the memory hierarchy as a performance argument.
It almost certainly did **not** teach you that the floppy connector has 34 pins, that the PS/2
mouse port is green, that a 3.5-inch HD floppy holds 1.44 MB, or that a CD's laser is 780 nm.
Those are exactly the facts a Diploma paper asks, because they are crisp, unambiguous and easy
to write four options for.

The real 2024 CS (Diploma) Paper-I confirms this. Around **17% of it** — roughly 35 of 200
questions — sat in the hardware / motherboard / storage / bus block, alongside another 18
questions on I/O devices and 16 on generations, classification and number systems. Together
that is **over a third of Paper-I** drawn from this single file's material. The questions were
things like: *"Which is a major circuitry that provides support and control for main memory,
cache memory and PCI bus controllers?"* (north bridge), *"Which defines a motherboard's size,
shape and how it is mounted to the case?"* (form factor), *"If there are continuous short beeps
there is a —"* (system board failure), and a matching question on the capacities of CD, DVD,
floppy and Blu-ray.

None of that is hard. All of it is **learnable in a fixed number of hours**, which is the best
property a topic can have three weeks out. Numbers memorised here convert directly into marks.

> **The one section to over-invest in: §9, the motherboard.** It is simultaneously a guaranteed
> 15-mark descriptive question, a rich source of MCQs, and the thing you know least well.

### How to use this file

1. **Read §1–§5 once** — they are short and mostly familiar.
2. **Drill §4 (number systems) with a pen**, not by reading. Speed matters more than
   understanding here; you already understand it.
3. **Learn §6–§8 as facts.** Use the tables. Cover the right-hand column and recite.
4. **Hand-draw the §9 motherboard diagram three times** on separate days.
5. Finish with the **"Numbers you must memorise"** table at the end — it is the single
   highest-yield half-page in this folder.

---

## Topic checklist

Tick only when you can write the answer from memory, not just recognise it.

- [ ] §1 Generations of computers — five-row table with technology, examples, limitations
- [ ] §2 Classification — super / mainframe / mini / workstation / micro, with the comparison table
- [ ] §3 Data representation — bit/byte/nibble/word, BCD, ASCII, EBCDIC, Unicode
- [ ] §4a Number systems and all six conversion directions
- [ ] §4b Binary arithmetic — addition, subtraction
- [ ] §4c 1's complement subtraction with end-around carry
- [ ] §4d 2's complement subtraction, both signs of result
- [ ] §5 Functional block diagram — hand-drawable, with data and control paths distinguished
- [ ] §6 Input devices — keyboard, mouse, scanners, OCR/OMR/MICR, bar-code
- [ ] §7a Output — CRT vs LCD working and comparison
- [ ] §7b Printers — the three-way comparison table, and the working of each
- [ ] §7c Plotters
- [ ] §8a ROM family — ROM/PROM/EPROM/EEPROM/Flash comparison
- [ ] §8b Registers, cache, RAM; SRAM vs DRAM; SDRAM vs DDR
- [ ] §8c Memory hierarchy table, capacity and speed
- [ ] §8d Floppy disks and their four capacities
- [ ] §8e Hard disk — components, organisation, capacity and access-time sums
- [ ] §8f Drive interfaces — IDE/PATA, SATA, SCSI
- [ ] §8g Optical storage — CD/DVD organisation and read/write mechanism
- [ ] §9 **Motherboard in full detail — labelled diagram drawn from memory**
- [ ] Numbers table memorised and self-tested

---

## 1. Generations of computers

### Concept

A "generation" is not a marketing label — it is defined by **the physical device used to switch
electrical signals**. Everything else about the machine follows from that one choice.

Think about why. If your switch is a vacuum tube, it is the size of a light bulb, needs a heated
filament, draws watts and burns out after a few thousand hours. A machine with 18,000 of them
must be room-sized, must have air conditioning, and will fail somewhere every few minutes.
Shrink the switch to a transistor and the same logic fits in a cabinet, runs cool and stays up
for weeks. Put thousands of transistors on one chip and it fits on a desk. Put millions on one
chip and it fits in a pocket.

**So the whole story of computing is one sentence: the switch got smaller.** Size, cost, power
and failure rate fell; speed, reliability and memory rose. If you remember only that, you can
reconstruct most of the table.

### Key points — the table to memorise

| | **1st Generation** | **2nd Generation** | **3rd Generation** | **4th Generation** | **5th Generation** |
|---|---|---|---|---|---|
| **Period** | 1946–1958 | 1959–1964 | 1965–1971 | 1971–present | Present / future |
| **Switching technology** | **Vacuum tube** (thermionic valve) | **Transistor** | **Integrated Circuit** (SSI, MSI) | **LSI / VLSI — the microprocessor** | **ULSI**, parallel processing, AI |
| **Main memory** | Magnetic drum, delay lines | **Magnetic core** | Magnetic core → early semiconductor | Semiconductor RAM (DRAM) | High-density semiconductor |
| **Secondary storage** | Punched cards, paper tape | Magnetic tape, magnetic disk | Magnetic disk | Hard disk, floppy, optical, SSD | SSD, cloud |
| **Language** | Machine language (binary) | Assembly; early HLL — FORTRAN, COBOL | HLL — FORTRAN IV, COBOL, PASCAL, BASIC | HLL, 4GL, GUI, OOP | Natural language, AI languages |
| **Operating system** | None — manual operation | Batch monitor | **Multiprogramming, time-sharing** | GUI, multitasking, networked | Distributed, intelligent |
| **Speed** | Milliseconds | Microseconds | Nanoseconds | Nanoseconds / picoseconds | Faster still |
| **Size / power** | Room-sized, tens of kW | Cabinet-sized | Desk-sized | Desktop → pocket | Miniature, embedded |
| **Reliability** | Very poor | Better | Good | Very high | Very high |
| **Examples** | **ENIAC, EDVAC, EDSAC, UNIVAC-I, IBM 701** | **IBM 1401, IBM 7090/7094, CDC 1604, Honeywell 400** | **IBM 360/370, PDP-8, PDP-11, ICL 2900** | **IBM PC, Apple II, Pentium, all modern PCs** | Robots, expert systems, quantum research |
| **Chief limitation** | Huge, hot, unreliable, hand-wired | Still needed AC; costly | Costly to maintain; needed AC | — | — |

### Facts most often turned into MCQs

| Fact | Answer |
|---|---|
| Who invented the transistor, and where | Bardeen, Brattain, Shockley — **Bell Laboratories, 1947** |
| Who invented the IC | **Jack Kilby (TI) and Robert Noyce (Fairchild), 1958–59** |
| First microprocessor | **Intel 4004, 1971**, 4-bit |
| Generation using ICs | **Third** |
| Generation where GUIs were developed | **Fourth** |
| First completely automatic general-purpose programmable digital computer | **Mark I** (Harvard Mark I, 1944) — ⚠️ some books say ENIAC; the 2024 paper offered Mark I, Analytical Engine, Colossus and ENIAC as options. Mark I is the safer answer for "automatic general-purpose programmable"; ENIAC is the answer for "first general-purpose *electronic*" |
| Characteristic feature of 1st generation | **Bulky** (not flexible, not portable, not easy to program) |
| A 2nd-generation machine among ENIAC / EDSAC / IBM 7090 / UNIVAC | **IBM 7090** |
| Father of the computer | Charles Babbage (Analytical Engine, 1837) |
| Stored-program concept | John von Neumann, 1945 |

### Characteristics of a computer (a stock 5-marker)

Speed · Accuracy · Diligence (no fatigue, no boredom) · Versatility · Storage capacity ·
Automation · Reliability. **A computer has no IQ, no intuition and no common sense** — it
cannot decide anything not programmed into it. That last point is a favourite "which is **not**
a characteristic" MCQ (2024 P-I Q182 offered Accuracy / IQ / Diligence / Efficiency; the answer
is **IQ**).

**Accuracy note:** a computer's accuracy depends on its configuration and on the instructions
given to it, **not** on its physical size. Errors are almost always **GIGO** — garbage in,
garbage out.

### Likely exam questions

- *Explain the generations of computers with the technology, characteristics and examples of each.* **[10]**
- *Write short notes on the fifth generation of computers.* **[5]**
- *What are the characteristics of a computer?* **[5]**

### MCQ traps

- **"Which generation used ICs?"** — Third. Do not confuse the IC (3rd) with the microprocessor (4th). The microprocessor *is* an IC, but the generation break is at LSI/VLSI.
- **UNIVAC-I is first generation, not second** — the name sounds modern.
- **Transistor ≠ IC.** 2nd gen used discrete transistors, 3rd put many on one chip.

---

## 2. Classification of computers

### Concept

Two computers can both be "fast" in completely different senses. A supercomputer is fast at
doing **one enormous calculation**; a mainframe is fast at doing **an enormous number of small
transactions**. That distinction — raw floating-point throughput versus transaction and I/O
throughput — is the axis the whole classification turns on, and it is exactly what examiners
test.

- **Supercomputer**: "How quickly can I simulate tomorrow's weather?" — measured in **FLOPS**.
- **Mainframe**: "How many bank withdrawals can I process this second, without ever losing
  one?" — measured in **transactions per second**, with legendary reliability and I/O capacity.
- **Minicomputer**: a department's shared machine — the middle ground, now largely extinct.
- **Workstation**: one user, but a demanding one — CAD, 3-D rendering, simulation.
- **Microcomputer**: one user, ordinary demands — the PC.

### Comparison table

| Feature | **Supercomputer** | **Mainframe** | **Minicomputer** | **Workstation** | **Microcomputer** |
|---|---|---|---|---|---|
| Users supported | Few (batch jobs) | **Thousands**, via terminals | Tens to hundreds | **One** | One |
| Processors | Thousands (massively parallel) | Several to hundreds | Few | 1–4 | 1–2 |
| Speed measure | **FLOPS** (TFLOPS/PFLOPS) | Transactions/sec, MIPS | MIPS | MIPS/FLOPS | GHz |
| Main memory | Terabytes+ | Hundreds of GB – TB | GB | GB – tens of GB | GB |
| Cost | ₹ hundreds of crores | ₹ crores | ₹ lakhs | ₹ lakhs | ₹ tens of thousands |
| Physical size | Hall | Room / large cabinets | Cabinet | Desk | Desk / lap / palm |
| Key strength | Raw computational speed | **Throughput, reliability, I/O, backward compatibility** | Cost-effective multi-user | Graphics and compute for one user | Cost and ubiquity |
| Typical use | Weather forecasting, nuclear simulation, molecular modelling, aerodynamics, cryptanalysis | Banking, insurance, railway reservation, census, airline reservation | Departmental processing, process control | CAD/CAM, animation, EDA, scientific visualisation | Home, office, education |
| Examples | **PARAM** (C-DAC), **CRAY-1/X-MP**, Sunway TaihuLight, Fugaku, PARAM Siddhi | **IBM z-series**, IBM System/360, UNIVAC 1100 | **PDP-8, PDP-11, VAX-11**, IBM AS/400 | Sun SPARCstation, HP 9000, SGI, Dell Precision | IBM PC, Apple Macintosh, laptops, tablets |
| Least → most powerful | (Micro < Workstation < Mini < Mainframe < Super) | | | | |

### Microcomputer sub-classification

| Type | Description |
|---|---|
| Desktop / PC | Fixed, separate monitor, keyboard, CPU cabinet |
| Laptop / Notebook | Portable, battery, integrated display and keyboard |
| Netbook | Small, cheap, low-power laptop for web use |
| Tablet | Touch-screen slate, no physical keyboard |
| Palmtop / PDA | Handheld, stylus-driven |
| Smartphone | Handheld with cellular telephony |
| Server | A micro or larger machine dedicated to serving other machines |
| Embedded | A microcomputer inside another product — washing machine, car ECU |

### Classification by purpose and by data handled

| Basis | Types |
|---|---|
| **By purpose** | **General purpose** (a PC — programmable for any task) vs **Special purpose** (embedded controller, ATM, calculator) |
| **By data handled** | **Analog** (measures continuous physical quantities — speedometer, thermometer, analog computers for simulation) · **Digital** (counts discrete values — all modern computers) · **Hybrid** (both — hospital ICU monitors, where analog sensors feed a digital processor) |

> **⚠️ Note on categorisation criteria.** 2024 asked which factor is *not* important when
> categorising a computer, with "where it was purchased" as the odd one out. The genuine
> criteria are **speed, memory capacity, storage capacity, number of users supported, and
> cost.**

### Likely exam questions

- *Classify computers on the basis of size and capacity, and compare them.* **[10]**
- *Differentiate between a supercomputer and a mainframe computer.* **[5]**
- *Differentiate between analog, digital and hybrid computers.* **[5]**

### MCQ traps

- **"Fastest computer" = supercomputer; "most users / highest throughput" = mainframe.** Read which one is asked.
- **"Least powerful"** among mini/micro/super/mainframe is the **microcomputer**.
- A **workstation is single-user** even though it is more powerful than a PC. It is not a server.

---

## 3. Data representation and coding schemes

### Concept

A computer has exactly one thing it can physically represent: **the presence or absence of a
voltage.** Everything — text, images, sound, this sentence — has to be encoded as a pattern of
those two states. A "coding scheme" is simply an agreed dictionary saying which bit pattern
means which character. There is nothing deep here; ASCII says `1000001` means `A` because a
committee decided so in 1963.

### Units

| Unit | Size | Note |
|---|---|---|
| **Bit** | 1 binary digit, 0 or 1 | Smallest unit of data. From "**bi**nary digi**t**" |
| **Nibble** | **4 bits** | Exactly one hexadecimal digit; half a byte |
| **Byte** | **8 bits** | Smallest **addressable** unit; holds one ASCII character |
| **Word** | 16 / 32 / 64 bits | The number of bits the CPU handles as one unit — sets register and data-bus width. **Word length is machine-dependent** |

| Multiple | Bytes | Power of 2 |
|---|---|---|
| Kilobyte (KB) | 1,024 | 2¹⁰ |
| Megabyte (MB) | 1,048,576 | 2²⁰ |
| Gigabyte (GB) | 1,073,741,824 | 2³⁰ |
| Terabyte (TB) | ≈ 1.1 × 10¹² | 2⁴⁰ |
| Petabyte (PB) | — | 2⁵⁰ |
| Exabyte (EB) | — | 2⁶⁰ |

> **Trap:** disk manufacturers use decimal (1 GB = 10⁹ bytes), operating systems use binary
> (2³⁰). That is why a "500 GB" drive shows as 465 GB. In an exam, **1 KB = 1024 bytes** unless
> the question says otherwise.
>
> **Second trap:** KB is a unit of *storage*; **Kbps is a unit of speed** (kilobits per second).
> 2024 asked "which is the odd one out — KB, MB, Word, KBPS" and the intended answer was
> **Word** (the only one that is not a size unit) — though KBPS is defensible. ⚠️ verify.

### Coding schemes

| Scheme | Bits | Characters | Origin | Notes |
|---|---|---|---|---|
| **BCD (Binary Coded Decimal)** | 4 bits per **decimal digit** | 0–9 only | — | Each decimal digit is coded separately: 59 → `0101 1001`. **1010–1111 are invalid.** Wastes space but makes decimal I/O trivial — used in calculators, digital clocks, financial systems |
| **6-bit BCD** | 6 | 64 | IBM, early | Uppercase, digits, few symbols |
| **ASCII** | **7** (extended: 8) | **128** (extended: 256) | ANSI, 1963 | **The one to know cold.** The 8th bit was originally a **parity** bit |
| **EBCDIC** | **8** | 256 | **IBM** mainframes | Extended Binary Coded Decimal Interchange Code. Incompatible with ASCII; letters are not contiguous |
| **Unicode** | 8/16/32 variable | > 149,000 | Unicode Consortium, 1991 | UTF-8 (1–4 bytes, ASCII-compatible, the web standard), UTF-16 (2 bytes in the BMP), UTF-32 (fixed 4 bytes). Covers every writing system |
| **Gray code** | n | 2ⁿ | — | Successive values differ in exactly **one bit**. Used in shaft encoders and K-maps to avoid transition glitches |

### ASCII code points you should memorise

| Character | Decimal | Hex | Binary |
|---|---|---|---|
| NUL | 0 | 00 | 0000000 |
| Bell (BEL) | 7 | 07 | — |
| Backspace | 8 | 08 | — |
| Tab (HT) | 9 | 09 | — |
| Line feed (LF) | 10 | 0A | — |
| Carriage return (CR) | 13 | 0D | — |
| Escape (ESC) | 27 | 1B | — |
| **Space** | **32** | 20 | 0100000 |
| `0` | **48** | 30 | 0110000 |
| `9` | 57 | 39 | — |
| **`A`** | **65** | 41 | 1000001 |
| `Z` | 90 | 5A | — |
| **`a`** | **97** | 61 | 1100001 |
| `z` | 122 | 7A | — |
| DEL | 127 | 7F | 1111111 |

**Three shortcuts worth knowing:**
1. **`a` − `A` = 32.** Lowercase is uppercase with bit 5 set. That is why case conversion is one XOR with `0x20`.
2. **The digits start at 48.** So `'7' − '0' = 7` converts a character digit to its value — the standard C idiom.
3. **Codes 0–31 are control characters**, 32–126 are printable, 127 is DEL.

### Worked example

> **Encode the word `Cab` in 7-bit ASCII and in hexadecimal.**
>
> `C` = 67 = 100 0011 = **43₁₆**
> `a` = 97 = 110 0001 = **61₁₆**
> `b` = 98 = 110 0010 = **62₁₆**
> So `Cab` = `1000011 1100001 1100010` = **43 61 62** in hex.

> **Represent 749 in BCD and compare with pure binary.**
>
> BCD: 7 → `0111`, 4 → `0100`, 9 → `1001` ⇒ **`0111 0100 1001`** (12 bits)
> Pure binary: 749 = 512+128+64+32+8+4+1 = **`1011101101`** (10 bits)
> **BCD needs more bits** — that is its cost. Its benefit is that decimal display and input
> need no conversion arithmetic.

### Likely exam questions

- *Define bit, byte, nibble and word.* **[5]**
- *What is BCD? Represent 428 in BCD.* **[5]**
- *Differentiate between ASCII and EBCDIC.* **[5]**
- *Explain the various coding schemes used to represent data in a computer.* **[10]**

### MCQ traps

- **7-bit ASCII represents 128 characters, and the highest code is 127.** "How many" vs "highest code" differ by one — read the question.
- **1010 is not valid BCD.** Any nibble from 1010 to 1111 is invalid.
- **EBCDIC is 8-bit and IBM's**; ASCII is 7-bit and ANSI's.
- Unicode is not "16-bit" flatly — **UTF-16 is 16 bits in the BMP**. If the option says "Unicode is 16-bit", it is the intended answer on a Diploma paper, but know the nuance.

---

## 4. Number systems, conversions and binary arithmetic

### Concept

A positional number system is just an agreement about **what each column is worth**. In base 10,
the columns from the right are worth 1, 10, 100, 1000 — that is, 10⁰, 10¹, 10², 10³. Change the
base and only the column values change; the method is identical. Base 2 columns are worth 1, 2,
4, 8, 16; base 8 columns are 1, 8, 64; base 16 columns are 1, 16, 256.

That is the whole idea. Every conversion below is an application of it.

**Why computers use binary:** a switch is reliably either on or off, but distinguishing ten
distinct voltage levels reliably is hard and expensive. **Why we also use octal and hex:**
binary is correct but unreadable — `11011110` is hard for a human to hold in mind, `DE` is
easy — and the conversion is trivial because 8 = 2³ and 16 = 2⁴, so digits group perfectly.

| System | Base | Digits | Group size in binary |
|---|---|---|---|
| Binary | 2 | 0, 1 | — |
| Octal | 8 | 0–7 | **3 bits** |
| Decimal | 10 | 0–9 | — |
| Hexadecimal | 16 | 0–9, A–F (A=10 … F=15) | **4 bits** |

**The 4-bit table. Memorise it and half of all conversion questions become instant.**

| Dec | Bin | Oct | Hex | | Dec | Bin | Oct | Hex |
|---|---|---|---|---|---|---|---|---|
| 0 | 0000 | 0 | 0 | | 8 | 1000 | 10 | 8 |
| 1 | 0001 | 1 | 1 | | 9 | 1001 | 11 | 9 |
| 2 | 0010 | 2 | 2 | | 10 | 1010 | 12 | A |
| 3 | 0011 | 3 | 3 | | 11 | 1011 | 13 | B |
| 4 | 0100 | 4 | 4 | | 12 | 1100 | 14 | C |
| 5 | 0101 | 5 | 5 | | 13 | 1101 | 15 | D |
| 6 | 0110 | 6 | 6 | | 14 | 1110 | 16 | E |
| 7 | 0111 | 7 | 7 | | 15 | 1111 | 17 | F |

And the powers of 2: **1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, 2048, 4096, 8192, 16384,
32768, 65536.** Know them to 2¹⁶ without thinking.

### 4.1 Conversions — every direction, worked

#### (a) Any base → decimal: multiply each digit by its column weight

> **(1101101)₂ → decimal**
>
> | Bit | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
> |---|---|---|---|---|---|---|---|
> | Weight | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
> | Product | 64 | 32 | 0 | 8 | 4 | 0 | 1 |
>
> 64 + 32 + 8 + 4 + 1 = **109₁₀**

> **(357)₈ → decimal**
> 3 × 8² + 5 × 8¹ + 7 × 8⁰ = 3(64) + 5(8) + 7 = 192 + 40 + 7 = **239₁₀**

> **(2AF)₁₆ → decimal**
> 2 × 256 + 10 × 16 + 15 × 1 = 512 + 160 + 15 = **687₁₀**

#### (b) Decimal → any base: repeated division, read remainders **upwards**

> **156 → binary**
>
> | Division | Quotient | Remainder |
> |---|---|---|
> | 156 ÷ 2 | 78 | **0** |
> | 78 ÷ 2 | 39 | **0** |
> | 39 ÷ 2 | 19 | **1** |
> | 19 ÷ 2 | 9 | **1** |
> | 9 ÷ 2 | 4 | **1** |
> | 4 ÷ 2 | 2 | **0** |
> | 2 ÷ 2 | 1 | **0** |
> | 1 ÷ 2 | 0 | **1** |
>
> Read the remainder column **bottom to top**: **(10011100)₂**
> *Check:* 128 + 16 + 8 + 4 = 156 ✓

> **156 → octal**
> 156 ÷ 8 = 19 r **4**; 19 ÷ 8 = 2 r **3**; 2 ÷ 8 = 0 r **2** ⇒ **(234)₈**
> *Check:* 2(64) + 3(8) + 4 = 128 + 24 + 4 = 156 ✓

> **156 → hexadecimal**
> 156 ÷ 16 = 9 r **12 = C**; 9 ÷ 16 = 0 r **9** ⇒ **(9C)₁₆**
> *Check:* 9(16) + 12 = 144 + 12 = 156 ✓

#### (c) Binary ↔ octal: group in **3s** from the binary point

> **(10011100)₂ → octal**
> Pad to a multiple of 3 from the right: `010 011 100` → 2, 3, 4 → **(234)₈** ✓ (matches above)

> **(357)₈ → binary**
> 3 = `011`, 5 = `101`, 7 = `111` ⇒ **(011101111)₂** = `11101111`

#### (d) Binary ↔ hexadecimal: group in **4s** from the binary point

> **(10011100)₂ → hex**
> `1001 1100` → 9, C ⇒ **(9C)₁₆** ✓

> **(2AF)₁₆ → binary**
> 2 = `0010`, A = `1010`, F = `1111` ⇒ **(001010101111)₂** = `1010101111`

#### (e) Octal ↔ hexadecimal: **always go via binary**

> **(357)₈ → hex**
> Step 1, to binary in 3s: `011 101 111` = `011101111`
> Step 2, regroup in 4s from the **right**, padding left: `0000 1110 1111`
> Step 3: 0, E, F ⇒ **(EF)₁₆**
> *Check:* 357₈ = 239₁₀; EF₁₆ = 14(16) + 15 = 239 ✓

#### (f) Fractions: multiply by the base, read integer parts **downwards**

> **0.6875₁₀ → binary**
>
> | Step | Product | Integer part |
> |---|---|---|
> | 0.6875 × 2 | 1.375 | **1** |
> | 0.375 × 2 | 0.75 | **0** |
> | 0.75 × 2 | 1.5 | **1** |
> | 0.5 × 2 | 1.0 | **1** |
> | fraction = 0, stop | | |
>
> Read **top to bottom**: **(0.1011)₂**
> *Check:* 1/2 + 0 + 1/8 + 1/16 = 0.5 + 0.125 + 0.0625 = 0.6875 ✓

> **(1101.101)₂ → decimal**
> Integer: 8 + 4 + 1 = 13. Fraction: 1/2 + 0 + 1/8 = 0.625. ⇒ **13.625₁₀**

> **0.1₁₀ → binary** is **non-terminating**: 0.0001100110011… (recurring `0011`). This is why
> floating-point arithmetic cannot represent 0.1 exactly. Worth one line in a 15-marker.

### 4.2 Binary arithmetic

#### Addition — four rules

| A | B | Sum | Carry |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | **0** | **1** |
| 1+1+1 | | **1** | **1** |

> **1011 + 1101**
> ```
>    1 1 1        ← carries
>      1 0 1 1    (11)
>    + 1 1 0 1    (13)
>    ---------
>    1 1 0 0 0    (24) ✓
> ```

#### Subtraction by borrowing — four rules

| A | B | Difference | Borrow |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |
| **0** | **1** | **1** | **1** (borrow 1 from the next column) |

> **(1011.001)₂ − (110.10)₂** *(this exact sum appeared in the 2024 paper)*
>
> Align the binary points and pad: `1011.001 − 0110.100`
> ```
>      1 0 1 1 . 0 0 1
>    - 0 1 1 0 . 1 0 0
>    -----------------
>      0 1 0 0 . 1 0 1
> ```
> Working right to left: 1−0 = 1; 0−0 = 0; 0−1 → borrow, = 1 and the `1` in the units column
> becomes 0; then 0−0 = 0 (units), 1−1 = 0 (twos), 0−1 → borrow from the 8s: = 1, and 1 becomes 0.
> Result **(100.101)₂**
> *Check:* 1011.001₂ = 11.125; 110.10₂ = 6.5; 11.125 − 6.5 = **4.625** = 100.101₂ ✓

### 4.3 Complements — and why they exist

**The intuition first.** Building an adder circuit is easy; building a *separate* subtractor is
extra hardware and extra cost. So designers found a trick: **express subtraction as addition of
a complement.** `A − B` becomes `A + (complement of B)`. One circuit does both operations. Every
CPU in existence uses this.

| | **1's complement** | **2's complement** |
|---|---|---|
| How to form | **Invert every bit** (0↔1) | **1's complement, then add 1** |
| Representations of zero | **Two** (+0 = 00000000, −0 = 11111111) | **One** (00000000) |
| Range for n bits | −(2ⁿ⁻¹ − 1) to +(2ⁿ⁻¹ − 1) | **−2ⁿ⁻¹ to +(2ⁿ⁻¹ − 1)** |
| 8-bit range | −127 to +127 | **−128 to +127** |
| Carry handling in subtraction | **End-around carry** — add the carry back in | **Discard** the carry |
| Used in modern hardware | Rarely | **Universally** |

#### Shortcut for forming a 2's complement by inspection

Scan from the **right**: copy bits up to and **including the first 1**, then **invert everything
to the left of it**.

> 2's complement of `00101100`: rightmost bits are `…100`. Copy `100`, invert the rest
> (`00101` → `11010`) ⇒ **`11010100`**.
> *Check the long way:* invert all = `11010011`, add 1 = `11010100` ✓

#### Worked: 1's complement subtraction

> **Compute 45 − 27 using 8-bit 1's complement.**
>
> 45 = `00101101`, 27 = `00011011`
> 1's complement of 27 = `11100100`
> ```
>      0 0 1 0 1 1 0 1     (45)
>    + 1 1 1 0 0 1 0 0     (1's comp of 27)
>    -------------------
>  1   0 0 0 1 0 0 0 1     ← carry out = 1
> ```
> **There is a carry out, so the result is positive: add the carry back in (end-around carry).**
> `00010001 + 1 = ` **`00010010` = 18** ✓

> **Compute 27 − 45 using 8-bit 1's complement.**
>
> 1's complement of 45 = `11010010`
> ```
>      0 0 0 1 1 0 1 1     (27)
>    + 1 1 0 1 0 0 1 0     (1's comp of 45)
>    -------------------
>  0   1 1 1 0 1 1 0 1     ← no carry out
> ```
> **No carry out, so the result is negative and is in 1's complement form.** Take the 1's
> complement of the result to get the magnitude: `11101101` → `00010010` = 18.
> Answer = **−18** ✓

#### Worked: 2's complement subtraction

> **Compute 45 − 27 using 8-bit 2's complement.**
>
> 2's complement of 27 = `11100100 + 1` = `11100101`
> ```
>      0 0 1 0 1 1 0 1     (45)
>    + 1 1 1 0 0 1 0 1     (2's comp of 27)
>    -------------------
>  1   0 0 0 1 0 0 1 0     ← carry out
> ```
> **Carry out = 1 ⇒ result positive; DISCARD the carry.**
> Answer = `00010010` = **18** ✓

> **Compute 27 − 45 using 8-bit 2's complement.**
>
> 2's complement of 45 = `11010010 + 1` = `11010011`
> ```
>      0 0 0 1 1 0 1 1     (27)
>    + 1 1 0 1 0 0 1 1     (2's comp of 45)
>    -------------------
>  0   1 1 1 0 1 1 1 0     ← no carry out
> ```
> **No carry out ⇒ result is negative and in 2's complement form.** Take the 2's complement of
> the result: invert `11101110` → `00010001`, add 1 → `00010010` = 18.
> Answer = **−18** ✓

#### The rule, in one box — memorise this

```
+------------------------------------------------------------------+
|  1's COMPLEMENT SUBTRACTION (A - B)                               |
|    1. Form the 1's complement of B (invert all bits)              |
|    2. Add it to A                                                 |
|    3. CARRY OUT?  -> result POSITIVE. ADD the carry back in       |
|                      (END-AROUND CARRY). That is the answer.      |
|       NO CARRY?   -> result NEGATIVE. Take the 1's complement     |
|                      of the sum; prefix a minus sign.             |
+------------------------------------------------------------------+
|  2's COMPLEMENT SUBTRACTION (A - B)                               |
|    1. Form the 2's complement of B (invert all bits, add 1)       |
|    2. Add it to A                                                 |
|    3. CARRY OUT?  -> result POSITIVE. DISCARD the carry.          |
|       NO CARRY?   -> result NEGATIVE. Take the 2's complement     |
|                      of the sum; prefix a minus sign.             |
+------------------------------------------------------------------+
|  MEMORY HOOK:  1's complement -> "1 comes back" (end-around)      |
|                2's complement -> "throw it away"                  |
+------------------------------------------------------------------+
```

#### Signed number representations compared

| Decimal | Sign-magnitude (8-bit) | 1's complement | **2's complement** |
|---|---|---|---|
| +5 | 0000 0101 | 0000 0101 | 0000 0101 |
| −5 | 1000 0101 | 1111 1010 | **1111 1011** |
| +0 | 0000 0000 | 0000 0000 | 0000 0000 |
| −0 | 1000 0000 | 1111 1111 | *does not exist* |
| −128 | *not representable* | *not representable* | **1000 0000** |

In all three, **the MSB is the sign bit: 0 = positive, 1 = negative.**

### Likely exam questions

- *Convert (1101101)₂ to decimal, octal and hexadecimal.* **[5]**
- *Subtract 27 from 45 using (a) 1's complement and (b) 2's complement arithmetic.* **[5]**
- *What is 2's complement? Why is it preferred over 1's complement?* **[5]**
- *Explain the number systems used in computers and demonstrate all conversions with examples.* **[15]**

### MCQ traps

- **1's vs 2's complement.** If the question says "2's complement", the "+1" is not optional. This is the single most common careless error in the whole syllabus.
- **End-around carry belongs to 1's complement only.** In 2's complement you discard.
- Octal ↔ hex **cannot** be done directly by grouping; you must pass through binary.
- Padding: when grouping binary into 3s or 4s, **pad on the left for the integer part and on the right for the fraction part.** Getting this backwards silently changes the answer.

---

## 5. Basic organisation of a computer

### Concept

Strip away every detail and a computer is five boxes. Something has to **get data in**, something
has to **hold it**, something has to **do arithmetic on it**, something has to **decide what
happens next**, and something has to **get results out**. That is the whole architecture, and
it has not changed since von Neumann described it in 1945.

The key insight von Neumann added — the **stored-program concept** — is that the *program* lives
in the same memory as the *data*. Before that, "programming" meant rewiring the machine by hand.
Once instructions are just numbers in memory, a machine can be re-purposed in seconds, and a
program can even modify itself.

### The functional block diagram — draw it exactly like this

```
                     +==================================================+
                     |                  C P U                           |
                     |                                                  |
  +-----------+      |   +--------------------+                         |      +------------+
  |           |      |   |   CONTROL UNIT     |                         |      |            |
  |   INPUT   |=====>|   |  (fetch, decode,   |                         |=====>|   OUTPUT   |
  |   UNIT    |      |   |   sequence, time)  |                         |      |    UNIT    |
  |           |      |   +---------+----------+                         |      |            |
  +-----------+      |             |                                    |      +------------+
   keyboard,         |             | (control signals - DASHED, to ALL) |       monitor,
   mouse,            |             v                                    |       printer,
   scanner           |   +--------------------+                         |       plotter,
                     |   | ARITHMETIC & LOGIC |                         |       speaker
                     |   |    UNIT  (ALU)     |                         |
                     |   |  + - x /  AND OR   |                         |
                     |   |  NOT  compare shift|                         |
                     |   +---------+----------+                         |
                     |             ^                                    |
                     +=============|====================================+
                                   |  (data bus - SOLID, both ways)
                                   v
                     +--------------------------------+
                     |     PRIMARY / MAIN MEMORY      |
                     |     (RAM + ROM)  - volatile    |
                     |   holds program + data +       |
                     |   intermediate + final results |
                     +----------------+---------------+
                                      ^
                                      |  (both ways)
                                      v
                     +--------------------------------+
                     |  SECONDARY / MASS STORAGE UNIT |
                     |  hard disk, SSD, CD/DVD, tape  |
                     |       (non-volatile)           |
                     +--------------------------------+

   LEGEND:  ===>  or  <-->   solid line = DATA / INSTRUCTION flow
            - - - >          dashed line = CONTROL signals from the CU to every block
```

**Drawing instructions for the exam.** Draw the CPU as one large box containing two inner boxes
(CU on top, ALU below). Put Input on the left, Output on the right, Memory below the CPU, and
Secondary Storage below Memory. Use **solid arrows** for the data path and **dashed arrows**
radiating from the Control Unit to *every* other block. Label the dashed arrows "control
signals" once. Add "CPU = CU + ALU + Registers" as a caption. That caption alone earns a mark.

### The five units

| Unit | Function | Examples |
|---|---|---|
| **Input unit** | Accepts data and instructions from the outside world; **converts them to binary**; supplies them to main memory | Keyboard, mouse, scanner, microphone |
| **Memory unit (primary)** | Stores the program, the input data, intermediate results and the final results before output. Directly accessible by the CPU. **Volatile** | RAM, ROM, cache |
| **ALU** | Performs **arithmetic** (+ − × ÷) and **logic** (AND, OR, NOT, XOR, compare, shift) operations. Works with the accumulator and the flag/status register | — |
| **Control unit** | The nerve centre. **Fetches** each instruction, **decodes** it, generates the timing and control signals that make every other unit act, and sequences the next instruction. **Processes no data itself** | — |
| **Output unit** | Converts binary results into human-readable form and presents them | Monitor, printer, speaker, plotter |
| **Secondary / mass storage** | Permanent bulk storage of programs and data not currently in use. **Non-volatile**, cheaper and slower than main memory, not directly addressable by the CPU | Hard disk, SSD, DVD, tape |

**CPU = Control Unit + ALU + Registers.** The CPU is also called the **microprocessor** when it
is on one chip, and is described as the **"brain" of the computer**. Within the CPU, the **ALU
is sometimes called the "heart" of the processor** (2024 asked exactly this).

### The machine cycle (fetch–decode–execute–store)

| Step | Who does it | What happens |
|---|---|---|
| **1. Fetch** | CU | The instruction at the address in the **PC** is copied from memory into the **IR** |
| **2. Decode** | CU | The instruction is interpreted; operands are identified |
| **3. Execute** | ALU | The operation is performed |
| **4. Store** | CU | The result is written back to a register or to memory |

The PC is then incremented (or loaded with a branch target) and the cycle repeats.
**Steps 1–2 are the *instruction cycle*; 3–4 are the *execution cycle*.**

> **2024 trap:** "Which is **not** a part of the CPU cycle — fetching, decoding, controlling,
> storing?" The intended answer is **controlling** (it is what the CU *is*, not a phase).

### Important registers

| Register | Full name | Holds |
|---|---|---|
| **PC** | Program Counter | Address of the **next** instruction to be executed |
| **IR** | Instruction Register | The instruction **currently** being executed |
| **MAR** | Memory Address Register | The **address** of the memory location to be read from or written to |
| **MBR / MDR** | Memory Buffer / Data Register | The **data** being transferred to or from memory |
| **AC** | Accumulator | The operand and result of ALU operations |
| **Flags / PSW** | Status register | Zero, carry, sign, overflow, parity bits |
| **SP** | Stack Pointer | Address of the top of the stack |

> **PC vs MAR is a favourite MCQ.** PC = *next instruction's* address. MAR = address of *whatever
> memory location is about to be accessed*, instruction or data.
> **MBR is not a register type** — beware: in a motherboard context MBR means **Master Boot
> Record**. 2024 offered "PC, PCB, MAR, MBR" for "which is not a type of register" and the
> intended answer was **PCB** (Process Control Block, an OS data structure).

### Likely exam questions

- *What are the basic functional units of a computer? Explain the role of each.* **[5]**
- *Explain, with a labelled block diagram, the basic organisation of a computer.* **[10]**
- *Explain the machine cycle. Name the registers involved and state what each holds.* **[10]**

---

## 6. Input devices

### 6.1 Keyboard

**Concept.** A keyboard is a grid of switches. Pressing a key closes a connection at one row–
column intersection; a small microcontroller inside the keyboard scans the grid continuously,
detects which intersection closed, and sends a **scan code** — not an ASCII code — to the PC.
The keyboard controller and the OS then translate the scan code into a character, applying Shift,
Caps Lock, and the current keyboard layout. There is a separate scan code for key-*down* and
key-*up*, which is how the machine knows you are holding Shift.

| Feature | Detail |
|---|---|
| Standard layout | **QWERTY** (named after the first six top-row letters). Alternatives: DVORAK, AZERTY (French), COLEMAK |
| Key count | **101 keys** (enhanced/AT-101); **104 keys** with the two Windows keys and the menu key. Older PC/XT keyboard = **83/84 keys** |
| **Function keys** | **F1 – F12 → twelve** (asked in 2024) |
| Key groups | Alphanumeric (typewriter) · **Numeric keypad** (17 keys) · **Function keys** (F1–F12) · **Cursor/navigation** (arrows, Home, End, PgUp, PgDn, Ins, Del) · **Modifier/special** (Shift, Ctrl, Alt, Caps Lock, Num Lock, Scroll Lock, Esc, Tab, Enter, Backspace, **PrtScn**, Pause) |
| Construction types | **Membrane** (cheap, quiet, mushy) · **Mechanical** (individual switches, tactile, durable, ~50 M keystrokes) · **Capacitive** · **Scissor-switch** (laptops) |
| Other types | Ergonomic/split, wireless (RF or Bluetooth), virtual/on-screen, projection, gaming, multimedia, Braille |
| Interfaces | PS/2 (**purple**, 6-pin mini-DIN) → USB → Bluetooth |

> **A keyboard is not a pointing device.** It can *substitute* for a mouse (Tab, arrow keys,
> keyboard shortcuts, Sticky Keys) but it does not control 2-D cursor movement directly. 2024
> tested exactly this distinction.

### 6.2 Mouse

**Concept.** A mouse reports **relative displacement**, not absolute position. It says "I moved
40 units right and 12 up since I last reported"; the OS adds that to the pointer's current
position. That is why lifting a mouse and putting it down elsewhere does not teleport the
pointer.

| Type | How it senses motion | Pros | Cons |
|---|---|---|---|
| **Mechanical / ball** | A rubber-coated steel ball rolls against two perpendicular rollers (X and Y); each roller turns a **slotted encoder wheel** interrupting an LED–photodetector pair; pulse counts give displacement | Cheap, works on any surface | Ball picks up dirt; rollers clog; needs cleaning; lower precision; moving parts wear |
| **Optical** | An **LED** (typically red) illuminates the surface at a shallow angle; a small **CMOS image sensor** photographs it 1,500–6,000+ times per second; an on-board **DSP** cross-correlates successive images to compute Δx and Δy | No moving parts, no cleaning, higher precision, more reliable | Struggles on glass and uniform glossy surfaces |
| **Laser** | Same as optical but uses a **laser diode (VCSEL)** instead of an LED — a coherent source resolves finer surface detail | Highest precision (up to 20,000 DPI); works on more surfaces including glossy | Costlier; can be *too* sensitive |
| **Trackball** | An inverted mouse — the user rolls the ball directly; the device stays still | Needs no desk space; good for RSI | Different motor skill |
| **Touchpad** | Capacitive sensing grid detects finger position | Integrated in laptops | Less precise for fine work |

**Parts of an optical mouse:** LED (or laser diode), **lens**, **optical/CMOS image sensor**,
DSP chip, left/right buttons, **scroll wheel**, cable or wireless transceiver, PCB.
> **2024 trap:** "Which is **not** a part of an optical mouse — LED, optical sensor, CCD,
> diode?" The intended answer is **CCD** — optical mice use **CMOS** sensors, not CCDs.

**The scroll wheel** is a third axis: a notched wheel between the buttons, read by its own
encoder, generating scroll events; pressing it acts as a middle-button click.

**Mouse resolution** is quoted in **DPI (dots per inch)** or CPI (counts per inch): higher DPI
means the pointer travels further on screen for the same physical movement.

**Mouse operations to name in an answer:** point, click, double-click, right-click (context
menu), **drag and drop**, scroll, hover.

### 6.3 Scanners

**Concept.** A scanner is a camera that moves. A bright lamp illuminates the document; the light
reflected from it is directed by mirrors and a lens onto a row of light-sensitive cells (a **CCD
array**); the assembly traverses the page line by line; each cell's output voltage — proportional
to the brightness it sees — is digitised by an **ADC** into a pixel value. Colour is captured by
using three filters (red, green, blue) or three sensor rows.

| Type | Description | Use |
|---|---|---|
| **Flatbed** | Document laid on a glass platen; the scan head moves beneath | General office; the most common |
| **Sheet-fed** | The document moves past a fixed head | Multi-page documents, fax machines |
| **Handheld** | Dragged over the document by hand | Small images, portable use |
| **Drum** | Document mounted on a rotating drum, read by a photomultiplier tube | Professional pre-press; the highest quality |
| **3-D scanner** | Captures object geometry by laser or structured light | CAD, forensics, printing |

**Scan parameters** you set before scanning: **resolution (DPI)**, **colour mode** (line art /
greyscale / colour) and **colour depth** (bits per pixel), **document size**, **file format**,
brightness/contrast, and **simplex vs duplex** for sheet-fed units.
> Note: "scanning method" is not a normally-set parameter — 2024 used it as the odd one out.

### 6.4 OCR, OMR, MICR and bar-code readers — the four "reader" technologies

These four are constantly confused and therefore constantly examined. Learn the table.

| | **OCR** | **OMR** | **MICR** | **Bar-code reader** |
|---|---|---|---|---|
| Full name | **Optical Character Recognition** | **Optical Mark Recognition/Reader** | **Magnetic Ink Character Recognition** | — |
| What it reads | **Printed or typed characters**, converting the image to editable text | **The presence or absence of a mark** in a predefined position | Characters printed in **magnetic (iron-oxide) ink** | A pattern of **parallel bars and spaces of varying width** |
| How it works | Scan the page → segment into characters → match each against stored patterns / neural network → output character codes | Reflected-light sensors detect darkened bubbles at fixed coordinates | The document passes a **magnetising head**, then a read head detects the magnetic signature of each character shape | A light source scans across; **dark bars absorb, light spaces reflect**; a photodiode converts the reflection to a pulse train; a decoder converts it to digits |
| Typeface | Any (with training) | n/a | **E-13B** (US/India) or CMC-7 (Europe) | UPC, EAN-13, Code 39, Code 128, QR (2-D) |
| Accuracy | Good but imperfect; errors on poor scans and handwriting | Very high | **Extremely high — unaffected by stamps, folds, signatures over the characters** | Very high |
| Typical use | Digitising books, forms, number plates, passports | **OMR answer sheets for competitive exams (this exam's own answer sheet!)**, ballot papers, surveys | **Bank cheques** — the code line at the bottom | Retail point of sale, inventory, library issue, courier tracking, boarding passes |

**Bar-code structure worth naming:** quiet zone, start character, data characters, **check
digit**, stop character, quiet zone. The **check digit** validates the read.

### 6.5 Other input devices — one line each

| Device | Description |
|---|---|
| **Joystick** | A pivoted stick reporting direction and displacement; gaming, flight simulators, industrial control |
| **Light pen** | A photodetector in a stylus; detects when the CRT's electron beam passes the point it is touching, giving its position |
| **Touch screen** | A display overlaid with position sensing — **resistive** (two conductive layers pressed together, works with any stylus), **capacitive** (senses the finger's charge, supports multi-touch), infrared, surface-acoustic-wave. **Both an input and an output device** |
| **Digitiser / graphics tablet** | A flat pad plus a stylus; reports **absolute** position; used for drawing, CAD, signature capture |
| **Microphone** | Converts sound pressure into an analog electrical signal, digitised by the sound card's ADC |
| **Webcam / digital camera** | Image sensor (CMOS/CCD) plus lens; captures still or moving images |
| **MIDI keyboard** | Sends note/velocity messages, not audio |
| **Biometric devices** | Fingerprint, iris, retina, face, voice, palm-vein readers |
| **Smart card / magnetic stripe reader** | Reads a chip or magnetic stripe |
| **RFID / NFC reader** | Reads a tag by radio; NFC allows a phone to act as a contactless smart card |
| **Sensors** | Temperature, pressure, light, accelerometer, GPS |

### Likely exam questions

- *Explain the working of an optical mouse. How does it differ from a mechanical mouse?* **[5]**
- *Differentiate between OCR, OMR and MICR.* **[5]**
- *What is a bar-code reader? Explain its working and applications.* **[5]**
- *Explain the various input devices of a computer.* **[10]**

### MCQ traps

- **MICR = cheques. OMR = answer sheets. OCR = converting scanned text.** Do not mix them.
- **Touch screen, modem, NIC and a multifunction printer are BOTH input and output devices.**
- An optical mouse uses a **CMOS** sensor, not a CCD.
- **A scanner is an input device; a plotter is an output device.** Obvious until you are tired.

---

## 7. Output devices

### 7.1 Monitors — CRT vs LCD

#### How a CRT works

Inside an evacuated glass tube, an **electron gun** heats a cathode until it emits electrons.
A high positive voltage on the anode accelerates them into a beam. **Deflection coils** (magnetic)
around the neck bend the beam so it sweeps across the screen in a raster — left to right, top to
bottom. The inside of the screen face is coated with **phosphor**, which glows where the beam
strikes it. Beam intensity controls brightness. For colour, there are **three guns (R, G, B)**
and three phosphor dots per pixel, with a **shadow mask** or **aperture grille** ensuring each
gun's beam hits only its own colour of phosphor.

Because the phosphor glow decays, the whole screen must be **redrawn many times per second** —
the **refresh rate** (60–100 Hz). Too low a refresh rate produces visible flicker and eye strain.

#### How an LCD works

Liquid crystals are molecules that **twist the polarisation of light**, and the amount of twist
changes with an applied voltage. An LCD panel is a sandwich: **backlight** (CCFL or LED) →
**polariser** → glass with transparent electrodes → **liquid crystal layer** → colour filter →
second polariser at 90°. With no voltage, the crystals twist the light 90° so it passes the
second polariser — the pixel is bright. Apply voltage and the crystals untwist, so the light is
blocked — the pixel is dark. Intermediate voltages give intermediate brightness. Each pixel has
three sub-pixels with red, green and blue filters.

**TFT (Thin Film Transistor) / active matrix** gives each sub-pixel its own transistor and
capacitor, so it holds its state; **passive matrix** addresses rows and columns in sequence and
is slower and lower-contrast.

**An LCD emits no light of its own** — it modulates a backlight. That is why an LCD washes out
in sunlight and why "LED monitor" is a marketing term for *an LCD with an LED backlight*.

#### The comparison table

| Feature | **CRT** | **LCD** |
|---|---|---|
| Technology | Electron beam on **phosphor** | Liquid crystals modulating a **backlight** |
| Physical depth / weight | Very deep, very heavy | Thin, light |
| Power consumption | High (70–150 W) | Low (20–40 W) |
| Radiation / emissions | Emits X-rays and EM radiation | Negligible |
| Flicker | Present at low refresh rates | **None** — pixels hold state |
| Geometric distortion | Possible (pincushion, barrel) | **None** — a fixed pixel grid |
| Resolution | **Any resolution looks acceptable** (multisync) | Sharp only at the **native resolution**; scaled images blur |
| Colour reproduction | Excellent; wide gamut, deep blacks | Very good; older panels had poorer blacks and gamma |
| Contrast ratio | Very high (true black when the beam is off) | Lower on basic panels (backlight leaks) |
| Viewing angle | Wide | Narrower on TN panels; wide on IPS |
| Response time | Instant | Slower (ghosting on early panels) |
| Screen size vs footprint | Small screen, huge footprint | Large screen, tiny footprint |
| Heat | High | Low |
| Cost | Cheaper historically | Cheaper now; CRT is obsolete |
| Lifetime | Phosphor burn-in possible | Backlight dims over time |

**Monitor terminology to define in an answer:** resolution (e.g. 1920 × 1080), **pixel**, **dot
pitch** (distance between same-colour phosphor dots — smaller is sharper), refresh rate (Hz),
aspect ratio (4:3, 16:9), colour depth (bits/pixel), **VDU** (Visual Display Unit, the formal
name), video adapter/graphics card, and the connectors VGA (analog), DVI, HDMI, DisplayPort.

**Also mention for completeness:** **LED** (LCD with LED backlight, or true OLED),
**plasma** (each cell is a tiny fluorescent lamp of ionised gas — big, bright, power-hungry,
obsolete), and **OLED** (organic LEDs emit their own light — perfect blacks, thin, flexible).

### 7.2 Printers

#### The primary division

| | **Impact printers** | **Non-impact printers** |
|---|---|---|
| Mechanism | A print head **physically strikes** an inked ribbon against the paper | **No physical contact**; ink is sprayed, or toner is fused, or paper is heated |
| Noise | Loud | Quiet |
| **Multi-part / carbon copies** | **YES** — the only kind that can | No |
| Speed | Slow | Fast |
| Quality | Lower | Higher |
| Examples | **Dot matrix**, daisy wheel, line printer, drum printer, chain printer | **Laser**, inkjet, thermal, electrostatic |

#### How each of the three works

**Dot matrix (DMP).** The print head carries a vertical column of **9 or 24 tiny pins** driven
by solenoids. As the head traverses the line, the right combination of pins fires at each
horizontal position, striking an inked ribbon and pressing ink onto the paper. Characters are
therefore built from a **matrix of dots** — hence the name. 24-pin heads give finer dots and
"near letter quality" (NLQ). Uses continuous **tractor-feed** stationery.

**Inkjet.** A print head with dozens to thousands of microscopic nozzles sprays **droplets of
liquid ink** (picolitres) directly at the paper. Two ejection technologies: **thermal
(bubble-jet)** — a tiny heater vaporises a bubble of ink which ejects a droplet; and
**piezoelectric** — a crystal deforms under voltage and squeezes out a droplet. Colour comes
from CMYK cartridges combining on the page.

**Laser.** A **page printer**, and the mechanism is worth knowing as a sequence of seven steps:
1. **Charging** — a corona wire or charge roller gives the photosensitive **drum** a uniform
   negative charge.
2. **Writing/exposing** — a **laser beam**, steered by a rotating polygonal mirror, scans the
   drum, discharging the spots it hits. This writes a hidden **electrostatic latent image**.
3. **Developing** — the drum rolls past the **toner** (a fine plastic-and-pigment powder), which
   sticks only to the discharged areas.
4. **Transferring** — the paper, given an opposite charge, passes the drum and pulls the toner off.
5. **Fusing** — hot rollers (~200 °C) **melt the toner into the paper fibres**. This is why laser
   output comes out warm and is smudge-proof.
6. **Cleaning** — a blade scrapes residual toner off the drum.
7. **Discharging** — an erase lamp neutralises the drum for the next page.

#### The three-way comparison table — learn this cold

| Feature | **Dot Matrix** | **Inkjet** | **Laser** |
|---|---|---|---|
| Impact / non-impact | **Impact** | Non-impact | Non-impact |
| Print element | 9 or 24 **pins** striking a ribbon | **Nozzles spraying ink droplets** | **Laser + drum + toner + heat fusing** |
| Prints by | Character | Character/band | **Whole page at once** |
| Consumable | Inked **ribbon** | Ink **cartridge** | **Toner** cartridge + drum |
| Speed measure | **CPS** (characters/sec) | **PPM** | **PPM** |
| Typical speed | 30 – 600 CPS | 4 – 20 PPM | 8 – 100+ PPM |
| Resolution | Low — 72–240 DPI, visible dots | 600 – 4800 DPI | 600 – 2400 DPI |
| Text quality | Poor to fair (NLQ on 24-pin) | Good | **Excellent — sharpest text** |
| Photo/colour quality | Very poor | **Excellent** | Good |
| Noise | **Very noisy** | Quiet | Quiet |
| Initial cost | Low | **Lowest** | High |
| Cost per page | **Lowest** | **Highest** (cartridges) | Low to medium |
| **Carbon / multi-part copies** | **YES** | No | No |
| Ink smudging | No | Possible until dry | No (fused) |
| Duty cycle | Rugged; tolerates dust and heat | Light | Heavy |
| Best suited to | Invoices, bills, railway tickets, multi-part stationery, harsh industrial environments | Home use, photographs, low-volume colour | Offices, high-volume text, sharp documents |

#### Other printer types worth one line

| Type | Note |
|---|---|
| **Daisy wheel** | Impact; a wheel of fully-formed characters struck by a hammer — typewriter quality but **text only, no graphics**; obsolete |
| **Line printer** (drum, chain, band) | Impact; prints a whole **line** at once at 300–3000 **LPM**; used with mainframes |
| **Thermal** | Non-impact; heats special heat-sensitive paper — receipts, ATM slips, fax. Cheap, but the print fades |
| **Thermal wax / dye-sublimation** | Non-impact; heats a coloured wax or dye ribbon — photo-quality continuous tone |
| **3-D printer** | Additive manufacturing; builds objects layer by layer |

**Printer classification by output unit:** **character printers** (DMP, daisy wheel, inkjet) ·
**line printers** (drum, chain, band) · **page printers** (laser). This three-way split is itself
an examinable classification.

### 7.3 Plotters

**Concept.** A printer thinks in **dots**: it fills a raster grid. A plotter thinks in **lines**:
it is given the coordinates of the endpoints and physically moves a pen from one to the other,
drawing a continuous stroke. That makes a plotter ideal for line drawings at very large sizes —
an architectural plan, a circuit layout, a map — where a raster image would need an impossible
number of dots, and where line quality matters more than filled colour.

| Type | Construction |
|---|---|
| **Drum plotter** | The paper is wrapped round a **rotating drum** that moves it back and forth on one axis; the pen carriage moves left–right on the other axis. Compact for a given paper width; can handle long continuous rolls |
| **Flatbed plotter** | The paper lies **flat and stationary**; the pen moves in **both X and Y** on a gantry. Higher accuracy; the machine must be as large as the paper |
| **Inkjet / electrostatic plotter** | Modern "plotters" are really large-format inkjet printers; faster and can fill colour |
| **Cutting plotter** | The pen is replaced by a **blade** — vinyl signage, stickers, fabric patterns |

| | **Printer** | **Plotter** |
|---|---|---|
| Image built from | **Dots (raster)** | **Continuous lines (vector)** |
| Input | Bitmap / page description | Coordinate pairs / vector commands |
| Strength | Text and photographs | **Line drawings, at very large size** |
| Typical size | A4 / A3 | A1, A0 and larger; rolls |
| Speed | Fast | Slow |
| Applications | Documents, photos | **CAD, engineering drawings, architectural plans, maps, circuit diagrams, banners** |

**Projector** (also examinable as an output device): its components are the **optical system**
(lens, mirrors), the **display/imaging element** (LCD panel, DLP micromirror chip, or three CRT
tubes in older units) and the **light source** (lamp or laser).

### Likely exam questions

- *Differentiate between CRT and LCD monitors.* **[5]**
- *Explain the working of a laser printer.* **[5]** or **[10]**
- *Compare dot matrix, inkjet and laser printers.* **[10]**
- *What is a plotter? How does it differ from a printer? Describe its types.* **[5]**
- *Explain the various output devices of a computer.* **[10]**

### MCQ traps

- **"Which printer produces carbon copies?" → dot matrix**, always, because it is the impact one.
- **DMP speed is in CPS; laser and inkjet in PPM; line printers in LPM.** DPI is *resolution*, not speed.
- **Laser is a page printer**; inkjet and DMP are character printers.
- **A plotter draws lines, a printer prints dots.** If the question mentions engineering drawings or A0 paper, the answer is plotter.
- **An LCD does not emit light**; it modulates a backlight.

---

## 8. Storage devices

### 8.1 The organising idea

You cannot have storage that is simultaneously **fast, large and cheap** — pick two. Fast memory
(SRAM) costs enormously per bit, so you can only afford a little. Cheap storage (disk) is huge
but glacially slow. The engineering answer is not to choose, but to **arrange several technologies
in a hierarchy** and let the fast small ones hold whatever is being used right now.

This works because of the **principle of locality**: programs do not access memory randomly.
They re-use the same variables (**temporal locality**) and walk through neighbouring addresses
(**spatial locality**). So a small fast cache holding the recently-used data captures the great
majority of accesses.

> Deeper treatment of cache organisation, mapping, replacement and virtual memory is in
> **`CORE_02_ComputerOrganization.md`**. What follows is the Diploma-level treatment: the
> device facts, the comparison tables, and the numbers.

### 8.2 The memory hierarchy

```
                              ^  faster, costlier per bit, smaller
                              |
                     /\      +-------------------+
                    /  \     |   REGISTERS       |   < 1 ns,  bytes
                   /----\    +-------------------+
                  /      \   |   L1 CACHE        |   1-2 ns,  32-128 KB
                 /--------\  +-------------------+
                /          \ |   L2 / L3 CACHE   |   3-20 ns, 256 KB - 32 MB
               /------------\+-------------------+
              /              |  MAIN MEMORY(RAM) |   50-100 ns, 4-64 GB
             /--------------\+-------------------+
            /                |  SSD / FLASH      |   25-100 us, 128 GB - 4 TB
           /----------------\+-------------------+
          /                  |  HARD DISK        |   5-15 ms, 500 GB - 20 TB
         /------------------\+-------------------+
        /                    |  OPTICAL / TAPE   |   seconds+, 100 GB - PB
       /--------------------\+-------------------+
                              |
                              v  slower, cheaper per bit, larger
```

| Level | Technology | Typical capacity | Access time | Cost/bit | Managed by | Volatile? |
|---|---|---|---|---|---|---|
| Registers | SRAM cells in the CPU | Tens–hundreds of bytes | **< 1 ns** | Highest | Compiler / CPU | Yes |
| L1 cache | SRAM | 32 – 128 KB | 1 – 2 ns | Very high | Hardware | Yes |
| L2 / L3 cache | SRAM | 256 KB – 32 MB | 3 – 20 ns | High | Hardware | Yes |
| **Main memory** | DRAM | 4 – 64 GB | **50 – 100 ns** | Medium | Operating system | Yes |
| SSD | NAND flash | 128 GB – 4 TB | 25 – 100 µs | Low | OS / file system | **No** |
| **Hard disk** | Magnetic | 500 GB – 20 TB | **5 – 15 ms** | Very low | OS / file system | **No** |
| Optical / tape | Optical / magnetic | 700 MB – PB | Seconds – minutes | Lowest | Operator | **No** |

> **Get the orders of magnitude right, because a favourite question is "how much slower is disk
> than RAM?"** Roughly: RAM ≈ 100 ns, disk ≈ 10 ms. That is a factor of **100,000**. If a
> register access took one second, a disk access would take about four months.

**Effective access time with a cache**, worked:
> h = hit ratio = 0.9, t_cache = 2 ns, t_main = 100 ns.
> EAT = h × t_cache + (1 − h) × (t_cache + t_main) = 0.9(2) + 0.1(102) = 1.8 + 10.2 = **12 ns**.
> (Some textbooks use EAT = h·t_c + (1−h)·t_m = 0.9(2) + 0.1(100) = **11.8 ns**. **State which
> model you are using** — either is accepted if you say so.)

### 8.3 Primary memory — RAM

| | **SRAM** (Static RAM) | **DRAM** (Dynamic RAM) |
|---|---|---|
| Storage cell | A **flip-flop**, typically **6 transistors** | **1 transistor + 1 capacitor** |
| Refresh needed? | **No** — holds its state while powered | **Yes** — the capacitor leaks; refreshed every few milliseconds |
| Speed | **Fast** (1–10 ns) | Slower (50–100 ns) |
| Density (bits per unit area) | Low | **High** |
| Cost per bit | **High** | Low |
| Power consumption | Higher static, no refresh power | Lower static, but refresh consumes power |
| Complexity of controller | Simple | Needs a **refresh circuit** |
| Typical use | **Cache memory**, registers, small buffers | **Main memory** |
| Both are | **Volatile** | **Volatile** |

#### The DRAM family — SDRAM vs DDR, and the DDR generations

**The step that matters.** Early **asynchronous DRAM** responded whenever it could. **SDRAM
(Synchronous DRAM)** synchronised the memory to the system clock, so transfers could be
pipelined and the CPU knew exactly when data would arrive. **DDR (Double Data Rate) SDRAM** then
made one further change: instead of transferring data only on the **rising** edge of the clock,
it transfers on **both the rising and the falling** edges — **two transfers per clock cycle**,
so roughly double the bandwidth at the same clock frequency.

> **⚠️ The classic misconception:** DDR does **not** double the clock speed. It doubles the
> number of transfers per clock. That is exactly what "double data rate" means, and it is the
> answer the examiner wants.

| | **SDR SDRAM** | **DDR SDRAM** |
|---|---|---|
| Full name | Single Data Rate Synchronous DRAM | **Double Data Rate** Synchronous DRAM |
| Transfers per clock cycle | **1** (rising edge only) | **2** (rising **and** falling edges) |
| Bandwidth at the same clock | 1× | **2×** |
| Prefetch buffer | 1 bit | 2 bits (DDR1) |
| Operating voltage | 3.3 V | 2.5 V |
| Module pins (DIMM) | **168** | **184** |
| Notches in the module | **2** | **1** |
| Typical speeds | PC66, PC100, PC133 | DDR-200 to DDR-400 |

| Generation | Prefetch | Voltage | DIMM pins | Typical data rate |
|---|---|---|---|---|
| SDR SDRAM | 1n | 3.3 V | **168** | 66–133 MT/s |
| **DDR** | 2n | 2.5 V | **184** | 200–400 MT/s |
| **DDR2** | 4n | 1.8 V | **240** | 400–1066 MT/s |
| **DDR3** | 8n | 1.5 V | **240** (different notch position from DDR2) | 800–2133 MT/s |
| **DDR4** | 8n | 1.2 V | **288** | 1600–3200 MT/s |
| **DDR5** | 16n | 1.1 V | 288 (different keying) | 4800+ MT/s |

> Each generation **lowers the voltage** and **increases the prefetch depth**. The notch position
> differs in every generation so a module physically cannot be fitted into the wrong slot — a
> nice one-line detail to include in an answer.

**Naming convention worth knowing:** `DDR3-1600` names the **transfer rate in MT/s**;
`PC3-12800` names the **peak bandwidth in MB/s** (1600 MT/s × 8 bytes = 12800 MB/s). Same module,
two names.

#### Other RAM terms

| Term | Meaning |
|---|---|
| **SIMM** | Single Inline Memory Module — contacts on both sides are **electrically identical**; 30-pin or 72-pin; obsolete |
| **DIMM** | **Dual** Inline Memory Module — the two sides are **independent** contacts; 168/184/240/288-pin |
| **SO-DIMM** | Small Outline DIMM — the shorter laptop module (200/204/260 pins) |
| **RDRAM** | Rambus DRAM — a fast, expensive 1990s alternative that lost to DDR |
| **VRAM / GDDR** | Video RAM — dual-ported / high-bandwidth memory on graphics cards |
| **ECC memory** | Error-Correcting Code memory — an extra chip stores parity/Hamming bits, detecting and correcting single-bit errors. Used in servers |

### 8.4 Primary memory — the ROM family

**Concept.** RAM forgets everything when the power goes. But the machine needs *some* code
already present at power-on to know how to start — you cannot load the boot program from disk
using a program that is itself on disk. So there must be non-volatile memory holding firmware.
That is ROM. The whole family history is one question: **how easily can you change what is in
it?**

| Type | Full name | Programmed | Erasable? | Erase method | Granularity | Reprogram cycles | Typical use |
|---|---|---|---|---|---|---|---|
| **Mask ROM** | Read Only Memory | **At manufacture**, by a photographic mask | **No** | — | — | 0 | High-volume fixed firmware; cheapest at scale |
| **PROM** | **Programmable** ROM | **Once, by the user**, in a "PROM burner" that blows fuses/antifuses | **No** | — | — | **1 (OTP)** | Small production runs |
| **EPROM** | **Erasable** PROM | Electrically, in a programmer | **Yes** | **Ultraviolet light** through a **quartz window**, ~20 minutes | **Whole chip** | ~100–1000 | Development firmware; older BIOS |
| **EEPROM** | **Electrically Erasable** PROM | Electrically | **Yes** | **Electrically, in circuit** | **Byte by byte** | 10⁴ – 10⁶ | CMOS settings, config data, smart cards |
| **Flash** | Flash EEPROM | Electrically | **Yes** | Electrically | **Block / sector** | 10⁴ – 10⁵ | **BIOS, SSDs, pen drives, memory cards** |

**All are non-volatile.** The progression is a straight line: harder to change → easier to
change, and correspondingly the BIOS went from unchangeable to field-updatable software.

**NOR vs NAND flash** (one line each, worth a mark): **NOR** flash is byte-addressable and
supports execute-in-place — used for BIOS. **NAND** flash is page-based, denser and cheaper —
used for SSDs, pen drives and memory cards.

### 8.5 Cache memory

| Aspect | Detail |
|---|---|
| What it is | Small, very fast **SRAM** between the CPU and main memory |
| Why | The CPU is ~100× faster than DRAM; without cache it would stall constantly |
| Why it works | **Locality of reference** — temporal (same data re-used soon) and spatial (nearby addresses used soon) |
| Levels | **L1** — smallest and fastest, on the CPU core, usually **split** into instruction (I-cache) and data (D-cache). **L2** — larger, per core. **L3** — largest, shared between cores |
| Hit / miss | A **hit** = the data is in the cache. **Hit ratio** h = hits ÷ total accesses. A well-designed cache achieves h > 0.9 |
| Mapping | Direct-mapped · Fully associative · **Set-associative** (the practical compromise) — see `CORE_02` |
| Write policies | **Write-through** (write to cache and memory together — simple, safe, slower) vs **write-back** (write only to cache, flush later using a *dirty bit* — faster, more complex) |
| Replacement | LRU, FIFO, Random |

### 8.6 Magnetic storage — floppy disks

A **floppy disk** is a thin flexible mylar disk coated with magnetic oxide, spinning inside a
protective jacket at ~300 RPM, written and read by heads that **physically touch** the surface
(hence the wear and the noise). Data is organised in concentric **tracks** divided into
**sectors**, and both surfaces are used.

**Memorise all four capacities — this is one of the most reliably asked facts in the syllabus:**

| Size | Density | **Capacity** | Tracks/side | Sectors/track | Sides |
|---|---|---|---|---|---|
| 5.25″ | Double density (DD) | **360 KB** | 40 | 9 | 2 |
| 5.25″ | High density (HD) | **1.2 MB** | 80 | 15 | 2 |
| 3.5″ | Double density (DD) | **720 KB** | 80 | 9 | 2 |
| **3.5″** | **High density (HD)** | **1.44 MB** | **80** | **18** | **2** |
| 3.5″ | Extra-high density (ED) | 2.88 MB | 80 | 36 | 2 |

> **Verify the 1.44 MB yourself, because the arithmetic is a common 5-mark question:**
> 2 sides × 80 tracks × 18 sectors × 512 bytes = **1,474,560 bytes** = 1440 KB = **1.44 "MB"**
> (using the marketing convention 1 MB = 1000 KB — which is why the number is 1.44 and not 1.41).

**Physical features of a 3.5″ floppy:** rigid plastic shell, sliding metal **shutter** protecting
the media window, central metal **hub** for the drive spindle, and a **write-protect notch** with
a sliding tab — **hole open = write protected**. (On a 5.25″ disk it is the opposite: the notch
must be *open* to write, so covering it with tape write-protects it. ⚠️ Note the reversal.)

**Floppy drive components:** read/write heads (one per side), head-positioning stepper motor,
drive spindle motor, disk-ejection mechanism, index sensor, write-protect sensor, controller
electronics. Connected by a **34-pin ribbon cable**.

### 8.7 Magnetic storage — the hard disk

#### Components and their functions

| Component | Function |
|---|---|
| **Platters** | Rigid **aluminium alloy or glass** discs coated on **both surfaces** with a thin magnetic film. 1–8 per drive. Rigidity is what allows the very close head flying height and hence the high density |
| **Spindle and spindle motor** | Holds and rotates all platters as one unit at a constant **5400 / 7200 / 10 000 / 15 000 RPM** |
| **Read/write heads** | **One per platter surface.** A tiny electromagnet that magnetises a region to write and senses the field to read. Modern drives use a separate **GMR (giant magnetoresistive)** element to read |
| **Air bearing / flying height** | The heads do **not touch** the platter — they **fly** on a cushion of air dragged along by the spinning disk, a few nanometres above it. If a head does touch the surface, that is a **head crash** and it destroys data |
| **Actuator arm assembly** | Carries all the heads; they move **together as one unit**, which is why the cylinder concept exists |
| **Voice-coil actuator** | A magnet-and-coil motor that swings the arm to position the heads. Replaced the older, slower stepper motor |
| **Logic / controller board** | The PCB on the underside: interface electronics, cache buffer, servo control, encoding/decoding |
| **HDA (Head-Disk Assembly)** | The sealed enclosure containing platters, heads and actuator, kept free of dust |
| **Breather filter** | A filtered vent equalising internal and external air pressure. **A hard disk is not a vacuum** — it needs air for the head to fly on |
| **Landing zone / park position** | An unused inner region where the heads rest when powered off |

#### Organisation of data — the four terms

```
   PLATTER (top view)              STACK (side view)  -- the CYLINDER idea
   ______________                   ____________________  <- head 0
  /   ________   \                 |____________________| <- platter 1, head 1
 /   /  ______  \ \                 ____________________  <- head 2
|   |  /  __  \  | |               |____________________| <- platter 2, head 3
|   |  | |  | |  | |                ____________________  <- head 4
|   |  |  \/  |  | |               |____________________| <- platter 3, head 5
 \   \  \____/  / /
  \   \________/ /                  The set of tracks at the SAME radius on
   \____________/                   ALL surfaces = one CYLINDER (a hollow
                                     cylinder cut through the stack).
   Concentric circles = TRACKS
   Pie-slice divisions  = SECTORS   Because all heads move together, reading a
   Track x Sector cell  = one       whole cylinder needs NO head movement --
                          SECTOR    which is why the OS allocates by cylinder.
                          (512 B)
```

| Term | Definition |
|---|---|
| **Track** | One **concentric circle** on one platter surface. Numbered from 0 at the outside edge inwards |
| **Sector** | A pie-slice division of a track — the **smallest physically addressable unit**. Traditionally **512 bytes**; modern "Advanced Format" drives use **4096 bytes**. Each sector has a header (address mark), the data field, and an **ECC** field |
| **Cylinder** | The set of **all tracks of the same number on all surfaces**. Reading a cylinder requires no head movement, so it is the natural allocation unit |
| **Cluster / allocation unit** | The **smallest unit the file system will allocate to a file** — 1, 2, 4, 8 … sectors. A 1-byte file still consumes one whole cluster; the wasted remainder is **slack space** (internal fragmentation) |
| **Head** | One read/write head per surface; head number identifies the surface |
| **CHS addressing** | The legacy Cylinder-Head-Sector scheme; replaced by **LBA (Logical Block Addressing)**, which numbers every sector linearly from 0 |
| **Zone Bit Recording (ZBR)** | Outer tracks are physically longer, so they are given **more sectors** than inner ones. This is why the constant "sectors per track" figure is a simplification, and why sequential transfer is faster at the outside of a modern disk |

#### Capacity and access time — worked

> **Capacity formula:**
> `Capacity = heads × cylinders × sectors per track × bytes per sector`

> **Worked example 1.** A disk has 4 platters (so 8 surfaces/heads), 16383 cylinders, 63 sectors
> per track and 512 bytes per sector. Find the capacity.
> 8 × 16383 × 63 × 512 = **4,227,858,432 bytes ≈ 4.23 GB** (≈ 3.94 GiB).

> **Worked example 2.** A disk has 2 platters, 1024 cylinders, 128 sectors/track, 512 B/sector.
> Surfaces = 2 × 2 = 4.
> Capacity = 4 × 1024 × 128 × 512 = **268,435,456 bytes = 256 MiB = 0.25 GiB.**

> **Access time formula:**
> `Access time = Seek time + Rotational latency + Transfer time`

| Component | What it is | Typical |
|---|---|---|
| **Seek time** | Time for the actuator to move the heads to the right cylinder | 3 – 15 ms (average ≈ 9 ms) |
| **Rotational latency** | Time for the required sector to rotate under the head. **On average, half a revolution** | See below |
| **Transfer time** | Time to read/write the data once positioned | µs per sector |

> **Worked example 3 — rotational latency.** At **7200 RPM**:
> One revolution = 60 / 7200 s = 8.33 ms.
> **Average rotational latency = half of that = 4.17 ms.**
>
> At 5400 RPM: 60/5400 = 11.1 ms → average **5.56 ms.**
> At 15 000 RPM: 60/15000 = 4 ms → average **2 ms.**

> **Worked example 4 — full access time.** Average seek 9 ms, 7200 RPM, transfer rate 100 MB/s,
> reading 4 KB.
> Seek = 9 ms; latency = 4.17 ms; transfer = 4 KB ÷ 100 MB/s ≈ 0.04 ms.
> **Total ≈ 13.2 ms.** Note that **seek and latency dominate completely** — which is why
> sequential access is enormously faster than random access, and why disk scheduling algorithms
> exist.

#### Formatting and disk structure

| Term | Meaning |
|---|---|
| **Low-level format** | Writes the physical sector structure (headers, ECC). Done at the factory on modern drives |
| **Partitioning** | Divides the drive into logical volumes. The **MBR (Master Boot Record)** in sector 0 holds the boot code and the partition table (max 4 primary partitions); **GPT** is the modern replacement |
| **High-level format** | Creates the file system — FAT12/16/32, NTFS, ext4 — writing the boot sector, the allocation tables and the root directory |
| **Boot sector** | The first sector of a partition; holds the volume parameters and the bootstrap code |
| **FAT / MFT** | The map recording which clusters belong to which file |
| **Bad sector** | A sector that fails ECC; the drive remaps it to a spare |
| **Defragmentation** | Rearranging file clusters to be contiguous, reducing seek time. **Useful on HDDs, harmful and unnecessary on SSDs** |

#### Solid State Drives (SSD) — for contrast

| | **HDD** | **SSD** |
|---|---|---|
| Technology | Spinning magnetic platters + moving heads | **NAND flash**, no moving parts |
| Access time | 5–15 ms | **25–100 µs** (~100× faster) |
| Random I/O | Poor (seek dominated) | **Excellent** |
| Shock resistance | Poor | **Excellent** |
| Noise / heat / power | Audible, warm, higher | **Silent, cool, lower** |
| Cost per GB | **Much lower** | Higher |
| Capacity per unit cost | **Higher** | Lower |
| Wear | Mechanical wear | **Limited write cycles per cell** — managed by wear levelling and TRIM |
| Defragmentation | Beneficial | **Never** — it just consumes write cycles |

> **⚠️ 2024 asked "which is *not* a property of an SSD"** with "less reliable" as the odd one
> out. SSDs are **more** reliable in the mechanical sense (no moving parts), though flash cells
> do wear.

### 8.8 Drive interfaces

| Interface | Full name | Devices per channel | Connector | Speed | Notes |
|---|---|---|---|---|---|
| **IDE / ATA / PATA** | Integrated Drive Electronics / (Parallel) AT Attachment | **2 — master and slave**, set by **jumpers** or cable select | **40-pin** ribbon; **80-conductor** cable for UDMA/66+ | ATA-33 to UDMA/133 (up to 133 MB/s) | The controller moved onto the drive itself — hence "integrated". Two channels on a motherboard: **primary and secondary**, so **4 devices total** |
| **SATA** | **Serial** ATA | **1 per port** (point-to-point) | 7-pin thin data cable + 15-pin power | SATA I 1.5 Gb/s, II 3 Gb/s, **III 6 Gb/s** | Thinner cables, better airflow, **hot-swappable**, no jumpers. Superseded PATA entirely |
| **SCSI** | Small Computer System Interface | **7 or 15** devices on one bus, each with a unique **SCSI ID**; the bus must be **terminated** at both ends | 50-pin (SCSI-1), 68-pin (Wide) | 5 – 320 MB/s | Servers and high-end workstations; supports drives, scanners, tape |
| **SAS** | Serial Attached SCSI | Point-to-point, expanders allow many | Like SATA | 3–24 Gb/s | Enterprise successor to SCSI |
| **NVMe** | Non-Volatile Memory express | Over PCIe | M.2 / U.2 | Several GB/s | Modern SSD interface; bypasses the AHCI/SATA bottleneck |
| **USB** | Universal Serial Bus | **127 via hubs** | 4-pin (USB 2.0) | 1.5/12/480 Mb/s, USB 3.0 **5 Gb/s** | External drives; hot-pluggable; **supplies 5 V power** |

> **PATA vs SATA is a guaranteed 5-marker.** Answer with: parallel vs serial transmission,
> ribbon vs thin cable, 40 pins vs 7 pins, master/slave jumpers vs one device per port,
> 133 MB/s vs 600 MB/s, not hot-swappable vs hot-swappable.
>
> **⚠️ 2024 trap:** a question defined "an electronic interface standard that defines the
> connection between a bus on a computer's motherboard and the computer's disk storage devices"
> and offered ATA / SATA / PATA / IDE. The generic, encompassing answer is **ATA**; IDE is its
> common informal name and PATA/SATA are its two forms. If forced, choose **ATA** for the
> generic definition. ⚠️ verify against the official key if you can get it.

### 8.9 Optical storage — CD and DVD

#### Physical structure

A CD is a **1.2 mm polycarbonate disc, 120 mm in diameter**, built up in layers:

```
   label / screen printing
   ------------------------------
   lacquer protective coat
   ------------------------------
   reflective ALUMINIUM layer      <- the pits and lands are moulded here
   ------------------------------
   POLYCARBONATE substrate  1.2 mm
   ------------------------------
        ^   laser reads from BELOW, through the plastic
        |   (so a scratch on the LABEL side is worse than one on the read side --
        |    the reflective layer is right under the label)
```

Data is stored on **one continuous spiral track** running **from the centre outwards** — unlike
a hard disk's concentric circles. The spiral is about **5 km long** on a CD.

#### The read mechanism — how pits and lands become bits

1. A **laser diode** emits a beam; a collimating lens and beam splitter focus it through the
   polycarbonate onto the reflective layer.
2. The track consists of **pits** (depressions) and **lands** (the flat areas between them).
3. A pit is made **one quarter of the laser's wavelength deep**. Light reflecting off a pit
   therefore travels **half a wavelength further** (down and back up) than light off the
   surrounding land, so the two reflections are **180° out of phase and interfere
   destructively** — the reflected intensity drops sharply.
4. A **photodiode** measures the reflected intensity: strong = land, weak = pit.
5. **Crucially: a bit is not "pit = 1, land = 0".** A **transition** from pit to land or land to
   pit represents a **1**; no transition represents a **0**. The encoding is **EFM
   (Eight-to-Fourteen Modulation)**, which guarantees a minimum and maximum run length so the
   drive can recover the clock.
6. The drive uses **CLV (Constant Linear Velocity)** for audio — spinning slower as the head
   moves outwards so the track passes at a constant speed — or CAV for data drives.

#### The write mechanisms

| Media | Recording layer | How it is written | Rewritable? |
|---|---|---|---|
| **CD-ROM** | Aluminium, **physically stamped** from a glass master at manufacture | Not written by the user | No |
| **CD-R** | An **organic dye** layer (cyanine, phthalocyanine, azo) | A **high-power laser burns/darkens** the dye at chosen points, creating permanently low-reflectivity spots that mimic pits | **No — write once (WORM)** |
| **CD-RW** | A **phase-change alloy** (Ag-In-Sb-Te) | **Three laser powers.** Write: heat above the melting point (~600 °C) then cool fast → **amorphous**, non-reflective (a "pit"). Erase: heat to ~200 °C and cool slowly → **crystalline**, reflective (a "land"). Read: low power, no change | **Yes**, ~1000 cycles |
| **DVD-RAM** | Phase change, with embedded sector servo | Same principle, random access | Yes, ~100 000 cycles |

#### CD vs DVD vs Blu-ray

**The one sentence that explains the whole progression:** *a shorter laser wavelength can be
focused to a smaller spot, so pits can be made smaller and packed closer, so more data fits on
the same-sized disc.*

| Feature | **CD** | **DVD** | **Blu-ray** |
|---|---|---|---|
| Laser wavelength | **780 nm** (infra-red) | **650 nm** (red) | **405 nm** (blue-violet) |
| Numerical aperture | 0.45 | 0.60 | 0.85 |
| **Track pitch** | 1.6 µm | 0.74 µm | 0.32 µm |
| Minimum pit length | 0.83 µm | 0.40 µm | 0.15 µm |
| **Capacity, single layer** | **650 – 700 MB** | **4.7 GB** | **25 GB** |
| Dual layer | — | **8.5 GB** | 50 GB |
| Double-sided dual-layer | — | 17 GB | — |
| **1× data rate** | **150 KB/s** | **1.38 MB/s** | 4.5 MB/s |
| Layer depth from surface | 1.2 mm | 0.6 mm | 0.1 mm |
| Diameter / thickness | 120 mm / 1.2 mm | 120 mm / 1.2 mm (two 0.6 mm halves bonded) | 120 mm / 1.2 mm |

> **The 1× speed figures matter.** A "52×" CD drive reads at 52 × 150 KB/s ≈ **7.8 MB/s**. A
> "16×" DVD drive reads at 16 × 1.38 ≈ **22 MB/s**. Note that **1× is not the same speed for CD
> and DVD** — a common trap.

**DVD variants:** DVD-ROM, DVD-R and DVD+R (write once, two competing standards), DVD-RW and
DVD+RW (rewritable), DVD-RAM (random access, cartridge). **DVD-5** = 4.7 GB single-sided single-
layer; **DVD-9** = 8.5 GB single-sided dual-layer; **DVD-10** = 9.4 GB double-sided;
**DVD-18** = 17 GB double-sided dual-layer.

> **⚠️ 2024 asked a capacity-matching question** whose key gave **CD ≈ 640 MB**, **DVD 4.7 GB**,
> **floppy 1.4 MB** and **Blu-ray ≈ 4× a DVD**. Note that "CD = 640 MB" and "CD = 700 MB" are
> both used in textbooks (640/650 MB is the 74-minute disc, 700 MB the 80-minute one). Read the
> options and pick the closest offered.

### 8.10 Other storage

| Device | Notes |
|---|---|
| **Magnetic tape** | **Sequential access only**; very cheap per GB; huge capacity (LTO-9 = 18 TB native); used for **archival backup**. Access time in seconds or minutes |
| **Pen drive / USB flash drive** | NAND flash + USB controller; 4 GB – 2 TB; hot-pluggable |
| **Memory cards** | SD, microSD, CF; NAND flash; cameras and phones |
| **Zip disk** | 100/250/750 MB removable magnetic cartridge; a 1990s floppy replacement; obsolete |
| **Cloud storage** | Remote storage accessed over a network; no local device |

### Likely exam questions

- *Differentiate between SRAM and DRAM.* **[5]**
- *Differentiate between SDRAM and DDR RAM.* **[5]**
- *Explain the terms track, sector, cylinder and cluster.* **[5]**
- *Compare cache, primary and secondary memory with respect to capacity and speed.* **[5]**
- *Explain the ROM family: ROM, PROM, EPROM, EEPROM and Flash.* **[10]**
- *Describe the components of a hard disk and the organisation of data on it.* **[10]**
- *Explain the read and write mechanism of a CD and a DVD.* **[10]**
- *Explain the various storage devices, classifying them and comparing capacity, speed and cost.* **[15]**

### MCQ traps

- **EPROM = UV erase, whole chip. EEPROM = electrical erase, byte by byte.** The single "E" difference is the whole question.
- **DDR = two transfers per clock, not double the clock.**
- **Cluster ≠ sector.** The disk is formatted into sectors; the file system allocates clusters.
- **3.5″ HD floppy = 1.44 MB.** Not 1.2 MB (that is the 5.25″ HD).
- **CD 1× = 150 KB/s but DVD 1× = 1.38 MB/s.**
- **Blu-ray uses a 405 nm blue-violet laser** — shorter wavelength, higher capacity.
- **ROM is non-volatile; cache and all RAM are volatile.**
- **A hard disk is sealed but not evacuated** — it needs air for the heads to fly on.

---

## 9. Components of the motherboard

> **This is the highest-value section in the file.** It is a near-certain 15-mark question, a
> reliable source of 8–12 MCQs, and the material you are least likely to already know.
> Read it twice and draw the diagram three times.

### 9.1 What the motherboard is, and the one idea behind its layout

The **motherboard** (also **mainboard**, **system board**, or **planar board**) is the main
printed circuit board that **integrates all of the PC's primary system components on a single
board** and provides the electrical pathways — the **buses** — over which they communicate.

The classic design has one organising principle, and if you understand it you can reconstruct
the whole diagram from memory:

> **Fast things go near the CPU; slow things go far from it.**

The chipset is therefore split into two halves:

- The **Northbridge**, or **Memory Controller Hub (MCH)**, handles the things that must be
  fast — the **CPU, the RAM and the graphics card**. It sits physically close to the CPU socket
  (which is why it is "north" on a diagram drawn with the CPU at the top) and usually has its
  own heatsink because it runs hot.
- The **Southbridge**, or **I/O Controller Hub (ICH)**, handles everything slower — **disks,
  PCI slots, USB, serial and parallel ports, keyboard, mouse, audio, BIOS**. It sits further
  down the board and connects to the Northbridge by an internal link.

Everything else on the board hangs off one of those two hubs.

> **Modern note (worth one closing line in an answer, no more):** since about 2008 the memory
> controller and the graphics link have migrated **onto the CPU die itself**, leaving a single
> chipset chip called the **PCH (Platform Controller Hub)**. **The Diploma syllabus explicitly
> names the MCH and the ICH, so answer the two-chip model as the main body of your answer** and
> add the modern note at the end to show awareness.

### 9.2 The diagram — described precisely enough to hand-draw

```
 +==========================================================================+
 |  [ATX 24-pin SMPS connector]                        [4/8-pin +12V CPU]   |
 |                                                                          |
 |     +----------------+                    | | | |  <- DIMM SLOTS        |
 |     |   PROCESSOR    |                    | | | |     (2 to 4, long,    |
 |     |     SOCKET     |<====== memory bus ==| | | |      keyed by notch) |
 |     |  (ZIF, LGA/PGA)|                    | | | |                       |
 |     |   + heatsink   |                                                   |
 |     |     mounts     |                                                   |
 |     +-------+--------+                                                   |
 |             ||  FSB / SYSTEM BUS                                         |
 |             ||                                                           |
 |     +-------vv-------+                                                   |
 |     |  NORTHBRIDGE   |========> [ AGP  /  PCI-Express x16 slot ]         |
 |     |   = MCH        |            (graphics card goes here)              |
 |     | Memory Ctrl Hub|                                                   |
 |     |  (has heatsink)|                                                   |
 |     +-------+--------+                                                   |
 |             ||  internal link (hub interface / DMI)                      |
 |             ||                                                           |
 |     +-------vv-------+-----> [ Primary IDE   40-pin ]                    |
 |     |  SOUTHBRIDGE   |-----> [ Secondary IDE 40-pin ]                    |
 |     |   = ICH        |-----> [ SATA ports x4-6 ]                         |
 |     | I/O Ctrl Hub   |-----> [ Floppy connector  34-pin ]                |
 |     |                |-----> [ USB headers ]                             |
 |     +--+---+------+--+-----> [ front-panel header: power, reset, LEDs ]  |
 |        |   |      |                                                      |
 |        |   |      +--> [BIOS ROM chip]  [CMOS CR2032 battery]  [RTC xtal]|
 |        |   |                                                             |
 |        |   +---------> [ SUPER I/O chip ] --> back panel:                |
 |        |                                      PS/2 keyboard (PURPLE)     |
 |        |                                      PS/2 mouse    (GREEN)      |
 |        |                                      Serial DB-9  (COM1/COM2)   |
 |        |                                      Parallel DB-25 (LPT1)      |
 |        |                                                                 |
 |        +-------------> [ PCI slot ] [ PCI slot ] [ PCI slot ]            |
 |                                                                          |
 |   [CMOS clear jumper]   [VRM capacitors near socket]  [mounting holes]   |
 +==========================================================================+
```

**How to draw it in the exam, in order:**
1. Draw a large rectangle for the board. Add four small circles for **mounting holes**.
2. **Top-left:** a square for the **processor socket**, labelled "ZIF socket / LGA".
3. **Top-right of the socket:** 2–4 long thin parallel rectangles = **DIMM slots**. Note the
   little notch.
4. **Top edge:** a wide connector = **ATX 24-pin SMPS**; near the socket a small one = **4-pin
   +12 V**.
5. **Below the socket:** a square labelled **Northbridge / MCH**, with a small heatsink drawn on
   it. Join it to the socket with a thick double line labelled **FSB / system bus**, to the DIMMs
   with a line labelled **memory bus**, and to a slot on the right labelled **AGP / PCIe x16**.
6. **Below that:** a square labelled **Southbridge / ICH**, joined to the Northbridge.
7. **From the Southbridge**, draw lines to: **Primary IDE (40-pin)**, **Secondary IDE (40-pin)**,
   **SATA ports**, **floppy connector (34-pin)**, a row of **PCI slots** on the left, and the
   **Super I/O chip** which in turn feeds the back-panel **PS/2, serial and parallel** ports.
8. Add the three small items near the Southbridge: **BIOS ROM chip**, **CMOS battery (round)**,
   and the **RTC crystal**.
9. Label the whole thing and add a legend for the buses.

**Label everything.** In a hand-marked paper, a well-labelled diagram scores faster than three
paragraphs of prose.

### 9.3 The Memory Controller Hub (Northbridge) and what hangs off it

#### (a) System bus / Front Side Bus (FSB)

**Concept.** A **bus** is a shared set of parallel wires connecting components. Every bus has
three functional parts:

| Sub-bus | Direction | Carries | Determines |
|---|---|---|---|
| **Address bus** | **Unidirectional** (CPU → memory/IO) | The address to be accessed | **How much memory can be addressed** — n address lines → 2ⁿ locations |
| **Data bus** | **Bidirectional** | The actual data | **Word size / how much data moves at once** |
| **Control bus** | Bidirectional | Read/Write, clock, interrupt, reset, bus request/grant signals | Timing and coordination |

> **Worked:** a CPU with a **20-bit address bus** can address 2²⁰ = **1 MB**. With **32 bits**,
> 2³² = **4 GB** — which is exactly why 32-bit systems cannot use more than 4 GB of RAM. That
> one sentence is worth a mark in any bus question.

The **FSB (Front Side Bus)** is the bus between the CPU and the Northbridge; its speed (e.g.
533/800/1066/1333 MHz) was a headline specification of Pentium-era systems. Related buses to
name: the **memory bus** (Northbridge ↔ RAM), the **backside bus** (CPU ↔ L2 cache),
**expansion buses** (PCI, AGP, PCIe, ISA, USB, SCSI), and the **local bus** (a fast bus running
at or near CPU speed, e.g. VESA local bus, PCI).

**Bus bandwidth** = bus width (bytes) × bus clock (MHz) × transfers per clock.
> Worked: a 64-bit (8-byte) FSB at 200 MHz with quad pumping = 8 × 200 × 4 = **6400 MB/s**
> ("FSB 800").

#### (b) Processor socket

| Aspect | Detail |
|---|---|
| Purpose | Holds the CPU and connects it electrically to the board |
| **ZIF** | **Zero Insertion Force** — a lever lifts to release all contacts so the chip drops in without pressing pins. Prevents bent pins |
| **PGA** | **Pin Grid Array** — pins on the **processor**, holes in the socket (AMD's approach) |
| **LGA** | **Land Grid Array** — flat **pads on the processor**, **pins in the socket** (Intel's modern approach) |
| Named examples | Socket 7, Socket 370, Socket A (462), **Socket 478**, **LGA 775**, LGA 1155, LGA 1200, LGA 1700, AM4, AM5 |
| Around the socket | **Heatsink/fan retention holes or bracket**, the **VRM** (Voltage Regulator Module — capacitors and MOSFETs that step the 12 V supply down to the ~1 V the core needs), the CPU fan header, and thermal-sensor traces |
| Key rule | A motherboard supports **exactly one socket type** — CPU and board must match. **One CPU per socket** |

#### (c) DIMM slots

| Aspect | Detail |
|---|---|
| Name | **Dual Inline Memory Module** slot — the RAM slot |
| Why "dual inline" | Contacts on the two faces of the module are **electrically independent** (on the older **SIMM** they were tied together) |
| Pin counts | **168** (SDRAM) · **184** (DDR) · **240** (DDR2 and DDR3, different notch positions) · **288** (DDR4/DDR5) |
| Keying | A **notch** in a generation-specific position physically prevents inserting the wrong module type |
| Retention | Plastic clips at each end snap over the module's side notches |
| Count | Typically 2 or 4 slots, often colour-coded in pairs |
| **Dual channel** | Populating matched modules in the **same-coloured pair** of slots lets the memory controller access two modules simultaneously, roughly doubling bandwidth |
| Laptop version | **SO-DIMM** — physically shorter |

#### (d) AGP — Accelerated Graphics Port

| Aspect | Detail |
|---|---|
| Purpose | A **dedicated, point-to-point port for the graphics card only** — created because 3-D graphics were saturating the shared PCI bus |
| Base spec | 32-bit wide, 66 MHz → 266 MB/s at 1× |
| Speeds | **1× = 266 MB/s · 2× = 533 MB/s · 4× = 1066 MB/s · 8× = 2133 MB/s** |
| Voltages | 3.3 V (AGP 1×/2×), 1.5 V (4×), 0.8 V (8×) — keyed slots prevent damage |
| Key feature | **DIME / GART** — Direct Memory Execute: the card can read textures directly out of system RAM rather than copying them to video RAM first |
| Position | A single slot, usually **brown/dark**, set slightly back from the PCI slots, connected **directly to the Northbridge** |
| Superseded by | **PCI Express x16** (2004 onward) — serial, point-to-point lanes, 4 GB/s each way at PCIe 1.0 x16 |

**AGP vs PCI, the short comparison:** AGP is **point-to-point and dedicated**; PCI is a **shared
bus**. AGP is **twice the clock** (66 vs 33 MHz) and supports **pipelining and sideband
addressing**. AGP connects to the **Northbridge**; PCI hangs off the **Southbridge**.

### 9.4 The I/O Controller Hub (Southbridge) and what hangs off it

#### (a) Primary and secondary IDE channels

| Aspect | Detail |
|---|---|
| Connector | **40-pin** male header on the board, two of them: **primary** and **secondary** |
| Cable | 40-conductor ribbon (older) or **80-conductor** ribbon for UDMA/66 and faster — the extra 40 wires are **grounds interleaved between signal wires to reduce crosstalk**. **The connector still has 40 pins** |
| Devices | **Two per channel: one master, one slave**, selected by a **jumper** on the drive or by *cable select* |
| Total | 2 channels × 2 devices = **4 IDE devices** per motherboard |
| Convention | The **boot hard disk** goes as **master on the primary channel**; the optical drive typically as master on the secondary |
| Pin 1 | Marked by a **red/coloured stripe** on the cable, aligned with pin 1 on the connector |
| Also called | PATA, ATA, ATAPI (the extension that lets CD/DVD drives use the same interface) |

#### (b) PCI — Peripheral Component Interconnect

| Aspect | Detail |
|---|---|
| Introduced | Intel, **1992**, replacing ISA and VESA local bus |
| Width and clock | **32-bit at 33 MHz** (also 64-bit and 66 MHz variants) |
| **Bandwidth** | **133 MB/s** (32 × 33 ÷ 8) |
| Type | A **shared, parallel bus** — all cards share the bandwidth |
| Voltage | 5 V / 3.3 V / universal, distinguished by slot keying |
| Key feature | **Plug and Play** — cards are auto-configured by the BIOS/OS; no manual IRQ and DMA jumpers as with ISA |
| **Bus mastering** | A card can take control of the bus and transfer directly to memory without the CPU |
| Physical | Usually **white/cream** slots, several in a row |
| Typical cards | Sound cards, NICs, modems, SCSI adapters, TV tuners, USB expansion |
| Successor | **PCI Express** — a **serial, point-to-point** interconnect of independent **lanes** (x1, x4, x8, x16), each lane 250 MB/s each way at PCIe 1.0, doubling with each generation. Not a bus at all despite the name |

**Older bus for contrast:** **ISA (Industry Standard Architecture)** — 8-bit/16-bit, 8 MHz,
8 MB/s, black slots, manual jumper configuration. Named in some syllabi; know the one line.

#### (c) Serial ports

| Aspect | Detail |
|---|---|
| Also called | **COM port**, **RS-232** port |
| Connector | **DB-9 male** on the PC's back panel (older equipment used DB-25) |
| Transmission | **One bit at a time** over a single data line, with start, data, parity and stop bits framing each character |
| Speed | 300 bps to 115.2 kbps |
| Distance | **Up to ~15 m** — better than parallel, because fewer wires means less crosstalk |
| Names | COM1, COM2, COM3, COM4 |
| Controlled by | The **UART** (Universal Asynchronous Receiver/Transmitter) inside the Super I/O chip |
| Devices | Mouse (legacy), external modem, serial printer, UPS, network/router console, industrial instruments, GPS |

#### (d) Parallel port

| Aspect | Detail |
|---|---|
| Also called | **LPT port**, **Centronics** port, printer port |
| Connector | **DB-25 female** on the PC (the printer end is a 36-pin Centronics) |
| Transmission | **8 bits (one byte) simultaneously** over 8 parallel data lines |
| Speed | 150 KB/s (SPP) up to 2 MB/s (ECP) |
| Distance | **Limited to ~3–5 m** — crosstalk and skew between the parallel wires |
| Modes | **SPP** (Standard, unidirectional), **EPP** (Enhanced, bidirectional, for non-printers), **ECP** (Extended Capability, bidirectional with DMA) |
| Names | LPT1, LPT2 |
| Devices | Printers, scanners, Zip drives, dongles |

> **Serial vs parallel — the classic comparison, and the counter-intuitive punchline.**
>
> | | Serial | Parallel |
> |---|---|---|
> | Bits at a time | 1 | 8 |
> | Wires | Few | Many |
> | Connector | DB-9 | DB-25 |
> | Max cable length | **~15 m** | ~3–5 m |
> | Speed | Slower per clock | Faster per clock |
> | Cost | Cheaper | Costlier |
>
> **Parallel sounds obviously faster — so why is every modern high-speed interface (SATA, USB,
> PCIe, HDMI) serial?** Because at high frequencies the bits on parallel wires arrive at
> slightly different times (**skew**) and interfere with each other (**crosstalk**), and both
> problems get worse with speed and length. A single serial line can be clocked far higher than
> a parallel bundle can be kept in step. **That is the insight the examiner is looking for if
> the question asks "why has serial replaced parallel".**

#### (e) PS/2 ports

| Aspect | Detail |
|---|---|
| Origin | IBM **Personal System/2**, 1987 |
| Connector | **6-pin mini-DIN**, round |
| **Colour code** | **PURPLE = keyboard · GREEN = mouse** — memorise this, it is asked |
| Signals | Clock, Data, +5 V, Ground, and two unused pins |
| Protocol | Bidirectional synchronous serial |
| Interrupts | Keyboard **IRQ 1**, mouse **IRQ 12** |
| **Not hot-pluggable** | Connecting one with the PC on can fail to detect it or damage the port — plug in before booting |
| Status | Superseded by USB, but persists on some boards (and is preferred by some gamers for its interrupt-driven, N-key-rollover behaviour) |

#### (f) USB — Universal Serial Bus

| Aspect | Detail |
|---|---|
| Purpose | One standard connector to replace serial, parallel, PS/2 and game ports |
| Topology | **Tiered star**, with hubs. **Up to 127 devices**, maximum **5 tiers** |
| Connector | **4 pins** for USB 1.1/2.0: **VBUS (+5 V), D−, D+, GND**. USB 3.0 adds 5 more (9 total) |
| **Speeds** | USB 1.1 **Low Speed 1.5 Mbps / Full Speed 12 Mbps** · USB 2.0 **High Speed 480 Mbps** · USB 3.0 **SuperSpeed 5 Gbps** · USB 3.1 10 Gbps · USB 3.2 20 Gbps · USB4 40 Gbps |
| **Power** | Supplies **5 V**, 500 mA (USB 2.0) / 900 mA (USB 3.0); USB-C Power Delivery up to 100 W+ |
| Cable length | Max **5 m** per segment (USB 2.0) |
| **Hot-pluggable** | **Yes** — connect and disconnect with the system running |
| **Plug and play** | Devices are enumerated and drivers loaded automatically |
| Connector types | Type-A (host), Type-B (device), Mini, Micro, **Type-C** (reversible) |
| Colour convention | Black/white = USB 2.0, **blue = USB 3.0**, teal = 3.1, yellow/red = always-on charging |

### 9.5 BIOS ROM

| Aspect | Detail |
|---|---|
| Full name | **Basic Input Output System** |
| What it is | **Firmware** — permanent software stored in a **ROM/flash chip** on the motherboard. "As permanent as hardware, stored in ROM" is the textbook definition of firmware |
| **Functions** | 1. **POST** — Power-On Self Test of CPU, memory, keyboard, video, drives · 2. **Initialise and identify** hardware · 3. **Bootstrap** — find the boot device and load its boot sector · 4. Provide **low-level I/O service routines** (interrupt handlers) that the OS can call · 5. Hold the **CMOS Setup utility** |
| Entering setup | Del, F2, F10, F12 or Esc at power-on, depending on the vendor |
| Settings it holds | Boot order, date/time, drive configuration, CPU/RAM parameters, passwords, enabling/disabling on-board devices |
| Vendors | AMI, Award, Phoenix, Insyde |
| Flashing | Because the chip is **flash EEPROM**, the BIOS can be **updated in software**. A failed flash can brick the board — hence dual-BIOS boards |
| **Successor** | **UEFI** (Unified Extensible Firmware Interface) — GUI setup, mouse support, GPT disks over 2 TB, faster boot, **Secure Boot** |

#### POST beep codes — memorise the pattern, not every vendor's table

The BIOS signals POST failures with beeps because the video card may not yet be working.

| Pattern | Usual meaning |
|---|---|
| **1 short beep** | POST successful — the normal, healthy beep |
| No beep at all | Power supply, motherboard, or speaker fault |
| **Continuous beep** | **Power supply, motherboard, or RAM fault** |
| **Continuous short beeps** | **Power supply or system-board (motherboard) failure** |
| Repeating long beeps | **Memory (RAM) problem** — reseat the modules |
| 1 long + 2 short / 1 long + 3 short | **Video card / display adapter error** |
| 3 short beeps | Memory error (AMI) |
| 5 short beeps | Processor error |
| 8 short beeps | Video memory error |

> ⚠️ **Beep codes differ between AMI, Award and Phoenix BIOSes.** If a question asks for an
> exact code, answer with the pattern above and note the vendor dependence. The one you can
> rely on is **one short beep = all is well**.

#### The BIOS boot sequence — get the order right

The examiner's favourite ordering question. The sequence is:

1. **Power on** → SMPS stabilises and asserts the **Power Good** signal.
2. **CPU reset** — the processor jumps to the BIOS entry point at address `FFFF:0000`.
3. **BIOS start-up / initialisation.**
4. **POST** — the self test.
5. **System check** — detect and initialise devices; display the BIOS screen.
6. Read the **boot order** from CMOS.
7. Load the **boot sector (512 bytes)** of the first bootable device to memory at `0000:7C00`.
8. Transfer control to the bootstrap loader, which loads the operating system.
9. The OS takes over.

### 9.6 CMOS battery

| Aspect | Detail |
|---|---|
| What CMOS is | A small block of **volatile CMOS SRAM** (traditionally 64 or 128 bytes) inside the Southbridge/RTC chip, holding the **BIOS settings** |
| Why a battery | The settings and the clock must survive with the PSU switched off, so they need standby power |
| The cell | **CR2032, 3 V lithium coin cell** — the number encodes 20 mm diameter, 3.2 mm thick |
| Life | **3–10 years** |
| **Symptoms of failure** | **Date and time reset at every power-off** · "CMOS checksum error" / "CMOS battery low" at boot · **BIOS settings revert to defaults** (boot order, drive settings) · the machine may refuse to boot from the right device. **It does NOT erase the hard disk or the RAM** |
| CMOS clear | A **3-pin jumper** near the battery, or removing the cell for a few minutes, resets the BIOS to defaults — the standard way to clear a forgotten BIOS password |
| **Key distinction** | **BIOS = the program, in non-volatile ROM. CMOS = the settings, in volatile RAM kept alive by the battery.** This distinction is very commonly examined |

### 9.7 Real Time Clock (RTC)

| Aspect | Detail |
|---|---|
| Function | Keeps the **date and time running continuously**, independent of whether the computer is on or which OS is installed |
| Implementation | A counter chip integrated into the Southbridge (historically the **Motorola MC146818**), sharing the CMOS RAM and the battery |
| **Crystal** | Driven by a **32.768 kHz quartz crystal** — chosen because **32,768 = 2¹⁵**, so a simple 15-stage binary divider produces an exact 1 Hz pulse. **Learn this number and the reason; it makes a neat exam point** |
| Powered by | The **CMOS battery** when the PSU is off |
| Provides | Time of day, calendar date, and a periodic interrupt (**IRQ 8**) usable for alarms and OS timing |
| Related but different | The **system clock generator** — a separate, much higher-frequency crystal (typically 14.318 MHz) whose output is multiplied by a PLL to produce the CPU, FSB and bus clocks. **Do not confuse the RTC (timekeeping) with the system clock (timing/synchronisation).** A frequent trap |

### 9.8 SMPS connector

| Aspect | Detail |
|---|---|
| SMPS | **Switched Mode Power Supply** — converts 230 V AC mains into the low-voltage DC rails the PC needs, by rectifying, then switching at high frequency through a small transformer, then rectifying and filtering again. **High-frequency switching is why the transformer can be small and the efficiency high** (~80–90%) |
| **Functions of a PSU** | **Rectification** (AC → DC) · **Filtering** (smoothing ripple) · **Voltage regulation** (holding rails steady under changing load) · **Transformation/stepping down** · Protection (over-voltage, over-current, short circuit). **Cooling is done *by* its fan but is not a power-conversion function** — 2024 used "cooling" as the odd one out |
| **Main connector** | **ATX 20-pin**, extended to **24-pin** in ATX12V 2.0 (the extra 4 pins add more +12 V, +5 V and +3.3 V for PCIe). Keyed and clipped so it cannot go in backwards |
| **CPU connector** | **4-pin (ATX12V) or 8-pin (EPS12V)** +12 V connector near the CPU socket, feeding the VRM |
| Other connectors | **PCIe 6-pin / 8-pin** for graphics cards · **SATA power** 15-pin flat · **Molex 4-pin** for older drives and fans · **4-pin Berg** for floppy drives |
| **Rails** | **+3.3 V** (chipset, RAM, some logic) · **+5 V** (logic, USB, older drives) · **+12 V** (CPU VRM, motors, fans, graphics) · **−12 V** (legacy serial ports) · **+5 VSB** (**5 V standby** — always live while the mains is connected; powers Wake-on-LAN and the power button) |
| **PS_ON** | A green wire pulled low by the power button to switch the supply on — this is why an ATX machine can be **switched off by software** ("It is now safe to turn off your computer" belonged to the older AT standard, which could not) |
| **Power Good (PWR_OK)** | A grey signal the PSU asserts once all rails are stable; the chipset holds the CPU in reset until it appears. Without it the machine will not start |
| Form factors | AT (obsolete, split P8/P9 connectors) · **ATX** · micro-ATX · SFX · TFX |
| Rating | Quoted in watts (300 W – 1200 W+); efficiency certified by **80 PLUS** grades |

### 9.9 Other motherboard items worth naming

| Item | Function |
|---|---|
| **Form factor** | Defines the board's **size, shape, mounting-hole positions and connector layout** so it fits a standard case: **AT, ATX (305 × 244 mm), micro-ATX (244 × 244), mini-ITX (170 × 170), BTX, E-ATX**. Asked directly in 2024 |
| **Chipset** | The MCH + ICH pair (or modern PCH) — determines which CPUs, how much and what type of RAM, and which buses the board supports |
| **Super I/O chip** | A single chip providing the legacy **serial UARTs, parallel port, floppy controller, PS/2 ports**, plus **hardware monitoring** (temperatures, fan speeds, voltages) |
| **Built-in controllers** | DMA controller, **interrupt controller (PIC/APIC)**, **programmable interval timer**, memory controller, keyboard controller, **RTC**. (A **PCB** is the board itself, not a controller — 2024's odd-one-out) |
| **Expansion slots** | PCI, PCIe x1/x4/x8/x16, AGP, ISA (legacy) |
| **CMOS jumper** | Clears BIOS settings/password |
| **Front panel header** | Power switch, reset switch, power LED, HDD activity LED, internal speaker, front USB and audio |
| **Fan headers** | 3-pin or 4-pin (PWM) for CPU and case fans |
| **On-board devices** | Integrated audio codec, LAN (NIC), and often integrated graphics |
| **VRM** | Voltage Regulator Module — steps 12 V down to the CPU's core voltage; the bank of capacitors and chokes around the socket |
| **Not on the motherboard** | The **SMPS itself** (it is a separate box; only its *connector* is on the board), the hard disk, the monitor, and the **video display adapter** if it is a separate expansion card. 2024 used both "SMPS" and "VDA" as the odd one out in "which is not a part of the motherboard" |

### Likely exam questions

- *Explain in detail the components of a motherboard, with a labelled diagram.* **[15]**
- *What is a bus? Explain the address, data and control buses.* **[5]**
- *Differentiate between a serial port and a parallel port.* **[5]**
- *What is BIOS? Explain its functions and the boot sequence it performs.* **[10]**
- *Differentiate between the Northbridge and the Southbridge.* **[5]**
- *What is the function of the CMOS battery and the real-time clock?* **[5]**
- *Explain the functions of an SMPS and the connectors it provides.* **[10]**
- *Compare AGP, PCI and PCI Express.* **[10]**

### MCQ traps

- **Northbridge = MCH = memory, CPU, graphics. Southbridge = ICH = disks, PCI, USB, ports.** If the question mentions *cache, main memory or the PCI bus controller*, the answer is **north bridge**.
- **Floppy = 34 pins, IDE = 40 pins, SCSI-1 = 50 pins, ATX main = 20/24 pins.** Four numbers.
- **80-conductor cable, 40-pin connector.** Both numbers are correct simultaneously.
- **PS/2: purple keyboard, green mouse.**
- **CMOS battery failure loses the *settings and clock*, not your data.**
- **BIOS ≠ CMOS.** Program vs settings.
- **RTC crystal = 32.768 kHz**, not the system clock frequency.
- **The SMPS is not a motherboard component** — only its connector is.
- **A serial cable can be longer than a parallel one**, despite parallel being "faster".

---

## 10. Numbers you must memorise

Cover the right column. Recite. Repeat daily from 20 September.

### Data representation

| Fact | Value |
|---|---|
| Bit / nibble / byte | 1 / **4** / 8 bits |
| Word length | 16, 32 or 64 bits (machine dependent) |
| 1 KB / MB / GB / TB | 2¹⁰ / 2²⁰ / 2³⁰ / 2⁴⁰ bytes |
| ASCII bits / characters | **7 bits / 128** (extended 8 bits / 256) |
| EBCDIC | **8-bit, IBM** |
| Unicode UTF-8 / UTF-16 / UTF-32 | 1–4 bytes / 16 bits (BMP) / 32 bits |
| BCD valid codes | **0000–1001 only**; 1010–1111 invalid |
| ASCII `A` / `a` / `0` / space | **65 / 97 / 48 / 32** |
| 8-bit 2's complement range | **−128 to +127** |
| 8-bit 1's complement range | −127 to +127 |

### Generations

| Fact | Value |
|---|---|
| 1st / 2nd / 3rd / 4th generation technology | Vacuum tube / transistor / IC / **VLSI microprocessor** |
| Transistor invented | **Bell Labs, 1947** |
| First microprocessor | **Intel 4004, 1971** |
| GUI generation | Fourth |

### Storage

| Fact | Value |
|---|---|
| Floppy 5.25″ DD / HD | 360 KB / **1.2 MB** |
| Floppy 3.5″ DD / HD / ED | 720 KB / **1.44 MB** / 2.88 MB |
| 1.44 MB derivation | 2 × 80 × 18 × 512 bytes |
| Hard disk sector | **512 bytes** (Advanced Format 4096) |
| Rotational latency, 5400 / 7200 / 15000 RPM | 5.56 / **4.17** / 2.0 ms |
| Typical average seek time | ~9 ms |
| CD capacity / 1× rate | **650–700 MB / 150 KB/s** |
| DVD SL / DL / DS-DL | **4.7 GB / 8.5 GB / 17 GB** |
| DVD 1× rate | **1.38 MB/s** |
| Blu-ray SL / DL | **25 GB / 50 GB** |
| CD / DVD / BD laser wavelength | **780 / 650 / 405 nm** |
| CD / DVD track pitch | 1.6 µm / 0.74 µm |
| Disc diameter / thickness | 120 mm / 1.2 mm |

### Motherboard, buses and ports

| Fact | Value |
|---|---|
| IDE connector pins / cable conductors | **40 pins / 40 or 80 conductors** |
| IDE devices per channel / per board | **2 (master + slave) / 4** |
| **Floppy connector pins** | **34** |
| SCSI-1 / Wide SCSI pins | 50 / 68 |
| SCSI devices per bus | 7 or 15 |
| SATA data / power pins | 7 / 15 |
| SATA I / II / III speed | 1.5 / 3 / **6 Gbps** |
| Serial port connector | **DB-9 male** (also DB-25) |
| Parallel port connector | **DB-25 female** |
| Serial / parallel max cable | **~15 m / ~3–5 m** |
| PS/2 connector / colours | **6-pin mini-DIN**; **purple = keyboard, green = mouse** |
| PS/2 IRQs | Keyboard 1, mouse 12 |
| USB pins (2.0) / max devices / max cable | **4 / 127 / 5 m** |
| USB 1.1 / 2.0 / 3.0 speeds | 1.5 & 12 Mbps / **480 Mbps** / **5 Gbps** |
| USB supply voltage | **5 V** |
| PCI width / clock / bandwidth | **32-bit / 33 MHz / 133 MB/s** |
| AGP 1× / 2× / 4× / 8× | 266 / 533 / 1066 / 2133 MB/s |
| DIMM pins SDR / DDR / DDR2-3 / DDR4 | **168 / 184 / 240 / 288** |
| ATX main power connector | **20-pin** (24-pin in ATX12V 2.0) |
| CPU auxiliary power connector | 4-pin or 8-pin +12 V |
| PSU rails | +3.3, +5, +12, −12, +5 VSB |
| CMOS battery | **CR2032, 3 V lithium** |
| **RTC crystal** | **32.768 kHz** (= 2¹⁵ Hz) |
| System clock crystal | 14.318 MHz |
| Normal POST result | **One short beep** |
| Continuous short beeps | Power supply / system board failure |
| BIOS entry vector | FFFF:0000 |
| Boot sector load address / size | 0000:7C00 / **512 bytes** |
| ATX board size | 305 × 244 mm |

### Devices

| Fact | Value |
|---|---|
| Keyboard keys | **101 / 104** (older 83/84) |
| **Function keys** | **12 (F1–F12)** |
| Numeric keypad keys | 17 |
| DMP pins | 9 or 24 |
| DMP / inkjet / laser speed units | **CPS / PPM / PPM** |
| Line printer speed unit | LPM |
| Laser fusing temperature | ~200 °C |
| Printer resolution unit | DPI |
| MICR font | **E-13B** |

---

## Where the rest of Paper-I lives

| Paper-I unit | Covered in |
|---|---|
| §1 Introduction to computers | **This file, §1–§5** |
| §2 Input and output devices | **This file, §6–§7** |
| §3 Storage devices | **This file, §8** · deeper: `CORE_02_ComputerOrganization.md` |
| §4 Components of the motherboard | **This file, §9** |
| §5 Computer networks | `CORE_05_ComputerNetworks.md` — **and note that 2024 made this ~25% of Paper-I. Do not skim it** |
| §6 Internet technology | `CSDip_03_SystemAnalysisAndViruses.md` §3 |
| §7 Computer languages | Brief treatment in `CSDip_03` and `CORE_09_Programming_C_CPP.md` |
| §8 Computer software / MS Office | `CSDip_02_MSOffice_and_DOS.md` |
| §9 Computer viruses | `CSDip_03_SystemAnalysisAndViruses.md` §1 |
| Number systems, deeper | `CORE_01_DigitalLogic.md` |
| All drill questions | `CSDip_04_MCQ_and_QuestionBank.md` |

> **A note on the file index.** `CSDip_00_OVERVIEW.md` §9 lists a seven-file plan
> (`CSDip_03_Networks_and_Internet`, `CSDip_04_Languages_and_Software`, `CSDip_05_Viruses`,
> `CSDip_06_SystemAnalysisDesign`). The folder has since been consolidated into **five** files:
> the viruses, System-Analysis-and-Design and Internet-technology material is combined in
> **`CSDip_03_SystemAnalysisAndViruses.md`**, and **`CSDip_04`** is now the **MCQ and question
> bank**. Networks are covered by `CORE_05` with the Diploma-specific angles noted in `CSDip_03`.
> **All the syllabus content is still covered — only the filenames changed.**
