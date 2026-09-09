# CORE 03 — Operating Systems

> **Shared-core file 3 of the NPSC CTSE 2026 prep set.**
> Three depths for every topic: **one-line fact** (MCQ), **5-mark answer** (~5–6 points),
> **10/15-mark answer** (worked explanation + diagram).

---

## 0. Why this matters — where OS appears in your three papers

| Elective | Where | How heavy |
|---|---|---|
| **Computer Forensic** | TP-I §8 — a full numbered unit: "Main functions of Operating Systems. Multi Programming, multiprocessing, and multitasking. Memory Management: Virtual memory, paging, fragmentation. Concurrent Processing: Mutual exclusion, Critical regions, lock and unlock. Scheduling: CPU scheduling, I/O scheduling, Resource scheduling, Deadlock and scheduling algorithms. Disk Management — formatting, boot block, disk free space management, RAID. Protection and Security: domain, access control, threats — Trojan horse, virus, worms; User authentication." Plus TP-I §4 (booting, file systems). | **Very heavy** |
| **CS Degree** | Paper-II §1 — "Introduction to Operating system, Evolution, Generations, Components & Services, Process Management, Scheduling algorithms, Memory management, I/O management, File system Management, Security & Protection." One of only 7 Paper-II subjects. | **Heavy** |
| **CS Diploma** | Paper-II §1 — "Definition, Functions, Evolution (Sequential, Batch, Multiprogramming, Multiprocessing, Real time, Multitasking). Process concept. CPU scheduling — FCFS, SJF, Priority, Round Robin, Multiprocessor scheduling. Memory management. I/O Systems and Mass Storage Structure." | **Heavy** |

**Read that list of three again.** The *same* sub-topics — scheduling algorithms, memory
management, deadlock, file systems, security — are named explicitly in all three electives.
Operating Systems is, with Networks and DBMS, one of the three biggest returns on study time
in your whole prep. Nothing you learn here is wasted.

**Strategic note on the MCQ paper.** With **negative marking of 1/3**, the numerical parts of
OS (scheduling averages, page-fault counts, disk head movement, Banker's safe sequences) are
gold: you can *compute* them to certainty rather than guess. The descriptive papers are the
mirror image — a 15-mark question is almost always "explain X **and** solve this numerical."
So **work every numerical in this file by hand, on paper, at least twice.** Reading them is
not the same as doing them.

**Time budget suggestion:** 8–10 sessions of 3 hours.
Session 1 — intro, types, process/PCB/threads. Session 2 — scheduling theory + all Gantt
numericals. Session 3 — IPC, critical section, semaphores, classical problems.
Session 4 — deadlock + Banker's. Session 5 — memory management + paging/segmentation
numericals. Session 6 — virtual memory + page replacement numericals. Session 7 — file
systems + disk scheduling numericals + RAID. Session 8 — protection & security.
Sessions 9–10 — full revision, blind numerical drill, past-paper attempt.

---

## Topic checklist

- [ ] 1. What an OS is; the two viewpoints (resource manager / extended machine)
- [ ] 2. Functions and services of an OS; system calls; kernel vs shell; monolithic/layered/microkernel
- [ ] 3. Evolution and generations; serial, batch, multiprogramming, multitasking, multiprocessing, time-sharing, real-time, distributed, clustered, embedded, network OS
- [ ] 4. Process concept; program vs process; the PCB and every field in it
- [ ] 5. **Process state diagram** — five states and all transitions (draw it)
- [ ] 6. Schedulers (long/short/medium term), context switch, dispatcher, degree of multiprogramming
- [ ] 7. Threads; user vs kernel threads; multithreading models; process vs thread table
- [ ] 8. Scheduling criteria and the definitions of WT, TAT, RT
- [ ] 9. **FCFS, SJF, SRTF, Priority (pre/non-pre), Round Robin — all worked with Gantt charts**
- [ ] 10. **Multilevel queue and multilevel feedback queue scheduling**
- [ ] 11. Convoy effect, starvation, ageing, the effect of the RR time quantum
- [ ] 12. IPC — shared memory vs message passing; pipes, sockets, RPC
- [ ] 13. **Critical section problem** and its three requirements; Peterson's solution
- [ ] 14. Hardware support: disabling interrupts, TestAndSet, Swap/Compare-and-Swap
- [ ] 15. **Semaphores** — counting/binary, wait/signal, busy-wait vs block-wakeup
- [ ] 16. **Monitors** and condition variables
- [ ] 17. **Producer–consumer, readers–writers, dining philosophers** — full solutions
- [ ] 18. **Deadlock** — four necessary conditions; RAG; prevention; avoidance
- [ ] 19. **Banker's algorithm — safety algorithm + resource-request algorithm, fully worked**
- [ ] 20. Deadlock detection and recovery; starvation vs deadlock
- [ ] 21. Memory management: logical vs physical address, MMU, relocation, swapping
- [ ] 22. Contiguous allocation: fixed vs variable partitioning; first/best/worst fit
- [ ] 23. **Internal vs external fragmentation; compaction**
- [ ] 24. **Paging** — page table, TLB, EAT calculation, multi-level and inverted page tables
- [ ] 25. **Segmentation** and **segmented paging**
- [ ] 26. Virtual memory, demand paging, page-fault service sequence, EAT with page faults
- [ ] 27. **Page replacement: FIFO, LRU, Optimal, Second-chance — worked fault counts**
- [ ] 28. **Belady's anomaly**; stack algorithms; frame allocation policies
- [ ] 29. **Thrashing** and the **working set model**; page-fault frequency
- [ ] 30. File concept: attributes, operations, types, access methods
- [ ] 31. Directory structures — single-level to acyclic graph
- [ ] 32. **Allocation methods — contiguous, linked, indexed (with FAT and inode)**
- [ ] 33. Free-space management — bit vector, linked list, grouping, counting
- [ ] 34. Disk structure; formatting; boot block; bad blocks
- [ ] 35. **Disk scheduling — FCFS, SSTF, SCAN, C-SCAN, LOOK, C-LOOK with head-movement sums**
- [ ] 36. **RAID levels 0–6** with a comparison table
- [ ] 37. Protection: domains, **access control matrix**, ACL vs capability list
- [ ] 38. Security threats: **Trojan horse, trap door, logic bomb, virus, worm**, buffer overflow
- [ ] 39. User authentication: passwords, biometrics, OTP, two-factor
- [ ] 40. Booting process, BIOS/UEFI, MBR/GPT (forensic relevance)

---
---

# PART A — INTRODUCTION TO OPERATING SYSTEMS

## A1. What an operating system is

### Concept — plain English first

Take the hardware away for a second and imagine writing a program that has to print a line
of text. Without an OS you would have to know which model of printer is attached, what its
control registers are, which interrupt line it uses, how to spin-wait for it, and what to do
if someone else's program is halfway through printing. Every programmer would rewrite that,
badly, for every device. And two programs running at once would trample each other's memory.

The operating system exists to end both problems. It sits between the raw hardware and your
programs and does two things:

1. **It hides the hardware behind a clean, uniform interface** — you say `write(fd, buf, n)`
   and you neither know nor care what device is on the other end. In this role the OS is an
   **extended machine** or **virtual machine**: it presents a nicer machine than the real one.
2. **It arbitrates** — the CPU, memory, disk and devices are finite and shared, so somebody
   has to decide who gets what, when, and for how long, and has to stop programs from
   interfering with each other. In this role the OS is a **resource manager**.

Those two sentences — *extended machine* and *resource manager* — are the standard "two views
of an operating system" and they are worth stating explicitly in any 5-mark definition answer.

### Formal definition

An **operating system** is the system software that acts as an intermediary between the user
and the computer hardware. It manages and allocates the system's resources (processor,
memory, storage, I/O devices), controls the execution of programs, and provides a convenient
and efficient environment in which application programs can run.

