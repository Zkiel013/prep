# CORE 08 — Data Structures

> **Shared-core file 8 of the NPSC CTSE 2026 prep set.**
> Three depths for every topic: **one-line fact** (MCQ), **5-mark answer** (~5–6 points),
> **10/15-mark answer** (worked explanation + diagram).

---

## 0. Why this matters — where data structures appear in your three papers

| Elective | Where | How heavy |
|---|---|---|
| **CS Degree** | P-I §2 — "Primitive data types, array, stack, queue, link list, trees, sorting and searching techniques, symbol tables, hashing etc. Analysing Algorithms, the big-Oh notation, divide and conquer & greedy method, Dynamic programming, Search and traversal techniques, NP completeness." A **full dedicated unit**, and it feeds straight into the Algorithms and Compiler units too. | **Very heavy** |
| **Computer Forensic** | TP-II §6 — "Data, Information, Definition of data structure. Arrays, stacks, queues, linked lists, trees, graphs, priority queues and heaps. File structures: Fields, records and files. Sequential, direct, index-sequential and relative files. Hashing, inverted lists and multi-lists. B-trees and B+ trees." Names **B-trees, B+ trees, inverted lists, multi-lists** explicitly. | **Heavy** |
| **CS Diploma** | Not a named unit — but C programming (P-II §5) leans on arrays, strings and structures, and the DBMS units assume file organisation. | **Light (indirect)** |

**Two of your three electives name data structures directly, and the topics overlap almost
perfectly.** The Forensic syllabus is the more demanding on *file structures* (inverted lists,
multi-lists, B+ trees); the Degree syllabus is the more demanding on *algorithm analysis*
(big-O, divide-and-conquer, greedy, DP). Study the union once. Worked numericals — an address
calculation, a postfix evaluation, an AVL rotation, a Dijkstra table, a sort trace — are the
highest-scoring descriptive answers because they are unambiguous to mark.

### Topic checklist

- [ ] Data vs information; ADT vs data structure; linear vs non-linear; static vs dynamic
- [ ] **Arrays**: 1D/2D, **address calculation (row- vs column-major), worked**
- [ ] Sparse matrices — triplet and linked representations
- [ ] **Stacks**: operations, array & linked implementation, applications
- [ ] **Infix → postfix/prefix conversion, and postfix/prefix evaluation — worked**
- [ ] Recursion; recursion vs iteration; the call stack; tail recursion
- [ ] **Queues**: simple, **circular (with the full/empty problem)**, priority, deque
- [ ] **Linked lists**: singly, doubly, circular; header nodes; array-vs-list comparison
- [ ] **Tree terminology; binary tree properties and counting formulas**
- [ ] **Traversals (in/pre/post/level) — worked traces**
- [ ] **Reconstruction of a tree from two traversals — worked**
- [ ] **BST** — insert, delete (three cases), search
- [ ] **AVL trees — all four rotations (LL, RR, LR, RL) worked**
- [ ] **B-trees and B+ trees** — order, insertion with splitting, the difference
- [ ] **Heaps and heap sort** — build-heap, heapify, worked
- [ ] **Graphs**: adjacency matrix vs list; **BFS/DFS worked traces**
- [ ] Spanning trees; **Prim and Kruskal — worked**; **Dijkstra — worked table**; topological sort
- [ ] Searching: linear, binary (iterative + recursive, worked)
- [ ] **Every sort** with a trace + the **master complexity/stability table**
- [ ] **Hashing**: functions, load factor, chaining, linear/quadratic probing, double hashing — worked
- [ ] File structures: sequential, direct, index-sequential, relative, inverted, multi-list
- [ ] Asymptotic notation: **big-O, big-Ω, big-Θ**; best/average/worst

---

## 1. Fundamentals — data, ADT, and classification

### Concept

**Data** are raw, unprocessed facts and figures (the number `42`, the string `"NPSC"`).
**Information** is data that has been processed, organised and given context so it becomes
meaningful (`42` marks out of 50 = 84%, a distinction). A **data structure** is a systematic
way of **organising and storing data in memory so that it can be used efficiently** — the
choice of structure directly determines how fast the operations you care about will run.

An **Abstract Data Type (ADT)** is the *specification* — **what** operations are available and
what they do — deliberately kept separate from the *implementation* — **how** they are coded.
A "Stack ADT" promises `push`, `pop`, `peek`, `isEmpty` with LIFO behaviour; whether you build
it on an array or a linked list is an implementation choice invisible to the user. **ADT = the
interface; data structure = the realisation.** Saying that sentence earns the mark.

### Classification

| Axis | Categories |
|---|---|
| **Primitive vs non-primitive** | Primitive = directly operated on by the machine: `int`, `float`, `char`, `pointer`. Non-primitive = built from primitives: arrays, lists, trees, graphs |
| **Linear vs non-linear** | **Linear** — elements form a sequence, each has one predecessor and one successor: array, stack, queue, linked list. **Non-linear** — an element may have many neighbours: tree, graph |
| **Static vs dynamic** | **Static** — size fixed at compile time, contiguous memory: array. **Dynamic** — grows/shrinks at run time, scattered memory linked by pointers: linked list, tree, graph |
| **Homogeneous vs heterogeneous** | Homogeneous — all elements same type (array). Heterogeneous — mixed types (structure/record) |

**Operations common to all structures:** traversal, insertion, deletion, searching, sorting,
merging, updating.

### Likely exam questions

- **[5]** Differentiate between data and information. Define a data structure and an ADT.
- **[5]** Classify data structures with examples. Distinguish linear from non-linear.
- **[5]** What is an abstract data type? Explain with the stack as an example.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Stack, queue, array, linked list are?" | **Linear** data structures. |
| "Tree and graph are?" | **Non-linear**. |
| "An array is static or dynamic?" | **Static** (fixed size, contiguous). |
| "ADT specifies?" | **What** operations do, **not how** they are implemented. |
| "int, char, float are?" | **Primitive** data types. |

---

## 2. Arrays

### Concept

An **array** is a collection of elements of the **same type** stored in **contiguous memory
locations**, accessed by an **index**. Contiguity is the whole point: because the elements are
adjacent and equal-sized, the machine can compute the address of any element **directly by
arithmetic** — no searching — giving **O(1) random access**. That is the array's superpower and
the reason address calculation is examined so heavily.

The trade-off: size is **fixed** (static), and insertion/deletion in the middle costs **O(n)**
because every following element must shift.

### 2.1 Address calculation — 1D array (WORKED)

For a 1D array `A` with **base address B**, element size **w** bytes, and **lower bound LB**
(the first index):

> **Address(A[i]) = B + (i − LB) × w**

*Worked:* `int A[50]` starts at address **2000**, `w = 4` bytes, indices start at **0**.
Find the address of `A[12]`.

```
Address(A[12]) = 2000 + (12 − 0) × 4 = 2000 + 48 = 2048
```

*Worked (1-based):* An array with `LB = 1`, base 1000, `w = 2`. Address of the 8th element:

```
Address(A[8]) = 1000 + (8 − 1) × 2 = 1000 + 14 = 1014
```

**The single most common mistake** is forgetting to subtract the lower bound. Always write the
`(i − LB)` term explicitly.

### 2.2 Address calculation — 2D array (WORKED)

A 2D array `A[m][n]` (m rows, n columns) is stored in **one dimension** in memory, in one of
two orders. Let element `A[i][j]`, base **B**, size **w**, row lower bound **LBr**, column
lower bound **LBc**.

**Row-major order** (C, C++, Python) — store **row by row**, left to right:

> **Address(A[i][j]) = B + [ (i − LBr) × n + (j − LBc) ] × w**
> (n = number of columns)

**Column-major order** (FORTRAN, MATLAB, R) — store **column by column**, top to bottom:

> **Address(A[i][j]) = B + [ (j − LBc) × m + (i − LBr) ] × w**
> (m = number of rows)

*Worked (both).* Array `A[1..4][1..5]` (so m = 4 rows, n = 5 cols), base **B = 1000**,
w = **4** bytes, lower bounds 1. Find the address of `A[3][4]`.

Row-major:
```
= 1000 + [ (3 − 1) × 5 + (4 − 1) ] × 4
= 1000 + [ 2 × 5 + 3 ] × 4
= 1000 + [ 13 ] × 4
= 1000 + 52 = 1052
```

Column-major:
```
= 1000 + [ (4 − 1) × 4 + (3 − 1) ] × 4
= 1000 + [ 3 × 4 + 2 ] × 4
= 1000 + [ 14 ] × 4
= 1000 + 56 = 1056
```

**The examiner's tell:** in row-major the **column count n** appears in the formula; in
column-major the **row count m** appears. Memorise it as *"multiply by the count of whatever
you finished storing first."* Row-major finishes rows first, so you multiply the row index by
the number of columns.

### 2.3 Rules for reading array problems

- If indices "start at 0", `LB = 0`; if the problem says `A[1..n]`, `LB = 1`.
- "Word" often means 2 bytes, "int" 4 bytes — but **use whatever size the question gives**.
- For a 3-D array `A[p][q][r]` in row-major:
  `B + [ (i)·(q·r) + (j)·(r) + k ] × w` (with lower bounds subtracted).

### 2.4 Advantages and disadvantages

| Advantages | Disadvantages |
|---|---|
| **O(1) random access** by index | **Fixed size** — must know maximum in advance |
| Simple, cache-friendly (contiguous) | **Insertion/deletion O(n)** — shifting |
| No pointer overhead per element | **Wasted space** if under-filled; overflow if over-filled |
| Basis for other structures (heap, hash table, matrix) | Contiguous block must be found in memory |

### Likely exam questions

- **[5]** Derive the address calculation formula for a 1D array and solve a numerical.
- **[5]** Differentiate row-major and column-major storage with an example.
- **[10]** For `A[1..6][1..8]`, base 500, each element 4 bytes, find the address of `A[4][6]`
  in both row-major and column-major order, showing all steps, and explain the difference.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Time to access A[i]?" | **O(1)** — direct address arithmetic. |
| "C stores 2D arrays in?" | **Row-major** order. |
| "FORTRAN/MATLAB store in?" | **Column-major**. |
| "Insertion in the middle of an array?" | **O(n)** — shifting required. |
| "Row-major formula multiplies row index by?" | **Number of columns (n)**. |

---

## 3. Sparse matrices

### Concept

A **sparse matrix** is one in which **most elements are zero**. Storing an n×n matrix that is
95% zeros in a full 2D array wastes enormous space and time. A sparse representation stores
**only the non-zero elements**, plus enough bookkeeping to locate them.

