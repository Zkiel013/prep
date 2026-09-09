# CORE 04 — UNIX / Linux

> **Shared-core file 4 of the NPSC CTSE 2026 prep set.**
> Read with `OFFICIAL_SYLLABUS.md` open. Everything here is written to be revised at three
> depths: **one-line fact** (MCQ), **5-mark answer** (~5–6 crisp points), **10/15-mark answer**
> (worked explanation + hand-drawn diagram).

---

## 0. Why this matters — where UNIX appears in your three papers

| Elective | Where it appears | How heavy |
|---|---|---|
| **CS Diploma** | Paper-II §2 — an *entire numbered unit* called "UNIX Operating System". Names ~30 commands **explicitly by name**. | **Very heavy.** This is the single most predictable unit in your whole Diploma paper. |
| **Computer Forensic** | TP-I §8 (Operating Systems → "UNIX: The Unix System: File system, process management, shell variables, command line programming. Filters and Commands") and TP-I §5 ("Linux System and Artifacts: Linux file system — Ownership and permissions, hidden files, User Accounts and Logs") | **Heavy**, and note the forensic slant: permissions, hidden files, logs. |
| **CS Degree** | Not named. But OS Paper-II §1 (file system management, process management, security & protection) is answered *beautifully* using UNIX as the worked example. | Indirect — use it as illustration. |