### Key points

- The OS is the **one program that is always running** on the machine. That always-resident
  core is the **kernel**; everything else is either a **system program** or an
  **application program**.
- The kernel executes in **kernel mode / supervisor mode / privileged mode** (mode bit = 0);
  user programs execute in **user mode** (mode bit = 1). This **dual-mode operation** is what
  makes protection possible — privileged instructions (I/O, changing the memory-protection
  registers, halting) can only be executed in kernel mode.
- A user program asks for an OS service through a **system call**, which triggers a
  **software interrupt / trap**, switching the CPU into kernel mode.
- The **shell** (command interpreter) is *not* the kernel; it is a user-level program that
  reads commands and asks the kernel to execute them. Examiners test this distinction.
- The OS is **event driven**: it does nothing until an interrupt, trap or system call
  arrives.

### Goals of an operating system

| Goal | Meaning |
|---|---|
| **Convenience** | Make the computer easy to use (primary goal on personal machines) |
| **Efficiency** | Use hardware resources fully — high CPU utilisation, high throughput (primary goal on mainframes/servers) |
| **Ability to evolve** | Allow new devices, services and functions to be added without disrupting service |
| **Protection & security** | Isolate processes and users from one another |
| **Fairness** | Give every process reasonable access to resources |

Convenience and efficiency **conflict**; the design of any particular OS is a chosen
compromise between them. Saying this in an answer earns a mark.

---

## A2. Functions and services of an operating system

### Concept

If the exam asks "state the main functions of an operating system" — and all three of your
electives can ask exactly that — the safest answer is a list organised by **which resource is
being managed**, plus the interface and protection functions. Never give an unstructured
list; group them.

### The six management functions (this is the spine of the answer)

| # | Function | What the OS actually does |
|---|---|---|
| 1 | **Process management** | Create and delete processes; suspend and resume; schedule the CPU; provide mechanisms for synchronisation, communication and deadlock handling |
| 2 | **Main-memory management** | Track which parts of memory are in use and by whom; decide which processes to load when space becomes available; allocate and de-allocate space; provide virtual memory |
| 3 | **File management** | Create/delete files and directories; map files onto secondary storage; provide primitives for manipulation; back up files onto stable storage |
| 4 | **Secondary-storage / disk management** | Free-space management, storage allocation, **disk scheduling** |
| 5 | **I/O device management** | Buffering, caching, spooling; a general device-driver interface; drivers for specific hardware; hide device peculiarities from the user |
| 6 | **Protection and security** | Control access of processes and users to system resources; authenticate users; defend against external and internal attack |

### Plus the service functions