**Rule of thumb:** if non-zeros < n²/3, a sparse representation saves space.

### 3.1 Triplet (3-column / coordinate) representation

Store each non-zero as a triple `(row, column, value)`. The **first row** of the triplet table
is a header giving `(number of rows, number of columns, number of non-zero elements)`.

*Worked.* The 4×5 matrix

```
0 0 3 0 0
0 5 0 0 0
0 0 0 0 7
2 0 0 0 0
```

has 4 non-zeros. Triplet form (using 0-based indices):

| Row | Col | Value |
|---|---|---|
| **4** | **5** | **4**  ← header: 4 rows, 5 cols, 4 non-zeros |
| 0 | 2 | 3 |
| 1 | 1 | 5 |
| 2 | 4 | 7 |
| 3 | 0 | 2 |

Space used: `(4 + 1) × 3 = 15` integers, versus `4 × 5 = 20` for the full matrix — and the
saving grows dramatically as the matrix gets larger and sparser.

### 3.2 Linked-list representation

Each non-zero becomes a node holding `(row, col, value, next)`. Nodes can be chained in a
single list, or organised as one linked list per row (a **multi-list**, see §17), which speeds
row-wise operations. Linked representation is preferred when the matrix changes over time
(insertions/deletions) because no shifting is needed.

### Likely exam questions

- **[5]** What is a sparse matrix? Represent a given matrix in triplet form.
- **[10]** Explain triplet and linked-list representations of a sparse matrix with an example,
  and compare their space requirements against the full 2D array.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "A sparse matrix has mostly?" | **Zero** elements. |
| "Header row of the triplet stores?" | **#rows, #columns, #non-zero elements**. |
| "Triplet uses how many columns?" | **Three** — row, column, value. |

---

## 4. Stacks

### Concept

A **stack** is a **LIFO** (Last-In-First-Out) linear list where all insertions and deletions
happen at **one end only**, called the **top**. Think of a stack of plates: you add and remove
from the top. The last element pushed is the first popped.

**Operations (all O(1)):**

| Operation | Effect |
|---|---|
| `push(x)` | Add `x` on top; error if **overflow** (array full) |
| `pop()` | Remove and return the top; error if **underflow** (empty) |
| `peek()` / `top()` | Return the top without removing it |
| `isEmpty()` / `isFull()` | Test conditions |

**Array implementation:** keep an index `top`, initialised to **−1** (empty). `push`
increments `top` then stores; `pop` returns then decrements. **Overflow** when `top == SIZE−1`;
**underflow** when `top == −1`.

**Linked implementation:** push/pop at the **head** of a singly linked list — no fixed size,
never overflows (until memory exhausts).

### 4.1 Applications of stacks

1. **Expression conversion and evaluation** (infix ↔ postfix/prefix) — §4.2, §4.3.
2. **Function-call management** — the **run-time call stack** stores return addresses, local
   variables and parameters; this is what makes **recursion** possible (§4.4).
3. **Recursion** implementation.
4. **Backtracking** — maze solving, N-queens, DFS.
5. **Undo/redo** in editors; browser **back** button.
6. **Balanced-parenthesis checking**.
7. **Reversing** a string or list.

### 4.2 Infix → postfix / prefix conversion (WORKED)

**Why bother?** Infix (`A + B`) needs parentheses and precedence rules to be unambiguous.
**Postfix** (Reverse Polish, `A B +`) and **prefix** (Polish, `+ A B`) need **neither
parentheses nor precedence** — a machine can evaluate them in a single left-to-right (or
right-to-left) scan with one stack. Compilers convert to postfix for exactly this reason.

**Operator precedence** (high → low): `^` (exponent, right-associative) > `* /` > `+ −`.
Parentheses override everything.

**Algorithm — infix to postfix (using an operator stack):**
1. Scan left to right.
2. **Operand** → output it directly.
3. **`(`** → push.
4. **`)`** → pop and output until `(` is popped (discard the pair).
5. **Operator o₁** → while the stack top is an operator of **greater-or-equal** precedence
   (for left-associative ops), pop and output; then push o₁. (For right-associative `^`, pop
   only strictly greater.)
6. End of input → pop and output everything remaining.

*Worked: convert `A + B * C − D / E` to postfix.*

| Symbol | Stack | Output |
|---|---|---|
| A | (empty) | A |
| + | + | A |
| B | + | A B |
| * | + * | A B |
| C | + * | A B C |
| − | + | A B C *  (pop *, its precedence ≥ −) then… |
| − | − | A B C * +  (pop + too, equal precedence) |
| D | − | A B C * + D |
| / | − / | A B C * + D |
| E | − / | A B C * + D E |
| end | (empty) | A B C * + D E / − |

**Postfix = `A B C * + D E / −`**

*Worked with parentheses and `^`: convert `(A + B) ^ C * D`.*