**The strategic read.** The Diploma syllabus lists commands by name. When a syllabus names a
command, an examiner can write a one-mark MCQ on it almost mechanically ("Which command
counts lines, words and characters?"). So the quick-reference table in §7 is not filler — it
*is* the MCQ paper. Learn it cold. Meanwhile the Forensic paper wants you to reason about
*permissions and ownership*, which is where the chmod arithmetic in §5 earns its 10 marks.

### Topic checklist

- [ ] UNIX history, development, and why it looks the way it does
- [ ] Features of UNIX (multiuser, multitasking, portability, hierarchical FS)
- [ ] Architecture: hardware → kernel → shell → utilities (draw the onion)
- [ ] Kernel functions; shell types (sh, bash, csh, ksh, tcsh, zsh)
- [ ] Hierarchical directory structure and the standard `/` subdirectories
- [ ] File types (all seven) and how to identify each from `ls -l`
- [ ] Inodes — what is stored *in* one and what is emphatically *not*
- [ ] Hard links vs symbolic links
- [ ] Ownership: user / group / other; `chown`, `chgrp`
- [ ] **Permissions — symbolic and numeric; chmod calculations both directions**
- [ ] umask and how it derives default permissions
- [ ] Special permission bits: SUID, SGID, sticky bit
- [ ] Navigation & file management commands
- [ ] File processing / filter commands (the big Diploma list)
- [ ] Formatting and printing — `pr` options, `lp`
- [ ] Online help — `man` sections, `help`, `info`, `whatis`, `apropos`
- [ ] Mathematical — `bc`, `expr`, `factor`, `units`
- [ ] Communication — `write`, `mail`, `wall`, `mesg`, `talk`
- [ ] System info — `who`, `who am i`, `tty`, `date`, `cal`, `uname`, `uptime`
- [ ] Booting procedure stages; init / runlevels / systemd; login process
- [ ] Startup and shutdown commands
- [ ] Shell variables (local, environment, special/positional)
- [ ] Shell scripting basics — shebang, conditionals, loops, functions
- [ ] Pipes, redirection, tee, filters
- [ ] Process management — `ps`, `kill`, signals, `&`, `nohup`, `jobs`, `fg`, `bg`, `nice`
- [ ] vi editor three modes

---

## 1. History and development of UNIX

### Concept — the plain-English story first

In the mid-1960s Bell Labs, GE and MIT were building **Multics**, an enormously ambitious
time-sharing operating system. It was late, huge and over-engineered, and Bell Labs pulled
out in 1969. Two of the researchers left holding the bag, **Ken Thompson** and **Dennis
Ritchie**, wanted the *nice parts* of Multics — a hierarchical file system, multiple users
sharing one machine — without the bloat. Thompson found a cast-off DEC PDP-7 and wrote a
tiny single-user system for it. Brian Kernighan punned that if Multics was "multiplexed",
this thing was "uniplexed" — **UNICS** — later spelled **UNIX**.

Three decisions made in those first few years explain almost everything about UNIX today:

1. **In 1973 it was rewritten in C.** Every operating system before it was written in
   assembly, and assembly is machine-specific. Rewriting UNIX in a high-level language made
   it *portable* — you could move it to a new machine by writing a C compiler for that
   machine. This is the single most important fact in UNIX history, and it is a favourite
   one-mark MCQ.
2. **Everything is a file.** Disks, terminals, printers, even processes (via `/proc`) are
   presented through the same read/write interface. So the same handful of commands work on
   everything, and pipes work universally.
3. **Small tools, one job each, joined by pipes.** Rather than one giant program with
   fifty options, UNIX gives you `sort`, `grep`, `wc`, `cut` and lets you chain them. This is
   the "UNIX philosophy" and it is why the command list in §7 is long but each entry is short.

### Timeline (memorise the bold rows — these are the MCQ rows)

| Year | Event |
|---|---|
| 1965 | Multics project begins (Bell Labs + GE + MIT) |
| 1969 | Bell Labs withdraws. **Ken Thompson** writes first UNIX on a **PDP-7**, in assembly |
| 1970 | Named "UNIX"; UNIX epoch begins **1 Jan 1970 00:00:00 UTC** |
| 1971 | First Edition; ported to PDP-11; `roff`/troff added |
| **1973** | **Rewritten in C by Dennis Ritchie & Ken Thompson → portability** |
| 1975 | Sixth Edition released to universities (source included) — spreads UNIX |
| 1977 | **BSD** (Berkeley Software Distribution) branch begins at UC Berkeley |
| 1979 | Seventh Edition — Bourne shell (`sh`), the "ancestor" UNIX |
| 1983 | AT&T **System V** released — the other great branch. C shell (`csh`) by Bill Joy |
| 1984 | Richard Stallman starts **GNU** ("GNU's Not UNIX") project |
| 1987 | MINIX by Andrew Tanenbaum (teaching OS) |
| 1988 | **POSIX** (IEEE 1003) standard — portable interface across UNIX variants |
| **1991** | **Linus Torvalds** releases the **Linux kernel** (v0.01), Helsinki |
| 1992 | Linux relicensed under **GPL**; GNU tools + Linux kernel = usable OS |
| 1993 | FreeBSD, NetBSD; Linux distributions begin (Slackware, Debian) |
| 2001 | Mac OS X — a BSD-derived (Darwin/Mach) UNIX, relevant to your Forensic paper |

**The two great families** — you will be asked to distinguish them:

| | **System V (AT&T)** | **BSD (Berkeley)** |
|---|---|---|
| Init | `/etc/inittab`, runlevels, `/etc/rc.d/` scripts | `/etc/rc` scripts, no runlevels |
| Print | `lp`, `lpstat`, `cancel` | `lpr`, `lpq`, `lprm` |
| Process listing | `ps -ef` | `ps aux` |
| Terminal | `termcap` replaced by `terminfo` | `termcap` |
| Descendants | Solaris, AIX, HP-UX | FreeBSD, NetBSD, OpenBSD, macOS |

Linux is a **System V-style** userland with many BSD features, GNU utilities, and its own
kernel written from scratch. Note carefully: **Linux is not derived from UNIX source code**
— it is a UNIX-*like* system, written independently, that conforms to POSIX. Examiners like
this distinction.

### Features of UNIX — the standard 5-mark list

| Feature | One-line explanation |
|---|---|
| **Multiuser** | Many users log in simultaneously; each has own home dir, permissions, environment |
| **Multitasking** | Many processes run concurrently via time-sharing; supports background jobs |
| **Portability** | Written in C; ~95% of the kernel is machine-independent |
| **Hierarchical file system** | Single inverted-tree rooted at `/`; all devices mounted into it |
| **Everything is a file** | Devices, pipes, sockets accessed via the same read/write calls |
| **Security** | User/group/other permissions, ownership, encrypted passwords, SUID model |
| **Pipes & filters** | Output of one command feeds directly into the next — tool composition |
| **Shell as programmable interface** | The command interpreter is also a full scripting language |
| **Open / standardised** | POSIX conformance; source availability in Linux/BSD |
| **Communication** | Built-in inter-user (`write`, `mail`, `wall`) and inter-process (pipes, signals, IPC) |

### Likely exam questions

- **[5]** Write a short note on the history and development of the UNIX operating system.
- **[5]** List and explain any five salient features of UNIX.
- **[5]** Distinguish between UNIX and Linux.
- **[10]** Trace the evolution of UNIX from Multics to Linux. Why was the 1973 rewrite in C
  the turning point? Compare the System V and BSD lineages.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Who developed UNIX?" | **Ken Thompson** (with Dennis Ritchie). Ritchie alone → C language. |
| "UNIX was originally written in?" | **Assembly language** (PDP-7). C came in 1973. |
| "First machine UNIX ran on?" | **DEC PDP-7** (not PDP-11 — that was the 1971 port). |
| "Linux kernel author / year?" | **Linus Torvalds, 1991**. |
| "UNIX epoch?" | **1 January 1970**. |
| "Full form of UNIX/UNICS?" | Uniplexed Information and Computing Service/System. |
| "Is Linux a UNIX?" | It is **UNIX-like / POSIX-compliant**, not derived from UNIX code. |
| "GNU stands for?" | **GNU's Not UNIX** (a recursive acronym). |

---

## 2. UNIX architecture — kernel, shell, utilities

### Concept

Think of UNIX as an **onion with four layers**. At the dead centre sits the **hardware**.
Wrapped around it is the **kernel**, the only piece of software allowed to touch hardware
directly. Around the kernel sits the **shell**, which is just an ordinary program whose job
is to read what you type and ask the kernel to do it. On the outside sit the **application
utilities** — `ls`, `grep`, `vi`, your own programs — and finally the **user**.

The crucial insight, and the one that gets marks: **the shell is not part of the kernel.**
It is a replaceable user-level program. That is why you can have half a dozen different
shells on the same machine and switch between them freely, while there is exactly one
kernel. When you type `ls`, the shell does not list files — it locates the `/bin/ls`
program, asks the kernel to create a process for it, and waits. The only way any program,
shell included, gets work out of the kernel is through **system calls** (`open`, `read`,
`write`, `fork`, `exec`, `wait`, `exit`).

### Diagram to hand-draw — "the UNIX onion"

Draw **four concentric circles**. Label from the inside out:

```
        ┌────────────────────────────────────────────┐
        │              U S E R                       │
        │   ┌────────────────────────────────────┐   │
        │   │   APPLICATION / UTILITY PROGRAMS   │   │
        │   │   ls  cp  grep  vi  cc  sort  who  │   │
        │   │   ┌────────────────────────────┐   │   │
        │   │   │          S H E L L         │   │   │
        │   │   │   sh bash csh ksh tcsh     │   │   │
        │   │   │   ┌────────────────────┐   │   │   │
        │   │   │   │      K E R N E L   │   │   │   │
        │   │   │   │  process mgmt      │   │   │   │
        │   │   │   │  memory mgmt       │   │   │   │
        │   │   │   │  file system       │   │   │   │
        │   │   │   │  device drivers    │   │   │   │
        │   │   │   │  ┌──────────────┐  │   │   │   │
        │   │   │   │  │  HARDWARE    │  │   │   │   │
        │   │   │   │  │ CPU Mem Disk │  │   │   │   │
        │   │   │   │  └──────────────┘  │   │   │   │
        │   │   │   └────────────────────┘   │   │   │
        │   │   └────────────────────────────┘   │   │
        │   └────────────────────────────────────┘   │
        └────────────────────────────────────────────┘
```

Add an arrow from SHELL to KERNEL labelled **"system calls"** — that single arrow is worth a
mark on its own, because it names the interface. Also mark that utilities can call the
kernel directly too (they need not go through the shell).

### Key points — the kernel

- Loaded into memory at boot and **stays resident** until shutdown; it is the core of the OS.
- Runs in **privileged / kernel mode**; user programs run in **user mode**.
- Everything it does is requested through **system calls** (~300 in Linux) — the boundary
  between user space and kernel space.
- Five classical responsibilities:

| Kernel subsystem | Responsibility |
|---|---|
| **Process management** | Creating (`fork`), running (`exec`), scheduling, terminating processes; context switching; signals; IPC |
| **Memory management** | Allocating/freeing memory, virtual memory, paging, swapping, protection between processes |
| **File system management** | Directories, inodes, blocks, mounting, buffering, permissions enforcement |
| **Device management** | Device drivers; the abstraction that makes `/dev/sda` look like a file |
| **Networking / system calls** | Protocol stack, sockets; providing the system-call interface itself |

- **Monolithic** kernel design in UNIX/Linux (all subsystems in one address space), as against
  microkernel designs (Mach, MINIX). Linux is monolithic but **modular** — drivers can be
  loaded/unloaded at runtime (`insmod`, `lsmod`, `rmmod`, `modprobe`).

### Key points — the shell

- The **command interpreter**: reads a command line, parses it, expands wildcards and
  variables, handles redirection and pipes, then forks/execs the program.
- It is a **user program**, not part of the kernel — replaceable per user.
- It is also a **programming language** (variables, `if`, loops, functions) — hence shell
  scripts.
- The user's login shell is recorded in the **last field of `/etc/passwd`**.
- The shell's own read-execute cycle: **prompt → read → parse → expand → fork → exec → wait → prompt**.

| Shell | Command | Author | Notes |
|---|---|---|---|
| **Bourne shell** | `sh` | Stephen Bourne, 1979 | The original standard; default prompt `$`; best for scripting portability |
| **C shell** | `csh` | Bill Joy, BSD | C-like syntax; introduced **history**, **aliases**, **job control**; prompt `%` |
| **Korn shell** | `ksh` | David Korn, AT&T | Bourne-compatible + csh features + arrays, arithmetic; prompt `$` |
| **Bourne-Again shell** | `bash` | Brian Fox, GNU | Default on Linux; sh-compatible superset; command completion |
| **TC shell** | `tcsh` | — | Enhanced csh with editing/completion |
| **Z shell** | `zsh` | — | Superset of bash/ksh; default on modern macOS |
| **Restricted shell** | `rsh`/`rbash` | — | Cannot `cd`, change PATH, or redirect — used for locked-down accounts |

Root's prompt is conventionally `#`; ordinary users get `$` (or `%` in csh). This is an MCQ.

### Key points — utilities / application programs

- Ordinary executables living in `/bin`, `/usr/bin`, `/sbin`, `/usr/sbin`.
- Each does **one job**; composed with pipes.
- Categories: file management, filters, text processing, compilers, editors, networking,
  system administration.

### Likely exam questions

- **[5]** With a neat diagram explain the structure of the UNIX operating system.
- **[5]** What is a shell? Name any four shells and state one distinguishing feature of each.
- **[5]** Differentiate between the kernel and the shell.
- **[10]** Explain the architecture of UNIX with a labelled diagram. Discuss in detail the
  functions of the kernel and describe how a typed command is executed end to end.
- **[15]** "UNIX is built in layers." Justify with a diagram, explaining hardware, kernel,
  shell and utilities, the role of system calls, and how the design delivers portability,
  multiuser operation and security.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "The shell is a part of the kernel." | **False** — it is a user-level program. |
| "Which is the default shell in Linux?" | **bash**. Default on modern macOS is **zsh**. Original UNIX default is **sh**. |
| "Interface between user and kernel?" | **Shell**. Interface between shell and hardware → kernel. |
| "Which shell introduced job control and history?" | **C shell (csh)**. |
| "How many kernels can run?" | **One**. Many shells, one kernel. |
| "Login shell is stored in?" | **`/etc/passwd`**, last (7th) field. |
| "Linux kernel type?" | **Monolithic (modular)** — not microkernel. |

---

## 3. The UNIX file system and hierarchical directory structure

### Concept

DOS and Windows give each disk its own letter — `C:`, `D:` — so there are several separate
trees. UNIX refuses to do this. There is exactly **one** tree, and its root is called `/`
(pronounced "root", "slash"). A second disk does not get a letter; it gets **mounted** onto
a directory inside the existing tree, say `/home`, and from then on it is simply part of the
same tree. Users cannot tell where one physical device ends and another begins, which is
exactly the point: the file system is a *logical* structure that hides physical devices.

An **inverted tree** is the standard phrase — root at the top, branches downward.

### Diagram to hand-draw — the standard hierarchy

```
                              /  (root)
   ┌────┬────┬────┬────┬─────┼─────┬────┬────┬────┬────┬────┐
  bin  sbin etc  dev  home  lib   usr  var tmp  boot proc  opt
                        │           │     │            │
                 ┌──────┴──┐   ┌────┼───┐ ├─ log       └─ (kernel/process
               user1     user2 bin lib share  ├─ spool      info, virtual)
                 │                            ├─ mail
          ┌──────┴──────┐                     └─ tmp
       docs        .bashrc (hidden)
```

### The standard directories — learn this table

| Directory | Holds |
|---|---|
| `/` | Root of the entire hierarchy; everything hangs off it |
| `/bin` | **Essential user binaries** available to all users: `ls`, `cp`, `cat`, `mv` |
| `/sbin` | **System binaries** for the superuser: `fsck`, `init`, `shutdown`, `mkfs` |
| `/etc` | **Configuration files** (text): `passwd`, `shadow`, `group`, `fstab`, `inittab`, `hosts`, `profile`. *Never binaries.* |
| `/dev` | **Device files**: `/dev/sda` (disk), `/dev/tty` (terminal), `/dev/null` (bit bucket), `/dev/zero`, `/dev/random` |
| `/home` | Ordinary users' **home directories** (`/home/ravi`) |
| `/root` | The **superuser's** home directory (not the same as `/`) |
| `/lib` | Shared **libraries** and kernel modules needed by `/bin` and `/sbin` |
| `/usr` | Secondary hierarchy of **user programs** — `/usr/bin`, `/usr/lib`, `/usr/share`, `/usr/local`, `/usr/include`. Read-only, shareable |
| `/var` | **Variable** data that changes constantly: `/var/log`, `/var/spool/mail`, `/var/spool/cron`, `/var/tmp` |
| `/tmp` | **Temporary** files; world-writable with **sticky bit**; usually cleared at boot |
| `/boot` | Bootloader files and the **kernel image** (`vmlinuz`), `initrd`, GRUB config |
| `/proc` | **Virtual/pseudo** file system — a window on kernel and process state. Occupies **zero disk**; created in memory. `/proc/cpuinfo`, `/proc/meminfo`, `/proc/<pid>/` |
| `/sys` | Virtual FS exposing kernel device/driver model (modern Linux) |
| `/mnt`, `/media` | Mount points for temporary / removable file systems |
| `/opt` | Optional, third-party add-on application packages |
| `/srv` | Data served by the system (web, ftp) |
| `/lost+found` | Files recovered by `fsck` after a crash; one per file system |

**For your Forensic paper, memorise these evidentiary locations:**

| Artefact | Path |
|---|---|
| User accounts | `/etc/passwd` (world-readable), `/etc/shadow` (hashes, root-only, mode 640/600) |
| Groups | `/etc/group`, `/etc/gshadow` |
| Successful/failed logins (binary) | `/var/log/wtmp` (read with `last`), `/var/log/btmp` (`lastb`), `/var/run/utmp` (`who`) |
| Last login per user | `/var/log/lastlog` (read with `lastlog`) |
| Auth events | `/var/log/auth.log` (Debian) or `/var/log/secure` (RHEL) |
| General system messages | `/var/log/messages`, `/var/log/syslog`, `dmesg` |
| Shell history | `~/.bash_history` |
| Scheduled tasks | `/var/spool/cron/crontabs/<user>`, `/etc/crontab`, `/etc/cron.d/` |
| Mounted FS at boot | `/etc/fstab`; currently mounted → `/etc/mtab`, `mount`, `df` |

### File system internal structure — the four blocks

A UNIX disk partition is divided into four regions. Draw this as a **horizontal bar split
into four labelled segments** — it is one of the easiest diagram marks available.

```
┌────────────┬────────────┬───────────────────┬───────────────────────────┐
│ BOOT BLOCK │ SUPER BLOCK│    INODE BLOCK    │      DATA BLOCK           │
│  block 0   │            │  (inode table)    │ (file contents + dirs)    │
└────────────┴────────────┴───────────────────┴───────────────────────────┘
```

| Region | Contents |
|---|---|
| **Boot block** | First block (block 0) of the file system. Holds the **bootstrap loader** that pulls the kernel into memory. Only the boot block of the root file system is actually used; others are empty but reserved. |
| **Super block** | The file system's "table of contents": size of the FS, size of the inode list, number of free blocks and free inodes, list of free blocks/inodes, FS state (clean/dirty), block size, magic number. **Corrupt superblock = unusable file system**, hence backup superblocks are kept. |
| **Inode block** | The **inode table** — a fixed-size array of inodes, one per file, created when the FS is made. This is why a file system can run out of inodes while still having free space (millions of tiny files). |
| **Data block** | Actual file contents, and directory entries. Numbered from the end of the inode list to the end of the FS. |

Common UNIX/Linux file system types: **ext2 / ext3 / ext4** (ext3 and ext4 are journaling),
**XFS**, **Btrfs**, **UFS/FFS** (BSD), **JFS**, **ReiserFS**, **ZFS**, plus **swap**. Journaling
means metadata changes are written to a log first so a crash can be recovered quickly without
a full `fsck` — a good one-liner for the Forensic paper too.

### File types — all seven

`ls -l` prints a ten-character string. The **first character is the file type**; the remaining
nine are permissions. Memorise the seven type characters:

| Char | Type | Explanation | Example |
|---|---|---|---|
| `-` | **Ordinary / regular file** | Text, binary, image, anything | `report.txt`, `/bin/ls` |
| `d` | **Directory** | A file containing (filename, inode number) pairs | `/home` |
| `l` | **Symbolic (soft) link** | A file whose content is a *pathname* pointing elsewhere | `/bin → /usr/bin` |
| `c` | **Character special file** | Device transferring data character by character, unbuffered | `/dev/tty`, `/dev/null`, terminals, printers |
| `b` | **Block special file** | Device transferring data in fixed-size blocks, buffered | `/dev/sda`, hard disks, CD-ROM |
| `p` | **Named pipe (FIFO)** | IPC channel with a name in the file system (`mkfifo`) | `/tmp/mypipe` |
| `s` | **Socket** | Endpoint for bidirectional IPC, often network | `/var/run/docker.sock` |

Broad classification often asked as a 5-marker: **(1) Ordinary files, (2) Directory files,
(3) Device/special files** — with links, pipes and sockets as further special types.

Use `file <name>` to determine content type (it reads magic numbers, not the extension) —
worth remembering for the Forensic paper, because **UNIX has no concept of file extensions**;
`report.txt` and `report` are equally valid names and the `.txt` means nothing to the kernel.

**Hidden files**: any file whose name begins with a **dot** (`.bashrc`, `.ssh`, `.profile`)
is hidden from a plain `ls`. Reveal with **`ls -a`**. This is explicitly in your Forensic
syllabus ("hidden files") — the exam point is that hiding is a *naming convention honoured by
`ls`*, not a file attribute or a security feature. Note `.` (current directory) and `..`
(parent directory) are themselves entries in every directory; `ls -A` shows hidden files but
suppresses `.` and `..`.

### Likely exam questions

- **[5]** Explain the hierarchical directory structure of UNIX with a diagram.
- **[5]** List and explain the different types of files in UNIX.
- **[5]** Explain the structure of a UNIX file system (boot block, super block, inode block,
  data block).
- **[5]** What are hidden files? How are they created and displayed?
- **[10]** Describe the UNIX file system in detail: the standard directory hierarchy, the
  four regions of a disk partition, and the seven file types with examples.
- **[15]** Explain the UNIX file system architecture. Include the directory hierarchy, the
  role of the superblock and inode table, file types, and describe how the kernel resolves
  the pathname `/home/ravi/notes.txt` to actual disk blocks.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Which directory holds configuration files?" | **`/etc`** (not `/config`, not `/var`). |
| "Which holds device files?" | **`/dev`**. |
| "Which is a virtual file system occupying no disk?" | **`/proc`**. |
| "Root user's home directory?" | **`/root`**, *not* `/`. |
| "Which block holds free block list and FS size?" | **Super block** (not boot block). |
| "Log files live in?" | **`/var/log`**. |
| "Which command shows hidden files?" | **`ls -a`**. |
| "First character `b` in `ls -l` means?" | **Block special file** (`c` = character special). |
| "Number of file systems trees in UNIX?" | **One** — a single tree rooted at `/`. |
| "Password hashes are in?" | **`/etc/shadow`**, not `/etc/passwd`. |

---

## 4. Inodes and links

### Concept

Here is the idea that surprises everybody: **in UNIX, a file's name is not part of the file.**

A file is a numbered object called an **inode** (index node). The inode holds everything the
system knows about the file — its size, its owner, its permissions, its timestamps, and the
disk block addresses where the data actually lives. What it does *not* hold is the **name**.

The name lives in a **directory**. A directory is just an ordinary file whose contents are a
simple two-column table:

| Filename | Inode number |
|---|---|
| `.` | 2341 |
| `..` | 118 |
| `notes.txt` | 5567 |
| `report` | 5567 |

Notice that `notes.txt` and `report` point at the *same* inode 5567. They are not a copy —
they are two **names for one file**. That is a **hard link**. Delete one name and the file
survives, because the inode keeps a **link count** and only when the count falls to zero (and
no process has it open) are the data blocks freed. This is why the delete system call is
literally named **`unlink`** — you remove a name, not a file.

### What an inode contains

| Stored in the inode | Stored elsewhere |
|---|---|
| File **type** (regular, dir, link…) | **The file name** → in the directory entry |
| **Permissions** (12 bits: 9 rwx + SUID/SGID/sticky) | **The inode number** → also in the directory entry |
| **UID** (owner) and **GID** (group) | The file's **contents** → in data blocks |
| **File size** in bytes | |
| **Link count** (number of hard links) | |
| **Timestamps**: `atime` (last access), `mtime` (last data modification), `ctime` (last inode/metadata change) | |
| **Pointers to data blocks** — typically 12 direct, 1 single-indirect, 1 double-indirect, 1 triple-indirect | |
| Number of blocks allocated | |

**There is no `ctime` = "creation time"** — `ctime` is *change* time (inode changed). Classic
MCQ trap. Traditional UNIX file systems store **no creation time at all** (ext4 does store
`crtime`/birth time internally). This matters in forensics.

**Block addressing arithmetic (a favourite numerical).** With 12 direct pointers, one single-,
one double- and one triple-indirect pointer, a 4 KB block size and 4-byte block addresses:

- Addresses per block = 4096 / 4 = **1024**
- Direct: 12 × 4 KB = **48 KB**
- Single indirect: 1024 × 4 KB = **4 MB**
- Double indirect: 1024 × 1024 × 4 KB = **4 GB**
- Triple indirect: 1024³ × 4 KB = **4 TB**
- **Maximum file size ≈ 48 KB + 4 MB + 4 GB + 4 TB ≈ 4 TB**

### Worked example — how the kernel opens `/home/ravi/notes.txt`

This is a superb 10-mark answer because it ties the whole file system together. Narrate it:

1. Path begins with `/`, so start at the **root inode**, which is **inode number 2** by
   convention (inode 1 is reserved for bad blocks). The kernel knows this without searching.
2. Read root's inode → get its data blocks → read them as a directory table → look up the
   name `home` → find inode number, say 128.
3. Check the **execute (search) permission** on `/` for this user. If absent, stop with
   "Permission denied".
4. Read inode 128 → confirm it is a directory → read its data blocks → look up `ravi` → get
   inode 4501. Check search permission again.
5. Read inode 4501 → read its data blocks → look up `notes.txt` → get inode 5567.
6. Read inode 5567 → check **read permission** on the file itself → obtain the data block
   pointers → read the data.
7. Allocate a **file descriptor** in the process's file-descriptor table pointing to a system
   file-table entry pointing to the in-core inode. Return the descriptor (first free number,
   typically 3, since 0/1/2 are stdin/stdout/stderr).

The takeaway sentence to write down: *directory traversal requires the **execute** bit on
every directory in the path, and the read bit only on the final file.*

### Hard links vs symbolic links — table you must be able to reproduce

| | **Hard link** (`ln file link`) | **Symbolic / soft link** (`ln -s file link`) |
|---|---|---|
| What it is | An **additional directory entry** pointing to the same inode | A **separate file** whose data is a pathname |
| Inode number | **Same** as original | **Different** (its own inode) |
| Link count | **Increments** the original's count | Does **not** change the original's count |
| Across file systems | **Not allowed** (inode numbers are per-FS) | **Allowed** |
| To a directory | **Not allowed** (except `.` and `..`, made by the kernel) | **Allowed** |
| If original deleted | Link still works — data survives | Link **breaks** (dangling link) |
| Size | Same as file | Size = number of characters in the pathname |
| `ls -l` type char | `-` (indistinguishable from a normal file) | `l`, shown as `link -> target` |

Commands: `ls -i` shows inode numbers; `ls -li` shows inode + link count; `stat file` dumps
the full inode; `df -i` shows inode usage per file system; `find . -inum 5567` finds all names
for an inode.

### Likely exam questions

- **[5]** What is an inode? List the information stored in an inode.
- **[5]** Differentiate between hard links and soft links.
- **[5]** Why does deleting a file in UNIX not always free its disk space?
- **[10]** Explain the concept of an inode. Draw the inode structure showing direct and
  indirect block pointers and calculate the maximum file size for 4 KB blocks and 4-byte
  addresses.
- **[15]** Describe in detail how UNIX stores and locates a file. Explain directory entries,
  inodes, data blocks, and trace the resolution of the pathname `/home/ravi/notes.txt`.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "The file name is stored in the inode." | **False** — in the directory entry. |
| "ctime is creation time." | **False** — inode **change** time. |
| "Root directory inode number?" | **2**. |
| "Hard link across file systems?" | **Not possible**. |
| "Symbolic link to a directory?" | **Possible** (hard link is not). |
| "Which command shows inode number?" | **`ls -i`** or `stat`. |
| "Deleting the original breaks which link?" | **Symbolic link** (hard link still works). |
| "System call to delete a file?" | **`unlink`**. |

---

## 5. Ownership and permissions — including chmod calculations

> **This section is the highest-yield numerical content in the file.** It is explicitly named
> in the Computer Forensic syllabus ("Linux file system — Ownership and permissions") and
> implied throughout the Diploma UNIX unit. Expect both an MCQ ("`chmod 754` gives?") and a
> 10-mark question.

### Concept

Every file has exactly one **owner** (a UID) and exactly one **group** (a GID). When you try
to touch a file, the kernel classifies you into **exactly one** of three categories, and it
checks that category's permissions **only**:

1. Are you the **owner**? → use the **user (u)** permissions. Stop.
2. Else, are you in the file's **group**? → use the **group (g)** permissions. Stop.
3. Else → use the **other (o)** permissions.

The word "stop" carries a mark. If you are the owner and the owner has no read permission,
you **cannot read the file even if group and other can**. The checks are not cumulative and
not most-permissive — they are first-match. Students get this wrong constantly.

Each category has three permission bits: **r** (read = 4), **w** (write = 2), **x** (execute = 1).

### What the bits actually mean — files vs directories

The same letter means something quite different on a directory. This is the second most
common misunderstanding.

| Bit | On an **ordinary file** | On a **directory** |
|---|---|---|
| **r** (4) | Read/view/copy the contents | **List the names** in it (`ls`) — but not their attributes without `x` |
| **w** (2) | Modify contents, append, truncate | **Create, delete or rename entries** in it — *regardless of the permissions on those files themselves* |
| **x** (1) | Execute it as a program or script | **Search / traverse** it — enter it with `cd`, use it as part of a pathname |

Two consequences to state in an answer:

- You can **delete a file you cannot even read**, provided you have **w+x on its directory**.
  Deletion is a directory operation, not a file operation. This is the reason `/tmp` needs the
  sticky bit (below).
- `r` without `x` on a directory lets you see filenames but nothing else — `ls` works,
  `ls -l` shows `?????` , and `cd` fails.

### Reading `ls -l`

```
-rwxr-xr--  1  ravi  staff  4096  Sep  5 09:14  script.sh
│└┬┘└┬┘└┬┘  │   │      │      │        │            │
│ u   g  o  │  owner group  size    mtime        name
│           └── link count
└── file type
```

### Numeric (octal) mode — the calculation

Treat each triad as a 3-bit binary number: **r = 4, w = 2, x = 1**, and add.

| Octal | Binary | Symbolic | Meaning |
|---|---|---|---|
| 0 | 000 | `---` | no permission |
| 1 | 001 | `--x` | execute only |
| 2 | 010 | `-w-` | write only |
| 3 | 011 | `-wx` | write + execute |
| 4 | 100 | `r--` | read only |
| 5 | 101 | `r-x` | read + execute |
| 6 | 110 | `rw-` | read + write |
| 7 | 111 | `rwx` | all |

#### Worked example 1 — symbolic → numeric

`-rwxr-xr--`

| Triad | Bits | Arithmetic | Digit |
|---|---|---|---|
| user `rwx` | 111 | 4+2+1 | **7** |
| group `r-x` | 101 | 4+0+1 | **5** |
| other `r--` | 100 | 4+0+0 | **4** |

**Answer: 754.** Command: `chmod 754 script.sh`

#### Worked example 2 — numeric → symbolic

`chmod 640 report.txt`

| Digit | Binary | Symbolic |
|---|---|---|
| 6 | 110 | `rw-` |
| 4 | 100 | `r--` |
| 0 | 000 | `---` |

**Answer: `-rw-r-----`** — owner reads and writes, group reads, others nothing. This is the
standard mode for a private document. (`/etc/shadow` is 640 or 600 for exactly this reason.)

#### Worked example 3 — the classic set

| Mode | Symbolic | Typical use |
|---|---|---|
| **777** | `rwxrwxrwx` | Everything to everyone — a security hole; never use |
| **755** | `rwxr-xr-x` | Executables, scripts, and **directories** — owner full, everyone else read+traverse |
| **754** | `rwxr-xr--` | As above but others may only read |
| **700** | `rwx------` | Private directory (e.g. `~/.ssh`) |
| **666** | `rw-rw-rw-` | Everyone can edit a data file; no execute |
| **644** | `rw-r--r--` | **Default for ordinary files** — owner writes, world reads |
| **640** | `rw-r-----` | Group-private document |
| **600** | `rw-------` | Private file (e.g. `~/.ssh/id_rsa`; SSH *refuses* to use a key that is more open) |
| **444** | `r--r--r--` | Read-only for all |
| **000** | `---------` | No access (root still bypasses everything) |

#### Worked example 4 — symbolic chmod (relative changes)

Syntax: `chmod [who][operator][permission] file`
- **who**: `u` user, `g` group, `o` other, `a` all (default if omitted)
- **operator**: `+` add, `-` remove, `=` set exactly (clears the rest)

Start with `report.txt` at **`-rw-r--r--` (644)**.

| Command | Effect | Resulting mode |
|---|---|---|
| `chmod u+x report.txt` | add execute for owner | `-rwxr--r--` = **744** |
| `chmod go-r report.txt` | remove read from group and other | `-rwx------` = **700** |
| `chmod a+r report.txt` | add read for all | `-rwxr--r--` = **744** |
| `chmod g=rw report.txt` | set group to exactly rw (x cleared) | `-rwxrw-r--` = **764** |
| `chmod o= report.txt` | set other to nothing | `-rwxrw----` = **760** |
| `chmod 755 report.txt` | absolute set | `-rwxr-xr-x` = **755** |

Note the difference between `+`/`-` (relative, leave other bits alone) and `=` (absolute for
that category). `chmod -R 755 dir` applies recursively.

#### Worked example 5 — umask

New files are **not** created with 777. The shell's **umask** is a mask of bits to *remove*.

- Default **base** permission: **666** for ordinary files, **777** for directories.
  (Files never get execute by default — a deliberate safety decision.)
- Effective permission = **base AND NOT umask**, which for exam purposes you compute as
  **base − umask** (digit-wise subtraction, never going below 0).

With the common default **umask 022**:

| | File | Directory |
|---|---|---|
| Base | 666 | 777 |
| umask | 022 | 022 |
| **Result** | **644** (`rw-r--r--`) | **755** (`rwxr-xr-x`) |

With **umask 027**:

| | File | Directory |
|---|---|---|
| Base | 666 | 777 |
| umask | 027 | 027 |
| **Result** | **640** (`rw-r-----`) | **750** (`rwxr-x---`) |

With **umask 077** (maximum privacy): files **600**, directories **700**.

**Careful with the subtraction shortcut.** It is really a bitwise AND-NOT. Take base 666 and
umask 033: naive subtraction gives 633, but the true answer is 666 AND NOT 033:
6 = 110, mask 3 = 011, NOT 011 = 100, 110 AND 100 = 100 = **4**. So the answer is **644**, not
633. Rule: *the mask can only remove bits that are present.* Since 6 (`rw-`) has no execute
bit, masking out execute changes nothing. Subtraction only works when no digit would go
negative and no absent bit is being removed — with umask 022 and 027 it is safe, with odd
digits against 6 it is not. **Always do the binary version if any digit is odd.**

Set it with `umask 027`; display it with `umask` (or `umask -S` for symbolic).

#### Worked example 6 — special permission bits

Beyond the nine bits there are three more, giving a **four-digit** octal mode `chmod 4755`.

| Bit | Octal | Symbol in `ls -l` | Meaning |
|---|---|---|---|
| **SUID** (Set User ID) | **4000** | `s` in the **user** execute position (`-rwsr-xr-x`) | While running, the process takes the **owner's** effective UID, not the caller's |
| **SGID** (Set Group ID) | **2000** | `s` in the **group** execute position (`-rwxr-sr-x`) | On a file: run with the file's group. **On a directory: new files inherit the directory's group** — used for shared project directories |
| **Sticky bit** | **1000** | `t` in the **other** execute position (`drwxrwxrwt`) | On a directory: **only the file's owner (or root) may delete or rename** entries in it, even though everyone can write. This is what makes world-writable `/tmp` safe |

Worked: `chmod 4755 /usr/bin/passwd` → `-rwsr-xr-x`. Why does `passwd` need it? Because
changing your password means writing to `/etc/shadow`, which is owned by root and mode 640.
An ordinary user cannot write it. SUID-root on `/usr/bin/passwd` means the *program* runs as
root for its lifetime, does the one controlled edit, and exits. **SUID binaries are therefore
the number-one privilege-escalation target** — a Forensic-paper point. Find them with:

```sh
find / -perm -4000 -type f 2>/dev/null      # all SUID files
find / -perm -2000 -type f 2>/dev/null      # all SGID files
```

If the corresponding execute bit is **absent**, the letter appears as a **capital** `S` or
`T` — a classic MCQ. `-rwSr--r--` means SUID set but owner has no execute (meaningless, and a
red flag).

### Ownership commands

| Command | Purpose | Example |
|---|---|---|
| `chown` | Change **owner** (root only, in practice) | `chown ravi file.txt` |
| `chown user:group` | Change owner **and** group at once | `chown ravi:staff file.txt` |
| `chown -R` | Recursively | `chown -R ravi:staff /project` |
| `chgrp` | Change **group** only | `chgrp staff file.txt` |
| `chmod` | Change **permissions** | `chmod 755 file.txt` |
| `umask` | Set default permission mask | `umask 022` |
| `id` | Show your UID, GID, groups | `id ravi` |
| `groups` | Show group memberships | `groups ravi` |
| `su` | Switch user | `su - ravi` |
| `sudo` | Run a single command as another user (config `/etc/sudoers`, edit via `visudo`) | `sudo apt update` |
| `passwd` | Change password | `passwd ravi` |
| `useradd` / `userdel` / `usermod` | Manage accounts | `useradd -m -s /bin/bash ravi` |

**Only the owner of a file or root can change its permissions** — even a user with write
permission cannot. And **root bypasses all permission checks** (except, on most systems, the
execute bit if nobody has it).

### Likely exam questions

- **[5]** Explain the UNIX file permission system with reference to user, group and other.
- **[5]** What is the significance of `chmod 754`? Show the calculation.
- **[5]** What is umask? If umask is 027, what are the default permissions of a newly created
  file and directory? Show the working.
- **[5]** Explain SUID, SGID and the sticky bit with one example each.
- **[10]** Describe file ownership and permissions in UNIX. Explain both symbolic and numeric
  modes of `chmod` with at least four worked examples, and explain how permissions differ in
  meaning for files and directories.
- **[15]** Explain the security model of the UNIX file system: ownership, the three permission
  categories and the first-match rule, the nine permission bits, the three special bits, umask,
  and how SUID programs such as `passwd` work and why they are a security risk.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "`chmod 754`?" | `rwxr-xr--`. |
| "`rw-r-----` in octal?" | **640**. |
| "Default umask 022 → new *file* permission?" | **644** (not 755 — files have no default execute). |
| "Default umask 022 → new *directory* permission?" | **755**. |
| "Owner is denied but group allowed — can the owner read?" | **No.** First-match, checks stop at owner. |
| "Can you delete a read-only file?" | **Yes**, if you have `w`+`x` on the directory. |
| "`t` at the end of `drwxrwxrwt`?" | **Sticky bit** (`/tmp`). |
| "SUID octal value?" | **4000**. SGID **2000**, sticky **1000**. |
| "Which permission lets you `cd` into a directory?" | **execute (x)**, not read. |
| "Who can change a file's permissions?" | **The owner or root** only. |
| "Value of `r`?" | **4**. (`w`=2, `x`=1.) |
| "Capital `S` in permission string?" | SUID set **without** the underlying execute bit. |

---

## 6. Booting, login, startup and shutdown

### Concept

From power-on to a login prompt, control is handed along a chain, and each link only knows
enough to find and start the next one. The chain gets shorter every step in terms of hardware
knowledge and longer in terms of capability.

### The booting procedure — six stages (learn the names in order)

| # | Stage | What happens |
|---|---|---|
| 1 | **BIOS / UEFI** | Firmware in ROM wakes up. Runs **POST** (Power-On Self Test) — checks CPU, RAM, keyboard, devices. Reads the boot-device order from CMOS. Loads the first sector of the chosen device into memory. |
| 2 | **MBR / boot sector** | The **Master Boot Record** is the first 512 bytes of the disk: 446 bytes of bootstrap code + 64 bytes partition table (4 entries × 16 B) + 2-byte magic number `0x55AA`. It locates and loads the boot loader. (GPT/UEFI systems use an EFI System Partition instead.) |
| 3 | **Boot loader** | **GRUB / GRUB2** (or LILO historically, or `boot` on classic UNIX). Presents the kernel menu, loads the kernel image `/boot/vmlinuz` and the **initrd / initramfs** (a temporary root file system holding the drivers needed to mount the real root) into memory. Passes kernel parameters. |
| 4 | **Kernel initialisation** | Kernel decompresses itself, initialises memory management and the scheduler, detects and initialises hardware, loads drivers, mounts the **root file system** (read-only first, then read-write), and then creates the very first process. |
| 5 | **init / systemd** | The kernel starts **`/sbin/init`** — **PID 1**, the ancestor of every other process. Classic SysV init reads **`/etc/inittab`**, determines the **default runlevel**, and runs the scripts in `/etc/rc.d/rcN.d/`. Modern Linux uses **systemd** (targets instead of runlevels) or Upstart. |
| 6 | **Getty & login** | init spawns a **`getty`** on each terminal, which prints the `login:` prompt and hands over to **`/bin/login`**. |

Draw this as a **vertical flowchart of six boxes with downward arrows**, annotating box 4 with
"kernel loaded into memory, stays resident" and box 5 with "PID 1".

### Runlevels (SysV) — a table examiners love

| Runlevel | Meaning |
|---|---|
| **0** | **Halt / shutdown** |
| **1** or `S`/`s` | **Single-user mode** — maintenance, root only, no networking |
| 2 | Multi-user **without** networking/NFS (Debian: full multi-user with GUI) |
| 3 | **Full multi-user, text/console mode** with networking |
| 4 | Unused / user-definable |
| **5** | Full multi-user with **GUI** (X11 / display manager) |
| **6** | **Reboot** |

Commands: `runlevel` (shows previous and current), `init 3` / `telinit 3` to change,
`who -r`. systemd equivalents: `multi-user.target` (≈3), `graphical.target` (≈5),
`rescue.target` (≈1); manage with `systemctl`.

### The login process

1. `getty` opens a terminal device and displays `login:`.
2. User types a username; `getty` execs **`/bin/login`**, which prompts for `Password:` with
   **echo disabled**.
3. `login` looks up the user in **`/etc/passwd`**, and the password hash in **`/etc/shadow`**.
4. It hashes the typed password with the **salt** stored alongside the hash and compares. It
   never decrypts anything — the stored value is a **one-way hash** (crypt/MD5/SHA-512/yescrypt).
5. On failure: generic "Login incorrect" (deliberately not saying which field was wrong),
   logged to `/var/log/btmp` and `auth.log`. Three failures typically drop the connection.
6. On success it:
   - sets UID and GID from fields 3 and 4 of `/etc/passwd`,
   - changes directory to the **home directory** (field 6),
   - executes the **login shell** (field 7),
   - records the session in `/var/run/utmp` and `/var/log/wtmp`,
   - prints `/etc/motd` (message of the day) and mail notification.
7. The shell then runs the **initialisation files** in order:

| Scope | Bourne/bash login shell | Read when |
|---|---|---|
| System-wide | `/etc/profile` | Every login |
| User | `~/.bash_profile` → else `~/.bash_login` → else `~/.profile` | Login shells only |
| User (non-login/interactive) | `~/.bashrc` | Every new interactive shell |
| Logout | `~/.bash_logout` | On exit |

(csh uses `.login`, `.cshrc`, `.logout`.) Forensically, `~/.bashrc` and `~/.bash_profile` are
common persistence locations for attackers.

### The `/etc/passwd` record — seven colon-separated fields

```
ravi : x : 1001 : 1001 : Ravi Kumar,,, : /home/ravi : /bin/bash
  1     2    3      4          5             6           7
```

| # | Field | Note |
|---|---|---|
| 1 | Username | |
| 2 | Password placeholder | **`x`** means the hash is in `/etc/shadow`. An empty field means **no password** — a red flag |
| 3 | **UID** | **0 = root**. 1–999 system accounts; 1000+ ordinary users (500+ on older RHEL) |
| 4 | GID | Primary group |
| 5 | GECOS / comment | Full name, office, phone |
| 6 | Home directory | |
| 7 | **Login shell** | `/sbin/nologin` or `/bin/false` = account cannot log in |

**Any account with UID 0 is root**, whatever it is called — the single most important line to
grep for in a Linux forensic examination.

### Startup and shutdown commands

| Command | Effect |
|---|---|
| `shutdown -h now` | Halt immediately |
| `shutdown -h +10 "message"` | Halt in 10 minutes, broadcasting a warning to all users |
| `shutdown -r now` | Reboot immediately |
| `shutdown -c` | Cancel a pending shutdown |
| `halt` | Stop the CPU (may not power off) |
| `poweroff` | Halt and cut power |
| `reboot` | Restart |
| `init 0` / `init 6` | Shutdown / reboot via runlevel |
| `sync` | Flush buffered disk writes to disk — traditionally typed **before** halting |
| `systemctl poweroff` / `reboot` / `rescue` | systemd equivalents |

Why `shutdown` and not just pulling the plug: UNIX **buffers** disk writes in memory. An
orderly shutdown warns users, kills processes with **SIGTERM** then **SIGKILL**, unmounts
file systems, and syncs the buffer cache. Yanking power leaves the file system **dirty**,
forcing a `fsck` at next boot and risking data loss. Say this in a 5-mark answer.

### Likely exam questions

- **[5]** Explain the stages of the UNIX booting procedure.
- **[5]** Describe the login process in UNIX.
- **[5]** Explain the fields of the `/etc/passwd` file.
- **[5]** What are runlevels? Tabulate runlevels 0–6.
- **[5]** Why must a UNIX system be shut down properly? List the shutdown commands.
- **[10]** With a neat flowchart, explain the complete boot sequence of a UNIX/Linux system
  from power-on to the shell prompt, including the role of BIOS, MBR, GRUB, the kernel, init
  and getty.
- **[15]** Explain booting, the login process, password verification and shell initialisation
  in UNIX, including the roles of `/etc/passwd`, `/etc/shadow`, `/etc/profile` and `~/.bashrc`.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "First process created by the kernel?" | **`init`** (or `systemd`), **PID 1**. |
| "PID 0?" | The **scheduler / swapper** — not init. |
| "Which runlevel is single-user?" | **1**. Halt is **0**, reboot is **6**. |
| "Size of MBR?" | **512 bytes**. |
| "Which prints the login prompt?" | **`getty`**. |
| "Where are password hashes?" | **`/etc/shadow`**. |
| "UID of root?" | **0**. |
| "POST is done by?" | **BIOS/UEFI firmware**. |
| "What does `sync` do?" | Flushes buffers to disk. |
| "`init 6` does?" | **Reboot** (students often say shutdown). |

---

## 7. Essential commands — organised by purpose

> **This is the MCQ engine room.** Revise the tables; do not try to memorise every option.
> Learn each command's *one-line purpose* first, then the two or three options that get asked.

### 7.1 Navigation and directory management

| Command | Purpose | Key options / examples |
|---|---|---|
| `pwd` | **P**rint **w**orking **d**irectory | `pwd` → `/home/ravi` |
| `cd` | Change directory | `cd /etc`; `cd ..` (parent); `cd` or `cd ~` (home); `cd -` (previous directory); `cd /` (root) |
| `ls` | List directory contents | `-l` long listing; `-a` all incl. hidden; `-A` hidden but not `.`/`..`; `-i` inode; `-R` recursive; `-t` sort by mtime; `-r` reverse; `-S` sort by size; `-h` human-readable sizes; `-d` the directory itself not contents; `-F` append type indicator (`/` dir, `*` exec, `@` link) |
| `mkdir` | Make directory | `mkdir docs`; `mkdir -p a/b/c` (**create parents as needed**); `mkdir -m 755 dir` |
| `rmdir` | Remove directory — **only if empty** | `rmdir docs`; `rmdir -p a/b/c` |
| `tree` | Show directory tree graphically | `tree -L 2` |

`md` appears in the Diploma syllabus — it is the DOS name and, on UNIX, only exists if
someone has aliased it; the real command is **`mkdir`**. Mention both in an answer.

**Absolute vs relative paths** — worth a 2-mark definition: an **absolute** path starts at
`/` and is unambiguous (`/home/ravi/notes.txt`); a **relative** path starts from the current
directory (`docs/notes.txt`, `../ravi/notes.txt`). Shorthands: `.` current, `..` parent,
`~` your home, `~ravi` ravi's home, `-` previous directory.

### 7.2 File creation, display and management

| Command | Purpose | Key options / examples |
|---|---|---|
| `cat` | **Cat**enate and display files; also create small files | `cat f1` display; `cat f1 f2 > f3` **concatenate**; `cat > new` create (end with **Ctrl+D**); `cat >> f` append; `-n` number all lines; `-b` number non-blank lines; `-A`/`-v` show non-printing chars; `-s` squeeze blank lines |
| `touch` | Create an empty file / update timestamps | `touch f`; `-t 202609051200 f` set specific time (note: **anti-forensic timestomping**) |
| `cp` | Copy | `cp src dst`; `cp f1 f2 dir/`; `-r`/`-R` **recursive** (required for directories); `-i` interactive prompt; `-p` **preserve** mode/owner/timestamps; `-a` archive (= `-dpR`); `-u` only if newer; `-v` verbose |
| `mv` | **Move or rename** (there is no separate `rename`) | `mv old new` rename; `mv f dir/` move; `-i` prompt; `-f` force; `-n` no-clobber |
| `rm` | Remove file | `rm f`; `-i` confirm; `-r` recursive (directories); `-f` force, no prompt, ignore missing. **`rm -rf /` is catastrophic** |
| `ln` | Create link | `ln f hard`; `ln -s f soft` |
| `file` | Identify file type by magic number | `file report` → `ASCII text` |
| `stat` | Display full inode information | `stat f` |
| `du` | **D**isk **u**sage by file/directory | `du -sh dir` (summary, human-readable) |
| `df` | **D**isk **f**ree by file system | `df -h`; `df -i` (inodes) |
| `find` | Search the hierarchy by attribute | `find /home -name "*.log"`; `-type f/d/l`; `-size +10M`; `-mtime -7` (modified in last 7 days); `-user ravi`; `-perm -4000`; `-exec rm {} \;` |
| `locate` | Fast filename search via a prebuilt database | `locate passwd` (update with `updatedb`) |
| `which` / `whereis` | Locate an executable in `PATH` / locate binary+source+man | `which ls`; `whereis ls` |
| `tar` | Archive | `tar -cvf a.tar dir` create; `-xvf` extract; `-tvf` list; `-z` gzip, `-j` bzip2 |
| `gzip`/`gunzip`, `zip`/`unzip`, `bzip2` | Compression | `gzip f` → `f.gz` |

### 7.3 File processing / filter commands — **the big Diploma list**

A **filter** is a command that reads from **standard input**, transforms, and writes to
**standard output** — so it can sit in the middle of a pipeline. `grep`, `sort`, `wc`, `cut`,
`tr`, `head`, `tail`, `uniq`, `sed`, `awk`, `more`, `less`, `tee` are filters. `ls`, `cp`,
`mv`, `rm`, `mkdir` are **not** filters (they don't read stdin).

| Command | Purpose | Key options / examples |
|---|---|---|
| **`wc`** | **W**ord **c**ount — prints **lines, words, characters** (in that order) | `wc f` → `12 84 512 f`; `-l` lines only; `-w` words; `-c` bytes; `-m` characters; `-L` longest line |
| **`head`** | First part of a file — **default 10 lines** | `head f`; `head -5 f` or `head -n 5 f`; `-c 100` first 100 bytes |
| **`tail`** | Last part — **default 10 lines** | `tail f`; `tail -20 f`; **`tail -f logfile`** follow a growing file (log monitoring); `tail +5 f` from line 5 onward |
| **`cut`** | Extract **columns / fields** from each line | `cut -c1-10 f` characters 1–10; `cut -d: -f1,7 /etc/passwd` fields 1 and 7 with `:` delimiter; `-d` delimiter (**default TAB**), `-f` field list |
| **`paste`** | Merge lines of files **side by side** (the horizontal opposite of `cat`) | `paste f1 f2`; `-d','` delimiter; `-s` serial (one file per line) |
| **`join`** | Relational join of two **sorted** files on a common field | `join f1 f2`; `-1 2 -2 1` join field 2 of file1 with field 1 of file2; `-t:` delimiter. **Both files must be sorted on the join field** |
| **`split`** | Split a file into fixed-size pieces | `split -l 100 big.txt part_` → `part_aa`, `part_ab`…; `-b 1M` by size |
| **`sort`** | Sort lines | `sort f`; `-r` reverse; `-n` **numeric** (else "10" sorts before "9"); `-k2` by field 2; `-t:` field separator; `-u` unique; `-f` fold case; `-M` month; `-o out` write to file; `-c` check if sorted |
| **`grep`** | **G**lobal **R**egular **E**xpression **P**rint — search lines matching a pattern | `grep "error" f`; `-i` ignore case; `-v` **invert** (lines NOT matching); `-n` line numbers; `-c` count only; `-l` list filenames only; `-w` whole word; `-r`/`-R` recursive; `-A3 -B3 -C3` context lines; `-E` extended regex (= `egrep`); `-F` fixed strings (= `fgrep`) |
| **`egrep`** | Extended grep — supports `+ ? \| ( ) { }` without backslashes | `egrep "cat\|dog" f`; `egrep "[0-9]{3}" f`. Equivalent to `grep -E` |
| `fgrep` | Fixed-string grep, no regex — fastest | `fgrep "a.b" f` matches literal `a.b` |
| **`tr`** | **Tr**anslate or delete characters. Reads **only from stdin** | `tr 'a-z' 'A-Z' < f` lowercase→uppercase; `tr -d ' '` delete spaces; `tr -s ' '` squeeze repeats; `tr -c` complement |
| **`comm`** | **Comm**on — compare two **sorted** files, three columns: lines only in file1, only in file2, in both | `comm f1 f2`; `comm -12 f1 f2` show only common lines; `-1` suppress col 1, `-2` col 2, `-3` col 3 |
| **`cmp`** | Byte-by-byte comparison; reports the **first difference** (byte and line number). Works on **binary** files | `cmp f1 f2` → `f1 f2 differ: byte 17, line 2`; `-s` silent (exit status only) |
| **`diff`** | Line-by-line difference; reports **what to change** to make file1 into file2 | `diff f1 f2`; `-u` unified format; `-i` ignore case; `-y` side-by-side; `-r` recursive. Output codes **`a`** append, **`d`** delete, **`c`** change |
| **`more`** | Page through output, **forward only** (older) | `more f`; SPACE next page, ENTER next line, `q` quit, `/pat` search |
| **`less`** | Page through output, **forward and backward**, doesn't load whole file — "less is more" | `less f`; arrows, `b` back, `G` end, `g` start, `/pat`, `q` |
| `uniq` | Remove **adjacent** duplicate lines — must `sort` first | `sort f \| uniq`; `-c` prefix counts; `-d` only duplicates; `-u` only unique |
| `nl` | Number lines | `nl f` |
| `tee` | Write stdin to a file **and** to stdout | `ls \| tee out.txt \| wc -l`; `-a` append |
| `sed` | **S**tream **ed**itor — non-interactive editing | `sed 's/old/new/g' f`; `sed -n '5,10p' f`; `sed '/^$/d' f` delete blank lines; `-i` edit in place |
| `awk` | Pattern-scanning and field-processing language | `awk '{print $1,$3}' f`; `awk -F: '$3>1000 {print $1}' /etc/passwd`; `awk 'END{print NR}' f` |

#### Worked pipeline examples (excellent 5-mark answers)

| Task | Command |
|---|---|
| Count the number of users on the system | `wc -l < /etc/passwd` |
| List all login shells in use, no duplicates | `cut -d: -f7 /etc/passwd \| sort \| uniq` |
| Find all users with UID 0 (root equivalents) | `awk -F: '$3==0 {print $1}' /etc/passwd` |
| Top 5 largest files in a directory | `ls -lS \| head -6` |
| Count how many times "error" appears in a log | `grep -c "error" /var/log/syslog` |
| Find the 10 most frequent words in a file | `tr -cs 'A-Za-z' '\n' < f \| sort \| uniq -c \| sort -rn \| head -10` |
| Display lines 10 to 20 of a file | `head -20 f \| tail -11` or `sed -n '10,20p' f` |
| List currently logged-in users, sorted, unique | `who \| cut -d' ' -f1 \| sort -u` |
| Total disk usage of `.log` files | `find . -name "*.log" -exec du -ch {} + \| tail -1` |

**`cmp` vs `diff` vs `comm` — a guaranteed question:**

| | `cmp` | `diff` | `comm` |
|---|---|---|---|
| Compares | Byte by byte | Line by line | Line by line |
| Files must be sorted | No | No | **Yes** |
| Reports | **First** difference (byte, line) | **All** differences + how to fix | Three columns: unique-to-1, unique-to-2, common |
| Binary files | **Yes** | Poorly ("Binary files differ") | No |

### 7.4 File formatting and printing

| Command | Purpose | Key options |
|---|---|---|
| **`pr`** | Format a file for **printing**: paginate and add a header (date, filename, page number) and 5-line header + 5-line trailer margins | see the table below |
| **`lp`** | Send a file to the printer (System V) — returns a request id | `lp -d laser f`; `-n 3` copies; `-t "title"` |
| `lpr` | BSD equivalent | `lpr -P laser f` |
| `lpstat` / `lpq` | Show printer/queue status | `lpstat -t`, `lpq` |
| `cancel` / `lprm` | Cancel a print job | `cancel laser-42` |
| `fmt` | Simple paragraph reformatter | `fmt -w 60 f` |
| `nl` | Number lines before printing | |

**`pr` options — the Diploma syllabus says "`pr` with options", so know these:**

| Option | Effect |
|---|---|
| `-h "text"` | Use *text* as the **header** in place of the filename |
| `-l n` | Set **page length** to *n* lines (**default 66**) |
| `-w n` | Set **page width** to *n* columns (**default 72**) |
| `-n` | **Number** the lines |
| `-d` | **Double-space** the output |
| `-t` | **Suppress** the header and trailer entirely |
| `-o n` | **Offset** each line by *n* spaces (left margin) |
| `-k` | Produce output in *k* **columns** (e.g. `pr -3 f`) |
| `-m` | **Merge** files, printing them side by side in parallel columns |
| `+n` | Begin printing at **page n** |
| `-a` | With `-k`, fill columns across rather than down |

Example: `pr -h "Salary Report" -l 60 -n -d salary.txt | lp -d laser`
— paginate `salary.txt` with a custom header, 60-line pages, numbered and double-spaced, and
send the result to the laser printer.

### 7.5 Online help

| Command | Purpose | Example |
|---|---|---|
| **`man`** | Display the **man**ual page for a command | `man ls`; `man 5 passwd` (section 5); `man -k copy` keyword search; `man man` |
| `help` | **Shell built-in** help — works only for built-ins like `cd`, `echo`, `export` | `help cd`; `help` alone lists all built-ins |
| `info` | GNU hypertext documentation, usually fuller than man | `info coreutils` |
| `whatis` | One-line description from the man database | `whatis ls` |
| `apropos` | Search man page descriptions by keyword (= `man -k`) | `apropos network` |
| `--help` | Most GNU commands' own brief usage | `ls --help` |
| `type` | Tell whether a name is a built-in, alias, or file | `type cd` → "cd is a shell builtin" |

**Manual sections** — an MCQ favourite, because `man passwd` gives the *command* while
`man 5 passwd` gives the *file format*:

| Section | Contents |
|---|---|
| **1** | User commands (`ls`, `cp`) |
| 2 | System calls (`open`, `fork`) |
| 3 | Library functions (`printf`, `malloc`) |
| 4 | Special files / devices (`/dev/null`) |
| **5** | **File formats and conventions** (`/etc/passwd`, `fstab`) |
| 6 | Games |
| 7 | Miscellaneous / conventions |
| **8** | System administration commands (`mount`, `shutdown`) |
| 9 | Kernel routines |

Man page structure: NAME, SYNOPSIS, DESCRIPTION, OPTIONS, EXAMPLES, FILES, SEE ALSO, BUGS,
AUTHOR. Navigation inside `man` is `less`: SPACE, `b`, `/pattern`, `n`, `q`.

### 7.6 Mathematical commands

| Command | Purpose | Worked examples |
|---|---|---|
| **`bc`** | **B**asic **c**alculator — an arbitrary-precision interactive calculator language. **Integer arithmetic by default**; set `scale` for decimals | `echo "5+3" \| bc` → `8`<br>`echo "10/3" \| bc` → `3` (integer!)<br>`echo "scale=4; 10/3" \| bc` → `3.3333`<br>`echo "scale=2; sqrt(2)" \| bc -l` → `1.41`<br>`echo "obase=2; 25" \| bc` → `11001` (**decimal→binary**)<br>`echo "ibase=2; 11001" \| bc` → `25`<br>`echo "2^10" \| bc` → `1024`<br>`bc -l` loads the math library (`s()`, `c()`, `a()`, `l()`, `e()`) |
| **`expr`** | Evaluate a simple expression — **integer only**, arguments must be **space-separated** | `expr 5 + 3` → `8`<br>`expr 5 \* 3` → `15` (**`*` must be escaped** — the shell would glob it)<br>`expr 10 / 3` → `3`<br>`expr 10 % 3` → `1`<br>`x=$(expr $x + 1)` classic increment in old shell scripts<br>`expr length "hello"` → `5`<br>`expr substr "hello" 2 3` → `ell`<br>`expr index "hello" l` → `3` |
| **`factor`** | Print the **prime factorisation** of an integer | `factor 60` → `60: 2 2 3 5`<br>`factor 97` → `97: 97` (prime)<br>`factor 100` → `100: 2 2 5 5` |
| **`units`** | Interactive unit **conversion** | `units` then `You have: 10 km` / `You want: miles` → `* 6.2137119`<br>Non-interactive: `units "5 kg" "pounds"` → `* 11.023113` |
| `dc` | Reverse-Polish desk calculator | `echo "5 3 + p" \| dc` → `8` |
| `seq` | Generate a number sequence | `seq 1 5` → 1 2 3 4 5; `seq 0 2 10` step 2 |
| `$(( ))` | Shell **arithmetic expansion** — the modern replacement for `expr` | `echo $((5+3))` → `8`; `x=$((x+1))` |

**Note for MCQs:** the trap is that both `bc` (without `scale`) and `expr` do **integer**
division, so `10/3` is `3`, not `3.33`. And in `expr`, `expr 5+3` (no spaces) prints the
*string* `5+3`, not `8`.

### 7.7 Communication commands

| Command | Purpose | Example / notes |
|---|---|---|
| **`write`** | Send a message to **one** logged-in user's terminal, line by line, in real time. Terminate with **Ctrl+D** | `write ravi` then type; `write ravi pts/2` to a specific terminal. Fails if the recipient has `mesg n` |
| **`wall`** | **W**rite to **all** logged-in users — a broadcast. Usually reserved for the superuser (shutdown warnings) | `wall "System going down at 5 pm"`; `wall < message.txt` |
| **`mail`** / `mailx` | Send and read **electronic mail**; store-and-forward, so the recipient need not be logged in | Send: `mail -s "Subject" ravi < body.txt`, or `mail ravi` then type and end with **`.`** on a line by itself or Ctrl+D.<br>Read: `mail` then `n` next, `d` delete, `s file` save, `r` reply, `q` quit.<br>Mailbox: **`/var/spool/mail/<user>`** or `/var/mail/<user>` |
| **`mesg`** | Control whether others may `write` to your terminal | `mesg n` **deny**, `mesg y` allow, `mesg` show current state |
| `talk` | **Two-way** interactive split-screen chat (vs `write`, which is one-way) | `talk ravi@host` |
| `finger` | Display information about a user (login name, real name, idle time, last login) | `finger ravi` |
| `news` | Read system news items | `news -a` |
| `ssh` / `scp` / `sftp` | Secure remote login and file transfer (replaced insecure `telnet`, `rlogin`, `ftp`) | `ssh ravi@host`; `scp f ravi@host:/tmp` |

**`write` vs `mail` — a standard 5-mark comparison:**

| | `write` | `mail` |
|---|---|---|
| Recipient must be logged in | **Yes** | **No** |
| Delivery | Immediate, to the terminal | Stored in a mailbox, read later |
| Direction | One-way (both parties can run it for a conversation) | One-way, asynchronous |
| Scope | One user | One or many, local or remote |
| Blocked by | `mesg n` | Nothing |

### 7.8 System information and status

| Command | Purpose | Output / options |
|---|---|---|
| **`who`** | List **all users currently logged in** — name, terminal, login time, host | `who` → `ravi pts/0 Sep 5 09:14 (192.168.1.5)`; `who -H` headings; `who -q` count only; **`who -r`** runlevel; `who -b` last boot time |
| **`who am i`** | Show **just your own** login line (i.e. `who` filtered to your terminal). Equivalent to `who -m`. Shows the **login/real** user | `who am i` → `ravi pts/0 Sep 5 09:14` |
| `whoami` | Print only the **effective** username — one word, no other fields | `whoami` → `ravi` |
| `w` | Who is logged in **and what they are running**, plus load average and idle time | `w` |
| `users` | Space-separated list of logged-in usernames | `users` |
| **`tty`** | Print the **filename of the terminal** connected to standard input | `tty` → `/dev/pts/0`; `tty -s` silent (script test) |
| **`date`** | Display or set the system date and time | `date` → `Sat Sep 5 09:14:03 IST 2026`<br>`date +"%d-%m-%Y"` → `05-09-2026`<br>`date +"%H:%M:%S"`; `date +%s` epoch seconds; `date -s "..."` set (root only)<br>Formats: `%d` day, `%m` month, `%Y` 4-digit year, `%y` 2-digit, `%H` hour, `%M` minute, `%S` second, `%A` weekday name, `%B` month name, `%j` day of year |
| **`cal`** | Display a **calendar** | `cal` current month; `cal 2026` whole year; **`cal 9 2026`** September 2026 (**month first, then year**); `cal -3` prev/current/next; `cal -y` |
| `uname` | System information | `uname -a` all; `-s` kernel name; `-r` **kernel release**; `-n` hostname; `-m` machine hardware |
| `hostname` | Show/set the system name | |
| `uptime` | How long the system has been up + load averages (1, 5, 15 min) | |
| `id` | Current UID, GID and groups | `id` → `uid=1001(ravi) gid=1001(ravi) groups=...` |
| `logname` | The name the user logged in with | |
| `last` | Login history (from `/var/log/wtmp`) — **forensic gold** | `last`, `last ravi`, `last -x` (shutdowns/runlevels) |
| `free` | Memory usage | `free -h` |
| `df` / `du` | Disk free / disk usage | `df -h`, `du -sh *` |
| `history` | Previously typed commands | `history 20`, `!45` re-run, `!!` last command |
| `echo` | Display a line of text or a variable | `echo "Hello"`, `echo $HOME`, `echo -n` no newline, `echo -e` interpret escapes |
| `clear` | Clear the terminal screen | |
| `exit` / `logout` / Ctrl+D | End the session | |

**`who` vs `who am i` vs `whoami`** is asked almost every year:
- `who` → **everyone** logged in.
- `who am i` → **one line** about you, in `who` format (terminal, time, host).
- `whoami` → **one word**, your effective username. After `su - root`, `whoami` prints
  **root** but `who am i` still prints your **original login name** — the difference between
  effective and real identity, and a genuinely useful forensic distinction.

### 7.9 The vi editor (three modes — a standard 5-marker)

| Mode | Entered by | Purpose |
|---|---|---|
| **Command mode** | Default on opening; **Esc** from anywhere | Navigation and manipulation — keystrokes are commands, not text |
| **Insert / Input mode** | `i` insert before cursor, `a` append after, `o` open line below, `O` above, `I` start of line, `A` end of line | Typing text |
| **Ex / Last-line / Escape mode** | `:` from command mode | File-level commands: `:w` save, `:q` quit, `:wq` or `ZZ` save+quit, `:q!` quit discarding, `:set nu` line numbers, `:%s/old/new/g` global substitute, `:1,10d` delete lines |

Command-mode essentials: `h j k l` (left/down/up/right), `x` delete char, `dd` delete line,
`3dd` delete 3 lines, `yy` yank/copy line, `p` paste, `u` undo, `.` repeat, `G` last line,
`1G`/`gg` first line, `/pat` search forward, `n` next match.

### 7.10 Master quick-reference table (last-night revision)

| Command | One-line purpose |
|---|---|
| `pwd` | Print working directory |
| `cd` | Change directory |
| `ls` | List directory contents |
| `mkdir` | Create directory |
| `rmdir` | Remove **empty** directory |
| `cat` | Display / create / concatenate files |
| `touch` | Create empty file, update timestamp |
| `cp` | Copy files/directories |
| `mv` | Move or rename |
| `rm` | Delete files (`-r` for directories) |
| `ln` | Create hard/symbolic link |
| `file` | Identify file type |
| `find` | Search hierarchy by attribute |
| `wc` | Count **lines, words, characters** |
| `head` | First 10 lines |
| `tail` | Last 10 lines (`-f` follow) |
| `cut` | Extract columns/fields |
| `paste` | Merge files side by side |
| `join` | Join two sorted files on a common field |
| `split` | Split a file into pieces |
| `sort` | Sort lines |
| `uniq` | Remove adjacent duplicates |
| `grep` | Search for a pattern |
| `egrep` | Extended-regex grep (`grep -E`) |
| `fgrep` | Fixed-string grep |
| `tr` | Translate/delete characters (stdin only) |
| `comm` | Compare two **sorted** files, 3 columns |
| `cmp` | Byte comparison, first difference |
| `diff` | Line differences and how to fix |
| `more` | Page forward |
| `less` | Page both ways |
| `tee` | Split output to file and screen |
| `sed` | Stream editor |
| `awk` | Field/pattern processing language |
| `pr` | Paginate/format for printing |
| `lp` | Print a file |
| `man` | Manual page |
| `help` | Help on shell built-ins |
| `whatis` / `apropos` | One-line description / keyword search |
| `bc` | Arbitrary-precision calculator |
| `expr` | Evaluate integer expression |
| `factor` | Prime factorisation |
| `units` | Unit conversion |
| `write` | Message one logged-in user |
| `wall` | Broadcast to all users |
| `mail` | Send/read email |
| `mesg` | Allow/deny messages to your terminal |
| `who` | All logged-in users |
| `who am i` | Your own login line |
| `whoami` | Your effective username |
| `tty` | Your terminal device file |
| `date` | Show/set date and time |
| `cal` | Display calendar |
| `uname` | System/kernel information |
| `uptime` | Uptime and load average |
| `ps` | Process status |
| `kill` | Send a signal to a process |
| `chmod` | Change permissions |
| `chown` / `chgrp` | Change owner / group |
| `umask` | Default permission mask |
| `su` / `sudo` | Switch user / run as another user |
| `shutdown` / `halt` / `reboot` | Stop or restart the system |
| `df` / `du` | Disk free / disk usage |
| `tar` / `gzip` | Archive / compress |
| `vi` | Visual editor |

### Likely exam questions (commands)

- **[5]** Explain any five file-processing commands in UNIX with syntax and an example.
- **[5]** Differentiate between `cmp`, `diff` and `comm`.
- **[5]** Explain the `pr` command with any five of its options.
- **[5]** What are mathematical commands in UNIX? Explain `bc`, `expr`, `factor` and `units`.
- **[5]** Explain the communication commands `write`, `wall` and `mail`.
- **[5]** Differentiate between `who`, `who am i` and `whoami`.
- **[10]** Explain, with syntax and examples, the UNIX file-processing commands `wc`, `head`,
  `tail`, `cut`, `paste`, `join`, `split`, `sort`, `grep`, `tr`, `comm`, `cmp` and `diff`.
- **[15]** Describe the essential UNIX commands grouped by purpose (navigation, file
  management, file processing, formatting/printing, help, mathematical, communication, system
  information), giving syntax and one example for each.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "`wc` output order?" | **lines, words, characters** — in that order. |
| "Default lines shown by `head`/`tail`?" | **10**. |
| "Which command removes a non-empty directory?" | **`rm -r`** — `rmdir` only removes empty ones. |
| "`grep -v`?" | **Invert** — show non-matching lines (not "verbose"). |
| "`cut` default delimiter?" | **TAB**, not space. |
| "Which requires sorted input?" | **`comm`** and **`join`** (not `diff`). |
| "`more` vs `less`?" | `less` scrolls **both** ways and does not load the whole file. |
| "`cal 2026` vs `cal 9 2026`?" | `cal 2026` = whole year; **month comes first**. |
| "`expr 5*3`?" | Error/literal — the `*` must be escaped: `expr 5 \* 3`. |
| "`echo 10/3 \| bc`?" | **3** — integer division unless `scale` is set. |
| "`tr` can take a filename argument?" | **No** — `tr` reads only stdin; use `tr ... < file`. |
| "Command to broadcast to all users?" | **`wall`**. |
| "`mkdir -p`?" | Create **parent** directories as needed. |
| "Which command counts only words?" | `wc -w`. |
| "`sort` without `-n` on numbers?" | Sorts **lexicographically** — "10" before "9". |
| "`man` section for file formats?" | **5**. |

---

## 8. Shell variables

### Concept

A shell variable is a name holding a string. What makes shells confusing is that there are
**two kinds**, and the difference is about *inheritance*:

- A **local (shell) variable** exists only in the current shell. If that shell starts a child
  process, the child does **not** see it.
- An **environment variable** has been **exported**. Every child process inherits a *copy*.

The classic exam sentence: **a child can never modify its parent's environment** — it only gets
a copy. That is precisely why a script that does `cd /tmp` leaves your shell where it was, and
why you must `source script` (or `. script`) to run it in the *current* shell instead of a child.

### Rules

- Assignment: `name=value` — **no spaces around `=`**. `name = value` is an error (the shell
  reads `name` as a command). This is an MCQ.
- Reference: `$name` or `${name}`. Braces are needed when adjacent text would be ambiguous:
  `${file}_backup`.
- Quoting matters enormously:

| Quoting | Behaviour | Example with `x=5` |
|---|---|---|
| `"double"` | Variables and command substitution **are** expanded | `echo "$x"` → `5` |
| `'single'` | Everything **literal** | `echo '$x'` → `$x` |
| `` `backquote` `` or `$( )` | **Command substitution** — replaced by the command's output | `d=$(date)` |
| `\` | Escape the next character | `echo \$x` → `$x` |

- Export: `export PATH=$PATH:/opt/bin` makes it environmental. `env` or `printenv` lists
  environment variables; `set` lists **all** variables including local ones and functions;
  `unset name` removes one; `readonly name` makes it immutable.

### Standard environment variables

| Variable | Meaning |
|---|---|
| **`PATH`** | Colon-separated list of directories searched for commands. `/usr/local/bin:/usr/bin:/bin`. **A `.` in PATH is a security risk** — an attacker leaving a malicious `ls` in a directory you `cd` into would get it run |
| **`HOME`** | Your home directory; the target of a bare `cd` |
| **`PS1`** | Primary prompt string (default `$` or `\u@\h:\w\$`) |
| `PS2` | Secondary/continuation prompt (default `>`) |
| **`SHELL`** | Path of your login shell |
| **`USER`** / `LOGNAME` | Your username |
| `PWD` / `OLDPWD` | Current / previous working directory |
| `TERM` | Terminal type (`xterm`, `vt100`) — used by `vi`, `clear` |
| `MAIL` | Path to your mailbox |
| `IFS` | **Internal Field Separator** — default space, tab, newline; how the shell splits words |
| `TZ` | Time zone |
| `EDITOR` / `VISUAL` | Default editor |
| `HISTSIZE` / `HISTFILE` | History length and file (`~/.bash_history`) |
| `LANG` / `LC_ALL` | Locale |

### Special (positional and status) variables — memorise this table

| Variable | Meaning |
|---|---|
| **`$0`** | Name of the **script itself** |
| **`$1` … `$9`** | Positional parameters (arguments). Beyond 9 use `${10}` |
| **`$#`** | **Number** of arguments passed |
| **`$*`** | All arguments as a **single** word ("a b c") |
| **`$@`** | All arguments as **separate** words ("a" "b" "c") — safer in loops |
| **`$?`** | **Exit status of the last command**: **0 = success**, non-zero = failure |
| **`$$`** | **PID of the current shell** |
| `$!` | PID of the last background command |
| `$-` | Current shell option flags |
| `shift` | Discards `$1` and shifts the rest down |

**`$?` = 0 means success** is counter-intuitive and therefore examined every time. Remember:
there is one way to succeed and many ways to fail, so 0 is reserved for success.

### Likely exam questions

- **[5]** What are shell variables? Distinguish between local and environment variables.
- **[5]** Explain any five environment variables in UNIX.
- **[5]** Explain the special shell variables `$0`, `$#`, `$?`, `$$` and `$*`.
- **[10]** Explain shell variables in UNIX: types, assignment and referencing rules, quoting,
  the `export` mechanism, standard environment variables and special variables, with examples.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "`x = 5` is valid?" | **No** — no spaces around `=`. |
| "`$?` returns 0 means?" | **Success**. |
| "`$$` is?" | **PID of current shell** (`$!` is the last background PID). |
| "`$#`?" | Number of arguments, **not including** `$0`. |
| "Difference between `$*` and `$@`?" | `$*` = one word; `$@` = separate words (when quoted). |
| "Which command lists only exported variables?" | **`env`** / `printenv` (`set` lists all). |
| "Variable inside single quotes?" | **Not expanded**. |
| "Can a child change the parent's environment?" | **No** — it gets a copy. |

---

## 9. Redirection, pipes and filters

### Concept

Every UNIX process starts life with **three open files**, identified by small integers called
**file descriptors**:

| FD | Name | Default connection |
|---|---|---|
| **0** | **stdin** — standard input | Keyboard |
| **1** | **stdout** — standard output | Screen/terminal |
| **2** | **stderr** — standard error | Screen/terminal |

Because they are just file descriptors, the shell can quietly reconnect them to files or to
each other **before** the program starts. The program never knows and never has to care —
this is the whole trick behind pipes and redirection, and it is the sentence to open a
10-mark answer with.

### Redirection operators

| Operator | Meaning |
|---|---|
| `>` | Redirect stdout to a file, **overwriting** (creates if absent, **truncates** if present) |
| `>>` | Redirect stdout to a file, **appending** |
| `<` | Take stdin **from** a file |
| `2>` | Redirect **stderr** |
| `2>>` | Append stderr |
| `&>` or `>file 2>&1` | Redirect **both** stdout and stderr to the same file |
| `2>&1` | Make stderr go wherever stdout is currently going |
| `1>&2` | Send stdout to stderr |
| `<<EOF` | **Here-document** — feed the following inline lines as stdin until `EOF` |
| `<<<"text"` | Here-string (bash) |
| `>/dev/null 2>&1` | Discard **all** output — `/dev/null` is the "bit bucket" |
| `\|` | **Pipe** — connect stdout of the left command to stdin of the right |
| `\|&` | Pipe both stdout and stderr (bash) |

**Order matters, and this is an examiner's favourite:** `cmd > file 2>&1` sends **both** to
the file, because stdout is redirected first and then stderr is pointed at the same place.
But `cmd 2>&1 > file` sends **stderr to the terminal** and stdout to the file, because when
`2>&1` executes, stdout was still the terminal. Read right-to-left in terms of effect.

### Pipes

A **pipe** (`|`) is an in-memory buffer connecting two processes. Both processes run
**concurrently**, not one after the other — the second starts consuming as the first produces.

```
who | wc -l          # how many users are logged in
ls -l | grep "^d"    # list only directories
cat f | sort | uniq -c | sort -rn | head -5
```

**Pipe vs redirection** (5-mark comparison):

| | Pipe `\|` | Redirection `>` `<` |
|---|---|---|
| Connects | Two **processes** | A process and a **file** |
| Intermediate file | None (memory buffer) | Yes |
| Concurrency | Both processes run simultaneously | Sequential |
| Direction | Always stdout → stdin | Either |

**`tee`** solves the "I want to see it *and* save it" problem: `ls -l | tee list.txt | wc -l`
writes the listing to `list.txt` while passing it on to `wc`.

### Filters

A **filter** reads stdin, transforms, writes stdout. That definition (worth stating verbatim)
is what makes a command usable in the middle of a pipeline. Standard filters: `cat`, `head`,
`tail`, `sort`, `uniq`, `grep`, `tr`, `cut`, `paste`, `wc`, `sed`, `awk`, `tee`, `more`,
`less`, `nl`, `pr`, `rev`, `fmt`. Non-filters: `ls`, `cp`, `mv`, `rm`, `mkdir`, `date`, `who`
(they generate or act but do not read stdin).

### Wildcards / metacharacters (shell globbing)

Expansion is done by **the shell, not the command** — by the time `ls` runs, it has already
been handed the expanded list of names. State this; it is a mark.

| Metachar | Matches |
|---|---|
| `*` | Any string of **zero or more** characters (but **not** a leading dot) |
| `?` | Exactly **one** character |
| `[abc]` | Any **one** of the listed characters |
| `[a-z]`, `[0-9]` | Any one character in the range |
| `[!abc]` or `[^abc]` | Any one character **not** listed |
| `{a,b,c}` | Brace expansion — generates `a b c` (not a wildcard; no file need exist) |
| `~` | Home directory |
| `;` | Command separator (run sequentially regardless of success) |
| `&&` / `\|\|` | Run next only if previous succeeded / failed |
| `&` | Run in background |
| `\` | Escape |

Examples: `ls *.txt`; `rm file?.log`; `ls [a-c]*`; `cp *.{jpg,png} images/`.

### Likely exam questions

- **[5]** What are standard input, standard output and standard error? Give their file
  descriptor numbers.
- **[5]** Explain input and output redirection in UNIX with examples.
- **[5]** What is a pipe? Differentiate between a pipe and redirection.
- **[5]** Define a filter. Name any six filter commands.
- **[10]** Explain redirection, pipes and filters in UNIX with suitable examples, including
  how to redirect standard error and how `tee` works.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "File descriptor of stderr?" | **2** (stdin 0, stdout 1). |
| "`>` on an existing file?" | **Overwrites/truncates** it. Use `>>` to append. |
| "Which discards output?" | `> /dev/null`. |
| "Who expands `*`?" | **The shell**, before the command runs. |
| "Does `*` match hidden files?" | **No** — not a leading dot. |
| "Does `ls > f` redirect errors too?" | **No** — only stdout. Need `2>&1`. |
| "In a pipe, do the commands run sequentially?" | **No** — concurrently. |

---

## 10. Basic shell scripting

### Concept

A shell script is a plain text file of commands. Two things make it a program rather than a
list: the **shebang** and the **execute bit**.

```sh
#!/bin/bash
# The first two characters must be #! and it must be line 1.
# The kernel reads them and runs /bin/bash with this file as its argument.
```

Then `chmod +x script.sh` and run it as `./script.sh` (the `./` is needed because `.` is
normally **not** in `PATH`, deliberately). Alternatively `bash script.sh` (shebang ignored) or
`. script.sh` / `source script.sh` (runs in the **current** shell, so variable and `cd`
changes persist).

### Constructs

```sh
# --- variables and input ---
name="Ravi"
read -p "Enter your age: " age

# --- conditionals ---
if [ $age -ge 18 ]; then
    echo "$name is an adult"
elif [ $age -ge 13 ]; then
    echo "$name is a teenager"
else
    echo "$name is a child"
fi

# --- case ---
case $choice in
    1) echo "One" ;;
    2|3) echo "Two or three" ;;
    *) echo "Invalid" ;;