| Service | Meaning |
|---|---|
| **User interface** | CLI (shell), batch interface, GUI, touch interface |
| **Program execution** | Load a program into memory, run it, terminate it normally or abnormally |
| **I/O operations** | Perform I/O on the program's behalf (users cannot access devices directly) |
| **File-system manipulation** | Read, write, create, delete, search, list, manage permissions |
| **Communication** | Between processes on the same machine (shared memory / message passing) or across a network |
| **Error detection** | Detect and handle CPU, memory, device and program errors; take consistent action |
| **Resource allocation** | Allocate CPU cycles, memory, files, I/O to competing users/jobs |
| **Accounting / logging** | Record which user used how much of which resource (billing, statistics, and **forensically, audit trails**) |

> **Forensic angle (for the CF paper).** The accounting/logging function is where OS study
> touches your Computer Forensic elective directly: Windows Event Logs, Linux `/var/log`,
> `wtmp`/`btmp`, and process accounting are all OS services that the investigator later
> harvests as evidence.

### System calls — the interface between the two worlds

A **system call** is the programmatic way a user program requests a service from the kernel.
It is implemented as a **trap** (software interrupt) that switches the CPU into kernel mode,
runs the kernel routine, and returns.

| Category | Examples (UNIX) | Examples (Windows) |
|---|---|---|
| **Process control** | `fork()`, `exec()`, `wait()`, `exit()`, `kill()` | `CreateProcess()`, `ExitProcess()`, `WaitForSingleObject()` |
| **File management** | `open()`, `read()`, `write()`, `close()`, `lseek()` | `CreateFile()`, `ReadFile()`, `WriteFile()`, `CloseHandle()` |
| **Device management** | `ioctl()`, `read()`, `write()` | `SetConsoleMode()`, `ReadConsole()` |
| **Information maintenance** | `getpid()`, `alarm()`, `sleep()`, `time()` | `GetCurrentProcessID()`, `SetTimer()` |
| **Communication** | `pipe()`, `shmget()`, `mmap()`, `socket()` | `CreatePipe()`, `MapViewOfFile()` |
| **Protection** | `chmod()`, `umask()`, `chown()` | `SetFileSecurity()` |

**Three ways parameters are passed to a system call:** in **registers**; in a **block/table
in memory** whose address is passed in a register (used when there are more parameters than
registers); or **pushed onto the stack**. The block and stack methods do not limit the number
or length of parameters.

### Kernel architectures — compare these

| Architecture | Idea | Advantages | Disadvantages | Examples |
|---|---|---|---|---|
| **Monolithic** | Whole OS is one large program running in kernel space; any routine can call any other | **Fast** (no message passing overhead); efficient | Huge, hard to maintain; one bug can crash everything; poor modularity | Classic UNIX, MS-DOS (partly), Linux (modular monolithic) |
| **Layered** | Kernel divided into N layers, each using only the layer below | Easy to build, debug and verify layer by layer | Deciding the layering is hard; a request crosses many layers → **slow** | THE OS, early Multics |
| **Microkernel** | Kernel keeps only the bare minimum (IPC, basic scheduling, minimal memory management); file system, drivers, networking run as **user-space servers** | **Reliable** (a driver crash does not kill the kernel), extensible, easier to port, better security | **Performance overhead** of user↔kernel message passing | Mach, QNX, MINIX, Symbian |
| **Hybrid / modular** | Monolithic core + loadable modules (LKMs) | Flexibility of microkernel with speed of monolithic | Still a large trusted kernel | Linux, Windows NT family, macOS (XNU) |
| **Virtual machine** | A hypervisor presents each OS with a copy of the bare machine | Complete isolation; run several OSes at once; ideal for testing/forensics | Hard to implement; some overhead | VMware, VirtualBox, Xen, KVM |