| Symbol | Stack | Output |
|---|---|---|
| ( | ( | |
| A | ( | A |
| + | ( + | A |
| B | ( + | A B |
| ) | (empty) | A B + |
| ^ | ^ | A B + |
| C | ^ | A B + C |
| * | * | A B + C ^  (^ has higher precedence, popped) |
| D | * | A B + C ^ D |
| end | (empty) | A B + C ^ D * |

**Postfix = `A B + C ^ D *`**

**Infix → prefix (the reliable method):**
1. **Reverse** the infix expression (swap `(` and `)`).
2. Convert to postfix (treating `^` associativity carefully).
3. **Reverse** the result.

*Worked: `A + B * C` → prefix.* Reverse: `C * B + A`. Postfix of that: `C B * A +`. Reverse:
`+ A * B C`. **Prefix = `+ A * B C`.** (Check: `+ A (* B C)` = A + (B*C). Correct.)

### 4.3 Evaluation of postfix and prefix (WORKED)

**Postfix evaluation — scan left to right, one operand stack:**
- Operand → push.
- Operator → pop **two** operands (`op2` first, then `op1`), compute `op1 (operator) op2`,
  push the result.
- At the end the stack holds the single answer.

*Worked: evaluate `5 6 2 + * 12 4 / −`.*

| Symbol | Action | Stack (bottom→top) |
|---|---|---|
| 5 | push | 5 |
| 6 | push | 5 6 |
| 2 | push | 5 6 2 |
| + | 6 + 2 = 8 | 5 8 |
| * | 5 * 8 = 40 | 40 |
| 12 | push | 40 12 |
| 4 | push | 40 12 4 |
| / | 12 / 4 = 3 | 40 3 |
| − | 40 − 3 = 37 | **37** |

**Answer = 37.**

**Prefix evaluation — scan RIGHT to left:**
- Operand → push.
- Operator → pop two (`op1` first this time, then `op2`), compute `op1 (operator) op2`, push.

*Worked: evaluate `− * + 4 3 2 5` right-to-left.*

| Symbol (R→L) | Action | Stack |
|---|---|---|
| 5 | push | 5 |
| 2 | push | 5 2 |
| 3 | push | 5 2 3 |
| 4 | push | 5 2 3 4 |
| + | 4 + 3 = 7 | 5 2 7 |
| * | 7 * 2 = 14 | 5 14 |
| − | 14 − 5 = 9 | **9** |

**Answer = 9.** (Check: − (* (+ 4 3) 2) 5 = ((4+3)*2) − 5 = 14 − 5 = 9. Correct.)

### 4.4 Recursion

**Recursion** is a function calling itself, directly or indirectly, on a **smaller sub-problem**
until it reaches a **base case** that stops the descent. Every recursive definition needs two
parts, and stating both earns the mark:

1. **Base case** — the terminating condition (no further recursion).
2. **Recursive case** — the function expressed in terms of a smaller input.

Each call pushes a new **activation record (stack frame)** — return address, parameters, local
variables — onto the **call stack**; returning pops it. Runaway recursion (missing/never-reached
base case) causes **stack overflow**.

*Classic example — factorial:*
```c
int fact(int n){
    if (n <= 1) return 1;      /* base case */
    return n * fact(n - 1);    /* recursive case */
}
```
`fact(4)` → `4 * fact(3)` → `4 * 3 * fact(2)` → `4 * 3 * 2 * fact(1)` → `4*3*2*1 = 24`.

**Recursion vs iteration:**

| | Recursion | Iteration |
|---|---|---|
| Mechanism | Function calls itself | Loop repeats a block |
| Termination | Base case | Loop condition becomes false |
| Memory | **Extra — a stack frame per call (O(depth))** | Constant (one set of variables) |
| Speed | Slower (call overhead) | Faster |
| Code | Often shorter, clearer for tree/divide-and-conquer | Better for simple counting loops |
| Risk | **Stack overflow** | Infinite loop (no crash) |

**Tail recursion** — the recursive call is the *last* action; a compiler can then reuse the
frame, achieving iteration-like O(1) space.

### Likely exam questions

- **[5]** Define a stack. List its operations and any four applications.
- **[5]** Explain overflow and underflow with the array implementation of a stack.
- **[10]** Convert `(A + B) * C − D ^ E ^ F` to postfix, showing the stack at each step.
- **[10]** Evaluate the postfix expression `6 2 3 + − 4 2 * +` step by step.
- **[10]** What is recursion? Explain the role of the stack in recursion using factorial, and
  compare recursion with iteration.
- **[15]** Explain the stack ADT and its applications. Give the algorithm for infix-to-postfix
  conversion and use it to convert one expression, then evaluate the resulting postfix.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "A stack works on which principle?" | **LIFO**. |
| "Both ends used?" | No — **one end (top) only**. |
| "top initialised to?" | **−1** (empty stack). |
| "Postfix of A+B*C?" | **A B C * +**. |
| "Which needs no parentheses?" | **Postfix and prefix**. |
| "Recursion uses which structure internally?" | **Stack** (the call stack). |
| "Deleting from an empty stack causes?" | **Underflow**. |
| "Postfix is also called?" | **Reverse Polish Notation (RPN)**. |

---

## 5. Queues

### Concept

A **queue** is a **FIFO** (First-In-First-Out) linear list: insertions happen at the **rear**
(enqueue) and deletions at the **front** (dequeue) — opposite ends. Like a queue at a ticket
counter: first to arrive is first served.

Two indices: **front** (points at the element to be removed next) and **rear** (the last
element inserted). Applications: **CPU scheduling** (ready queue), **printer/disk spooling**,
**BFS traversal**, **buffering** (I/O, keyboard, streaming), request handling in servers.

### 5.1 Simple (linear) queue — and its flaw

Array of size `n`, `front = rear = −1` when empty. Enqueue increments `rear`; dequeue
increments `front`. **The flaw:** after several dequeues, `front` marches forward and the
vacated cells at the start **cannot be reused** — the queue reports "full" (`rear == n−1`)
while the front cells sit empty. This wasted space is called **false overflow** (rightward
drift). The **circular queue** fixes it.

### 5.2 Circular queue (WORKED)

Treat the array as a **ring**: after the last index, wrap to index 0 using **modulo n**.

- Enqueue: `rear = (rear + 1) % n; A[rear] = x;`
- Dequeue: `x = A[front]; front = (front + 1) % n;`

**The full-vs-empty ambiguity** — the classic exam point. If you only track `front` and `rear`,
the condition `rear + 1 == front` (mod n) means *full*, but a genuinely empty queue can look
the same. Two standard fixes:
1. **Leave one cell empty** — declare full when `(rear + 1) % n == front`; empty when
   `front == rear`. (Wastes one slot; simplest.)
2. **Keep a `count`** of elements — full when `count == n`, empty when `count == 0`.

*Worked (n = 5, method 1, indices 0–4).* Start empty: `front = rear = 0`.

| Operation | front | rear | Contents |
|---|---|---|---|
| enqueue 10 | 0 | 1 | [10] |
| enqueue 20 | 0 | 2 | [10 20] |
| enqueue 30 | 0 | 3 | [10 20 30] |
| enqueue 40 | 0 | 4 | [10 20 30 40] — now `(4+1)%5 == 0 == front` ⇒ **FULL** (one slot left empty) |
| dequeue → 10 | 1 | 4 | [20 30 40] |
| enqueue 50 | 1 | 0 | [20 30 40 50] — rear wrapped to 0 |

### 5.3 Priority queue

Elements carry a **priority**; **dequeue removes the highest-priority element**, not the oldest.
Ties are broken FIFO. Used in **CPU scheduling (priority scheduling)**, **Dijkstra** and
**Prim**, **Huffman coding**, event simulation.

Implementations: unsorted array (O(1) insert, O(n) delete-max), sorted array (O(n) insert,
O(1) delete-max), or — the efficient one — a **binary heap** (O(log n) both; see §10).

### 5.4 Deque (double-ended queue)

Insertion and deletion allowed at **both** ends. Operations: `insertFront`, `insertRear`,
`deleteFront`, `deleteRear`. Two restricted forms:
- **Input-restricted deque** — insertion at one end only, deletion at both.
- **Output-restricted deque** — deletion at one end only, insertion at both.

A deque can emulate **both a stack and a queue**, which is a favourite MCQ.

### Comparison

| Type | Insert | Delete | Order out |
|---|---|---|---|
| Simple queue | rear | front | FIFO |
| Circular queue | rear (wraps) | front (wraps) | FIFO, reuses space |
| Priority queue | by priority | highest priority first | by priority |
| Deque | both ends | both ends | flexible |

### Likely exam questions

- **[5]** Define a queue. Distinguish it from a stack.
- **[5]** What is the drawback of a linear queue? How does a circular queue overcome it?
- **[5]** Differentiate priority queue and deque.
- **[10]** Explain the circular queue with enqueue/dequeue algorithms and the full/empty
  conditions; trace a sequence of operations on a size-5 queue.
- **[10]** Explain the types of queues (simple, circular, priority, deque) with diagrams.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "A queue follows?" | **FIFO**. |
| "Insertion and deletion in a queue happen at?" | **Rear and front** respectively (different ends). |
| "Circular queue full condition (one-slot method)?" | **(rear + 1) % n == front**. |
| "Which can act as both stack and queue?" | **Deque**. |
| "Highest priority served first — which queue?" | **Priority queue**. |
| "BFS uses which structure?" | **Queue**. DFS uses a **stack**. |

---

## 6. Linked lists

### Concept

A **linked list** is a **dynamic** linear structure in which elements (**nodes**) are stored at
scattered memory locations and threaded together by **pointers**. Each node holds **data** plus
the **address of the next node**. The list is reached through an external pointer, **HEAD**; the
last node's link is **NULL**, marking the end. Because nodes are allocated on demand, the list
**grows and shrinks at run time** — no fixed size, no shifting.

**The core trade-off vs arrays:** a linked list gives **O(1) insertion/deletion** once you hold
the relevant node (just re-point links, no shifting) but **loses O(1) random access** — to reach
the i-th node you must **traverse** from HEAD, which is **O(n)**.

### 6.1 Singly linked list (SLL)

Each node: `[data | next]`. Links point **one way** only. You can move forward, never back.

```
HEAD → [10|•] → [20|•] → [30|NULL]
```

Operations: insert at head O(1); insert at end O(n) (must walk to the tail unless a tail
pointer is kept); delete a node O(1) if you have its predecessor; search O(n).

### 6.2 Doubly linked list (DLL)

Each node: `[prev | data | next]` — **two** links, so traversal is possible in **both
directions**. Costs one extra pointer per node, but makes deletion easier (you have the
predecessor for free) and enables backward scans.

```
NULL ← [•|10|•] ⇄ [•|20|•] ⇄ [•|30|•] → NULL
```

### 6.3 Circular linked list (CLL)

The **last node points back to the first** (in a circular DLL, first's `prev` points to last
too). There is no NULL end; any node can be a starting point, and you can loop around forever —
useful for **round-robin scheduling** and buffering. Care needed to avoid infinite loops
(stop when you return to the start).

### 6.4 Header (dummy) node

An extra node at the front that holds no data (or holds the list length). It removes the special
case of "inserting/deleting at the head", simplifying code.

### 6.5 Array vs linked list — the standard comparison table

| Criterion | **Array** | **Linked list** |
|---|---|---|
| Memory | **Contiguous**, fixed at compile time | **Scattered**, allocated at run time |
| Size | **Static** — fixed | **Dynamic** — grows/shrinks |
| Access to i-th element | **O(1)** random access | **O(n)** — must traverse |
| Insertion/deletion (middle) | **O(n)** — shift elements | **O(1)** once the node is located (re-point links) |
| Memory per element | Just the data | Data **+ pointer(s)** — extra overhead |
| Memory utilisation | Can waste (over-allocated) or overflow | Uses exactly what is needed |
| Cache locality | **Excellent** (contiguous) | Poor (scattered) |
| Ease of implementation | Simple | More complex (pointer handling) |

**One-line summary examiners like:** *"Use an array when you mostly index/read and know the
size; use a linked list when you mostly insert/delete and the size is unpredictable."*

### 6.6 Applications

Implementing stacks, queues and deques; **polynomial representation and arithmetic**; **sparse
matrices**; dynamic memory management (free lists); **hash-table chaining**; adjacency lists for
graphs; music playlists (CLL); undo (DLL).

### Likely exam questions

- **[5]** Differentiate an array and a linked list (tabular).
- **[5]** Explain singly, doubly and circular linked lists with diagrams.
- **[5]** Write the algorithm to insert a node at the beginning of a singly linked list.
- **[10]** Explain the doubly linked list. Give algorithms to insert and delete a node, and
  state its advantages over a singly linked list.
- **[15]** Compare arrays and linked lists in detail. Explain the types of linked lists with
  diagrams and list four applications of linked lists.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Random access is possible in?" | **Array** (O(1)); **not** a linked list. |
| "Last node's next in an SLL?" | **NULL**. |
| "Which list allows backward traversal?" | **Doubly** linked list. |
| "Extra memory in a linked list is for?" | The **pointer(s)**. |
| "Round-robin scheduling suits which list?" | **Circular** linked list. |
| "Insertion at head of a list is?" | **O(1)**. |

---

## 7. Trees — terminology and binary-tree properties

### Concept

A **tree** is a **non-linear**, **hierarchical** structure: a set of nodes with one special
node called the **root**, and the rest partitioned into disjoint subsets each of which is itself
a tree (the subtrees). It has **no cycles** — a tree with *n* nodes has exactly **n − 1 edges**.

### 7.1 Terminology (memorise — pure MCQ fuel)

| Term | Meaning |
|---|---|
| **Root** | The topmost node; has no parent |
| **Parent / child** | An immediate predecessor / successor |
| **Siblings** | Nodes with the same parent |
| **Leaf (external/terminal)** | A node with **no children** |
| **Internal node** | A node with at least one child |
| **Degree of a node** | Number of children it has |
| **Degree of a tree** | Maximum degree of any node |
| **Level** | Root is level 0 (some texts: level 1); each step down adds 1 |
| **Height / depth of tree** | Number of edges on the longest root-to-leaf path (a single node has height 0) |
| **Ancestor / descendant** | Any node on the path up to the root / down from a node |
| **Subtree** | A node together with all its descendants |
| **Forest** | A set of disjoint trees (remove the root of a tree → a forest) |

### 7.2 Types of binary tree

A **binary tree** is a tree in which every node has **at most two children** (left and right).

| Type | Definition |
|---|---|
| **Full (strict/proper)** | Every node has **0 or 2** children (never 1) |
| **Complete** | All levels full **except possibly the last**, which is filled **left to right**. (This is the shape used for heaps and array storage.) |
| **Perfect** | All internal nodes have 2 children **and** all leaves are at the **same level** |
| **Skewed** | Every node has only one child — degenerates to a linked list (left-skewed or right-skewed) |
| **Balanced** | Height ≈ log₂n; heights of left and right subtrees differ by a bounded amount (AVL: ≤ 1) |

### 7.3 Binary-tree properties (the counting formulas — WORKED)

For a binary tree:

1. **Maximum nodes at level ℓ** (root = level 0) = **2ˡ**.
2. **Maximum nodes in a tree of height h** = **2^(h+1) − 1**.
3. **Minimum height** for n nodes = **⌈log₂(n+1)⌉ − 1**; a tree with n nodes has height at
   least ⌊log₂n⌋.
4. In a **full/strict** binary tree, **number of leaf nodes = number of internal (degree-2)
   nodes + 1**, i.e. **L = I + 1**.
5. A binary tree with **n** nodes has **n + 1 NULL (external) links** (and n − 1 real edges).

*Worked (property 4).* A full binary tree has 8 internal (2-child) nodes. Leaves = 8 + 1 = **9**;
total nodes = 8 + 9 = **17**.

*Worked (property 2).* A perfect binary tree of height 3 has `2^(3+1) − 1 = 15` nodes, of which
`2³ = 8` are leaves.

### 7.4 Array vs linked representation of a binary tree

- **Array (sequential):** store the root at index 1; for node at index `i`, **left child =
  2i**, **right child = 2i + 1**, **parent = ⌊i/2⌋**. Efficient for **complete** trees (heaps);
  wasteful for skewed trees (many empty slots).
- **Linked:** each node `[left | data | right]`. Flexible for any shape; the usual choice.

### Likely exam questions

- **[5]** Define: root, leaf, degree, height, sibling, forest.
- **[5]** Differentiate full, complete and perfect binary trees.
- **[5]** State and prove: a full binary tree with I internal nodes has I + 1 leaves.
- **[10]** Explain the array and linked representations of a binary tree with examples, and give
  the index relations for the array form.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Max nodes at level ℓ (root = 0)?" | **2ˡ**. |
| "Max nodes in a tree of height h?" | **2^(h+1) − 1**. |
| "A tree with n nodes has how many edges?" | **n − 1**. |
| "In the array form, left child of node i?" | **2i** (root at 1). |
| "Node with no children?" | **Leaf**. |
| "Full binary tree: every node has?" | **0 or 2** children. |

---

## 8. Binary tree traversals — with worked traces and reconstruction

### Concept

**Traversal** = visiting every node exactly once in a systematic order. For binary trees there
are three **depth-first** orders, defined by *when the root is visited relative to its subtrees*,
plus one **breadth-first** order.

| Traversal | Order | Rule |
|---|---|---|
| **Inorder** | **Left, Root, Right** | Visit left subtree, then root, then right subtree |
| **Preorder** | **Root, Left, Right** | Visit root first |
| **Postorder** | **Left, Right, Root** | Visit root last |
| **Level-order (BFS)** | Level by level, left to right | Uses a **queue** |

**The one fact that unlocks the topic:** *the position of "Root" in the name tells you when to
print the root.* **In**order → root in the **middle**; **pre**order → root **first**;
**post**order → root **last**. Left always precedes right.

**Key result:** the **inorder traversal of a BST yields the elements in sorted (ascending)
order.** That is why inorder matters.

### 8.1 Worked traces

Consider this binary tree:

```
            A
          /   \
         B     C
        / \     \
       D   E     F
```

- **Inorder (L,Root,R):** left of A first. Left subtree of A is rooted at B: (inorder of B) =
  D, B, E. Then A. Then right subtree (C): inorder of C = C, F.
  **→ D B E A C F**
- **Preorder (Root,L,R):** A, then preorder(B) = B D E, then preorder(C) = C F.
  **→ A B D E C F**
- **Postorder (L,R,Root):** postorder(B) = D E B, postorder(C) = F C, then A.
  **→ D E B F C A**
- **Level-order:** A / B C / D E F → **A B C D E F** (uses a queue: dequeue a node, enqueue its
  children).

### 8.2 Reconstruction from two traversals (WORKED)

**The rule:** you can rebuild a unique binary tree from **(inorder + preorder)** or
**(inorder + postorder)**. **Inorder is essential** — it tells you the left/right split.
Preorder+postorder **cannot** reconstruct a general binary tree uniquely (only a full one).

**Method (inorder + preorder):**
1. The **first** element of **preorder** is the **root**.
2. Find that root in **inorder**: everything to its **left** is the left subtree, everything to
   its **right** is the right subtree.
3. Recurse on each part (the next preorder elements fill the left subtree first).

*Worked. Given:*
```
Inorder  : D B E A C F
Preorder : A B D E C F
```
- Preorder[0] = **A** → root. In inorder, `D B E | A | C F` ⇒ left = {D,B,E}, right = {C,F}.
- Left subtree — preorder segment `B D E`, inorder `D B E`: root **B**; inorder `D | B | E` ⇒
  left leaf **D**, right leaf **E**.
- Right subtree — preorder segment `C F`, inorder `C F`: root **C**; inorder `C | F` ⇒ nothing
  left, right child **F**.

Reconstructed tree:
```
            A
          /   \
         B     C
        / \     \
       D   E     F
```
— exactly the original. (Verify by taking its postorder: D E B F C A. ✓)

**Method (inorder + postorder)** is identical except the **root is the LAST element of
postorder**, and you process the right subtree first when recursing.

### Likely exam questions

- **[5]** Write the inorder, preorder and postorder traversals of a given tree.
- **[5]** State which pairs of traversals uniquely determine a binary tree, and why inorder is
  indispensable.
- **[10]** Given inorder `D B E A F C` and preorder `A B D E C F`, reconstruct the binary tree,
  showing each step, and give its postorder.
- **[10]** Explain the four traversal methods with an example tree, and state which traversal of
  a BST gives sorted output.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Inorder of a BST gives?" | **Sorted (ascending) order**. |
| "First node in preorder is the?" | **Root**. |
| "Last node in postorder is the?" | **Root**. |
| "Level-order traversal uses a?" | **Queue**. |
| "Which pair cannot uniquely rebuild a general tree?" | **Preorder + postorder**. |
| "Root visited last in?" | **Postorder**. |

---

## 9. Binary search trees (BST) and AVL trees

### 9.1 BST

A **binary search tree** is a binary tree with the **ordering invariant**: for every node, **all
keys in its left subtree are smaller, and all keys in its right subtree are larger** (no
duplicates, conventionally). This makes search, insert and delete **O(h)** — O(log n) when the
tree is balanced, but **O(n) if it degenerates into a skewed tree** (e.g. inserting sorted data).

**Search / insert:** compare the key with the root; go left if smaller, right if larger; repeat.
Insertion always adds a **new leaf** at the position where the search fails.

*Worked insert.* Insert `50, 30, 70, 20, 40, 60, 80` into an empty BST:
```
            50
          /    \
        30      70
       /  \    /  \
     20   40  60   80
```
(50 is root; 30 < 50 → left; 70 > 50 → right; 20 < 30 → left of 30; etc.)

**Deletion — three cases** (the examined part):
1. **Leaf node** — simply remove it.
2. **One child** — replace the node with its single child.
3. **Two children** — replace the node's key with its **inorder successor** (the smallest key
   in the right subtree) or **inorder predecessor** (largest in the left subtree), then delete
   that successor/predecessor node (which has at most one child).

*Worked (case 3).* Deleting **50** from the tree above: inorder successor = smallest in right
subtree = **60**. Copy 60 into the root, then delete the old 60 (a leaf):
```
            60
          /    \
        30      70
       /  \       \
     20   40      80
```

### 9.2 AVL trees — the four rotations (WORKED)

An **AVL tree** (Adelson-Velsky & Landis, **1962** — the first self-balancing BST) is a BST
that additionally keeps, for **every** node, a **balance factor**

> **BF = height(left subtree) − height(right subtree) ∈ {−1, 0, +1}.**

If an insertion or deletion makes any BF equal to **+2 or −2**, the tree is rebalanced by a
**rotation**, restoring O(log n) height. There are exactly **four cases**, named by the
direction of the imbalance:

| Case | When it happens | Fix |
|---|---|---|
| **LL** (left-left) | Inserted into the **left** subtree of the **left** child (BF = +2, child BF = +1) | **Single right rotation** |
| **RR** (right-right) | Inserted into the **right** subtree of the **right** child (BF = −2, child BF = −1) | **Single left rotation** |
| **LR** (left-right) | Inserted into the **right** subtree of the **left** child (BF = +2, child BF = −1) | **Left rotation on child, then right rotation** (double) |
| **RL** (right-left) | Inserted into the **left** subtree of the **right** child (BF = −2, child BF = +1) | **Right rotation on child, then left rotation** (double) |

**Rule of thumb:** the two single rotations (LL, RR) fix "straight-line" imbalances; the two
doubles (LR, RL) fix "zig-zag" imbalances by first straightening the zig-zag into a straight
line, then doing a single rotation.

**Worked LL — insert 30, 20, 10:**
```
Insert 30, 20:   30          Insert 10:      30 (BF=+2)   →  single RIGHT rotation at 30  →   20
                /                            /                                               /  \
              20                           20                                              10    30
                                          /
                                        10   (LL case)
```
Result: `20` is root, `10` left, `30` right. Balanced.

**Worked RR — insert 10, 20, 30:**
```
10 (BF=−2)                    single LEFT rotation at 10          20
  \                                                             /  \
   20                                                         10    30
     \
      30   (RR case)
```

**Worked LR — insert 30, 10, 20:**
```
   30 (BF=+2)      step 1: LEFT rotate at 10 (child)     30       step 2: RIGHT rotate at 30    20
  /                                                     /                                       /  \
 10                                                    20                                     10    30
   \                                                  /
    20   (LR case)                                   10
```
Result root = `20`, children `10` and `30`.

**Worked RL — insert 10, 30, 20:**
```
10 (BF=−2)       step 1: RIGHT rotate at 30 (child)    10        step 2: LEFT rotate at 10      20
  \                                                      \                                      /  \
   30                                                     20                                  10    30
  /                                                         \
 20   (RL case)                                              30
```
Result root = `20`.

**A larger worked insertion sequence** (good for 15 marks): insert `10, 20, 30, 40, 50, 25`.
- 10,20,30 → RR at 10 → root 20 (10,30).
- Insert 40 → right of 30, still balanced.
- Insert 50 → 30 becomes BF −2 (RR) → left rotate at 30 → subtree 40(30,50). Tree: 20 root,
  left 10, right 40(30,50).
- Insert 25 → goes left of 30. Now 40 has BF +2 with left-child 30 having BF +1... check the
  first unbalanced ancestor from the new node: node 40 has BF = height(left=30-subtree=2) −
  height(right=50=1) = +... trace carefully and apply the matching rotation. (The point the
  examiner wants: **identify the lowest unbalanced node, classify LL/RR/LR/RL, rotate.**)

**Why AVL matters:** it **guarantees** O(log n) search/insert/delete by keeping height ≤
~1.44 log₂n, whereas a plain BST can degrade to O(n). The price is the rotation bookkeeping on
every update.

### Likely exam questions

- **[5]** Define a BST. Insert a given sequence and draw the tree.
- **[5]** Explain BST deletion with the three cases.
- **[5]** What is a balance factor? State the four AVL rotation cases.
- **[10]** Construct an AVL tree by inserting `21, 26, 30, 9, 4, 14, 28, 18, 15, 10, 2, 3, 7`,
  showing each rotation. *(Any given sequence — method is what is marked.)*
- **[15]** Explain AVL trees. Describe all four rotations with diagrams, and build an AVL tree
  from a given insertion sequence, showing balance factors and rotations at each step.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Inorder of a BST is?" | **Sorted**. |
| "AVL balance factor range?" | **−1, 0, +1**. |
| "LL imbalance is fixed by?" | **Single right rotation**. |
| "LR needs?" | **Two rotations** (left then right). |
| "Worst-case search in a plain BST?" | **O(n)** (skewed). AVL guarantees **O(log n)**. |
| "Who invented AVL / in which year?" | **Adelson-Velsky & Landis, 1962**. |
| "Deleting a two-child BST node uses?" | **Inorder successor or predecessor**. |

---

## 10. Heaps and heap sort

### Concept

A **binary heap** is a **complete binary tree** satisfying the **heap property**:
- **Max-heap:** every parent ≥ its children ⇒ the **maximum is at the root**.
- **Min-heap:** every parent ≤ its children ⇒ the **minimum is at the root**.

Because it is complete, a heap is stored in an **array** with no pointers: for index `i`
(1-based), **left child = 2i, right child = 2i+1, parent = ⌊i/2⌋**. A heap is the standard
efficient **priority queue** (§5.3): insert and delete-max/min are **O(log n)**; peek-max is
**O(1)**.

### 10.1 Operations

- **Insert:** place the new key at the next array slot (bottom), then **sift up (bubble up)** —
  swap with the parent while it violates the heap property. O(log n).
- **Delete-max (extract root):** swap root with the last element, remove the last, then
  **sift down (heapify)** the new root — swap with its larger child while it violates the
  property. O(log n).
- **Build-heap:** heapify the array bottom-up from index ⌊n/2⌋ down to 1. Cost is **O(n)**
  (tighter than the naive O(n log n)).

### 10.2 Heap sort (WORKED)

**Idea:** (1) build a **max-heap** from the array; (2) repeatedly **swap the root (largest)
with the last element**, shrink the heap by one, and **heapify** the root. After n−1 rounds the
array is sorted ascending.

*Worked. Sort `4, 10, 3, 5, 1`.*

**Build max-heap** (from array [4,10,3,5,1], heapify from index 2 down):
- Heapify index 2 (value 10, children 5,1): 10 already ≥ both → no change.
- Heapify index 1 (value 4, children 10,3): largest child 10 > 4 → swap → [10,4,3,5,1];
  now index 2 (4) has children 5,1: 5 > 4 → swap → [10,5,3,4,1].
- Max-heap: **[10, 5, 3, 4, 1]**.

**Sort phase:**
| Step | Action | Array |
|---|---|---|
| 1 | swap root 10 with last (1); heapify [1,5,3,4] | [5,4,3,1 | 10] |
| 2 | swap 5 with 1; heapify [1,4,3] | [4,1,3 | 5 10] |
| 3 | swap 4 with 3; heapify [3,1] | [3,1 | 4 5 10] |
| 4 | swap 3 with 1 | [1 | 3 4 5 10] |

**Sorted: 1 3 4 5 10.**

**Complexity:** build O(n) + n heapify O(log n) = **O(n log n)** in **all** cases (best, average,
worst) — its selling point. **In-place** (O(1) extra), but **not stable**.

### Likely exam questions

- **[5]** Define a max-heap and a min-heap. Give the array index relations.
- **[5]** Insert `15` into the max-heap [40,30,20,10,25]; show sift-up.
- **[10]** Explain heap sort with an algorithm; sort `12, 11, 13, 5, 6, 7` showing the heap at
  each step.
- **[10]** How is a priority queue implemented using a heap? Give the complexities.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Root of a max-heap is the?" | **Maximum**. |
| "A heap is which kind of binary tree?" | **Complete**. |
| "Heap sort time complexity (worst)?" | **O(n log n)**. |
| "Is heap sort stable?" | **No**. In-place: **yes**. |
| "Build-heap cost?" | **O(n)**. |
| "Parent of index i (1-based)?" | **⌊i/2⌋**. |

---

## 11. B-trees and B+ trees

### Concept — why they exist

BSTs and AVL trees assume the data sit in **RAM**. Databases and file systems store indexes on
**disk**, where a single seek is ~100,000× slower than a memory access. The cost is dominated by
the **number of disk blocks read**, i.e. the **height** of the tree. So we want a **short, bushy,
balanced** tree with a **high branching factor (order)** — one node = one disk block holding
*many* keys. That is the **B-tree**.

### 11.1 B-tree

A **B-tree of order m** is a balanced multi-way search tree in which:
1. Every node holds **at most m − 1 keys** and **at most m children**.
2. Every node (except root) holds **at least ⌈m/2⌉ − 1 keys** (so ≥ ⌈m/2⌉ children) — the
   **half-full** rule that keeps it balanced.
3. Keys within a node are **sorted**; children hang between/around the keys like a multi-way BST.
4. **All leaves appear at the same level** — the tree is **perfectly height-balanced**.
5. A non-leaf node with k keys has exactly **k + 1 children**.

**Insertion:** always insert into the correct **leaf** (found by search). If the leaf overflows
(m keys), **split** it at the **median**: the median key moves **up** into the parent, and the
node divides into two. Splits can cascade upward; if the root splits, the tree **grows in height
by one** — this is the only way a B-tree height increases, and it grows from the **root**, which
is why it stays balanced.

*Worked (order 3 = 2-3 tree, max 2 keys/node). Insert 10, 20, 5, 6, 12, 30, 7, 17:*
- 10, 20 → node `[10 20]`.
- Insert 5 → `[5 10 20]` overflows (3 keys); median **10** goes up:
  ```
        [10]
       /    \
    [5]     [20]
  ```
- Insert 6 → leaf `[5 6]`. Insert 12 → leaf `[12 20]`. Insert 30 → `[12 20 30]` overflows;
  median **20** goes up to root `[10 20]`:
  ```
          [10 20]
         /   |   \
      [5 6] [12] [30]
  ```
- Insert 7 → leaf `[5 6 7]` overflows; median **6** up → root `[6 10 20]`... and so on. **The
  marked skill: insert into a leaf, split on overflow, push the median up.**

### 11.2 B+ tree

A **B+ tree** is the variant used by virtually all real databases (and NTFS, etc.). Two
differences from a B-tree, both worth stating:

1. **All actual data/record pointers live only in the LEAF nodes.** Internal nodes store
   **only keys as an index/routing map** — so a key may appear twice (once as a router, once in
   a leaf). This lets each internal block index **more** children (no data taking up room),
   giving a shorter tree.
2. **The leaves are linked together in a sorted linked list.** This makes **range queries and
   sequential/ordered scans extremely efficient** — find the start leaf, then walk the link
   chain — which a plain B-tree cannot do without repeated root-to-leaf traversals.

### 11.3 B-tree vs B+ tree

| Criterion | **B-tree** | **B+ tree** |
|---|---|---|
| Data stored in | **All nodes** (internal + leaf) | **Leaf nodes only** |
| Internal nodes | Hold keys **and** data | Hold **keys only** (index) |
| Key duplication | No | Yes (routing keys repeat in leaves) |
| Leaves linked? | No | **Yes** — sorted linked list |
| Range/sequential query | Poorer | **Excellent** |
| Tree height | Slightly taller | **Shorter** (more keys per internal node) |
| Search cost | Can stop early (data in internal node) | Always goes to a leaf (uniform) |
| Used by | Some file systems | **Most DBMS indexes, NTFS** |

### Likely exam questions

- **[5]** What is a B-tree of order m? State its properties.
- **[5]** Differentiate B-tree and B+ tree.
- **[5]** Why are B-trees preferred for database indexing over AVL trees?
- **[10]** Construct a B-tree of order 3 by inserting `1, 2, 3, 4, 5, 6, 7`, showing splits.
- **[10]** Explain the B+ tree structure and how it supports efficient range queries.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "In a B+ tree, data is stored in?" | **Leaf nodes only**. |
| "B-tree of order m: max children / max keys?" | **m children, m − 1 keys**. |
| "B-tree keeps balance by?" | **Splitting on overflow, pushing the median up**; all leaves at the same level. |
| "Which structure links its leaves?" | **B+ tree**. |
| "A B-tree of order m: min keys (non-root)?" | **⌈m/2⌉ − 1**. |
| "Why B-trees for disk?" | **Minimise disk accesses (short, high-fan-out tree)**. |

---

## 12. Graphs

### Concept

A **graph** G = (V, E) is a set of **vertices** V and **edges** E connecting pairs of vertices.
Unlike a tree, a graph may have **cycles**, may be **disconnected**, and a vertex may have any
number of neighbours. It is the most general non-linear structure.

| Term | Meaning |
|---|---|
| **Directed (digraph)** | Edges have direction (u → v ≠ v → u) |
| **Undirected** | Edges are bidirectional |
| **Weighted** | Each edge carries a cost/weight |
| **Degree** | Number of edges at a vertex (in-degree/out-degree for digraphs) |
| **Path** | A sequence of vertices joined by edges |
| **Cycle** | A path that returns to its start |
| **Connected** | A path exists between every pair (undirected) |
| **Complete** | Every pair of vertices is joined; `n(n−1)/2` edges (undirected) |
| **Adjacent** | Two vertices joined by an edge |

### 12.1 Representations — adjacency matrix vs adjacency list

**Adjacency matrix:** an n×n matrix `A` where `A[i][j] = 1` (or the weight) if an edge i→j
exists, else 0. Symmetric for undirected graphs.

**Adjacency list:** an array of n lists; list `i` holds the neighbours of vertex i.

| Criterion | **Adjacency matrix** | **Adjacency list** |
|---|---|---|
| Space | **O(V²)** — wasteful for sparse graphs | **O(V + E)** — compact for sparse graphs |
| Edge lookup "is u–v an edge?" | **O(1)** | O(degree) |
| Iterate neighbours of u | O(V) | **O(degree)** — efficient |
| Add edge | O(1) | O(1) |
| Best for | **Dense** graphs, quick edge tests | **Sparse** graphs (the common case), traversals |

### 12.2 BFS and DFS — worked traces

**Breadth-First Search (BFS):** explore **level by level** from the source, using a **QUEUE**.
Visit a vertex, enqueue all unvisited neighbours, repeat. Finds the **shortest path in an
unweighted graph**. Time **O(V + E)**.

**Depth-First Search (DFS):** go **as deep as possible** before backtracking, using a **STACK**
(or recursion). Time **O(V + E)**. Used for cycle detection, topological sort, connected
components, path finding.

*Worked. Graph (undirected), neighbours listed in ascending order:*
```
1 — 2, 3
2 — 1, 4, 5
3 — 1, 6
4 — 2
5 — 2, 6
6 — 3, 5
```

**BFS from 1** (queue in brackets):
| Dequeue | Enqueue unvisited neighbours | Visited order |
|---|---|---|
| 1 | 2, 3 → [2,3] | 1 |
| 2 | 4, 5 → [3,4,5] | 1 2 |
| 3 | 6 → [4,5,6] | 1 2 3 |
| 4 | — → [5,6] | 1 2 3 4 |
| 5 | (6 already queued) → [6] | 1 2 3 4 5 |
| 6 | — → [] | 1 2 3 4 5 6 |

**BFS order = 1 2 3 4 5 6.**

**DFS from 1** (recursive / stack, take smallest unvisited first):
1 → 2 → 4 (dead end, back) → 5 → 6 → 3 (6's neighbour 3 unvisited) → back up, all done.
**DFS order = 1 2 4 5 6 3.**

### 12.3 Spanning trees and MST

A **spanning tree** of a connected graph with n vertices is a **subgraph that is a tree
(no cycles) and includes all n vertices** — hence exactly **n − 1 edges**. A **minimum spanning
tree (MST)** is the spanning tree of **least total edge weight**. Two greedy algorithms:

**Prim's algorithm** — grow **one tree** from a start vertex: repeatedly add the **cheapest edge
that connects a vertex already in the tree to one outside it**. Good for dense graphs;
O(E log V) with a heap.

**Kruskal's algorithm** — consider **all edges in ascending weight order**; add an edge if it
**does not form a cycle** (checked with a **union-find / disjoint-set** structure). Stop at n−1
edges. Good for sparse graphs; O(E log E).

*Worked MST. Weighted undirected graph:*
```
Edges: A-B 4, A-C 4, B-C 2, B-D 5, C-D 8, C-E 10, D-E 2, D-F 6, E-F 3
Vertices: A B C D E F
```

**Kruskal** — sort edges: B-C 2, D-E 2, E-F 3, A-B 4, A-C 4, B-D 5, D-F 6, C-D 8, C-E 10.
| Edge | Weight | Cycle? | Action |
|---|---|---|---|
| B-C | 2 | no | **add** {B,C} |
| D-E | 2 | no | **add** {D,E} |
| E-F | 3 | no | **add** {D,E,F} |
| A-B | 4 | no | **add** {A,B,C} |
| A-C | 4 | **yes** (A,C already joined) | skip |
| B-D | 5 | no | **add** — now all vertices joined (5 edges = n−1) |
| stop | | | |
**MST edges: B-C, D-E, E-F, A-B, B-D. Total weight = 2+2+3+4+5 = 16.**

**Prim from A** gives the *same weight* (16): A-B(4), B-C(2), B-D(5), D-E(2), E-F(3). (MSTs may
differ in edges if weights tie, but total weight is unique.)

### 12.4 Dijkstra's shortest path (WORKED TABLE)

**Dijkstra** finds the **shortest path from a single source to all vertices** in a graph with
**non-negative weights**. Greedy: maintain a tentative distance for each vertex; repeatedly
**finalise the unvisited vertex with the smallest tentative distance**, then **relax** its
neighbours (update `dist[v] = min(dist[v], dist[u] + w(u,v))`).

*Worked. Directed/undirected weighted graph, source = A:*
```
A-B 4, A-C 1, C-B 2, C-D 5, B-D 1, B-E 5, D-E 3
```

| Iteration | Finalised (dist) | A | B | C | D | E |
|---|---|---|---|---|---|---|
| init | — | 0 | ∞ | ∞ | ∞ | ∞ |
| pick A (0) | A | 0 | 4 | **1** | ∞ | ∞ |
| pick C (1) | A,C | 0 | **3** (1+2) | 1 | **6** (1+5) | ∞ |
| pick B (3) | A,C,B | 0 | 3 | 1 | **4** (3+1) | **8** (3+5) |
| pick D (4) | A,C,B,D | 0 | 3 | 1 | 4 | **7** (4+3) |
| pick E (7) | all | 0 | 3 | 1 | 4 | 7 |

**Shortest distances from A:** A=0, B=3, C=1, D=4, E=7.
**Shortest path to E:** A → C → B → D → E (1+2+1+3 = 7).

**Key exam point:** Dijkstra **fails with negative edge weights** — use **Bellman-Ford** there.

### 12.5 Topological sort

A **topological ordering** of a **DAG** (Directed Acyclic Graph) is a linear ordering of
vertices such that for **every edge u → v, u comes before v**. Used for **task scheduling,
course prerequisites, build systems, instruction ordering**.

Two methods:
- **Kahn's (BFS-based):** repeatedly output a vertex with **in-degree 0**, remove it and
  decrement its neighbours' in-degrees.
- **DFS-based:** do DFS; push each vertex onto a stack **on finishing** (postorder); the
  reversed stack is the topological order.

*Worked. Edges: A→C, B→C, C→D, D→E, B→D.*
In-degrees: A=0, B=0, C=2, D=2, E=1. Output in-degree-0 vertices: **A** (C→1), then **B**
(C→0, D→1), then **C** (D→0), then **D** (E→0), then **E**.
**Topological order: A B C D E.** (Multiple valid orders exist when several vertices have
in-degree 0.)

### Likely exam questions

- **[5]** Differentiate adjacency matrix and adjacency list; give space complexities.
- **[5]** Differentiate BFS and DFS; name their auxiliary structures.
- **[5]** Define spanning tree and minimum spanning tree.
- **[10]** Apply Kruskal's/Prim's algorithm to a given weighted graph and find the MST.
- **[10]** Apply Dijkstra's algorithm from a given source; show the distance table at each step.
- **[10]** Perform BFS and DFS on a given graph starting from a given vertex; show the order.
- **[15]** Explain graph representations, traversals (BFS, DFS with traces), and find the MST by
  both Prim and Kruskal, plus the shortest path by Dijkstra, for a given weighted graph.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "BFS uses a? DFS uses a?" | **Queue** / **Stack (or recursion)**. |
| "Adjacency matrix space?" | **O(V²)**. Adjacency list: **O(V + E)**. |
| "MST of a graph with n vertices has?" | **n − 1 edges**. |
| "Kruskal avoids cycles using?" | **Union-Find / disjoint set**. |
| "Dijkstra fails when?" | There are **negative edge weights** (use Bellman-Ford). |
| "Topological sort applies to?" | A **DAG** (directed acyclic graph). |
| "BFS finds shortest path in?" | An **unweighted** graph. |
| "Prim grows? Kruskal grows?" | Prim: **one tree**. Kruskal: **a forest merging into one**. |

---

## 13. Searching

### 13.1 Linear (sequential) search

Scan from the first element until the key is found or the list ends. Works on **any** list
(sorted or not). **Best O(1)** (first element), **worst/average O(n)**. Simple but slow for
large data.

### 13.2 Binary search (WORKED)

Requires a **sorted array**. Compare the key with the **middle** element; if equal, done; if the
key is smaller, search the **left half**; if larger, the **right half**. Each step halves the
search space → **O(log n)**.

```
low = 0; high = n−1;
while (low <= high){
    mid = (low + high) / 2;
    if (A[mid] == key) return mid;
    else if (A[mid] < key) low = mid + 1;
    else high = mid − 1;
}
return −1;   /* not found */
```

*Worked. Search 23 in `[2, 5, 8, 12, 16, 23, 38, 45, 56, 72]` (indices 0–9).*
| Step | low | high | mid | A[mid] | Compare |
|---|---|---|---|---|---|
| 1 | 0 | 9 | 4 | 16 | 23 > 16 → low = 5 |
| 2 | 5 | 9 | 7 | 45 | 23 < 45 → high = 6 |
| 3 | 5 | 6 | 5 | 23 | **found at index 5** |

Three comparisons versus up to six for linear search — the gap widens hugely as n grows
(1,000,000 elements ⇒ ≤ 20 comparisons).

| | Linear search | Binary search |
|---|---|---|
| Data must be sorted? | No | **Yes** |
| Best case | O(1) | O(1) |
| Worst/avg case | **O(n)** | **O(log n)** |
| Data structure | Array or linked list | **Array only** (needs random access) |

### Likely exam questions

- **[5]** Compare linear and binary search.
- **[5]** Write the binary search algorithm and trace it for a given key.
- **[10]** Explain binary search (iterative and recursive); derive its O(log n) complexity.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Binary search requires the data to be?" | **Sorted**. |
| "Binary search time complexity?" | **O(log n)**. |
| "Binary search on a linked list?" | **Inefficient** — no O(1) random access. |
| "Linear search worst case?" | **O(n)**. |

---

## 14. Sorting — every algorithm, worked, with the master table

### Concept

**Stability:** a sort is **stable** if equal keys keep their original relative order — matters
when sorting records by a secondary key. **In-place:** uses O(1) extra space. **Comparison
sorts** are bounded below by **Ω(n log n)**; **non-comparison sorts** (counting, radix) beat
that by exploiting key structure.

### 14.1 Bubble sort

Repeatedly step through the list, **swap adjacent out-of-order pairs**; the largest "bubbles" to
the end each pass. With a swapped-flag, best case (already sorted) is O(n).

*Worked. `5 1 4 2` ascending.*
- Pass 1: (5,1)→1 5 4 2; (5,4)→1 4 5 2; (5,2)→1 4 2 5. [5 fixed]
- Pass 2: (1,4)ok; (4,2)→1 2 4 5; [4 fixed]
- Pass 3: (1,2)ok. **Sorted: 1 2 4 5.**

### 14.2 Selection sort

Find the **minimum** of the unsorted part and swap it into the next position. Always O(n²);
**minimises swaps** (n−1). Not stable.

*Worked. `29 10 14 37 13`:*
min=10 → swap: `10 29 14 37 13`; min(rest)=13 → `10 13 14 37 29`; min=14 (in place);
min=29 → `10 13 14 29 37`. **Sorted.**

### 14.3 Insertion sort

Build the sorted portion one element at a time: take the next element and **insert it into its
correct place** among the already-sorted elements by shifting. Best case O(n) (nearly sorted),
**stable**, great for small/almost-sorted data.

*Worked. `12 11 13 5 6`:*
- 11 < 12 → `11 12 13 5 6`
- 13 in place → `11 12 13 5 6`
- 5 shifts to front → `5 11 12 13 6`
- 6 inserts after 5 → `5 6 11 12 13`. **Sorted.**

### 14.4 Merge sort

**Divide and conquer:** split the array in half, **recursively sort each half**, then **merge**
the two sorted halves. Always **O(n log n)**, **stable**, but needs **O(n) extra space** for
merging. The go-to for linked lists and external sorting.

*Worked. `38 27 43 3 9 82 10`:*
- Split → [38 27 43 3] [9 82 10]
- Sort left → [3 27 38 43]; sort right → [9 10 82]
- Merge → compare fronts repeatedly → **3 9 10 27 38 43 82**.

### 14.5 Quick sort

Pick a **pivot**, **partition** so that smaller elements go left and larger go right, then
recurse on each side. Average **O(n log n)** and usually the **fastest in practice** (good cache
behaviour, in-place). **Worst case O(n²)** when the pivot is always the smallest/largest (e.g.
already-sorted data with first-element pivot) — mitigated by random or median-of-three pivots.
Not stable.

*Worked. `7 2 1 6 8 5 3 4`, pivot = last (4), Lomuto partition:*
Elements < 4: 2,1,3 → left; ≥ 4: 7,6,8,5 → right; pivot 4 lands between:
`2 1 3 | 4 | 7 6 8 5` → recurse each side → sorted `1 2 3 4 5 6 7 8`.

### 14.6 Heap sort

Covered in §10.2: build a max-heap, repeatedly extract the max. **O(n log n) in all cases**,
in-place, **not stable**.

### 14.7 Counting sort

**Non-comparison.** For integer keys in a small range [0, k]: **count** occurrences of each key,
compute prefix sums, then place each element directly. **O(n + k)**, **stable**, but needs
O(k) space — impractical when k ≫ n.

*Worked. `4 2 2 8 3 3 1` (range 0–8):* counts → 1:1, 2:2, 3:2, 4:1, 8:1 → output
`1 2 2 3 3 4 8`.

### 14.8 Radix sort

**Non-comparison.** Sort integers **digit by digit**, least-significant digit first, using a
**stable** sub-sort (usually counting sort) at each digit. **O(d·(n + b))** where d = number of
digits, b = base. Stable.

*Worked. `170 45 75 90 802 24 2 66`:*
- By units: 170 90 802 2 24 45 75 66
- By tens: 802 2 24 45 66 170 75 90
- By hundreds: 2 24 45 66 75 90 170 802. **Sorted.**

### 14.9 Shell sort

An improved insertion sort: sort elements far apart first using a **gap sequence** (e.g. n/2,
n/4, …, 1), shrinking the gap to 1. This moves out-of-place elements a long way early, so the
final gap-1 insertion pass has little work. In-place, **not stable**; complexity depends on the
gap sequence (roughly **O(n log²n)** typical, worst O(n²)).

*Worked. `35 33 42 10 14 19 27 44`, gap 4:* compare positions 4 apart and swap → then gap 2 →
then gap 1 (ordinary insertion sort on a nearly-sorted array). Final: sorted ascending.

### 14.10 THE MASTER TABLE — memorise this

| Algorithm | Best | Average | Worst | Space | Stable? | In-place? | Notes |
|---|---|---|---|---|---|---|---|
| **Bubble** | **O(n)**† | O(n²) | O(n²) | O(1) | **Yes** | Yes | †with swapped-flag |
| **Selection** | O(n²) | O(n²) | O(n²) | O(1) | **No** | Yes | Fewest swaps (n−1) |
| **Insertion** | **O(n)** | O(n²) | O(n²) | O(1) | **Yes** | Yes | Best for small/nearly-sorted |
| **Merge** | O(n log n) | O(n log n) | **O(n log n)** | **O(n)** | **Yes** | No | Divide & conquer; external sort |
| **Quick** | O(n log n) | O(n log n) | **O(n²)** | O(log n) | **No** | Yes | Fastest in practice; pivot matters |
| **Heap** | O(n log n) | O(n log n) | **O(n log n)** | O(1) | **No** | Yes | Guaranteed n log n, in-place |
| **Counting** | O(n+k) | O(n+k) | O(n+k) | O(k) | **Yes** | No | Integer keys, small range k |
| **Radix** | O(d(n+b)) | O(d(n+b)) | O(d(n+b)) | O(n+b) | **Yes** | No | Digit-by-digit; needs stable subsort |
| **Shell** | O(n log n) | ~O(n^1.25) | O(n²) | O(1) | **No** | Yes | Gap-based insertion sort |

**The four facts examiners hammer:**
1. **Stable sorts:** bubble, insertion, merge, counting, radix. **Unstable:** selection, quick,
   heap, shell.
2. **Merge and heap sort are O(n log n) in the worst case; quick sort is O(n²) worst case.**
3. **Comparison-sort lower bound is Ω(n log n)**; counting/radix beat it because they don't
   compare keys.
4. **Insertion (and bubble with flag) are O(n) on already-sorted data**; quick sort with a
   first-element pivot is **O(n²)** on already-sorted data — the classic trap pair.

### Likely exam questions

- **[5]** Define stability and in-place sorting; classify the standard sorts.
- **[5]** Trace bubble/selection/insertion sort on a given list.
- **[10]** Explain merge sort with an example and derive its O(n log n) complexity.
- **[10]** Explain quick sort; show partitioning on a given array; discuss best and worst cases.
- **[15]** Compare all major sorting algorithms on time, space, stability and in-place property
  in a table, and trace any two of them on a given data set.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Which sort is O(n²) in the worst case but usually fastest?" | **Quick sort**. |
| "Worst case of quick sort?" | **O(n²)** (already-sorted with bad pivot). |
| "Which comparison sort is O(n log n) worst-case AND in-place?" | **Heap sort**. |
| "Which sorts are stable?" | Bubble, insertion, merge, counting, radix. |
| "Which sort does the fewest swaps?" | **Selection** (n−1). |
| "Non-comparison sorts?" | **Counting, radix** (also bucket). |
| "Best case of insertion sort?" | **O(n)** (nearly sorted). |
| "Lower bound for comparison sorting?" | **Ω(n log n)**. |

---

## 15. Hashing

### Concept

**Hashing** maps a key directly to an array index via a **hash function** `h(key)`, giving
**average O(1)** insert, search and delete — beating the O(log n) of trees. A **hash table** is
the array; a **collision** is when two keys hash to the same slot, and **collision resolution**
is the heart of the topic.

**Load factor** **α = n / m** (n = keys stored, m = table size). It measures fullness:
performance degrades as α rises. Rule of thumb — **keep α below ~0.7** for open addressing;
rehash (grow and re-insert) when exceeded.

### 15.1 Hash functions

| Method | h(k) | Note |
|---|---|---|
| **Division** | **k mod m** | Simplest; choose **m prime** (and not near a power of 2) to spread keys |
| **Mid-square** | Square k, take the middle digits | Depends on all digits of k |
| **Folding** | Split k into parts, add them, mod m | Good for long keys |
| **Multiplication** | ⌊m (kA mod 1)⌋, A ≈ 0.618 | m need not be prime |

### 15.2 Collision resolution

**(a) Separate chaining** — each slot holds a **linked list** of all keys hashing there.
Insert = prepend (O(1)); search = scan the chain (O(1 + α) average). Simple, α can exceed 1,
deletion easy. Extra memory for pointers.

**(b) Open addressing** — all keys live **in the table itself**; on collision, **probe** for the
next free slot by a fixed sequence. α ≤ 1 always. Three probe sequences:

| Scheme | Probe i (i = 0,1,2,…) | Problem |
|---|---|---|
| **Linear probing** | `(h(k) + i) mod m` | **Primary clustering** — long runs of filled slots form and grow |
| **Quadratic probing** | `(h(k) + i²) mod m` | **Secondary clustering**; may not probe all slots |
| **Double hashing** | `(h₁(k) + i·h₂(k)) mod m` | **Best spread**; needs a good second hash, e.g. `h₂(k) = R − (k mod R)`, R prime < m |

### 15.3 Worked insertions

**Table size m = 10, h(k) = k mod 10. Insert 23, 43, 13, 27, 33.**

**Linear probing** `(h + i) mod 10`:
| Key | h(k) | Probe sequence | Slot |
|---|---|---|---|
| 23 | 3 | slot 3 free | **3** |
| 43 | 3 | 3 taken → 4 free | **4** |
| 13 | 3 | 3,4 taken → 5 free | **5** |
| 27 | 7 | slot 7 free | **7** |
| 33 | 3 | 3,4,5 taken → 6 free | **6** |

Table: `[_,_,_,23,43,13,33,27,_,_]` — note the **cluster** 3–7.

**Quadratic probing** `(h + i²) mod 10` for the same keys:
| Key | h | Probes (i²=0,1,4,9,…) | Slot |
|---|---|---|---|
| 23 | 3 | 3 | **3** |
| 43 | 3 | 3(taken), 3+1=4 | **4** |
| 13 | 3 | 3,4 taken, 3+4=7 | **7** |
| 27 | 7 | 7 taken, 7+1=8 | **8** |
| 33 | 3 | 3,4 taken, 3+4=7 taken, 3+9=12 mod10=2 | **2** |

**Double hashing** `h₂(k) = 7 − (k mod 7)`, probe `(h₁ + i·h₂) mod 10`:
| Key | h₁=k mod10 | h₂=7−(k mod7) | Probes | Slot |
|---|---|---|---|---|
| 23 | 3 | 7−2=5 | 3 | **3** |
| 43 | 3 | 7−1=6 | 3 taken → 3+6=9 | **9** |
| 13 | 3 | 7−6=1 | 3 taken → 4 | **4** |
| 27 | 7 | 7−6=1 | 7 | **7** |
| 33 | 3 | 7−5=2 | 3 taken → 5 | **5** |

**Separate chaining** — simply hang each key on the list at `k mod 10`: slot 3 → 23→43→13→33
(a chain of 4), slot 7 → 27.

### 15.4 Chaining vs open addressing

| Criterion | **Chaining** | **Open addressing** |
|---|---|---|
| Storage | Table + linked lists | Table only |
| Load factor α | Can exceed 1 | Must stay **≤ 1** |
| Deletion | Easy | Hard (needs tombstones) |
| Clustering | None | Linear/quadratic clustering |
| Cache performance | Poorer (pointer chasing) | **Better** (contiguous) |
| Extra memory | Pointers | None |

### Likely exam questions

- **[5]** What is hashing? Define hash function, collision and load factor.
- **[5]** Explain linear probing, quadratic probing and double hashing.
- **[5]** Differentiate separate chaining and open addressing.
- **[10]** Insert the keys `12, 22, 32, 42, 52` into a table of size 10 using (a) linear probing
  and (b) chaining; show the final table.
- **[10]** Explain collision resolution techniques with worked examples and compare them.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Load factor is?" | **α = n / m** (keys / slots). |
| "Average time for hash search?" | **O(1)**. |
| "Linear probing suffers from?" | **Primary clustering**. |
| "Which resolution can have α > 1?" | **Separate chaining**. |
| "Best hash-table size choice?" | A **prime** number (for division method). |
| "Double hashing probe?" | **(h₁(k) + i·h₂(k)) mod m**. |
| "Deletion is awkward in?" | **Open addressing** (needs tombstones). |

---

## 16. File structures / file organisation

### Concept

A **file** is a named collection of **records**; each record is a set of **fields**; a field is
a group of characters representing one data item. A **key field** uniquely identifies a record.
**File organisation** is how records are physically arranged on secondary storage and how they
are accessed — the on-disk analogue of choosing a data structure.

| Organisation | How records are stored | Access | Pros | Cons |
|---|---|---|---|---|
| **Sequential** | Records stored **one after another**, usually **sorted on a key** | Read in order; must scan from the start | Simple; **efficient for batch processing** and full-file reads; compact | **No fast random access**; insert/delete needs rewriting/reorganising |
| **Relative / Direct (random)** | Record address computed **directly from the key** (often by **hashing**) | **Direct access** to any record in ~O(1) | **Very fast random access** | Needs a key→address function; collisions; poor for sequential/range reads |
| **Indexed** | Data file **+ a separate index** (key → record address), the index searched (often a B+ tree) | Random **and** ordered | Fast random access without hashing; supports range queries | Index storage and maintenance overhead |
| **Index-sequential (ISAM)** | Records **sorted sequentially**, **plus an index** of key ranges/blocks | Both **sequential** and **indexed (random)** | Best of both — ordered scans *and* keyed lookups | Index maintenance; overflow areas on insertion |

### 16.1 Inverted lists (inverted files) — named in the Forensic syllabus

An **inverted list/index** maps **each attribute value → the list of record keys that have that
value** — the inverse of "record → its field values". It is the structure behind **search
engines and full-text search**: for the word "forensic", store the list of all documents/records
containing it. Fast **multi-attribute and content queries** ("all records where dept = CS AND
year = 2026") without scanning the whole file; cost is the storage and update of the indexes.

### 16.2 Multi-lists — named in the Forensic syllabus

A **multi-list** organisation threads records into **multiple linked lists**, one **per indexed
attribute**. Each record carries a **link field for every attribute list** it belongs to, so it
can be reached along any of those chains. Example: one chain links all "CS" records, another
links all "2026" records; a record in CS-2026 sits on both chains. Contrast with inverted lists,
where the pointers live in the **index** rather than **inside the records**.

| | **Inverted list** | **Multi-list** |
|---|---|---|
| Where pointers live | In the **index** (a full list of keys per value) | **Inside each record** (one link per attribute) |
| Index size | Large (variable-length lists) | Small (index just points to each chain's head) |
| Query speed | Faster (list is precomputed) | Must traverse chains |
| Update cost | Higher (rebuild lists) | Lower (splice a node) |

### Likely exam questions

- **[5]** Define field, record and file. Differentiate sequential and direct file organisation.
- **[5]** What is an index-sequential file? State its advantages.
- **[5]** Differentiate inverted lists and multi-lists.
- **[10]** Explain the various file organisation techniques (sequential, direct/relative,
  indexed, index-sequential) with their access methods, advantages and disadvantages.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Best organisation for batch processing?" | **Sequential**. |
| "Direct/relative file access is achieved by?" | **Hashing / key→address computation**. |
| "ISAM supports?" | **Both sequential and random** access. |
| "Search engines use?" | **Inverted lists/indexes**. |
| "Pointers stored inside records characterise?" | **Multi-list** organisation. |
| "Smallest unit — field, record or file?" | **Field**. |

---

## 17. Algorithm analysis and asymptotic notation

### Concept

An **algorithm's** efficiency is measured by how its **running time / space grows with the input
size n** — the machine-independent, constants-ignored view. We describe growth with **asymptotic
notation**:

| Notation | Bounds | Meaning | Says |
|---|---|---|---|
| **Big-O — O(f)** | **Upper** | Grows **no faster than** f | **Worst case** guarantee |
| **Big-Omega — Ω(f)** | **Lower** | Grows **at least as fast as** f | **Best case** / lower bound |
| **Big-Theta — Θ(f)** | **Tight** | Grows **exactly like** f (both bounds) | Exact order when best = worst |

Formally, `T(n) = O(f(n))` if there exist constants c > 0 and n₀ such that `T(n) ≤ c·f(n)` for
all n ≥ n₀. We **drop constants and lower-order terms**: `3n² + 5n + 7 = O(n²)`.

**The growth hierarchy** (slowest-growing = best, left to right):

> **O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(n³) < O(2ⁿ) < O(n!)**

| Class | Name | Typical source |
|---|---|---|
| O(1) | Constant | Array index, hash lookup, stack push |
| O(log n) | Logarithmic | Binary search, balanced-tree operation |
| O(n) | Linear | Linear search, one loop over the data |
| O(n log n) | Linearithmic | Merge/heap sort, efficient comparison sorts |
| O(n²) | Quadratic | Bubble/selection/insertion sort, nested loops |
| O(2ⁿ) | Exponential | Naive subset generation, brute-force TSP |
| O(n!) | Factorial | Permutation generation, brute-force TSP |

**Best vs average vs worst case:** for the same algorithm these can differ — e.g. quick sort is
Θ(n log n) average but O(n²) worst; linear search is O(1) best, O(n) worst. **Big-O quoted alone
almost always means the worst case.**

**Design paradigms** (named in the CS-Degree syllabus, worth a sentence each):
- **Divide and conquer** — split, solve recursively, combine (merge sort, quick sort, binary
  search).
- **Greedy** — make the locally optimal choice each step (Prim, Kruskal, Dijkstra, Huffman).
- **Dynamic programming** — solve overlapping subproblems once and store results (Floyd-Warshall,
  LCS, knapsack).
- **NP-completeness** — the class of problems for which no known polynomial algorithm exists and
  a solution is verifiable in polynomial time (SAT, TSP-decision, subset-sum).

### Likely exam questions

- **[5]** Define big-O, big-Ω and big-Θ notation.
- **[5]** State the order of growth of common complexity classes with examples.
- **[5]** Give the best, average and worst-case complexity of quick sort and binary search.
- **[10]** Explain asymptotic notation with formal definitions and examples; analyse the time
  complexity of a given code fragment.

### MCQ traps

| Trap | Correct answer |
|---|---|
| "Big-O denotes the ___ bound?" | **Upper** (worst case). |
| "Which is faster: O(n log n) or O(n²)?" | **O(n log n)**. |
| "3n² + 2n + 1 is?" | **O(n²)**. |
| "Binary search is?" | **O(log n)**. |
| "Θ gives which bound?" | **Tight (both upper and lower)**. |
| "Merge sort belongs to which class?" | **O(n log n)**. |

---

## 18. Last-week revision sheet

**Twenty-five facts most likely to be one-mark MCQs:**

1. Stack = **LIFO**; queue = **FIFO**; deque = both ends; both stack & queue emulated by a deque.
2. **1D address:** B + (i − LB)·w. **2D row-major** multiplies row index by **#columns (n)**;
   **column-major** by **#rows (m)**.
3. Postfix of `A+B*C` = **A B C * +**; prefix = **+ A * B C**. Postfix/prefix need **no
   parentheses**.
4. **Recursion uses the call stack**; needs a **base case**; risk = **stack overflow**.
5. Circular-queue full (one-slot method): **(rear+1) % n == front**.
6. Array = O(1) access, O(n) insert; linked list = O(n) access, O(1) insert. **Random access →
   array only.**
7. Tree with n nodes = **n − 1 edges**; max nodes at level ℓ = **2ˡ**; max nodes height h =
   **2^(h+1) − 1**.
8. **Inorder of a BST = sorted.** Preorder root **first**, postorder root **last**.
9. Unique reconstruction needs **inorder + (pre or post)**; **pre + post fails** for general trees.
10. **AVL balance factor ∈ {−1,0,+1}**; LL→right, RR→left, LR→left-then-right, RL→right-then-left.
11. **Heap = complete tree**; max-heap root = max; heap sort **O(n log n)**, in-place, **not
    stable**; build-heap **O(n)**.
12. **B-tree order m:** ≤ m children, ≤ m−1 keys, all leaves same level, split pushes **median
    up**.
13. **B+ tree:** data in **leaves only**, **leaves linked** → fast range queries.
14. **BFS = queue** (shortest path, unweighted); **DFS = stack/recursion**. Both **O(V+E)**.
15. Adjacency matrix **O(V²)**; adjacency list **O(V+E)**.
16. **MST has n−1 edges**; Prim grows one tree, Kruskal sorts edges + union-find.
17. **Dijkstra needs non-negative weights**; else **Bellman-Ford**.
18. **Topological sort → DAG** only.
19. **Binary search → sorted array, O(log n).**
20. **O(n²) sorts:** bubble, selection, insertion. **O(n log n):** merge, heap always; quick on
    average.
21. **Quick sort worst = O(n²)**; **merge & heap worst = O(n log n)**.
22. **Stable:** bubble, insertion, merge, counting, radix. **Unstable:** selection, quick, heap,
    shell.
23. **Counting/radix** are **non-comparison** → beat Ω(n log n).
24. **Load factor α = n/m**; linear probing → **primary clustering**; double hashing = best
    spread.
25. **Big-O = upper/worst; Ω = lower/best; Θ = tight.** Growth: 1 < log n < n < n log n < n² <
    2ⁿ < n!.

**Descriptive-paper strategy.** Data structures reliably supply Section A short answers and at
least one Section C 15-marker in the CS-Degree and Forensic papers. Prepare these six as
guaranteed long answers, each with its worked example or diagram:
(a) **Stacks — infix-to-postfix conversion + postfix evaluation, fully worked**;
(b) **AVL tree — all four rotations + a build-from-sequence trace**;
(c) **Graph algorithms — BFS/DFS traces + Prim/Kruskal + a Dijkstra table** on one graph;
(d) **Sorting — the master comparison table + a trace of merge and quick sort**;
(e) **Hashing — collision resolution with a worked linear-probing / chaining insertion**;
(f) **B-tree / B+ tree — construction with splitting + the B-tree vs B+ tree table**.
For every numerical (address calc, postfix, Dijkstra, hashing, sort trace) **show every
intermediate step in a table** — worked numericals are unambiguous to mark and score the highest
per minute of writing.