esac

# --- loops ---
for i in 1 2 3 4 5; do echo "Number $i"; done
for f in *.txt; do echo "Found $f"; done
for ((i=1; i<=5; i++)); do echo $i; done

count=1
while [ $count -le 5 ]; do
    echo $count
    count=$((count+1))
done

until [ $count -gt 10 ]; do count=$((count+1)); done

# --- function ---
greet() {
    echo "Hello, $1"
    return 0
}
greet "World"
```

### Test operators — a table you should be able to reproduce

| Numeric | Meaning | | String | Meaning | | File | Meaning |
|---|---|---|---|---|---|---|---|
| `-eq` | equal | | `=` | equal | | `-e` | exists |
| `-ne` | not equal | | `!=` | not equal | | `-f` | is a **regular file** |
| `-gt` | greater than | | `-z` | **zero length** | | `-d` | is a **directory** |
| `-ge` | ≥ | | `-n` | **non-zero** length | | `-r` `-w` `-x` | readable/writable/executable |
| `-lt` | less than | | `<` `>` | lexical order | | `-s` | size greater than zero |
| `-le` | ≤ | | | | | `-L` | is a symbolic link |

Combine with `-a` (and), `-o` (or), `!` (not) inside `[ ]`, or `&&`/`||` between `[[ ]]`.
**Spaces inside the brackets are mandatory**: `[ $a -eq $b ]`, never `[$a -eq $b]` — `[` is
literally a command (`/usr/bin/[`), so it needs to be a separate word. That is a superb MCQ
explanation to give.

### Worked script examples

**1. Sum of command-line arguments and argument checking**

```sh
#!/bin/bash
if [ $# -eq 0 ]; then
    echo "Usage: $0 num1 num2 ..."
    exit 1
fi
sum=0
for n in "$@"; do
    sum=$((sum + n))
done
echo "Number of arguments: $#"
echo "Sum = $sum"
```

**2. Check whether a file exists and report its type**

```sh
#!/bin/bash
read -p "Enter filename: " f
if [ ! -e "$f" ]; then
    echo "$f does not exist"; exit 1
elif [ -d "$f" ]; then
    echo "$f is a directory"
elif [ -f "$f" ]; then
    echo "$f is a regular file, $(wc -l < "$f") lines"
fi
[ -r "$f" ] && echo "readable"
[ -w "$f" ] && echo "writable"
```

**3. Factorial (demonstrates a loop and arithmetic)**

```sh
#!/bin/bash
read -p "Enter a number: " n
fact=1
for ((i=2; i<=n; i++)); do
    fact=$((fact * i))
done
echo "Factorial of $n is $fact"
```

**4. Menu-driven script (a very common exam ask)**

```sh
#!/bin/bash
while true; do
    echo "1. Date  2. Users  3. Directory listing  4. Exit"
    read -p "Choice: " ch
    case $ch in
        1) date ;;
        2) who ;;
        3) ls -l ;;
        4) exit 0 ;;
        *) echo "Invalid choice" ;;
    esac