> **Forensic note:** the VM row is directly on your CF syllabus ("Virtual machine and Cloud
> technology forensics", TP-II §2). Snapshots and virtual disk files (.vmdk, .vdi) are
> examinable evidence containers.

### Likely exam questions

- **[5]** Define an operating system. Explain the two views of an OS (extended machine and
  resource manager).
- **[5]** What is a system call? Give any five categories of system calls with one example each.
- **[5]** Distinguish between kernel and shell.
- **[10]** Explain in detail the main functions of an operating system.
- **[10]** Compare monolithic, layered and microkernel operating-system structures with
  diagrams, advantages and disadvantages.
- **[15]** "An operating system is both a resource manager and an extended machine."
  Discuss, describing all its major management functions and services, and explain how
  dual-mode operation and system calls enforce protection.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "The OS is application software" | **System software.** |
| "Shell is part of the kernel" | **No** — the shell is a user-level command interpreter. |
| "Which is always resident in memory?" | The **kernel**. |
| "A system call is a hardware interrupt" | It is a **software interrupt / trap**. |
| "In which mode do user programs run?" | **User mode** (mode bit 1); kernel mode is 0. |
| "Microkernel is faster than monolithic" | **Slower** — message-passing overhead. It is more *reliable*, not faster. |
| "Spooling stands for" | **S**imultaneous **P**eripheral **O**perations **On** **L**ine. |
| "Which is NOT an OS function?" | Compilation / text editing — those are done by **system programs**, not the kernel. |

---

## A3. Evolution, generations and types of operating system

### Concept

The history of operating systems is really the history of **one question: how do we stop the
very expensive CPU from sitting idle?** Every generation is an answer to that question, and
each answer creates the problem that the next generation solves. Learn the *sequence of
motivations* and you never have to memorise the list.

```
No OS (plugboards)     → CPU idle while humans mount tapes
   ↓ automate job setup
Batch systems          → CPU idle during a job's own I/O
   ↓ keep several jobs in memory
Multiprogramming       → users must wait hours for a result; no interaction
   ↓ give each user a short slice of CPU
Time-sharing           → one CPU is still a bottleneck
   ↓ add more CPUs
Multiprocessing        → machines are separate and networked
   ↓ hide the network
Distributed / network OS  → some jobs must meet hard deadlines
   ↓ guarantee response time
Real-time OS           → machines are small, battery powered
   ↓
Embedded / mobile OS
```

### The generations

| Generation | Years | Technology | OS characteristics |
|---|---|---|---|
| **First** | 1945–55 | Vacuum tubes, plugboards | **No operating system at all.** Programmer = operator. Machine language only. |
| **Second** | 1955–65 | Transistors, punched cards, tape | **Batch systems**; resident monitor; JCL; FMS, IBSYS |
| **Third** | 1965–80 | ICs, multiprogramming | **Multiprogramming, spooling, time-sharing**; OS/360, MULTICS, UNIX |
| **Fourth** | 1980–present | LSI/VLSI, PCs | **Personal computer OS, GUI, networking**; MS-DOS, Windows, Linux, macOS |
| **Fifth** (often listed) | present | Mobile/cloud/AI | **Mobile, distributed, cloud, virtualisation**; Android, iOS, hypervisors |

### The types — the table the exam actually wants

| Type | Core idea | How the CPU is kept busy | Advantages | Disadvantages | Examples |
|---|---|---|---|---|---|
| **Serial / simple batch** | Jobs with similar needs are batched on tape and run one after another by a resident monitor; **no interaction** with the user once submitted | Poorly — CPU idles during that job's I/O | Simple; no idle operator time between jobs | Long turnaround; no interaction; a job can monopolise the machine; **CPU still idle during I/O** | Early IBM 1401/7094 setups |
| **Multiprogrammed batch** | **Several jobs are kept in main memory at once**; when the running job blocks for I/O, the OS switches the CPU to another job | Very well — CPU and I/O overlap | High **CPU utilisation** and throughput | Needs memory management, CPU scheduling and protection; complex | OS/360 MVT |
| **Multitasking / time-sharing** | Multiprogramming **plus** rapid switching so each of many interactive users gets the illusion of a private machine | Same as multiprogramming, but switching is driven by a **time quantum**, not only by I/O | **Interactive**; short response time; resource sharing among users | Overhead of frequent context switches; needs swapping/virtual memory; security between users is essential | UNIX, CTSS, MULTICS, Linux, Windows |
| **Multiprocessing (parallel/tightly coupled)** | **Two or more CPUs share a common memory, bus and clock**, under one OS | More CPUs = genuine parallel execution | **Increased throughput**; economy of scale (share peripherals and memory); **graceful degradation / fault tolerance** | Complex; more OS overhead; speed-up is sub-linear (Amdahl's law) | SMP servers, multi-core PCs |
| **Real-time (RTOS)** | Correctness depends on **meeting a deadline**, not just producing the right answer | Priority-driven pre-emption; predictable, bounded latency | **Guaranteed response time**; deterministic | Little or no virtual memory/secondary storage; limited multitasking; expensive to design | VxWorks, RTLinux, QNX; used in avionics, missile control, medical, robotics, industrial control |
| **Distributed (loosely coupled)** | Several autonomous machines, **each with its own memory**, connected by a network, presented to the user as **one system** | Jobs are placed on whichever node is free | Resource sharing; speed-up; reliability (one node down ≠ system down); incremental growth | Network dependence; hard to design; security across nodes | Amoeba, LOCUS; modern cluster/cloud platforms |
| **Network OS** | Machines stay **visibly separate**; the OS just adds networking services (file/print sharing, remote login) | — | Simple, stable, easy to upgrade servers | User is **aware** of the multiplicity of machines; must know where resources live | Novell NetWare, Windows Server |
| **Clustered** | Multiple whole computers coupled to work together, usually sharing storage | — | **High availability** (failover), high performance | Complex cluster management software | Beowulf, Windows Failover Clustering |
| **Embedded / mobile** | OS for a special-purpose device with tight memory, power and cost limits | — | Small footprint, low power, real-time capable | Limited generality; often no user-installable software | Android, iOS, embedded Linux, RTOS in appliances |

### The three "multi-" words — the single most common confusion

| Term | What is multiple | One-line definition |
|---|---|---|
| **Multiprogramming** | **Programs in memory** | More than one job resides in main memory; when one blocks for I/O the CPU is switched to another. **Goal: maximise CPU utilisation.** |
| **Multitasking (time-sharing)** | **Tasks getting CPU turns rapidly** | Logical extension of multiprogramming where the CPU switches on a **time quantum** so users get interactive response. **Goal: minimise response time.** |
| **Multiprocessing** | **CPUs (processors)** | Two or more physical processors under one OS sharing memory. **Goal: true parallelism and throughput.** |
| *(Multithreading)* | *Threads within one process* | *One process split into several independently schedulable threads sharing its address space.* |

> **Say it like this in the exam:** multiprogramming multiplies *programs*, multitasking
> multiplies *turns*, multiprocessing multiplies *processors*, multithreading multiplies
> *threads inside one process*. That sentence alone has earned candidates full marks on a
> 5-mark question.

### Asymmetric vs symmetric multiprocessing

| | **Asymmetric (ASMP)** | **Symmetric (SMP)** |
|---|---|---|
| Role of CPUs | One **master** CPU runs the OS and assigns work; others are slaves | **All CPUs are peers**; each runs a copy of the OS and can perform any task |
| Failure of a CPU | Master failure is fatal | Graceful degradation |
| Complexity | Simpler | More complex (needs careful locking) |
| Used in | Older/large systems, some embedded | Virtually all modern multi-core systems |

### Hard vs soft real-time

| | **Hard real-time** | **Soft real-time** |
|---|---|---|
| Deadline | **Must** be met; a miss is a **system failure** | Should be met; a miss degrades quality only |
| Secondary storage / virtual memory | Usually **absent** (unpredictable delays) | Allowed |
| Examples | Airbag deployment, nuclear reactor control, flight control, pacemaker | Video streaming, VoIP, multimedia playback, online gaming |

### Likely exam questions

- **[5]** Distinguish between multiprogramming, multitasking and multiprocessing.
- **[5]** What is a real-time operating system? Differentiate hard and soft real-time systems.
- **[5]** Explain batch processing systems and their limitations.
- **[10]** Trace the evolution of operating systems from serial processing to distributed
  systems, explaining what problem each stage solved.
- **[10]** Explain the different types of operating systems with their advantages,
  disadvantages and examples.
- **[15]** Describe multiprogramming, time-sharing, multiprocessing, real-time and
  distributed operating systems in detail, comparing them on CPU utilisation, response time,
  hardware requirement and application area.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Multiprogramming needs multiple CPUs" | **No** — one CPU, several programs in memory. |
| "Time-sharing = multiprogramming" | Time-sharing is multiprogramming **plus** time-quantum switching for interactivity. |
| "Main objective of multiprogramming" | **Maximise CPU utilisation** (not response time — that is time-sharing). |
| "Main objective of time-sharing" | **Minimise response time.** |
| "RTOS is one that runs very fast" | It is one that responds **within a guaranteed deadline** — predictability, not raw speed. |
| "In a distributed system, processors share a common clock and memory" | **No** — that is *multiprocessing*. Distributed systems are **loosely coupled**, no shared memory or clock. |
| "Spooling is a form of buffering that requires…" | Spooling uses the **disk** as a huge buffer; buffering usually uses **memory**. |
| "First generation OS" | There **was no OS** in the first generation. |
| "Which OS type has graceful degradation?" | **Multiprocessing** (and clustered). |

---
---

# PART B — PROCESS MANAGEMENT

## B1. The process concept

### Concept — plain English first

A **program** is a file on disk: a passive lump of instructions. Nothing about it changes
over time. The moment you run it, the OS creates a *living instance* of it — code loaded
into memory, a program counter pointing at the current instruction, a stack of function
calls, some heap memory, a set of open files, a user identity, a priority. **That living
instance is a process.** The same program run three times gives you three processes: same
code, three completely separate sets of everything else.

The classic analogy: the program is the **recipe**; the process is the **act of cooking** it.
One recipe, three cooks, three simultaneous cooking processes, each at a different step with
its own bowls and ingredients.

### Formal definition

A **process** is a program in execution — an active entity comprising the program code (text
section), the current activity represented by the value of the program counter and processor
registers, a stack (temporary data: parameters, return addresses, local variables), a data
section (global variables) and a heap (dynamically allocated memory).

### Program vs process — the table

| | **Program** | **Process** |
|---|---|---|
| Nature | **Passive** entity | **Active** entity |
| Location | Stored on **secondary storage** (disk) | Loaded in **main memory** |
| Lifetime | Permanent until deleted | Exists only while executing; **transient** |
| Resources | Holds none | Holds CPU time, memory, files, devices |
| Relationship | One program → **many** processes | One process → exactly one program (at a time) |
| Contains | Only instructions | Instructions **+ PC + registers + stack + heap + data + PCB** |

### The memory layout of a process — hand-draw this

```
   HIGH ADDRESSES
  ┌──────────────────────────┐
  │        STACK             │   local variables, parameters,
  │           │              │   return addresses  — grows DOWNWARD
  │           ▼              │
  ├──────────────────────────┤
  │                          │
  │      (free space)        │
  │                          │
  ├──────────────────────────┤
  │           ▲              │
  │           │              │   malloc / new — grows UPWARD
  │        HEAP              │
  ├──────────────────────────┤
  │        DATA              │   global and static variables
  │  (initialised + BSS)     │
  ├──────────────────────────┤
  │        TEXT              │   the program code — usually read-only
  └──────────────────────────┘
   LOW ADDRESSES
```

**Why stack and heap grow towards each other:** so that the single free region between them
can be used by whichever needs it, instead of fixing a boundary in advance. If they meet, you
get a **stack overflow / out-of-memory** condition. (**Forensic relevance:** stack smashing —
a buffer overflow that overwrites the saved return address — is the classic exploitation
technique, and it is possible precisely because of this layout.)

### The Process Control Block (PCB)

**Concept.** When the OS takes the CPU away from a process, it must be able to put the
process back *exactly* as it was, possibly minutes later. So it needs a place to write down
everything about that process. That place is the **PCB** — also called the **Task Control
Block** or, in Linux, `task_struct`. **The PCB is the process, as far as the OS is
concerned.** It is created when the process is created and destroyed when the process
terminates.

**Every field — learn this list, it is a guaranteed 5-mark question:**

| Field | Contents |
|---|---|
| **Process ID (PID)** | Unique identifier; also parent PID (PPID) |
| **Process state** | New / Ready / Running / Waiting / Terminated |
| **Program counter** | Address of the next instruction to execute |
| **CPU registers** | Accumulators, index registers, stack pointers, general-purpose registers, condition codes — everything that must be saved on a switch |
| **CPU-scheduling information** | Priority, pointers to scheduling queues, scheduling parameters |
| **Memory-management information** | Base and limit registers, page tables or segment tables |
| **Accounting information** | CPU time used, real time elapsed, time limits, account numbers, job/process numbers |
| **I/O status information** | List of open files (file descriptor table), allocated I/O devices, pending I/O requests |
| **Pointers** | To parent, children, and to the next PCB in a queue |
| **Privileges / ownership** | UID, GID, security context |

```
        THE PCB — draw this box in the exam
   ┌───────────────────────────────┐
   │  Process ID  /  Parent PID    │
   ├───────────────────────────────┤
   │  Process state                │
   ├───────────────────────────────┤
   │  Program counter              │
   ├───────────────────────────────┤
   │  CPU registers                │
   ├───────────────────────────────┤
   │  CPU-scheduling information   │
   ├───────────────────────────────┤
   │  Memory-management info       │
   ├───────────────────────────────┤
   │  Accounting information       │
   ├───────────────────────────────┤
   │  I/O status information       │
   ├───────────────────────────────┤
   │  Pointer to next PCB          │
   └───────────────────────────────┘
```

The set of all PCBs is the **process table**.

---

## B2. Process states and transitions

### Concept

A process does not run continuously from start to finish. It runs a bit, asks for data from
disk, waits, gets the data, waits for the CPU to become free again, runs a bit more. The OS
tracks where in that cycle each process is by giving it a **state**.

The crucial insight for the exam: **there are exactly two things that can take a process out
of the Running state, and they lead to two different places.** If it is *forced off* by the
scheduler (its quantum expired, or a higher-priority process arrived) it goes to **Ready** —
it could still run, it just isn't allowed to. If it *voluntarily* gives up the CPU to wait
for something (I/O, a signal, a resource) it goes to **Waiting/Blocked** — it *cannot* run
even if the CPU were free. That distinction is worth a mark every time.

### The five-state model

| State | Meaning |
|---|---|
| **New** | The process is being created; its PCB exists but it has not yet been admitted to the ready queue |
| **Ready** | Runnable and waiting only to be assigned a processor |
| **Running** | Instructions are being executed (on a single-CPU system, exactly one process is Running) |
| **Waiting / Blocked** | Waiting for some event — I/O completion, a semaphore, a child to terminate, a signal |
| **Terminated / Exit** | Execution has finished; the OS is reclaiming resources |

### The state diagram — hand-draw this exactly

```
                       admitted                dispatch (scheduler)
      ┌─────┐  ──────────────────►  ┌───────┐ ─────────────────► ┌─────────┐
      │ NEW │                       │ READY │                    │ RUNNING │
      └─────┘                       └───────┘ ◄───────────────── └─────────┘
                                        ▲       interrupt /            │
                                        │       time-out /             │ exit
                                        │       pre-emption            ▼
                                        │                        ┌────────────┐
                                        │                        │ TERMINATED │
                                        │                        └────────────┘
                                        │
                                        │  I/O or event completion       │ I/O or
                                        │                                │ event wait
                                    ┌───┴─────────┐ ◄────────────────────┘
                                    │  WAITING    │
                                    │  (BLOCKED)  │
                                    └─────────────┘
```

**Label every arrow. The five transitions and their causes:**

| # | Transition | Cause |
|---|---|---|
| 1 | New → Ready | **Admit** — the long-term scheduler accepts the process |
| 2 | Ready → Running | **Dispatch** — the short-term scheduler (dispatcher) selects it |
| 3 | Running → Ready | **Time-out / pre-emption / interrupt** — quantum expired or a higher-priority process arrived. *Involuntary.* |
| 4 | Running → Waiting | **Event wait** — issues an I/O request or a `wait()`. *Voluntary.* |
| 5 | Waiting → Ready | **Event completion** — the I/O finished or the awaited event occurred |
| 6 | Running → Terminated | **Exit** — normal completion or abort |

**Impossible transitions — a favourite MCQ.**
- **Ready → Waiting** is impossible: a Ready process is not executing, so it cannot issue an
  I/O request.
- **Waiting → Running** is impossible: after its event completes, a process must go through
  **Ready** and be selected by the scheduler.

### The seven-state model (with swapping)

When main memory is short, the medium-term scheduler **swaps** whole processes out to disk.
This adds two suspended states:

| Extra state | Meaning |
|---|---|
| **Ready-suspended** | Runnable but currently swapped out to secondary storage |
| **Blocked-suspended** | Waiting for an event **and** swapped out |

Transitions: Ready ↔ Ready-suspended (**suspend / resume**), Blocked ↔ Blocked-suspended, and
crucially **Blocked-suspended → Ready-suspended** when the awaited event completes while the
process is still on disk.

### Additional UNIX-specific states worth one line

- **Zombie**: the process has terminated but its parent has not yet called `wait()`, so its
  exit status is still held in the process table. It consumes a PID but no other resources.
- **Orphan**: the parent terminated first; the process is **re-parented to `init`/`systemd`**
  (PID 1), which reaps it.

### Likely exam questions

- **[5]** Differentiate between a program and a process.
- **[5]** What is a PCB? List the information stored in it.
- **[5]** Why can a process not move directly from Waiting to Running?
- **[10]** Draw and explain the process state transition diagram, describing each state and
  every transition with its cause.
- **[10]** Explain the seven-state process model with suspended states and swapping.
- **[15]** Explain the process concept in detail: process vs program, the memory layout of a
  process, the process control block with all its fields, the five-state diagram with all
  transitions, and the role of the three schedulers.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "How many processes can be in Running state on a single CPU?" | **Exactly one.** |
| "Ready → Blocked is a valid transition" | **Invalid.** |
| "Blocked → Running is valid" | **Invalid** — must pass through Ready. |
| "The PCB is stored in the process's own stack" | It is stored in **kernel memory** (the process table). |
| "A zombie process consumes CPU" | It consumes only a **process-table entry**. |
| "Which is NOT in the PCB?" | The **program's source code**. (The *text section* is in the process's memory, not in the PCB.) |
| "An orphan process is killed" | It is **adopted by init (PID 1)**. |

---

## B3. Schedulers, the dispatcher and context switching

### The three schedulers

| | **Long-term (job) scheduler** | **Short-term (CPU) scheduler** | **Medium-term scheduler** |
|---|---|---|---|
| Selects from | The **job pool** on disk | The **ready queue** in memory | Processes in memory |
| Selects for | Loading into main memory (New → Ready) | Execution on the CPU (Ready → Running) | **Swapping out** to disk / back in |
| Frequency | **Infrequent** (seconds/minutes) | **Very frequent** (milliseconds) | In between |
| Must be | Slow is acceptable; can use complex algorithms | **Very fast** — its own running time is pure overhead | Moderate |
| Controls | The **degree of multiprogramming** | Which process runs next | Reduces the degree of multiprogramming |
| Present in | Batch systems (absent or minimal in time-sharing/UNIX) | **All** systems | Systems with swapping |

**Degree of multiprogramming** = the number of processes resident in main memory. The
long-term scheduler must maintain a good **mix of CPU-bound and I/O-bound processes**: all
CPU-bound → the I/O devices sit idle and the ready queue is long; all I/O-bound → the CPU
sits idle. Stating this mix argument is a standard mark-earner.

### Dispatcher

The **dispatcher** is the module that actually gives the CPU to the process the short-term
scheduler chose. Its jobs: **switching context, switching to user mode, and jumping to the
proper location in the user program to restart it.** The time it takes is the **dispatch
latency**, and because it happens on every single switch it **must be as fast as possible**.

> **Scheduler vs dispatcher** is a classic 5-mark question. The **scheduler decides**
> (policy); the **dispatcher does** (mechanism).

### Context switching

**Concept.** To move the CPU from process A to process B, the OS must **save A's entire
CPU state into A's PCB** and **load B's state from B's PCB**. That is a context switch.

**Key points:**
- Context-switch time is **pure overhead** — no useful work is done during it.
- Typical cost: a few microseconds; depends heavily on **hardware support** (some CPUs have
  multiple register sets, so a switch is just changing a pointer).
- It also usually means flushing or invalidating the **TLB** and polluting the **cache**,
  which is a hidden extra cost.
- Context switches are triggered by: interrupts, system calls that block, time-quantum
  expiry, and higher-priority process arrival.
- **A context switch between two threads of the same process is cheaper** than between
  processes, because the memory map (page tables) does not change.

### Process creation and termination

- **Creation (UNIX):** `fork()` creates a child that is an **exact copy** of the parent
  (same code, data copied — in practice **copy-on-write**). `fork()` returns **0 to the
  child** and the **child's PID to the parent** (and −1 on failure). The child then usually
  calls **`exec()`** to replace its memory image with a new program. The parent may
  **`wait()`** for the child.
- Windows uses a single `CreateProcess()` that loads a specified program directly.
- **Termination:** `exit()`. A parent may `abort()`/`kill()` a child if it exceeds resource
  usage, its task is no longer required, or the parent is exiting (**cascading termination**).
- **Process hierarchy:** UNIX processes form a tree rooted at `init`/`systemd` (PID 1).

**Classic numerical:** how many processes does this create?

```c
int main() { fork(); fork(); fork(); return 0; }
```
Each `fork()` doubles the number of processes: **2³ = 8 processes total**, i.e. the original
plus **7 children**. In general **n `fork()` calls in a straight line → 2ⁿ processes, 2ⁿ − 1
new ones.**

### Likely exam questions

- **[5]** Distinguish between long-term, short-term and medium-term schedulers.
- **[5]** What is a context switch? Why is it considered overhead?
- **[5]** Differentiate between the scheduler and the dispatcher.
- **[10]** Explain process creation and termination in UNIX using `fork()`, `exec()`,
  `wait()` and `exit()`, with a diagram of the resulting process tree.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "`fork()` returns the child's PID to the child" | It returns **0 to the child**, the **child's PID to the parent**. |
| "Which scheduler controls the degree of multiprogramming?" | **Long-term.** |
| "Context switch does useful work" | It is **pure overhead**. |
| "Time-sharing systems have a long-term scheduler" | Usually **minimal or absent**. |
| "Dispatch latency is the time to select the next process" | It is the time to **stop one process and start another** (selection is the scheduler's job). |

---

## B4. Threads

### Concept

A process is expensive: its own address space, its own page tables, its own file table.
But often you want several activities inside **one** application that share all of that —
a word processor that formats text, checks spelling and autosaves at the same time, all
working on the *same document in the same memory*. Creating three processes would mean three
copies of the document and painful IPC to keep them in sync.

**A thread is a lightweight process: an independent path of execution (its own program
counter, register set and stack) that shares the process's code, data, heap and open files
with its sibling threads.** One process, many threads, one address space.

### What is shared and what is private

| **Shared by all threads of a process** | **Private to each thread** |
|---|---|
| Code / text section | **Program counter** |
| Data section (globals) | **Register set** |
| Heap | **Stack** |
| Open files / file descriptors | Thread ID |
| Signals and signal handlers | Priority / scheduling state |
| Current working directory, UID/GID | Errno, thread-local storage |

### Process vs thread

| | **Process** | **Thread** |
|---|---|---|
| Also called | Heavyweight process | **Lightweight process (LWP)** |
| Address space | **Own, isolated** | **Shared** with siblings |
| Creation cost | High | **Low** (order of 10–100× cheaper) |
| Context switch cost | High (page tables, TLB flush) | **Low** (no memory-map change) |
| Communication | Needs IPC (pipes, shared memory, messages) — kernel involvement | **Direct** via shared variables — but needs synchronisation |
| Protection | Processes are protected from each other | **No protection** between threads — one bad thread can corrupt the whole process |
| Effect of a crash | Other processes unaffected | Can bring down the **entire process** |
| Blocking | One process blocking does not block others | With **user-level threads**, one blocking call blocks all threads of the process |

### Benefits of multithreading — four standard points

1. **Responsiveness** — the UI thread stays alive while another thread does the long job.
2. **Resource sharing** — threads share memory and files by default; no IPC set-up needed.
3. **Economy** — far cheaper to create and context-switch than processes.
4. **Scalability / utilisation of multiprocessor architectures** — threads of one process can
   genuinely run in parallel on different cores. (A single-threaded process can only ever use
   one core.)

### User-level vs kernel-level threads

| | **User-level threads (ULT)** | **Kernel-level threads (KLT)** |
|---|---|---|
| Managed by | A **thread library** in user space; kernel is unaware | The **kernel** itself |
| Switching | Fast — no mode switch to kernel | Slower — requires kernel intervention |
| Blocking system call | **Blocks the entire process** (all its threads) | Blocks only that thread |
| True parallelism on multiple CPUs | **No** (kernel sees one schedulable entity) | **Yes** |
| Scheduling | Application-specific scheduling possible | Kernel's scheduler |
| Portability | High (library-level) | OS-dependent |
| Examples | POSIX Pthreads (can be either), Java green threads, older Solaris | Windows threads, Linux tasks, modern Solaris/Linux Pthreads |

### Multithreading models

| Model | Mapping | Notes | Example |
|---|---|---|---|
| **Many-to-One** | Many ULTs → **one** KLT | Efficient switching but **no parallelism**; one blocking call blocks everything | Green threads |
| **One-to-One** | Each ULT → its own KLT | **True concurrency**; but creating a user thread creates a kernel thread → overhead limits thread count | **Linux, Windows** |
| **Many-to-Many** | m ULTs → n KLTs (n ≤ m) | Best of both: parallelism *and* unlimited user threads; complex to implement | Older Solaris, Windows with ThreadFiber |
| **Two-level** | Many-to-many **plus** the ability to bind a specific user thread to a kernel thread | Hybrid | IRIX, HP-UX |

### Likely exam questions

- **[5]** Define a thread. What resources does it share with other threads of the same process?
- **[5]** State any four benefits of multithreading.
- **[5]** Differentiate between user-level and kernel-level threads.
- **[10]** Distinguish between a process and a thread. Explain the multithreading models with
  diagrams.
- **[15]** What is a thread? Explain why threads are called lightweight processes. Describe
  user-level and kernel-level threads, the four multithreading models, and the benefits and
  problems of multithreaded programming.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Threads share the stack" | **No** — each thread has its **own stack**. They share code, data, heap and files. |
| "Threads have their own address space" | **No** — that is a process. |
| "A thread is a heavyweight process" | **Lightweight.** |
| "Many-to-one gives true parallelism" | **No** — only one-to-one and many-to-many do. |
| "Linux uses many-to-many" | **One-to-one.** |
| "Threads of a process are protected from each other" | **They are not.** |

---