done
```

### Likely exam questions

- **[5]** What is a shell script? How is it created and executed?
- **[5]** Write a shell script to find the largest of three numbers.
- **[5]** Explain the decision-making statements available in the shell.
- **[10]** Write a shell script that accepts a filename and reports whether it exists, its
  type, its permissions and its line count. Explain each construct used.
- **[10]** Explain shell programming: variables, control structures (`if`, `case`, `for`,
  `while`, `until`) and functions, with a complete worked script.
- **[15]** Explain shell scripting in UNIX, covering the shebang, execution methods, variables,
  positional parameters, test operators, all control structures and functions. Illustrate with
  at least two complete scripts.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "`#!` is called?" | **Shebang / hashbang**; must be **line 1**. |
| "`#` elsewhere?" | A **comment**. |
| "Why `./script`?" | `.` is not in `PATH` by default. |
| "Difference between `bash s.sh` and `. s.sh`?" | The latter runs in the **current** shell (changes persist). |
| "`[ $a -eq $b]` fails because?" | Missing **space** before `]`; `[` is a command. |
| "String equality operator?" | `=` (or `==` in bash), **not** `-eq` (that is numeric). |
| "`-z` tests?" | String is **empty**. |
| "How to exit with an error status?" | `exit 1` (non-zero). |

---

## 11. Process management

### Concept

A **program** is a passive file on disk. A **process** is a program in execution — it has an
address space, a program counter, registers, open files, and an entry in the kernel's process
table. Every process has:

- a **PID** (process ID), unique;
- a **PPID** (parent PID) — because in UNIX **every process except `init` is created by
  another process**;
- an owner (real and effective UID/GID), a priority, a current directory, and a controlling
  terminal.

**How processes are born.** UNIX does it in a way that surprises people: there is no "run this
program" call. Instead:

1. **`fork()`** — the parent makes an almost-exact **duplicate** of itself. The duplicate is
   the child. `fork()` returns **0 in the child** and the **child's PID in the parent** — this
   is how each knows which one it is. Returns **−1** on failure.
2. **`exec()`** — the child then **overlays itself** with the new program. Its PID does not
   change; only its memory image does. Hence "**fork and exec**".
3. **`wait()`** — the parent suspends until the child finishes and collects its exit status.
4. **`exit()`** — the child terminates, returning a status.

Two consequences worth stating:

- A **zombie** is a process that has terminated but whose parent has not yet called `wait()`,
  so its exit status still occupies a process-table slot. It uses no memory or CPU — it is
  just an entry. Shown as `Z` or `<defunct>`. You cannot kill a zombie; you kill or fix the
  **parent**.
- An **orphan** is a process whose parent died first. The kernel immediately **re-parents it
  to `init` (PID 1)**, which reaps it properly. Orphans are harmless; zombies are the leak.

### Process states

| State | `ps` code | Meaning |
|---|---|---|
| Running / runnable | `R` | Executing or on the run queue |
| Interruptible sleep | `S` | Waiting for an event (I/O, input) |
| Uninterruptible sleep | `D` | Waiting on disk I/O; cannot be killed until it returns |
| Stopped | `T` | Suspended (Ctrl+Z or SIGSTOP) |
| Zombie | `Z` | Terminated, not yet reaped |

### Commands

| Command | Purpose | Options |
|---|---|---|
| `ps` | Process status | `ps` current terminal only; **`ps -ef`** (System V) all processes full format; **`ps aux`** (BSD) all with CPU/memory; `ps -u ravi`; `ps -l` long, shows priority/nice |
| `top` / `htop` | Live, sorted, updating process display | `top`, then `k` kill, `q` quit |
| `pstree` | Processes as a tree showing parentage | `pstree -p` |
| `pgrep` / `pkill` | Find / signal processes by name | `pkill -9 firefox` |
| `kill` | Send a **signal** (default SIGTERM 15) | `kill 1234`; **`kill -9 1234`** SIGKILL; `kill -l` list signals |
| `killall` | Kill by **name** | `killall httpd` |
| `&` | Run a command in the **background** | `sleep 100 &` |
| `jobs` | List background jobs of this shell | `jobs -l` |
| `fg` / `bg` | Bring job to foreground / resume in background | `fg %1`, `bg %1` |
| `nohup` | Run immune to hangup — survives logout; output to `nohup.out` | `nohup ./long.sh &` |
| `nice` / `renice` | Start / change scheduling priority. **Nice value −20 (highest priority) to +19 (lowest)**; only root may lower it below 0 | `nice -n 10 cmd`; `renice -5 -p 1234` |
| `wait` | Wait for background jobs to finish | `wait` |
| `sleep` | Pause n seconds | `sleep 5` |
| `at` / `batch` | Run a command once at a given time | `at 5pm` |
| `cron` / `crontab` | Run commands on a **repeating schedule** | `crontab -e`, `crontab -l` |
| `time` | Report real/user/sys time for a command | `time ./prog` |
| `lsof` | List open files (and which process holds them) | `lsof -p 1234` |
| `strace` | Trace system calls | `strace -p 1234` |

**Cron field order** (a reliable MCQ): `minute hour day-of-month month day-of-week command`
— e.g. `30 2 * * 1 /backup.sh` runs at 02:30 every Monday. Minute 0–59, hour 0–23, DOM 1–31,
month 1–12, DOW 0–7 (0 and 7 both = Sunday).

### Important signals

| Signal | Number | Meaning | Catchable? |
|---|---|---|---|
| **SIGHUP** | 1 | Hangup — terminal closed; conventionally makes daemons reload config | Yes |
| **SIGINT** | 2 | Interrupt — **Ctrl+C** | Yes |
| SIGQUIT | 3 | Quit with core dump — Ctrl+\ | Yes |
| **SIGKILL** | **9** | **Kill immediately — cannot be caught, blocked or ignored** | **No** |
| SIGSEGV | 11 | Segmentation fault | Yes |
| **SIGTERM** | **15** | **Terminate politely — the default of `kill`**; lets the program clean up | Yes |
| SIGSTOP | 19 | Suspend — **cannot be caught** | No |
| SIGTSTP | 20 | Terminal stop — **Ctrl+Z** | Yes |
| SIGCONT | 18 | Continue a stopped process | Yes |
| SIGCHLD | 17 | Child stopped or terminated | Yes |

**Always try `kill -15` before `kill -9`.** SIGTERM lets a program flush buffers, close files
and remove lock files; SIGKILL is handled by the kernel and gives the process no chance at
all, so it can corrupt data. Saying this is worth a mark.

### Likely exam questions

- **[5]** What is a process? Differentiate between a program and a process.
- **[5]** Explain `fork()` and `exec()` in UNIX process creation.
- **[5]** What are zombie and orphan processes?
- **[5]** Explain foreground and background processing in UNIX with examples.
- **[5]** Explain the `kill` command. Differentiate between signals 9 and 15.
- **[10]** Explain process management in UNIX: process attributes, states, creation via
  fork/exec/wait/exit, and the commands used to monitor and control processes.
- **[15]** Describe the UNIX process model in detail. Include the process table, PID/PPID
  relationships, the fork-exec mechanism with a diagram, process states with a state-transition
  diagram, zombies and orphans, signals, job control and scheduling priority (`nice`).

### MCQ traps

| Trap | Correct answer |
|---|---|
| "`fork()` returns what in the child?" | **0**. In the parent: the **child's PID**. |
| "Does `exec` create a new process?" | **No** — it replaces the current process image; PID unchanged. |
| "PID 1?" | `init`/`systemd`. |
| "Which signal cannot be caught?" | **SIGKILL (9)** and SIGSTOP (19). |
| "Default signal of `kill`?" | **SIGTERM (15)**, not 9. |
| "Ctrl+C sends?" | **SIGINT (2)**. Ctrl+Z → SIGTSTP (20). |
| "A zombie consumes memory?" | **No** — only a process-table entry. |
| "Orphan is adopted by?" | **`init` (PID 1)**. |
| "Highest priority nice value?" | **−20** (lowest is +19). Lower number = higher priority. |
| "Which command runs a job after logout?" | **`nohup`**. |

---

## 12. Last-week revision sheet

**Twelve facts most likely to appear as one-mark MCQs:**

1. UNIX — Ken Thompson, 1969, PDP-7, assembly; **rewritten in C in 1973** by Ritchie.
2. Linux kernel — **Linus Torvalds, 1991**; UNIX-*like*, POSIX-compliant, not UNIX-derived.
3. Shell = user program, **not** part of the kernel; interface via **system calls**.
4. File system regions: **boot block, super block, inode block, data block**.
5. Inode holds everything **except the file name** (which is in the directory entry).
6. `r`=4, `w`=2, `x`=1. **umask 022 → files 644, directories 755.**
7. On a **directory**: `x` = traverse, `w` = create/delete entries, `r` = list names.
8. **SUID 4000, SGID 2000, sticky 1000**; `/tmp` is `drwxrwxrwt`.
9. `wc` prints **lines, words, characters**; `head`/`tail` default to **10** lines.
10. `comm` and `join` need **sorted** input; `cmp` gives the **first** difference.
11. **`$?` = 0 means success**; `$$` = current shell PID; `$#` = argument count.
12. **SIGKILL 9 cannot be caught**; `kill` defaults to **SIGTERM 15**; PID 1 is `init`.

**Descriptive-paper strategy for this topic.** Section A (5 marks) will almost certainly offer
at least one UNIX question in the Diploma paper — take it, they are the cheapest marks on the
paper. For Section B/C, the reliably examinable long answers are: (a) UNIX architecture with
diagram, (b) the file system with the four regions and inodes, (c) permissions with worked
chmod/umask arithmetic, (d) the boot sequence, (e) a grouped command catalogue, (f) shell
scripting with a complete script. Prepare a **clean, fast, labelled diagram** for (a), (b) and
(d) — a good diagram earns 3–4 of the 10 or 15 marks on its own, and it takes thirty seconds.
