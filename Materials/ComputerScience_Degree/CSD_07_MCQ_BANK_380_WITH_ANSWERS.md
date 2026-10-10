# CS (Degree) MCQ Bank — 380 Questions with Answers

**NPSC CTSE 2026 · Computer Science & Engineering (Degree) · MCQ paper: 100 Qs × 2 marks, 2 hours · Monday 12 Oct 2026**

## Exam strategy in 30 seconds

- **Marking:** +2 for a correct answer, 0 for a blank. For a wrong answer the 2025 booklet printed **"−⅓ mark"**, while the official pattern note says "one-third", which some read as ⅓ of 2 = **−0.67**. Check tomorrow's instructions page.
- **Guessing maths, under either reading:** a blind 4-option guess is worth **+0.25** (if −⅓) or **exactly 0** (if −0.67), so it never loses on average. After eliminating one option it's worth at least **+0.22**, and with two options left at least **+0.67**. **Rule: attempt everything, and always guess once you've eliminated one option.**
- **Time:** 120 min for 100 Qs, about 70 sec each. Do one pass answering what you know, then a second pass with eliminations.
- **The paper mixes both syllabi.** In 2025 the split was roughly: DSA 20 · C/C++ 14 · AI 9 · SE 9 · DBMS 9 · OS 8 · Logic 8 · Networks 8 · COA 5 · Web 5 · Compilers 2 · ML 2 · Mobile 1. Questions were mostly **definitional**, with a few small numericals and C-output questions.

## How this bank is laid out

| Part | Topics | Questions |
|---|---|---|
| **A** (Paper-I syllabus) | C/C++ · DSA · Logic Design · COA · System Software & Compilers · Mobile Apps | Q1–Q170 |
| **B** (Paper-II syllabus) | OS · Software Engg · DBMS · Networks · Web (HTML/PHP) · AI · ML | Q171–Q380 |

The answer is printed **directly below each question** with a one-line reason. Every numerical, conversion and code-output answer was worked out and checked by running it. Items marked ⚠️ are ambiguous as worded; the note says which answer to pick and why.

**Self-test tip:** cover the green answer box with your thumb, answer, then reveal.

# Part A — Paper-I syllabus topics

## A1. C / C++ Programming & Basics

**1.** Which of the following is NOT one of the basic functional units of a computer?  
(a) Input unit (b) Memory unit (c) Compiler unit (d) Arithmetic Logic Unit
> **Ans: (c) Compiler unit** — The basic units are Input, Output, Memory, ALU and Control Unit; a compiler is software, not a hardware unit.

**2.** In a flowchart, a decision (e.g. `x > 0 ?`) is drawn using which symbol?  
(a) Rectangle (b) Parallelogram (c) Oval (d) Diamond
> **Ans: (d) Diamond** — Oval = start/stop, parallelogram = input/output, rectangle = process, diamond = decision.

**3.** Which property must every algorithm have?  
(a) Finiteness — it terminates after a finite number of steps (b) It must be written in C (c) It must use recursion (d) It must have at least two inputs
> **Ans: (a) Finiteness** — Knuth's properties: finiteness, definiteness, input (zero or more), output (one or more), effectiveness.

**4.** On a typical 32/64-bit GCC system, what are `sizeof(char)`, `sizeof(int)` and `sizeof(double)`?  
(a) 1, 2, 4 (b) 1, 4, 8 (c) 2, 4, 8 (d) 1, 4, 4
> **Ans: (b) 1, 4, 8** — `char` is always 1 byte by definition; `int` is 4 and `double` is 8 on mainstream compilers (int size is implementation-defined, but 4 is standard on GCC).

**5.** What is printed?
```c
int a = 7, b = 2;
printf("%d %d %.1f", a / b, a % b, (float)a / b);
```
(a) 3.5 1 3.5 (b) 3 1 3.0 (c) 3 1 3.5 (d) 4 1 3.5
> **Ans: (c) 3 1 3.5** — 7/2 is integer division → 3; 7%2 → 1; the cast makes a float division 7.0/2 = 3.5. (Compiled & run with gcc.)

**6.** What is printed?
```c
int i = 5;
int j = i++;
int k = ++i;
printf("%d %d %d", i, j, k);
```
(a) 7 5 7 (b) 7 6 7 (c) 6 5 6 (d) 7 5 6
> **Ans: (a) 7 5 7** — j = 5 then i→6 (post-increment uses old value); ++i makes i = 7 and k = 7. (Compiled & run with gcc.)

**7.** Which operator has the HIGHEST precedence in C?  
(a) `&&` (b) `=` (c) `==` (d) `*` (multiplication)
> **Ans: (d) `*`** — Order (high→low): `* / %` > `+ -` > relational > `==` > `&&` > `||` > `?:` > `=`.

**8.** What is printed?
```c
int x = 10;
printf("%d %d\n", x > 5 && x < 8, !x || x);
printf("%d", 5 & 3 | 8);
```
(a) 1 1 then 9 (b) 0 1 then 9 (c) 0 1 then 1 (d) 0 0 then 9
> **Ans: (b) 0 1 then 9** — 10<8 is false so `&&` gives 0; `!x` is 0 but `x` is non-zero so `||` gives 1; `&` binds tighter than `|`: (5&3)=1, 1|8 = 9. (Compiled & run with gcc.)

**9.** What is printed?
```c
int x = 10, y = 3;
x += y *= 2;
printf("%d %d", x, y);
```
(a) 13 6 (b) 16 3 (c) 26 6 (d) 16 6
> **Ans: (d) 16 6** — Assignment operators are right-associative: y *= 2 → y = 6, then x += 6 → 16. (Compiled & run with gcc.)

**10.** Which format specifier prints an integer in hexadecimal with capital letters?  
(a) `%X` (b) `%o` (c) `%h` (d) `%x`
> **Ans: (a) `%X`** — `%x` gives lowercase hex, `%X` uppercase, `%o` octal; `%h` alone is a length modifier, not a conversion.

**11.** What does `printf("%d %o %X", 26, 26, 26);` print?  
(a) 26 26 1A (b) 26 32 1a (c) 26 32 1A (d) 26 31 1A
> **Ans: (c) 26 32 1A** — 26 = 3×8 + 2 → octal 32; 26 = 1×16 + 10 → hex 1A (uppercase with %X). (Compiled & run with gcc.)

**12.** Why is `&` used before the variable in `scanf("%d", &n);`?  
(a) It converts n to an integer (b) scanf needs the address of n so it can store the input there (c) It is optional and only for style (d) It prints the address of n
> **Ans: (b)** — C passes arguments by value; scanf must receive a pointer (address) to write the read value into the variable.

**13.** What is printed by three successive calls `f(); f(); f();`?
```c
void f(void) { static int c = 0; c++; printf("%d ", c); }
```
(a) 1 1 1 (b) 0 1 2 (c) 1 2 3 (d) Compilation error
> **Ans: (c) 1 2 3** — A `static` local is initialised once and retains its value between calls. (Compiled & run with gcc.)

**14.** Which storage class declares a variable that is DEFINED in another source file?  
(a) extern (b) static (c) auto (d) register
> **Ans: (a) extern** — `extern` gives a declaration (no storage allocated) referring to a definition elsewhere, giving external linkage.

**15.** Which statement about the `register` storage class is correct?  
(a) The variable is guaranteed to be in a CPU register (b) It has global scope (c) It retains its value between function calls (d) Its address cannot be taken with `&`
> **Ans: (d)** — `register` is only a hint to the compiler; it is still local/automatic, and applying `&` to it is a compile error in C.

**16.** What is the default initial value of an `auto` (local, non-static) variable in C?  
(a) Garbage (indeterminate) value (b) 0 (c) NULL (d) 1
> **Ans: (a) Garbage** — Automatic locals are not initialised; `static` and global variables default to 0.

**17.** What is printed?
```c
int a[] = {10, 20, 30, 40};
int *p = a;
p += 2;
printf("%d %d", *p, *(p - 1) + 1);
```
(a) 12 11 (b) 30 21 (c) 30 31 (d) 20 21
> **Ans: (b) 30 21** — p+2 points to a[2] = 30; *(p−1) is a[1] = 20, plus 1 = 21. Pointer arithmetic scales by sizeof(int). (Compiled & run with gcc.)

**18.** If `int *p` holds address 1000 and `sizeof(int)` is 4, what address does `p + 3` hold?  
(a) 1003 (b) 1006 (c) 1012 (d) 1034
> **Ans: (c) 1012** — p + 3 = 1000 + 3 × sizeof(int) = 1000 + 12 = 1012.

**19.** What is printed for `int arr[5] = {1, 2}; printf("%d", arr[3]);`?  
(a) 2 (b) Garbage value (c) 1 (d) 0
> **Ans: (d) 0** — In a partially initialised array, the remaining elements are set to 0.

**20.** What is printed?
```c
char s[20] = "NPSC";
printf("%zu %zu", strlen(s), sizeof(s));
```
(a) 4 20 (b) 5 20 (c) 4 5 (d) 20 20
> **Ans: (a) 4 20** — strlen counts characters before '\0' (4); sizeof gives the declared array size (20 bytes). (Compiled & run with gcc.)

**21.** Which `string.h` function appends one string to the end of another?  
(a) strcpy() (b) strcat() (c) strcmp() (d) strrev()
> **Ans: (b) strcat()** — strcpy copies, strcmp compares, strcat concatenates; strrev is non-standard.

**22.** What does `strcmp("apple", "banana")` return?  
(a) 0 (b) A positive value (c) A negative value (d) The length difference
> **Ans: (c) A negative value** — strcmp returns <0 when the first string is lexicographically smaller ('a' < 'b').

**23.** On a typical GCC system with 4-byte int, what does this print?
```c
union U  { int i; char c[8]; };
struct S { int i; char c[8]; };
printf("%zu %zu", sizeof(union U), sizeof(struct S));
```
(a) 12 12 (b) 8 8 (c) 4 12 (d) 8 12
> **Ans: (d) 8 12** — A union's size is that of its largest member (8); a structure stores all members one after another (4 + 8 = 12, already aligned). (Compiled & run with gcc.)

**24.** Which statement about structures and unions is correct?  
(a) All members of a union share the same memory location (b) All members of a structure share the same memory (c) A union can hold all its members' values at the same time (d) Unions cannot contain arrays
> **Ans: (a)** — Union members overlap at the same address, so only one member holds a meaningful value at a time; structure members get separate storage.

**25.** Which function allocates memory for an array AND initialises all bytes to zero?  
(a) malloc() (b) realloc() (c) calloc() (d) free()
> **Ans: (c) calloc()** — `calloc(n, size)` allocates n × size bytes and zero-fills them; malloc leaves memory uninitialised.

**26.** Which header must be included to use `malloc()`, `calloc()`, `realloc()` and `free()`?  
(a) `<stdlib.h>` (b) `<stdio.h>` (c) `<string.h>` (d) `<conio.h>`
> **Ans: (a) `<stdlib.h>`** — The dynamic-memory functions are declared in stdlib.h.

**27.** What is a "memory leak"?  
(a) Accessing an array out of bounds (b) Dynamically allocated memory that is never freed and is no longer reachable (c) Dereferencing a NULL pointer (d) Stack overflow from deep recursion
> **Ans: (b)** — Memory obtained with malloc/new that is not released with free/delete stays allocated until the program ends.

**28.** What is printed?
```c
#define SQ(x) x * x
printf("%d", SQ(2 + 3));
```
(a) 25 (b) 13 (c) 10 (d) 11
> **Ans: (d) 11** — Macros do textual substitution: 2 + 3 * 2 + 3 = 2 + 6 + 3 = 11. Writing `((x) * (x))` would give 25. (Compiled & run with gcc.)

**29.** What is printed?
```c
int f(int n) { if (n <= 1) return 1; return n * f(n - 1); }
printf("%d", f(5));
```
(a) 120 (b) 24 (c) 15 (d) 720
> **Ans: (a) 120** — f computes the factorial recursively: 5×4×3×2×1 = 120. (Compiled & run with gcc.)

**30.** What is printed?
```c
int x = 2;
switch (x) {
  case 1: printf("A");
  case 2: printf("B");
  case 3: printf("C"); break;
  default: printf("D");
}
```
(a) B (b) BCD (c) BC (d) ABC
> **Ans: (c) BC** — Control jumps to `case 2`, prints B, falls through (no break) to case 3, prints C, then `break` exits. (Compiled & run with gcc.)

**31.** What is printed?
```c
int i, s = 0;
for (i = 1; i <= 10; i++) {
  if (i % 2 == 0) continue;
  if (i > 7) break;
  s += i;
}
printf("%d", s);
```
(a) 25 (b) 16 (c) 9 (d) 28
> **Ans: (b) 16** — Even i are skipped; odd i = 1, 3, 5, 7 are added (16); at i = 9 the loop breaks. (Compiled & run with gcc.)

**32.** Which loop always executes its body at least once?  
(a) for (b) while (c) do-while (d) None of these
> **Ans: (c) do-while** — It is an exit-controlled loop; the condition is checked after the body runs.

**33.** Which C++ access specifier makes members accessible in the class itself and in derived classes, but NOT from outside?  
(a) protected (b) public (c) private (d) friend
> **Ans: (a) protected** — private: class only; protected: class + derived classes; public: everywhere. `friend` is not an access specifier.

**34.** What is printed?
```cpp
class A { public: A() { cout << "A"; } ~A() { cout << "a"; } };
class B : public A { public: B() { cout << "B"; } ~B() { cout << "b"; } };
int main() { { B obj; } }
```
(a) BAba (b) ABab (c) ABba (d) BAab
> **Ans: (c) ABba** — Constructors run base-first (A then B); destructors run in reverse order (B's then A's). (Compiled & run with g++.)

**35.** What is printed?
```cpp
class Base { public: virtual ~Base() {}
  virtual void show() { cout << "Base "; }
  void hello() { cout << "B-hello "; } };
class Derived : public Base { public:
  void show() override { cout << "Derived "; }
  void hello() { cout << "D-hello "; } };
Base *p = new Derived(); p->show(); p->hello();
```
(a) Base B-hello (b) Derived D-hello (c) Base D-hello (d) Derived B-hello
> **Ans: (d) Derived B-hello** — `show()` is virtual → dynamic binding calls Derived's version; `hello()` is non-virtual → static binding on the pointer type (Base). (Compiled & run with g++.)

**36.** A class containing at least one pure virtual function (e.g. `virtual void draw() = 0;`) is called?  
(a) A friend class (b) An abstract class (c) A template class (d) A final class
> **Ans: (b) An abstract class** — It cannot be instantiated; derived classes must override the pure virtual function to become concrete.

**37.** Function overloading in C++ is an example of?  
(a) Run-time polymorphism (b) Inheritance (c) Compile-time (static) polymorphism (d) Encapsulation
> **Ans: (c)** — The call is resolved at compile time from the argument list; virtual functions give run-time polymorphism.

**38.** What is printed?
```cpp
void inc(int &r) { r += 5; }
void inc2(int v) { v += 5; }
int main() { int x = 1; inc(x); inc2(x); cout << x; }
```
(a) 6 (b) 1 (c) 11 (d) 16
> **Ans: (a) 6** — `inc` takes a reference and changes x to 6; `inc2` gets a copy, so x stays 6. (Compiled & run with g++.)

**39.** Which statement about a `friend` function in C++ is correct?  
(a) It is a member function of the class (b) It is called using the object and dot operator (c) It is inherited by derived classes (d) It is a non-member function that can access the class's private and protected members
> **Ans: (d)** — Friendship is granted by the class, is not a member, is not inherited and is not transitive.

**40.** What is printed?
```cpp
template <typename T> T mx(T a, T b) { return a > b ? a : b; }
int main() {
  cout << mx(3, 7) << " " << mx(2.5, 1.5);
  try { throw 5; } catch (int e) { cout << " int " << e; } catch (...) { cout << " other"; }
}
```
(a) 7 2.5 other (b) 7 2.5 int 5 (c) 3 1.5 int 5 (d) Compilation error
> **Ans: (b) 7 2.5 int 5** — The template is instantiated for int and double, returning the larger value; `throw 5` throws an int, caught by the first matching handler `catch (int)`. (Compiled & run with g++.)

## A2. Data Structures & Algorithms

**41.** What is the worst-case time complexity of Quick Sort?  
(a) O(n log n) (b) O(n) (c) O(log n) (d) O(n²)
> **Ans: (d) O(n²)** — The worst case happens when the pivot is always the smallest or largest element (e.g. an already-sorted array with first-element pivot); average is O(n log n).

**42.** Which sorting algorithm has O(n log n) time complexity in the best, average AND worst cases?  
(a) Merge Sort (b) Quick Sort (c) Insertion Sort (d) Bubble Sort
> **Ans: (a) Merge Sort** — It always splits in half and merges in O(n) per level → Θ(n log n). Heap sort is also O(n log n) in all cases.

**43.** What is the best-case time complexity of Insertion Sort, and when does it happen?  
(a) O(n log n), random input (b) O(n), already-sorted input (c) O(1), single element (d) O(n²), reverse-sorted input
> **Ans: (b) O(n), already sorted** — Each new element needs only one comparison; reverse-sorted input is the O(n²) worst case.

**44.** What is the maximum number of comparisons binary search needs on a sorted array of 1024 elements?  
(a) 10 (b) 11 (c) 512 (d) 1024
> **Ans: (b) 11** — Worst case = ⌊log₂ n⌋ + 1 = ⌊log₂ 1024⌋ + 1 = 10 + 1 = 11 comparisons.

**45.** What is the average-case time complexity of searching in a hash table with a good hash function and a low load factor?  
(a) O(1) (b) O(log n) (c) O(n) (d) O(n log n)
> **Ans: (a) O(1)** — Expected cost is O(1 + α); it degrades to O(n) in the worst case when all keys collide.

**46.** Which data structure is used for function calls and recursion?  
(a) Queue (b) Heap (c) Stack (d) Graph
> **Ans: (c) Stack** — Each call pushes an activation record (return address, locals); it is popped on return (LIFO).

**47.** Which application uses a QUEUE?  
(a) Balancing parentheses (b) Undo/redo in an editor (c) Converting infix to postfix (d) CPU scheduling of processes in order of arrival (FCFS)
> **Ans: (d)** — FIFO order fits arrival-order scheduling, BFS, printer spooling and buffers; the other three use stacks.

**48.** In a circular queue of size N implemented with an array (one slot left empty), when is the queue FULL?  
(a) front == rear (b) (rear + 1) % N == front (c) rear == N − 1 (d) front == 0
> **Ans: (b)** — Leaving one slot empty tells full apart from empty: empty when front == rear, full when (rear+1) % N == front.

**49.** A double-ended queue (deque) allows?  
(a) Insertion and deletion at both ends (b) Insertion at both ends, deletion only at the front (c) Access by priority only (d) Insertion only in the middle
> **Ans: (a)** — Input-restricted and output-restricted deques are the limited variants.

**50.** Which data structure gives the most efficient priority queue (O(log n) insert and delete-max/min)?  
(a) Sorted array (b) Unsorted linked list (c) Binary heap (d) Stack
> **Ans: (c) Binary heap** — Insert and extract are both O(log n); a sorted array needs O(n) insert, an unsorted list needs O(n) extract.

**51.** What is the postfix form of the infix expression `A + B * C - D / E`?  
(a) A B + C * D E / - (b) A B C * + D E / - (c) A B C * D E / - + (d) A B C + * D E / -
> **Ans: (b) A B C * + D E / -** — `*` first: B C *; then A + that → A B C * +; D E /; finally `-` (left to right) → A B C * + D E / -.

**52.** What is the postfix form of `(A + B) * (C - D)`?  
(a) A B C D + - * (b) * + A B - C D (c) A B + C - D * (d) A B + C D - *
> **Ans: (d) A B + C D - *** — Each bracket becomes A B + and C D -, then the `*` comes last. Option (b) is the prefix form.

**53.** Evaluate the postfix expression `5 3 + 8 2 - *`.  
(a) 48 (b) 40 (c) 22 (d) 64
> **Ans: (a) 48** — push 5, 3; `+` → 8; push 8, 2; `-` → 6; `*` → 8 × 6 = 48.

**54.** Evaluate the postfix expression `2 3 1 * + 9 -`.  
(a) 4 (b) −4 (c) 14 (d) −10
> **Ans: (b) −4** — 3 1 * = 3; 2 + 3 = 5; 5 − 9 = −4.

**55.** What is the time complexity of inserting a node at the END of a singly linked list that keeps only a head pointer?  
(a) O(1) (b) O(log n) (c) O(n) (d) O(n²)
> **Ans: (c) O(n)** — You must walk the list to reach the last node; with a tail pointer it would be O(1).

**56.** What is the maximum number of nodes in a binary tree of height h, where height is counted as the number of levels (a single root has h = 1)?  
(a) 2^h (b) 2h (c) 2^(h−1) (d) 2^h − 1
> **Ans: (d) 2^h − 1** — Level i (root = level 0) holds at most 2^i nodes; 1 + 2 + … + 2^(h−1) = 2^h − 1. (If height counts edges from root = 0, it is 2^(h+1) − 1.)

**57.** A binary tree has 10 nodes of degree 2. How many leaf nodes does it have?  
(a) 9 (b) 10 (c) 11 (d) 20
> **Ans: (c) 11** — In any binary tree n₀ = n₂ + 1 → 10 + 1 = 11.

**58.** Consider the binary tree: root A; A's left = B, right = C; B's left = D, right = E; C's right = F. What is its INORDER traversal?  
(a) D B E A C F (b) A B D E C F (c) D E B F C A (d) A B C D E F
> **Ans: (a) D B E A C F** — Inorder = Left, Root, Right: (D B E) A (C F). The others are preorder (b), postorder (c) and level-order (d).

**59.** For the same tree (A; B, C; D, E under B; F as C's right child), what is the POSTORDER traversal?  
(a) D B E F C A (b) D E B F C A (c) F C E D B A (d) D E B C F A
> **Ans: (b) D E B F C A** — Left subtree (D E B), right subtree (F C), then root A.

**60.** Keys 15, 10, 20, 8, 12, 25 are inserted in this order into an empty BST. What is the preorder traversal?  
(a) 8 10 12 15 20 25 (b) 15 10 20 8 12 25 (c) 8 12 10 25 20 15 (d) 15 10 8 12 20 25
> **Ans: (d) 15 10 8 12 20 25** — Root 15; 10 left, 20 right; 8 and 12 under 10; 25 right of 20. Preorder = root, left subtree, right subtree. (a) is the inorder (always sorted).

**61.** When a BST node with TWO children is deleted, it is replaced by?  
(a) Its left child always (b) Its inorder successor (smallest key in its right subtree) or inorder predecessor (c) The root (d) Any leaf node
> **Ans: (b)** — Copy the successor's (or predecessor's) key in, then delete that node, which has at most one child.

**62.** In an AVL tree, a node becomes unbalanced after an insertion into the RIGHT subtree of its LEFT child. Which rotation fixes it?  
(a) Single right rotation (LL case) (b) Single left rotation (RR case) (c) Left-Right (double) rotation (d) No rotation is needed
> **Ans: (c) LR double rotation** — LR case: first rotate left at the left child, then rotate right at the unbalanced node.

**63.** What is the allowed balance factor (height(left) − height(right)) of every node in an AVL tree?  
(a) 0 only (b) −2 to +2 (c) Any value (d) −1, 0 or +1
> **Ans: (d)** — |BF| ≤ 1 keeps the height O(log n), so search, insert and delete are O(log n).

**64.** The array [4, 10, 3, 5, 1] is converted into a MAX-heap using bottom-up heapify. What is the resulting array?  
(a) [10, 5, 3, 4, 1] (b) [10, 4, 3, 5, 1] (c) [10, 5, 4, 3, 1] (d) [1, 3, 4, 5, 10]
> **Ans: (a) [10, 5, 3, 4, 1]** — heapify(i=1): 10 > 5, 1, no change; heapify(i=0): swap 4↔10 → [10,4,3,5,1]; then sift 4 down at i=1: swap with 5 → [10,5,3,4,1]. (Checked with python3.)

**65.** What is the time complexity of building a binary heap from n elements using bottom-up heapify?  
(a) O(n log n) (b) O(n) (c) O(log n) (d) O(n²)
> **Ans: (b) O(n)** — Most nodes are near the bottom and sift down only a little; Σ h·n/2^(h+1) = O(n). Inserting n keys one by one is O(n log n).

**66.** B-trees are mainly used in?  
(a) Expression evaluation (b) Database and file-system indexing on disk (c) Recursion (d) Graph colouring
> **Ans: (b)** — B-trees have a high fan-out and stay balanced with all leaves at the same level, which keeps the number of disk accesses low; B+ trees are used for DBMS indexes.

**67.** Which data structure does Breadth-First Search (BFS) use?  
(a) Queue (b) Stack (c) Priority queue (d) Hash table
> **Ans: (a) Queue** — BFS explores level by level (FIFO); DFS uses a stack, either explicitly or through recursion.

**68.** What is the space required for an adjacency MATRIX representation of a graph with V vertices and E edges?  
(a) O(V + E) (b) O(E) (c) O(V²) (d) O(E log V)
> **Ans: (c) O(V²)** — It is a V×V array no matter how many edges there are; an adjacency list needs O(V + E), which is better for sparse graphs.

**69.** How many edges does a complete undirected graph with 6 vertices have?  
(a) 30 (b) 12 (c) 36 (d) 15
> **Ans: (d) 15** — n(n−1)/2 = 6 × 5 / 2 = 15.

**70.** Undirected weighted graph with edges A–B 4, A–C 1, B–C 2, B–D 5, C–D 8, C–E 10, D–E 3. What is the total weight of its Minimum Spanning Tree?  
(a) 11 (b) 10 (c) 14 (d) 15
> **Ans: (a) 11** — Kruskal in increasing order: A–C 1 ✓, B–C 2 ✓, D–E 3 ✓, A–B 4 ✗ (cycle), B–D 5 ✓ → 1+2+3+5 = 11, with 4 edges = V − 1. (Checked with python3.)

**71.** In the same graph (A–B 4, A–C 1, B–C 2, B–D 5, C–D 8, C–E 10, D–E 3), what is the shortest distance from A to D found by Dijkstra's algorithm?  
(a) 9 (b) 8 (c) 13 (d) 7
> **Ans: (b) 8** — A→C 1, C→B 1+2 = 3 (better than the direct 4), B→D 3+5 = 8 (vs A→C→D = 9). (Checked with python3.)

**72.** Which statement about Prim's and Kruskal's algorithms is correct?  
(a) Both are dynamic programming algorithms (b) Kruskal grows one tree from a start vertex (c) Both are greedy; Kruskal sorts edges and uses union-find, while Prim grows a single tree from a start vertex (d) Prim works only on directed graphs
> **Ans: (c)** — Kruskal is O(E log E); Prim with a binary heap is O(E log V).

**73.** Dijkstra's algorithm may give WRONG results when the graph has?  
(a) Cycles (b) Negative edge weights (c) More than 100 vertices (d) Undirected edges
> **Ans: (b) Negative edge weights** — Once a vertex is finalised, Dijkstra never revisits it. Bellman-Ford handles negative weights and detects negative cycles.

**74.** Topological sorting is possible only for which kind of graph?  
(a) Directed Acyclic Graph (DAG) (b) Undirected connected graph (c) Complete graph (d) Any directed graph
> **Ans: (a) DAG** — A cycle would make a linear "u before v" ordering impossible. It can be computed with DFS finish times or Kahn's in-degree algorithm in O(V + E).

**75.** A hash table of size 10 uses h(k) = k mod 10 with LINEAR probing. Keys 12, 22, 32, 15, 25 are inserted in order. At which index is 25 stored?  
(a) 5 (b) 7 (c) 2 (d) 6
> **Ans: (d) 6** — 12→2; 22→2 is taken, so 3; 32→2,3 taken, so 4; 15→5; 25→5 is taken, so 6. (Checked with python3.)

**76.** A hash table has 20 slots and holds 15 keys. What is its load factor α?  
(a) 1.33 (b) 0.75 (c) 0.25 (d) 15
> **Ans: (b) 0.75** — α = n / m = 15 / 20 = 0.75.

**77.** Separate chaining resolves collisions by?  
(a) Probing the next free slot (b) Using a second hash function (c) Doubling the table immediately (d) Keeping a linked list of all keys that hash to the same slot
> **Ans: (d)** — Open addressing (linear/quadratic probing, double hashing) stores all keys in the table itself instead.

**78.** For the 0/1 knapsack and the fractional knapsack problems, which statement is correct?  
(a) Greedy by value/weight ratio is optimal for both (b) DP is needed for fractional knapsack (c) Greedy by ratio is optimal for fractional knapsack; 0/1 knapsack needs DP (or branch-and-bound) (d) Both are NP-hard
> **Ans: (c)** — Fractional knapsack: sort by ratio, O(n log n). 0/1 knapsack: DP in O(nW), which is pseudo-polynomial.

**79.** Knapsack capacity W = 50; items (value, weight) = (60, 10), (100, 20), (120, 30). What is the maximum value for the FRACTIONAL knapsack?  
(a) 220 (b) 180 (c) 280 (d) 240
> **Ans: (d) 240** — Ratios 6, 5, 4. Take item1 (60, w10) and item2 (100, w20): w = 30, 20 left → 20/30 of item3 = 80. Total 60+100+80 = 240. (The 0/1 optimum is 220.)

**80.** What is the length of the Longest Common Subsequence of "ABCBDAB" and "BDCABA"?  
(a) 3 (b) 4 (c) 5 (d) 6
> **Ans: (b) 4** — For example "BCBA" or "BDAB". The DP table L[i][j] = L[i−1][j−1]+1 on a match, else max(L[i−1][j], L[i][j−1]). (Checked with python3.)

**81.** Matrices A(10×20), B(20×30), C(30×40). What is the MINIMUM number of scalar multiplications to compute ABC?  
(a) 18000 (b) 32000 (c) 24000 (d) 6000
> **Ans: (a) 18000** — (AB)C = 10·20·30 + 10·30·40 = 6000 + 12000 = 18000; A(BC) = 20·30·40 + 10·20·40 = 24000 + 8000 = 32000.

**82.** Which algorithm finds shortest paths between ALL pairs of vertices in O(V³) time using dynamic programming?  
(a) Dijkstra (b) Prim (c) Floyd-Warshall (d) Kruskal
> **Ans: (c) Floyd-Warshall** — Recurrence d[i][j] = min(d[i][j], d[i][k] + d[k][j]) for each intermediate vertex k.

**83.** Which algorithm design technique do Merge Sort, Quick Sort and Binary Search use?  
(a) Greedy (b) Dynamic programming (c) Backtracking (d) Divide and conquer
> **Ans: (d) Divide and conquer** — Divide into sub-problems, solve them recursively, then combine the results.

**84.** What does the Master theorem give for T(n) = 2T(n/2) + n?  
(a) Θ(n) (b) Θ(n log n) (c) Θ(n²) (d) Θ(log n)
> **Ans: (b) Θ(n log n)** — a = 2, b = 2, n^(log_b a) = n¹ = f(n) → Case 2 → Θ(n log n). This is the merge sort recurrence.

**85.** What does the Master theorem give for T(n) = 8T(n/2) + n²?  
(a) Θ(n² log n) (b) Θ(n²) (c) Θ(n³) (d) Θ(n log n)
> **Ans: (c) Θ(n³)** — n^(log₂ 8) = n³, which grows polynomially faster than f(n) = n² → Case 1 → Θ(n³).

**86.** f(n) = Ω(g(n)) means that, for some constants c > 0 and n₀, for all n ≥ n₀?  
(a) f(n) ≤ c·g(n) (b) f(n) = g(n) (c) c₁g(n) ≤ f(n) ≤ c₂g(n) (d) f(n) ≥ c·g(n)
> **Ans: (d)** — Ω is an asymptotic lower bound, O is an upper bound (a), and Θ is a tight bound (c).

**87.** A decision problem is NP-complete if?  
(a) It is solvable in polynomial time (b) It is in NP AND every problem in NP reduces to it in polynomial time (c) It is undecidable (d) It is NP-hard but not in NP
> **Ans: (b)** — NP-hard only requires that every NP problem reduces to it (it may not be in NP, e.g. the halting problem); NP-complete = NP ∩ NP-hard.

**88.** Which of these problems was the FIRST to be proved NP-complete (Cook–Levin theorem)?  
(a) Boolean Satisfiability (SAT) (b) Sorting (c) Minimum spanning tree (d) Shortest path
> **Ans: (a) SAT** — Sorting, MST and shortest path are all in P. Vertex cover, Hamiltonian cycle, clique and decision-TSP are other NP-complete problems.

**89.** Which of the following problems is in class P (solvable in polynomial time)?  
(a) Hamiltonian cycle (b) Vertex cover (c) Finding a Minimum Spanning Tree (d) 0/1 knapsack (decision version)
> **Ans: (c) MST** — Kruskal and Prim run in polynomial time; the other three are NP-complete.

**90.** The optimisation version of the Travelling Salesman Problem (find the minimum-cost tour) is classified as?  
(a) In P (b) NP-hard (c) Undecidable (d) Solvable greedily in O(n log n)
> **Ans: (b) NP-hard** — Its decision version ("is there a tour with cost ≤ k?") is NP-complete; the optimisation version is NP-hard.

## A3. Logic Design & Number Systems

**91.** What is the decimal number 156 in binary, octal and hexadecimal?  
(a) 10011010, 232, 9A (b) 10011100, 234, 9C (c) 11001100, 314, CC (d) 10011100, 324, 9C
> **Ans: (b) 10011100₂ = 234₈ = 9C₁₆** — 156 = 128+16+8+4. Octal grouping 10|011|100 → 2 3 4; hex 1001|1100 → 9 C. (Checked with python3.)

**92.** What is (2F)₁₆ in decimal?  
(a) 32 (b) 45 (c) 47 (d) 215
> **Ans: (c) 47** — 2 × 16 + 15 = 47.

**93.** What is (101.101)₂ in decimal?  
(a) 5.625 (b) 5.5 (c) 5.505 (d) 6.625
> **Ans: (a) 5.625** — 101 = 5; .101 = 1/2 + 0 + 1/8 = 0.625. (Checked with python3.)

**94.** What is the 2's complement of the 8-bit binary number 0101 1000?  
(a) 1010 0111 (b) 1010 1001 (c) 0101 1000 (d) 1010 1000
> **Ans: (d) 1010 1000** — 1's complement = 1010 0111; adding 1 gives 1010 1000. (Checked with python3.)

**95.** How is −20 represented in 8-bit 2's complement?  
(a) 1001 0100 (b) 1110 1011 (c) 1110 1100 (d) 0001 0100
> **Ans: (c) 1110 1100** — +20 = 0001 0100; invert → 1110 1011; +1 → 1110 1100. (a) is sign-magnitude and (b) is 1's complement. (Checked with python3.)

**96.** What is the range of an 8-bit signed integer in 2's complement representation?  
(a) −127 to +127 (b) −128 to +127 (c) 0 to 255 (d) −128 to +128
> **Ans: (b)** — −2^(n−1) to 2^(n−1) − 1. Sign-magnitude and 1's complement give −127 to +127 because they have two zeros.

**97.** What is the BCD (8421) code of the decimal number 59?  
(a) 0011 1011 (b) 0101 1001 (c) 1000 1100 (d) 0101 1010
> **Ans: (b) 0101 1001** — Each decimal digit is coded in 4 bits: 5 = 0101, 9 = 1001. (a) is plain binary (59 = 111011).

**98.** What is the Excess-3 code of the decimal number 59?  
(a) 0101 1001 (b) 1000 1001 (c) 0101 1100 (d) 1000 1100
> **Ans: (d) 1000 1100** — Add 3 to each digit: 5+3 = 8 → 1000; 9+3 = 12 → 1100. (Checked with python3.)

**99.** What is the Gray code of the binary number 1011?  
(a) 1110 (b) 1101 (c) 1011 (d) 0111
> **Ans: (a) 1110** — G = B ⊕ (B >> 1): MSB 1; 1⊕0 = 1; 0⊕1 = 1; 1⊕1 = 0 → 1110. (Checked with python3.)

**100.** What is the binary equivalent of the Gray code 1101?  
(a) 1011 (b) 1001 (c) 1101 (d) 1110
> **Ans: (b) 1001** — b₃ = g₃ = 1; b₂ = 1⊕1 = 0; b₁ = 0⊕0 = 0; b₀ = 0⊕1 = 1 → 1001. (Checked with python3.)

**101.** Simplify the Boolean expression A + A'B.  
(a) A (b) B (c) A + B (d) AB
> **Ans: (c) A + B** — Absorption/redundancy law: A + A'B = (A + A')(A + B) = A + B. (Checked with a python3 truth table.)

**102.** By De Morgan's theorem, (A · B)' is equal to?  
(a) A' + B' (b) A' · B' (c) A + B (d) (A + B)'
> **Ans: (a) A' + B'** — The complement of a product is the sum of the complements; (A + B)' = A'·B'.

**103.** Using the consensus theorem, AB + A'C + BC simplifies to?  
(a) AB + BC (b) A'C + BC (c) AB + A'C (d) A + C
> **Ans: (c) AB + A'C** — BC is the consensus term of AB and A'C and is redundant. (Checked with a python3 truth table.)

**104.** Minimise F(A, B, C) = Σm(0, 2, 4, 6) using a K-map.  
(a) A' (b) B' (c) AC' (d) C'
> **Ans: (d) C'** — All four minterms have C = 0 (000, 010, 100, 110), so one quad gives C'. (Checked with a python3 truth table.)

**105.** Minimise F(A, B, C, D) = Σm(0, 2, 8, 10) using a K-map.  
(a) B'D' (b) A'B' (c) B'D (d) A'D'
> **Ans: (a) B'D'** — The four corner cells form one quad where B = 0 and D = 0 (0000, 0010, 1000, 1010). (Checked with a python3 truth table.)

**106.** Minimise F(A, B, C) = Σm(1, 2, 3, 5, 7).  
(a) C + AB (b) A'B + C (c) A' + C (d) B + C
> **Ans: (b) C + A'B** — Quad m(1,3,5,7) = C; pair m(2,3) = A'B. (Checked with a python3 truth table.)

**107.** F(A, B, C, D) = Σm(1, 3, 5, 7, 8, 10, 12, 14) simplifies to?  
(a) A ⊙ D (XNOR) (b) A'D (c) AD' (d) A ⊕ D
> **Ans: (d) A ⊕ D** — Quad m(1,3,5,7) = A'D; quad m(8,10,12,14) = AD'; A'D + AD' = A ⊕ D. (Checked with a python3 truth table.)

**108.** Why are NAND and NOR called universal gates?  
(a) They are the fastest gates (b) They are available in every IC (c) Any Boolean function can be built using only NAND gates (or only NOR gates) (d) They have the most inputs
> **Ans: (c)** — NOT, AND and OR can each be built from NAND alone, or from NOR alone.

**109.** What is the minimum number of 2-input NAND gates needed to build an XOR gate?  
(a) 4 (b) 3 (c) 5 (d) 2
> **Ans: (a) 4** — Standard circuit: N1 = (AB)', then (A·N1)' and (B·N1)', then a final NAND. (For comparison: OR needs 3 NANDs, AND needs 2.)

**110.** What are the sum and carry outputs of a FULL adder?  
(a) S = A ⊕ B, C = AB (b) S = A ⊕ B ⊕ Cin, Cout = AB + Cin(A ⊕ B) (c) S = AB + Cin, C = A ⊕ B (d) S = A + B + Cin, C = ABCin
> **Ans: (b)** — (a) is the half adder. A full adder can be built from two half adders and an OR gate.

**111.** For a HALF subtractor computing A − B, what are the difference D and borrow Bo?  
(a) D = A ⊕ B, Bo = AB' (b) D = A ⊙ B, Bo = A'B (c) D = A + B, Bo = AB (d) D = A ⊕ B, Bo = A'B
> **Ans: (d)** — A borrow happens only when A = 0 and B = 1 → Bo = A'B.

**112.** How many select lines does a 16-to-1 multiplexer need?  
(a) 2 (b) 4 (c) 8 (d) 16
> **Ans: (b) 4** — 2^s = 16 → s = 4.

**113.** Which circuit has n inputs and 2ⁿ outputs, with exactly one output active for each input combination?  
(a) Decoder (b) Encoder (c) Multiplexer (d) Comparator
> **Ans: (a) Decoder** — For example, a 3-to-8 decoder. An encoder does the reverse (2ⁿ → n), and a DEMUX sends one input to one of 2ⁿ outputs.

**114.** What is the characteristic equation of a JK flip-flop?  
(a) Q⁺ = D (b) Q⁺ = T ⊕ Q (c) Q⁺ = JQ' + K'Q (d) Q⁺ = S + R'Q
> **Ans: (c)** — (a) is the D flip-flop, (b) is T, and (d) is SR (with SR = 0). With J = K = 1, the JK flip-flop toggles.

**115.** The race-around condition in a level-triggered JK flip-flop occurs when?  
(a) J = 0, K = 0 (b) J = 1, K = 0 (c) S = R = 1 (d) J = K = 1 and the clock pulse width is longer than the propagation delay
> **Ans: (d)** — The output toggles many times within one pulse. Fix it with a master-slave JK flip-flop or edge triggering.

**116.** Which input combination is INVALID (forbidden) for an SR latch built from NOR gates?  
(a) S = 0, R = 0 (b) S = 1, R = 0 (c) S = 1, R = 1 (d) S = 0, R = 1
> **Ans: (c) S = R = 1** — Both outputs are forced to 0 (Q = Q'), and the next state is unpredictable when the inputs return to 0. The JK flip-flop removes this.

**117.** How many distinct states does a 4-bit Johnson (twisted-ring) counter have?  
(a) 8 (b) 4 (c) 16 (d) 15
> **Ans: (a) 8** — A Johnson counter has 2n states (n = 4 → 8); a ring counter has n states; a binary counter has 2ⁿ.

**118.** What is the minimum number of flip-flops needed for a MOD-10 (decade) counter?  
(a) 10 (b) 3 (c) 4 (d) 5
> **Ans: (c) 4** — The smallest n with 2ⁿ ≥ 10 is 4 (2³ = 8 is too few).

**119.** A 4-bit ripple (asynchronous) counter uses flip-flops with a 10 ns propagation delay each. What is the maximum clock frequency?  
(a) 100 MHz (b) 40 MHz (c) 10 MHz (d) 25 MHz
> **Ans: (d) 25 MHz** — The total settling time is 4 × 10 = 40 ns, so f_max = 1/40 ns = 25 MHz. Synchronous counters avoid this delay build-up.

**120.** A shift register that takes data in one bit at a time and makes all bits available at once is?  
(a) SISO (b) PIPO (c) SIPO (d) PISO
> **Ans: (c) SIPO (Serial-In Parallel-Out)** — It is used for serial-to-parallel conversion, e.g. in UART receivers; PISO does the reverse.

## A4. Computer Organization & Architecture

**121.** What is the main difference between the von Neumann and Harvard architectures?  
(a) Harvard has no ALU (b) von Neumann uses separate memories for code and data (c) Harvard uses separate memories and buses for instructions and data; von Neumann shares one memory and bus (d) von Neumann is used only in DSPs
> **Ans: (c)** — The shared bus causes the von Neumann bottleneck. Harvard architecture is common in microcontrollers and DSPs.

**122.** Which register holds the instruction currently being decoded and executed?  
(a) Program Counter (PC) (b) Instruction Register (IR) (c) Memory Address Register (MAR) (d) Stack Pointer (SP)
> **Ans: (b) IR** — The PC holds the address of the NEXT instruction; the MAR holds the address being accessed; the MDR holds the data read or written.

**123.** In the FETCH phase of the instruction cycle, which is the correct micro-operation sequence?  
(a) MAR ← PC; MDR ← M[MAR], PC ← PC + 1; IR ← MDR (b) IR ← PC; MAR ← IR (c) PC ← MDR; IR ← MAR (d) MDR ← PC; IR ← M[MDR]
> **Ans: (a)** — The fetch is followed by decode, operand fetch, execute and interrupt check.

**124.** In which addressing mode is the operand value itself part of the instruction (e.g. `MOV R1, #5`)?  
(a) Direct (b) Indirect (c) Register (d) Immediate
> **Ans: (d) Immediate** — No memory access is needed for the operand. In direct mode the instruction holds the operand's address; in indirect mode it holds the address of that address.

**125.** In which addressing mode is the effective address EA = PC + offset? It is commonly used for branches.  
(a) Relative (b) Indexed (c) Base register (d) Register indirect
> **Ans: (a) PC-relative** — It allows position-independent code. Indexed mode gives EA = index register + address; base mode gives EA = base register + displacement.

**126.** Which is a characteristic of RISC compared to CISC?  
(a) Many complex, variable-length instructions (b) Microprogrammed control and many addressing modes (c) Memory-to-memory arithmetic instructions (d) Fixed-length instructions, load/store architecture, many registers, hardwired control
> **Ans: (d)** — RISC aims for about one instruction per cycle with easy pipelining; options (a) to (c) describe CISC (e.g. x86).

**127.** Compared with a microprogrammed control unit, a hardwired control unit is?  
(a) Faster but harder to modify (b) Slower but easier to modify (c) Stored in control memory (d) Used mainly in CISC processors
> **Ans: (a)** — Hardwired control generates signals from fixed logic (used in RISC). Microprogrammed control reads control words from control memory, which is flexible but slower (used in CISC).

**128.** A 5-stage pipeline runs 100 instructions (one stage per clock, no stalls). What is its speedup over a non-pipelined processor with the same total delay?  
(a) 5.00 (b) 4.81 (c) 4.00 (d) 1.04
> **Ans: (b) ≈ 4.81** — S = nk / (k + n − 1) = 100 × 5 / (5 + 99) = 500 / 104 ≈ 4.81. As n → ∞, S → k = 5.

**129.** A pipeline hazard where an instruction needs the result of an earlier instruction that has not finished yet is called?  
(a) Structural hazard (b) Control hazard (c) Data hazard (RAW) (d) Branch hazard
> **Ans: (c) Data hazard** — It is fixed by operand forwarding/bypassing or by stalls. Structural hazard = resource conflict; control hazard = branches.

**130.** A cache has a hit time of 2 ns, a miss rate of 5% and a miss penalty of 100 ns. What is the Average Memory Access Time (AMAT)?  
(a) 5 ns (b) 102 ns (c) 7 ns (d) 97 ns
> **Ans: (c) 7 ns** — AMAT = hit time + miss rate × miss penalty = 2 + 0.05 × 100 = 7 ns.

**131.** A direct-mapped cache of 64 KB with 16-byte blocks uses 32-bit byte addresses. How many bits are in the tag, index and offset fields?  
(a) 16, 12, 4 (b) 20, 8, 4 (c) 18, 10, 4 (d) 12, 16, 4
> **Ans: (a) Tag 16, Index 12, Offset 4** — offset = log₂16 = 4; lines = 64K/16 = 4096 → index = 12; tag = 32 − 12 − 4 = 16.

**132.** Which cache mapping lets a memory block be placed in ANY cache line?  
(a) Direct mapping (b) Set-associative mapping (c) Paging (d) Fully associative mapping
> **Ans: (d) Fully associative** — It has no conflict misses but needs a comparator for every line. Direct mapping allows exactly one line; set-associative allows any line within one set.

**133.** A program accesses array elements one after another in a loop. Which property of memory references does this mainly use?  
(a) Spatial locality (b) Temporal locality (c) Thrashing (d) Write-back
> **Ans: (a) Spatial locality** — Nearby addresses are used soon, so fetching whole blocks helps. Temporal locality means the same address is reused soon (e.g. loop variables).

**134.** Which is the correct memory hierarchy from FASTEST to SLOWEST?  
(a) Cache → Registers → RAM → Disk (b) Registers → Cache → Main memory → Secondary storage (c) Registers → RAM → Cache → Disk (d) Cache → RAM → Registers → Disk
> **Ans: (b)** — Going down the hierarchy, speed and cost per bit decrease and capacity increases.

**135.** Which RAM type stores each bit in a capacitor and must be refreshed periodically?  
(a) SRAM (b) EEPROM (c) DRAM (d) Flash ROM
> **Ans: (c) DRAM** — It uses 1 transistor + 1 capacitor per bit, which is dense and cheap (main memory). SRAM uses flip-flops (6 transistors), which is fast (cache) and needs no refresh.

**136.** Which ROM type can be erased electrically, byte by byte, without removing it from the circuit?  
(a) PROM (b) EPROM (c) Mask ROM (d) EEPROM
> **Ans: (d) EEPROM** — EPROM is erased with UV light; PROM can be programmed only once; mask ROM is fixed at manufacture.

**137.** How many 1K × 4 RAM chips are needed to build a 32K × 8 memory?  
(a) 64 (b) 32 (c) 16 (d) 128
> **Ans: (a) 64** — (32K × 8) / (1K × 4) = 32 × 2 = 64 chips (32 rows of 2 chips side by side).

**138.** What is the purpose of a Translation Lookaside Buffer (TLB)?  
(a) To buffer I/O data (b) To store the whole page table on disk (c) To cache recent virtual-to-physical page translations and speed up address translation (d) To replace main memory
> **Ans: (c)** — A TLB hit avoids the extra memory access to the page table.

**139.** Which I/O technique transfers blocks of data between an I/O device and memory WITHOUT the CPU handling every word?  
(a) Programmed I/O (b) Interrupt-driven I/O (c) Polling (d) Direct Memory Access (DMA)
> **Ans: (d) DMA** — The DMA controller takes the bus (cycle stealing or burst mode) and interrupts the CPU only when the transfer is complete.

**140.** In isolated I/O (I/O-mapped I/O), as opposed to memory-mapped I/O?  
(a) Separate address spaces and special instructions (e.g. IN/OUT) are used for I/O (b) I/O devices share the memory address space (c) No control lines are needed (d) Every memory instruction can access I/O
> **Ans: (a)** — In memory-mapped I/O, device registers are memory addresses accessed with normal load/store instructions.

**141.** A system bus is made up of which three groups of lines?  
(a) Serial, parallel and USB (b) Address, data and control buses (c) Input, output and storage (d) Cache, RAM and ROM
> **Ans: (b)** — The address bus is unidirectional (CPU→memory); the data bus is bidirectional; the control bus carries signals such as read/write and interrupt.

**142.** With an address bus of 16 lines, how many memory locations can be addressed?  
(a) 16 (b) 256 (c) 65,536 (d) 1,048,576
> **Ans: (c) 65,536** — 2¹⁶ = 64K locations. 20 lines would give 1M.

**143.** GPUs and vector processors that apply one instruction to many data elements at once fall under which class of Flynn's taxonomy?  
(a) SISD (b) MISD (c) SIMD (d) MIMD
> **Ans: (c) SIMD** — SISD = classic uniprocessor; MIMD = multicores/clusters; MISD is rare (fault-tolerant systems).

**144.** In the stack-based PUSH operation (stack grows downward), which register is updated?  
(a) Stack Pointer (SP) (b) Program Counter (c) Instruction Register (d) Accumulator
> **Ans: (a) SP** — SP ← SP − 1; M[SP] ← data. The SP always points to the top of the stack.

**145.** An interrupt in which the device supplies the address of its service routine directly to the CPU is called?  
(a) Polled interrupt (b) Software interrupt (c) Maskable interrupt (d) Vectored interrupt
> **Ans: (d) Vectored interrupt** — It avoids polling to find out which device interrupted. A non-maskable interrupt (NMI) cannot be disabled.

## A5. System Software & Compilers

**146.** Why does a TWO-pass assembler need two passes?  
(a) To solve forward references: pass 1 builds the symbol table (labels → addresses); pass 2 generates the object code (b) To optimise the code twice (c) To link libraries (d) To load the program into memory
> **Ans: (a)** — A one-pass assembler must use back-patching to resolve forward references.

**147.** What is the difference between a macro and a subroutine (function)?  
(a) A macro call transfers control at run time (b) A macro is expanded in-line at every call (faster, larger code); a subroutine's code exists once and is called with call/return overhead (c) Subroutines are expanded by the preprocessor (d) There is no difference
> **Ans: (b)** — Macro expansion happens at assembly or preprocessing time.

**148.** Which loader brings the operating system into memory when the computer is switched on?  
(a) Absolute loader (b) Relocating loader (c) Bootstrap loader (d) Linking loader
> **Ans: (c) Bootstrap loader** — It is a small program in ROM/firmware that loads the OS.

**149.** How does dynamic linking differ from static linking?  
(a) Static linking resolves library calls at run time (b) Dynamic linking copies all library code into the executable (c) Dynamic linking makes executables larger (d) Dynamic linking resolves shared-library references at load or run time, so executables are smaller and libraries are shared (.so/.dll)
> **Ans: (d)** — Static linking copies the library code into the executable at link time.

**150.** What is the correct order of compiler phases?  
(a) Syntax → Lexical → Semantic → Code generation (b) Lexical → Semantic → Syntax → Optimisation (c) Lexical → Intermediate code → Syntax → Semantic (d) Lexical → Syntax → Semantic → Intermediate code → Optimisation → Code generation
> **Ans: (d)** — The symbol table and the error handler are used by all phases.

**151.** How many tokens are in the C statement `int a = b + 10;`?  
(a) 7 (b) 5 (c) 6 (d) 8
> **Ans: (a) 7** — `int`, `a`, `=`, `b`, `+`, `10`, `;`. Whitespace is not a token.

**152.** In lexical analysis, the actual character sequence in the source (e.g. `count`) that matches a token pattern is called?  
(a) Token (b) Lexeme (c) Grammar (d) Parse tree
> **Ans: (b) Lexeme** — The token is the category (identifier); the pattern (a regex) describes the lexemes. Tokens are recognised by DFAs, and LEX generates the scanner.

**153.** A grammar is called ambiguous if?  
(a) It has left recursion (b) It has ε-productions (c) Some string has two or more distinct parse trees (or leftmost derivations) (d) It is not context-free
> **Ans: (c)** — Example: E → E + E | E * E | id gives two trees for id + id * id.

**154.** What is the result of removing left recursion from A → Aα | β?  
(a) A → βA', A' → αA' | ε (b) A → αA | β (c) A → Aβ | α (d) A → βα*, with no new symbol
> **Ans: (a)** — Top-down (LL/recursive-descent) parsers would loop forever on left recursion; left factoring removes common prefixes.

**155.** Which correctly orders LR parsers by POWER (the set of grammars they accept), from strongest to weakest?  
(a) SLR > LALR > CLR > LR(0) (b) LALR > CLR > SLR > LR(0) (c) LR(0) > SLR > LALR > CLR (d) CLR(1) > LALR(1) > SLR(1) > LR(0)
> **Ans: (d)** — LALR merges CLR states with the same core, giving smaller tables. YACC produces LALR(1) parsers.

**156.** Replacing `x = 2 * 3.14 * r` with `x = 6.28 * r` at compile time is an example of?  
(a) Dead code elimination (b) Constant folding (c) Strength reduction (d) Loop unrolling
> **Ans: (b) Constant folding** — Constant expressions are evaluated at compile time. Strength reduction would replace, for example, `i * 2` with `i + i` or a shift.

**157.** Which intermediate representation of three-address code stores each instruction as (operator, arg1, arg2, result)?  
(a) Triples (b) Syntax tree (c) Postfix notation (d) Quadruples
> **Ans: (d) Quadruples** — Triples omit the result field and refer to temporaries by instruction position; indirect triples add a list of pointers.

**158.** In panic-mode error recovery, what does the parser do?  
(a) Discards input symbols until a synchronising token (such as `;` or `}`) is found (b) Inserts a missing token and continues (c) Stops compiling immediately (d) Uses error productions in the grammar
> **Ans: (a)** — Option (b) describes phrase-level recovery. Error productions and global correction are the other strategies.

**159.** Which statement about compilers and interpreters is correct?  
(a) An interpreter produces an object file (b) A compiler executes the program line by line (c) A compiler translates the whole program into target code before execution; an interpreter translates and executes it statement by statement (d) An interpreter always runs faster
> **Ans: (c)** — A cross-compiler runs on one platform and produces code for a different target, e.g. for embedded systems.

**160.** Moving a computation whose value does not change inside a loop to before the loop is called?  
(a) Loop-invariant code motion (b) Dead code elimination (c) Constant propagation (d) Peephole optimisation
> **Ans: (a)** — It is a machine-independent loop optimisation.

## A6. Mobile Applications

**161.** Which is NOT a key constraint when developing mobile applications?  
(a) Limited battery life (b) Small screen size (c) Intermittent network connectivity (d) Unlimited RAM and CPU
> **Ans: (d)** — Mobile devices have limited memory and processing power, so apps must manage these resources carefully.

**162.** Which statement best describes a HYBRID mobile app?  
(a) Written only in Kotlin or Swift (b) Runs only in a mobile browser and cannot be installed (c) Built with web technologies (HTML/CSS/JS) inside a native container (WebView), installable from app stores (d) Runs only on smart TVs
> **Ans: (c)** — Native apps use platform SDKs (Kotlin/Java, Swift); web apps run in a browser.

**163.** Which framework uses the Dart language to build cross-platform apps?  
(a) React Native (b) Flutter (c) Xamarin (d) Android SDK
> **Ans: (b) Flutter** — React Native uses JavaScript/React; Xamarin uses C#/.NET; the Android SDK uses Java/Kotlin.

**164.** In Android, which class converts text into spoken audio?  
(a) TextToSpeech (b) SpeechRecognizer (c) MediaPlayer (d) AudioRecord
> **Ans: (a) TextToSpeech** — Create it with an OnInitListener, call setLanguage() in onInit(), then speak(); call shutdown() in onDestroy(). SpeechRecognizer does the reverse (speech → text).

**165.** In the Android Activity lifecycle, which sequence of callbacks happens when an activity is first launched?  
(a) onStart → onCreate → onResume (b) onCreate → onResume → onStart (c) onResume → onStart → onCreate (d) onCreate → onStart → onResume
> **Ans: (d)** — When the app goes to the background, onPause → onStop are called; onDestroy is called at the end (onRestart before onStart when returning).

**166.** Which Android storage option is best for saving small key-value pairs such as user settings?  
(a) SQLite database (b) SharedPreferences (c) External storage (d) Content Provider
> **Ans: (b) SharedPreferences** — SQLite/Room suit structured relational data; internal/external storage suit files; a Content Provider shares data with other apps.

**167.** A user interface that lets the user interact through several input modes AT ONCE (e.g. voice + touch + gesture) is called?  
(a) Multimodal UI (b) Multichannel UI (c) Command-line UI (d) Single-modal UI
> **Ans: (a) Multimodal** — A multichannel UI gives access to the same service through different channels or devices (web, mobile app, SMS, IVR).

**168.** In mobile data synchronisation, the "offline-first" approach means?  
(a) The app refuses to work without a network (b) Data is stored only on the server (c) Data is synchronised only once at install time (d) The app reads and writes a local database first and syncs with the server when connectivity returns, resolving conflicts
> **Ans: (d)** — Common conflict-resolution strategies are last-write-wins, timestamps/versions and server-wins/client-wins.

**169.** Which file in an Android app declares its components (activities, services), required permissions and the launcher activity?  
(a) build.gradle (b) strings.xml (c) AndroidManifest.xml (d) MainActivity.java
> **Ans: (c) AndroidManifest.xml** — Components and the intent-filters for MAIN/LAUNCHER are declared there.

**170.** What is the publishing format required by Google Play for new apps, which lets Play generate optimised APKs for each device?  
(a) Android App Bundle (.aab) (b) .exe (c) .ipa (d) .jar
> **Ans: (a) AAB** — Apps must be signed with a release key (Play App Signing) before upload. .ipa is the iOS format.

# Part B — Paper-II syllabus topics

## B1. Operating Systems

**171.** Which of the following is NOT a recognised type of operating system?  
(a) Batch OS (b) Time-sharing OS (c) Distributed OS (d) Compiler OS
> **Ans: (d) Compiler OS** — a compiler is system software (language translator), not a category of OS; batch, time-sharing, distributed, real-time, network OS are standard types.

**172.** The introduction of integrated circuits (ICs) and multiprogramming is associated with which generation of operating systems?  
(a) First (b) Second (c) Fourth (d) Third
> **Ans: (d) Third** — 1st gen = vacuum tubes/no OS, 2nd = transistors + batch systems, 3rd = ICs + multiprogramming/time-sharing, 4th = microprocessors/PCs.

**173.** The part of the OS that is always resident in memory and directly manages CPU, memory and devices is the  
(a) Kernel (b) Shell (c) Loader (d) Compiler
> **Ans: (a) Kernel** — the kernel is the core of the OS running in privileged mode; the shell is only the user's command interpreter.

**174.** A system call is  
(a) an interrupt raised by a disk controller (b) a call from one user process to another (c) the programmatic interface by which a user process requests a kernel service, switching to kernel mode (d) a library routine that never enters the kernel
> **Ans: (c) the programmatic interface by which a user process requests a kernel service** — e.g. fork(), read(), open(); executed via a trap into kernel mode.

**175.** A running process whose time quantum expires in Round Robin scheduling moves to the  
(a) Ready state (b) Waiting state (c) Terminated state (d) New state
> **Ans: (a) Ready state** — timer interrupt → Running→Ready; only an I/O/event wait sends it to Waiting.

**176.** Which of the following is NOT normally stored in a Process Control Block (PCB)?  
(a) Program counter (b) Process state (c) CPU-scheduling information (d) The source-code file of the program
> **Ans: (d) The source-code file of the program** — PCB holds state, PC, registers, scheduling, memory-management, accounting and I/O-status info, not source code.

**177.** A context switch is  
(a) changing from user mode to kernel mode only (b) saving the state of the running process in its PCB and restoring the saved state of the next process (c) moving a process from disk to main memory (d) changing a process's priority
> **Ans: (b) saving the running process's state in its PCB and loading another's** — it is pure overhead; no useful work is done during the switch.

**178.** Threads belonging to the same process share all of the following EXCEPT  
(a) code section (b) data section (c) open files (d) stack and register set
> **Ans: (d) stack and register set** — each thread has its own thread ID, PC, registers and stack; code, data and OS resources are shared.

**179.** The long-term (job) scheduler primarily controls  
(a) the degree of multiprogramming (b) which ready process gets the CPU next (c) the disk-arm movement (d) the TLB contents
> **Ans: (a) the degree of multiprogramming** — it decides which jobs are admitted from the job pool into memory.

**180.** Processes P1, P2, P3 arrive at time 0 in that order with burst times 24, 3 and 3 ms. Under FCFS the average waiting time is  
(a) 3 ms (b) 17 ms (c) 27 ms (d) 13 ms
> **Ans: (b) 17 ms** — WT: P1 = 0, P2 = 24, P3 = 27 → (0+24+27)/3 = 17 ms.

**181.** Four processes arrive at time 0 with bursts P1 = 6, P2 = 8, P3 = 7, P4 = 3 ms. Average waiting time under non-preemptive SJF is  
(a) 7 ms (b) 10.25 ms (c) 6 ms (d) 8 ms
> **Ans: (a) 7 ms** — order P4(3), P1(6), P3(7), P2(8): WT = 0, 3, 9, 16 → 28/4 = 7 ms. (10.25 is FCFS order.)

**182.** Processes P1 = 24, P2 = 3, P3 = 3 ms arrive at time 0. With Round Robin, time quantum 4 ms, the average waiting time is  
(a) 17 ms (b) 4 ms (c) 7 ms (d) 5.67 ms
> **Ans: (d) 5.67 ms** — Gantt: P1 0–4, P2 4–7, P3 7–10, P1 10–30. WT: P1 = 30−24 = 6, P2 = 4, P3 = 7 → 17/3 ≈ 5.67 ms.

**183.** Aging is a technique used to overcome  
(a) deadlock (b) thrashing (c) Belady's anomaly (d) starvation in priority scheduling
> **Ans: (d) starvation in priority scheduling** — aging gradually raises the priority of processes that have waited long.

**184.** The "convoy effect", where short processes wait behind one long CPU-bound process, is characteristic of  
(a) FCFS scheduling (b) Round Robin (c) SRTF (d) Multilevel feedback queue
> **Ans: (a) FCFS scheduling** — non-preemptive arrival order lets one long job hold up all short ones.

**185.** Which of the following is NOT one of the three requirements of a solution to the critical-section problem?  
(a) Mutual exclusion (b) Progress (c) Bounded waiting (d) Preemption
> **Ans: (d) Preemption** — the three requirements are mutual exclusion, progress and bounded waiting.

**186.** In a blocking (no busy-wait) counting semaphore S, the wait()/P() operation  
(a) increments S and wakes a process (b) decrements S and blocks the caller if S becomes negative (c) sets S to zero (d) has no effect if S is positive
> **Ans: (b) decrements S and blocks the caller if S becomes negative** — signal()/V() increments S and wakes a blocked process if any.

**187.** Which of the following is NOT one of Coffman's four necessary conditions for deadlock?  
(a) Mutual exclusion (b) Hold and wait (c) Preemption (d) Circular wait
> **Ans: (c) Preemption** — the condition is *no* preemption; deadlock needs mutual exclusion, hold-and-wait, no preemption and circular wait simultaneously.

**188.** The Banker's algorithm is a method of deadlock  
(a) avoidance (b) prevention (c) detection only (d) recovery
> **Ans: (a) avoidance** — it grants a request only if the system stays in a safe state.

**189.** A system uses 32-bit logical addresses and a page size of 4 KB. How many bits form the page number?  
(a) 12 (b) 22 (c) 20 (d) 10
> **Ans: (c) 20** — 4 KB = 2¹² → offset = 12 bits; page number = 32 − 12 = 20 bits (2²⁰ page-table entries).

**190.** TLB lookup takes 20 ns, a memory access takes 100 ns, and the TLB hit ratio is 80%. The effective memory-access time (single-level page table) is  
(a) 120 ns (b) 220 ns (c) 160 ns (d) 140 ns
> **Ans: (d) 140 ns** — EAT = 0.8 × (20+100) + 0.2 × (20+100+100) = 96 + 44 = 140 ns.

**191.** In segmentation, each segment-table entry contains  
(a) frame number and valid bit only (b) page number and offset (c) segment base and limit (d) TLB tag and ASID
> **Ans: (c) segment base and limit** — offset is checked against limit, then added to base to form the physical address.

**192.** Paging eliminates external fragmentation but can still suffer from  
(a) internal fragmentation in the last page of a process (b) external fragmentation (c) Belady's anomaly in all algorithms (d) circular wait
> **Ans: (a) internal fragmentation in the last page** — fixed-size frames mean the final page may be partly unused; external fragmentation arises in variable-size contiguous allocation/segmentation.

**193.** Reference string 7,0,1,2,0,3,0,4,2,3,0,3,2,1,2,0,1,7,0,1 with 3 frames (initially empty). Number of page faults under FIFO is  
(a) 12 (b) 9 (c) 15 (d) 10
> **Ans: (c) 15** — simulated FIFO: 15 faults (classic Silberschatz example; verified by simulation).

**194.** For the same reference string 7,0,1,2,0,3,0,4,2,3,0,3,2,1,2,0,1,7,0,1 with 3 frames, LRU gives how many page faults?  
(a) 15 (b) 9 (c) 11 (d) 12
> **Ans: (d) 12** — LRU simulation gives 12 faults (Optimal gives 9, FIFO 15).

**195.** Which page-replacement algorithm can suffer from Belady's anomaly?  
(a) LRU (b) Optimal (c) FIFO (d) None of these
> **Ans: (c) FIFO** — e.g. string 1,2,3,4,1,2,5,1,2,3,4,5: 3 frames → 9 faults, 4 frames → 10 faults. LRU and Optimal are stack algorithms and cannot show it.

**196.** Thrashing occurs when  
(a) CPU utilisation is high because many processes are ready (b) processes spend more time paging than executing (c) the disk head moves to the last cylinder (d) two processes deadlock on a printer
> **Ans: (b) processes spend more time paging than executing** — too little memory per process → page faults dominate and CPU utilisation collapses.

**197.** Disk head at cylinder 53; queue 98, 183, 37, 122, 14, 124, 65, 67. Total head movement under FCFS is  
(a) 236 (b) 640 (c) 208 (d) 382
> **Ans: (b) 640** — |53−98|+|98−183|+|183−37|+|37−122|+|122−14|+|14−124|+|124−65|+|65−67| = 45+85+146+85+108+110+59+2 = 640.

**198.** Same request queue (98, 183, 37, 122, 14, 124, 65, 67), head at 53. Total head movement under SSTF is  
(a) 640 (b) 299 (c) 236 (d) 208
> **Ans: (c) 236** — order 65, 67, 37, 14, 98, 122, 124, 183: 12+2+30+23+84+24+2+59 = 236.

**199.** Which file-allocation method supports direct access without external fragmentation by keeping all block pointers of a file in one block?  
(a) Contiguous (b) Linked (c) FAT chain (d) Indexed
> **Ans: (d) Indexed** — the index block lets block i be found directly; linked allocation supports only sequential access, contiguous suffers external fragmentation.

**200.** Which directory structure allows sharing of files/subdirectories between users but forbids cycles?  
(a) Single-level (b) Two-level (c) Tree-structured (d) Acyclic-graph
> **Ans: (d) Acyclic-graph** — it adds links (sharing) to a tree while disallowing cycles; a pure tree allows no sharing.

**201.** Which RAID level provides block-level striping with distributed parity?  
(a) RAID 5 (b) RAID 0 (c) RAID 1 (d) RAID 3
> **Ans: (a) RAID 5** — RAID 0 = striping with no redundancy, RAID 1 = mirroring, RAID 3 = byte-level striping with a dedicated parity disk.

**202.** Which I/O technique transfers a block of data between device and memory without CPU involvement for each byte?  
(a) Polling (b) Programmed I/O (c) Direct Memory Access (DMA) (d) Spooling
> **Ans: (c) Direct Memory Access (DMA)** — the DMA controller moves the block and interrupts the CPU only on completion.

**203.** Holding the output of several jobs on disk so that a slow printer can print them one by one is called  
(a) buffering (b) spooling (c) caching (d) paging
> **Ans: (b) spooling** — Simultaneous Peripheral Operations On-Line; the disk acts as a large buffer queue for the device.

**204.** In the access-matrix model of protection, storing each column (object) as a list of (domain, rights) pairs gives a(n)  
(a) capability list (b) global table (c) lock-key scheme (d) access control list
> **Ans: (d) access control list** — column-wise = ACL per object; row-wise (per domain) = capability list.

**205.** A program that appears useful but secretly performs a malicious action is a  
(a) worm (b) Trojan horse (c) logic bomb (d) denial-of-service
> **Ans: (b) Trojan horse** — a worm self-replicates across a network; a Trojan relies on disguise.

## B2. Software Engineering

**206.** Which of the following is a basic characteristic of every system?  
(a) Isolation from its environment (b) Organisation and interaction of components towards a common objective (c) Absence of boundaries (d) Single component only
> **Ans: (b) Organisation and interaction of components towards a common objective** — systems have organisation, interaction, interdependence, integration and a central objective; they have boundaries and an environment, not isolation.

**207.** The classical Waterfall model is most suitable when  
(a) requirements are well understood and stable (b) requirements change frequently (c) the customer wants a working version every two weeks (d) risk is very high and unknown
> **Ans: (a) requirements are well understood and stable** — it is linear-sequential; going back to an earlier phase is costly.

**208.** Which SDLC model was proposed by Barry Boehm and is explicitly risk-driven, with each loop including risk analysis?  
(a) V-model (b) RAD (c) Spiral model (d) Incremental model
> **Ans: (c) Spiral model** — each spiral: objectives → risk analysis → engineering → customer evaluation/planning.

**209.** In the V-model, each development phase is paired with  
(a) a prototype (b) a corresponding testing phase (c) a risk-analysis loop (d) a sprint
> **Ans: (b) a corresponding testing phase** — e.g. requirements ↔ acceptance testing, design ↔ system/integration testing, coding ↔ unit testing (verification & validation model).

**210.** The Prototyping model is most useful when  
(a) the customer cannot state detailed requirements clearly at the start (b) the project is a simple, well-understood re-write (c) no customer involvement is possible (d) documentation is the main deliverable
> **Ans: (a) the customer cannot state detailed requirements clearly** — a quick throw-away/evolutionary prototype helps elicit and refine requirements.

**211.** In Scrum, the time-boxed iteration (typically 1–4 weeks) that produces a potentially shippable increment is a  
(a) backlog (b) milestone (c) scrum (d) sprint
> **Ans: (d) sprint** — the product backlog is the prioritised list of features; the sprint backlog is the subset chosen for one sprint.

**212.** In Scrum, the person who facilitates the process and removes impediments for the team is the  
(a) Product Owner (b) Scrum Master (c) Project Sponsor (d) Tester
> **Ans: (b) Scrum Master** — the Product Owner owns and prioritises the product backlog.

**213.** Which type of feasibility study checks whether the benefits of a system exceed its costs?  
(a) Technical feasibility (b) Operational feasibility (c) Schedule feasibility (d) Economic feasibility
> **Ans: (d) Economic feasibility** — cost–benefit analysis; technical = can it be built, operational = will users use it.

**214.** Which of the following is a functional requirement?  
(a) The system shall generate a monthly salary report (b) The system shall be available 99.9% of the time (c) Pages shall load within 2 seconds (d) The system shall run on Linux and Windows
> **Ans: (a) The system shall generate a monthly salary report** — it states a service/behaviour; the others are non-functional (availability, performance, portability).

**215.** Which property is NOT expected of a good SRS?  
(a) Correct (b) Unambiguous (c) Verifiable (d) Containing detailed source code
> **Ans: (d) Containing detailed source code** — an SRS says *what* the system should do (correct, complete, consistent, unambiguous, verifiable, modifiable, traceable), not *how*.

**216.** In Basic COCOMO, a project developed by a small experienced team with familiar, well-understood requirements is classified as  
(a) Organic (b) Semi-detached (c) Embedded (d) Detached
> **Ans: (a) Organic** — semi-detached is intermediate; embedded has tight hardware/regulatory constraints.

**217.** In Basic COCOMO the effort equation has the form  
(a) E = a + b·KLOC (b) E = a·(KLOC)^b person-months (c) E = KLOC / a (d) E = a·log(KLOC)
> **Ans: (b) E = a·(KLOC)^b person-months** — development time D = c·(E)^d months.

**218.** An organic-mode project is estimated at 32 KLOC. Using Basic COCOMO (E = 2.4·KLOC^1.05), the effort is approximately  
(a) 76.8 PM (b) 146 PM (c) 91 PM (d) 14 PM
> **Ans: (c) 91 PM** — E = 2.4 × 32^1.05 = 2.4 × 38.05 ≈ 91.3 person-months (D = 2.5 × 91.3^0.38 ≈ 13.9 months).

**219.** Function Point Analysis measures software size based on  
(a) lines of code written (b) number of programmers (c) number of test cases (d) external inputs, outputs, inquiries, internal logical files and external interface files
> **Ans: (d) external inputs, outputs, inquiries, internal logical files and external interface files** — weighted counts adjusted by 14 value-adjustment factors.

**220.** The Delphi technique of cost estimation is based on  
(a) iterative, anonymous consensus among a panel of experts (b) a regression equation on KLOC (c) counting function points (d) copying last year's budget
> **Ans: (a) iterative, anonymous consensus among a panel of experts** — a coordinator circulates estimates over several rounds until they converge.

**221.** A tool that shows project tasks as horizontal bars against a calendar time-line is a  
(a) PERT network (b) Gantt chart (c) Data-flow diagram (d) Work breakdown structure
> **Ans: (b) Gantt chart** — PERT/CPM show task dependencies as a network; WBS is a hierarchical decomposition of work.

**222.** Activities: A (3 days, start), B (4 days, after A), C (2 days, after A), D (5 days, after B and C). The critical-path length is  
(a) 10 days (b) 14 days (c) 9 days (d) 12 days
> **Ans: (d) 12 days** — paths: A–B–D = 3+4+5 = 12, A–C–D = 3+2+5 = 10; longest = critical path A–B–D = 12 (slack of C = 2).

**223.** In PERT, the expected time of an activity with optimistic a, most-likely m and pessimistic b times is  
(a) (a + 4m + b)/6 (b) (a + m + b)/3 (c) (a + 2m + b)/4 (d) (b − a)/6
> **Ans: (a) (a + 4m + b)/6** — beta-distribution estimate; (b − a)/6 is the standard deviation.

**224.** A control-flow graph has 9 edges and 7 nodes (one connected component). Its cyclomatic complexity is  
(a) 2 (b) 3 (c) 4 (d) 16
> **Ans: (c) 4** — V(G) = E − N + 2P = 9 − 7 + 2 = 4 (= number of independent paths to test).

**225.** Designing test cases from the specification without looking at internal code is  
(a) white-box testing (b) black-box testing (c) path testing (d) statement coverage
> **Ans: (b) black-box testing** — techniques include equivalence partitioning and boundary value analysis.

**226.** An input field accepts integers from 1 to 100. Under Boundary Value Analysis, which set of test values is most appropriate?  
(a) 50 only (b) 1, 50, 100 only (c) −100, 0, 1000 (d) 0, 1, 2, 99, 100, 101
> **Ans: (d) 0, 1, 2, 99, 100, 101** — BVA tests just below, on and just above each boundary, where defects cluster.

**227.** Testing performed by real users at their own sites, after alpha testing, is  
(a) beta testing (b) unit testing (c) integration testing (d) regression testing
> **Ans: (a) beta testing** — alpha testing is by users at the developer's site under developer supervision.

**228.** Re-running existing tests after a change to ensure that old functionality still works is called  
(a) smoke testing (b) stress testing (c) regression testing (d) acceptance testing
> **Ans: (c) regression testing** — smoke = quick build-verification check; stress = beyond-normal load.

**229.** Which statement correctly distinguishes Verification from Validation?  
(a) Verification: "Are we building the product right?"; Validation: "Are we building the right product?" (b) Both mean testing the final product (c) Verification is done only by the customer (d) Validation involves only code reviews
> **Ans: (a) Verification = building the product right; Validation = building the right product** — verification checks conformance to specifications (reviews, inspections); validation checks it meets user needs (testing the actual product).

**230.** Quality Assurance (QA) differs from Quality Control (QC) in that QA is  
(a) product-oriented defect detection (b) performed only after coding (c) process-oriented and preventive (d) the same as testing
> **Ans: (c) process-oriented and preventive** — QC is product-oriented and detective (inspection, testing).

**231.** The correct order of SEI Capability Maturity Model (CMM) levels from 1 to 5 is  
(a) Initial, Defined, Repeatable, Managed, Optimizing (b) Initial, Repeatable, Defined, Managed, Optimizing (c) Repeatable, Initial, Defined, Optimizing, Managed (d) Initial, Managed, Defined, Repeatable, Optimizing
> **Ans: (b) Initial, Repeatable, Defined, Managed, Optimizing** — (CMMI renames level 2 "Managed" and level 4 "Quantitatively Managed".)

**232.** Which pair represents the BEST design goals for modules?  
(a) High coupling, low cohesion (b) Low coupling, high cohesion (c) High coupling, high cohesion (d) Low coupling, low cohesion
> **Ans: (b) Low coupling, high cohesion** — best cohesion = functional (worst = coincidental); best coupling = data (worst = content).

**233.** Modifying software so that it continues to work after the OS or hardware environment changes is  
(a) corrective maintenance (b) perfective maintenance (c) preventive maintenance (d) adaptive maintenance
> **Ans: (d) adaptive maintenance** — corrective fixes bugs, perfective adds/improves features, preventive improves future maintainability.

**234.** Tools that support analysis, design, code generation and testing activities of software development are called  
(a) DBMS tools (b) CASE tools (c) BIOS tools (d) ERP tools
> **Ans: (b) CASE tools** — Computer-Aided Software Engineering; upper CASE (analysis/design), lower CASE (coding/testing).

**235.** A hierarchical decomposition of the total project work into smaller, manageable work packages is the  
(a) Gantt chart (b) Critical path (c) Work Breakdown Structure (d) SRS
> **Ans: (c) Work Breakdown Structure** — the WBS is the basis for estimation and scheduling.

## B3. DBMS & SQL

**236.** The three levels of data abstraction in the ANSI/SPARC architecture, from lowest to highest, are  
(a) View, Logical, Physical (b) Physical, Logical (conceptual), View (external) (c) Logical, Physical, View (d) Internal, View, Conceptual
> **Ans: (b) Physical, Logical (conceptual), View (external)** — physical = how data is stored, logical = what data and relationships, view = part seen by a user.

**237.** The ability to change the physical (internal) schema without changing the conceptual schema or application programs is  
(a) logical data independence (b) data abstraction (c) data redundancy (d) physical data independence
> **Ans: (d) physical data independence** — logical data independence (harder to achieve) is changing the conceptual schema without affecting external schemas/programs.

**238.** The overall design of a database that changes rarely is called the \_\_\_\_\_\_, while the data stored at a particular moment is the \_\_\_\_\_\_.  
(a) schema; instance (b) instance; schema (c) view; table (d) tuple; relation
> **Ans: (a) schema; instance** — schema ≈ variable type declaration; instance ≈ current value.

**239.** In which data model are records organised as a tree with parent–child (one-to-many) links only?  
(a) Network model (b) Relational model (c) Hierarchical model (d) Object-oriented model
> **Ans: (c) Hierarchical model** — e.g. IBM IMS; the network model allows a record to have many owners (graph).

**240.** Which of the following SQL statements is a DCL command?  
(a) GRANT (b) UPDATE (c) ALTER (d) COMMIT
> **Ans: (a) GRANT** — DCL = GRANT, REVOKE; UPDATE is DML, ALTER is DDL, COMMIT is TCL.

**241.** Which of the following is NOT a DDL statement?  
(a) CREATE TABLE (b) DROP TABLE (c) TRUNCATE TABLE (d) INSERT INTO
> **Ans: (d) INSERT INTO** — INSERT/UPDATE/DELETE/SELECT are DML; CREATE, ALTER, DROP, TRUNCATE, RENAME are DDL.

**242.** An attribute such as "Phone_numbers" that can hold several values for one entity is a(n)  
(a) derived attribute (b) composite attribute (c) key attribute (d) multivalued attribute
> **Ans: (d) multivalued attribute** — shown by a double ellipse in an ER diagram; "Age" computed from DOB would be derived (dashed ellipse).

**243.** A minimal super key is called a  
(a) candidate key (b) foreign key (c) composite key (d) alternate key
> **Ans: (a) candidate key** — one candidate key is chosen as primary key; the remaining ones are alternate keys.

**244.** A foreign key is an attribute (set) that  
(a) uniquely identifies tuples in its own relation and cannot be NULL (b) is always a composite key (c) is computed from other attributes (d) refers to the primary key of another (or the same) relation
> **Ans: (d) refers to the primary key of another (or the same) relation** — it enforces referential integrity.

**245.** In a Chen ER diagram, a weak entity set is represented by  
(a) a diamond (b) a double rectangle (c) an ellipse (d) a dashed ellipse
> **Ans: (b) a double rectangle** — its identifying relationship is a double diamond; its partial key (discriminator) is underlined with a dashed line.

**246.** The relational algebra operator that selects a subset of tuples satisfying a predicate is  
(a) π (projection) (b) σ (selection) (c) ⋈ (join) (d) ÷ (division)
> **Ans: (b) σ (selection)** — π picks columns (attributes), σ picks rows (tuples).

**247.** Relation A has 3 tuples and relation B has 4 tuples. The Cartesian product A × B contains  
(a) 7 tuples (b) 1 tuple (c) 3 tuples (d) 12 tuples
> **Ans: (d) 12 tuples** — |A × B| = |A| × |B| = 3 × 4 = 12 (degree = sum of degrees).

**248.** Queries of the form "find students who have taken ALL courses" are expressed in relational algebra using  
(a) Division (÷) (b) Union (∪) (c) Projection (π) (d) Rename (ρ)
> **Ans: (a) Division (÷)** — R ÷ S returns tuples of R associated with every tuple in S.

**249.** The logical order in which the clauses of a SELECT query are evaluated is  
(a) SELECT → FROM → WHERE → GROUP BY → HAVING → ORDER BY (b) FROM → SELECT → WHERE → HAVING → GROUP BY → ORDER BY (c) FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY (d) WHERE → FROM → GROUP BY → SELECT → HAVING → ORDER BY
> **Ans: (c) FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY** — which is why WHERE cannot use aggregates but HAVING can.

**250.** Table Emp(name, dept, salary) has 5 rows; exactly one row has salary = NULL. What does `SELECT COUNT(*), COUNT(salary) FROM Emp;` return?  
(a) 5, 5 (b) 4, 4 (c) 5, 4 (d) 4, 5
> **Ans: (c) 5, 4** — COUNT(*) counts all rows; COUNT(column) ignores NULLs (verified in SQLite).

**251.** Emp(name, dept, salary) contains: (Asha, IT, 50000), (Bina, IT, 60000), (Chen, HR, 40000), (Dev, HR, NULL), (Ezra, FIN, 70000). What is the result of `SELECT AVG(salary) FROM Emp;`?  
(a) 44000 (b) 55000 (c) 50000 (d) NULL
> **Ans: (b) 55000** — aggregates skip NULL: (50000+60000+40000+70000)/4 = 220000/4 = 55000 (not /5 = 44000). Verified in SQLite.

**252.** Using the same Emp table, how many rows does `SELECT dept, COUNT(*) FROM Emp GROUP BY dept HAVING COUNT(*) > 1;` return?  
(a) 1 (b) 3 (c) 0 (d) 2
> **Ans: (d) 2** — groups: IT = 2, HR = 2, FIN = 1 → IT and HR qualify (verified in SQLite).

**253.** Which condition correctly finds rows whose salary is missing?  
(a) WHERE salary = NULL (b) WHERE salary IS NULL (c) WHERE salary == 0 (d) WHERE salary = ''
> **Ans: (b) WHERE salary IS NULL** — any comparison with NULL using = yields UNKNOWN, so `= NULL` never matches.

**254.** A LEFT OUTER JOIN of R with S returns  
(a) only matching rows from both (b) all rows of S and matching rows of R (c) all rows of R, with matching S values or NULLs where there is no match (d) the Cartesian product
> **Ans: (c) all rows of R, padded with NULLs where no S match** — an INNER JOIN returns only matching rows.

**255.** Which statement removes the table's structure (definition) as well as all its data?  
(a) DROP TABLE (b) DELETE FROM (c) TRUNCATE TABLE (d) DELETE ... WHERE
> **Ans: (a) DROP TABLE** — DELETE (DML) removes rows, can use WHERE and be rolled back; TRUNCATE (DDL) removes all rows but keeps the structure.

**256.** A view in SQL is  
(a) a physical copy of a table on disk (b) an index on a table (c) a stored procedure (d) a virtual table defined by a stored query
> **Ans: (d) a virtual table defined by a stored query** — it is computed when referenced (unless materialized) and supports security and logical independence.

**257.** R(A, B, C, D, E) has FDs A → B, B → C, CD → E. Which is the candidate key?  
(a) A (b) AD (c) CD (d) ABD
> **Ans: (b) AD** — A⁺ = {A,B,C}; (AD)⁺ = {A,B,C,D,E} = all attributes. A and D never appear on any RHS so every key must contain both; ABD is a superkey but not minimal.

**258.** A relation is in 2NF if it is in 1NF and  
(a) it has no multivalued attributes (b) no non-prime attribute is partially dependent on any candidate key (c) no non-prime attribute is transitively dependent on a key (d) every determinant is a candidate key
> **Ans: (b) no partial dependency of a non-prime attribute on a candidate key** — 3NF removes transitive dependencies; BCNF requires every determinant to be a superkey.

**259.** A relation is in BCNF if, for every non-trivial FD X → Y,  
(a) Y is a prime attribute (b) X is a subset of a candidate key (c) X is a superkey (d) Y is a foreign key
> **Ans: (c) X is a superkey** — 3NF additionally allows Y to be prime, so BCNF is stricter.

**260.** The ACID property which guarantees that a transaction's effects are either all applied or none are applied is  
(a) Atomicity (b) Consistency (c) Isolation (d) Durability
> **Ans: (a) Atomicity** — durability means committed changes survive failures; isolation hides concurrent transactions' intermediate states.

**261.** A schedule is conflict-serializable if and only if  
(a) it has no read operations (b) all transactions commit (c) it contains a cycle in its precedence graph (d) its precedence (serialization) graph is acyclic
> **Ans: (d) its precedence graph is acyclic** — a topological order of the graph gives the equivalent serial schedule.

**262.** In Two-Phase Locking (2PL), a transaction  
(a) acquires all locks in the growing phase and releases them in the shrinking phase, never acquiring a lock after releasing one (b) releases locks before acquiring any (c) holds no locks while reading (d) uses timestamps instead of locks
> **Ans: (a) growing phase then shrinking phase** — 2PL guarantees conflict-serializability but does not prevent deadlock; strict 2PL holds exclusive locks until commit.

**263.** During recovery, a checkpoint in the log is used to  
(a) encrypt the log (b) start a new transaction (c) limit how much of the log must be scanned for undo/redo after a crash (d) delete committed transactions
> **Ans: (c) limit the log scanned during recovery** — at a checkpoint, log records and modified buffers are flushed to stable storage.

**264.** The correct order of the basic steps in query processing is  
(a) Optimization → Parsing → Execution (b) Parsing and translation → Optimization → Evaluation (execution) (c) Execution → Parsing → Optimization (d) Evaluation → Optimization → Parsing
> **Ans: (b) Parsing and translation → Optimization → Evaluation** — the parser builds a relational-algebra expression, the optimizer picks the cheapest evaluation plan, the engine executes it.

**265.** A sparse index contains  
(a) an entry for every search-key value (b) no pointers (c) entries only for some search-key values, and requires the file to be sorted on that key (d) only hash values
> **Ans: (c) entries only for some search-key values, on a sorted file** — a dense index has an entry for every search-key value.

**266.** In a B+ tree index  
(a) all data pointers are stored in the leaf nodes, which are linked for sequential access (b) data pointers are only in the root (c) the tree may be unbalanced (d) leaves are not linked
> **Ans: (a) all data pointers are in leaf nodes, which are linked** — it is always balanced; internal nodes hold only keys for navigation.

**267.** In a distributed database, splitting a relation by rows (tuples) across sites is called  
(a) vertical fragmentation (b) replication (c) horizontal fragmentation (d) normalization
> **Ans: (c) horizontal fragmentation** — vertical fragmentation splits by columns (each fragment keeps the key); replication stores copies.

**268.** The Two-Phase Commit (2PC) protocol in distributed databases is used to  
(a) ensure atomic commitment of a transaction across all participating sites (b) lock data in two phases (c) replicate data to two sites (d) optimise queries
> **Ans: (a) ensure atomic commitment across sites** — phase 1: coordinator sends PREPARE and collects votes; phase 2: global COMMIT or ABORT.

**269.** Entering `' OR '1'='1` into a login form to bypass authentication is an example of  
(a) phishing (b) SQL injection (c) denial of service (d) buffer overflow
> **Ans: (b) SQL injection** — prevented by parameterised/prepared statements and input validation.

**270.** The integrity constraint stating that no component of a primary key may be NULL is  
(a) referential integrity (b) domain constraint (c) entity integrity (d) key-uniqueness only
> **Ans: (c) entity integrity** — referential integrity requires each foreign-key value to match an existing primary key or be NULL.

## B4. Data Communication & Computer Networks

**271.** A network that spans a city, such as a cable-TV network interconnecting several LANs, is a  
(a) PAN (b) LAN (c) MAN (d) WAN
> **Ans: (c) MAN** — Metropolitan Area Network; PAN ≈ a few metres, LAN ≈ building/campus, WAN ≈ country/global.

**272.** How many dedicated links are needed to connect 6 devices in a fully connected mesh topology?  
(a) 30 (b) 15 (c) 12 (d) 6
> **Ans: (b) 15** — n(n−1)/2 = 6 × 5 / 2 = 15 duplex links; each device needs n − 1 = 5 ports.

**273.** In which topology does failure of the central device bring down the whole network?  
(a) Star (b) Mesh (c) Ring with dual links (d) Fully connected
> **Ans: (a) Star** — every device connects only to the central hub/switch.

**274.** A router operates at which OSI layer?  
(a) Physical (b) Data link (c) Transport (d) Network
> **Ans: (d) Network** — routers forward packets using logical (IP) addresses; switches/bridges are layer 2; hubs/repeaters layer 1.

**275.** Communication in which both stations can transmit, but only one at a time, is  
(a) simplex (b) full-duplex (c) half-duplex (d) multiplex
> **Ans: (c) half-duplex** — e.g. walkie-talkie; simplex = one direction only (keyboard→CPU), full-duplex = both simultaneously (telephone).

**276.** Which of the following is an unguided (wireless) transmission medium?  
(a) Microwave (b) Twisted pair (c) Coaxial cable (d) Optical fibre
> **Ans: (a) Microwave** — guided media use a physical conductor or fibre; radio, microwave and infrared are unguided.

**277.** The correct order of OSI layers from top (7) to bottom (1) is  
(a) Application, Session, Presentation, Transport, Network, Data link, Physical (b) Application, Presentation, Session, Network, Transport, Data link, Physical (c) Application, Presentation, Session, Transport, Data link, Network, Physical (d) Application, Presentation, Session, Transport, Network, Data link, Physical
> **Ans: (d) Application, Presentation, Session, Transport, Network, Data link, Physical** — mnemonic "All People Seem To Need Data Processing".

**278.** Which OSI layer is responsible for encryption, compression and translation of data formats?  
(a) Session (b) Presentation (c) Application (d) Transport
> **Ans: (b) Presentation** — the session layer handles dialogue control and synchronisation (checkpoints).

**279.** The PDU (protocol data unit) at the data link layer is called a  
(a) segment (b) packet (c) frame (d) bit
> **Ans: (c) frame** — Transport = segment, Network = packet/datagram, Data link = frame, Physical = bits.

**280.** Process-to-process (end-to-end) delivery, segmentation and port addressing are functions of the  
(a) Transport layer (b) Network layer (c) Data link layer (d) Physical layer
> **Ans: (a) Transport layer** — the network layer gives host-to-host delivery; data link gives node-to-node (hop) delivery.

**281.** The TCP/IP (Internet) model's layer that corresponds to the OSI Network layer is the  
(a) Application layer (b) Transport layer (c) Network-access layer (d) Internet layer
> **Ans: (d) Internet layer** — IP, ICMP, ARP operate here.

**282.** The well-known port number of HTTPS is  
(a) 80 (b) 443 (c) 8080 (d) 21
> **Ans: (b) 443** — HTTP = 80, FTP = 20 (data)/21 (control).

**283.** SMTP, DNS and SSH use which well-known ports respectively?  
(a) 25, 53, 22 (b) 110, 53, 23 (c) 25, 67, 22 (d) 143, 53, 23
> **Ans: (a) 25, 53, 22** — POP3 = 110, IMAP = 143, Telnet = 23, DHCP = 67/68.

**284.** Which statement about TCP and UDP is correct?  
(a) UDP is connection-oriented and reliable (b) TCP is connectionless and has no flow control (c) TCP is connection-oriented and reliable; UDP is connectionless with no guaranteed delivery (d) Both provide sequencing and retransmission
> **Ans: (c) TCP is connection-oriented and reliable; UDP is connectionless** — TCP provides ordered delivery, acknowledgements, flow and congestion control; UDP is lightweight (used by DNS queries, VoIP, streaming).

**285.** The correct sequence of segments in the TCP three-way handshake is  
(a) SYN, ACK, SYN-ACK (b) SYN-ACK, SYN, ACK (c) ACK, SYN, FIN (d) SYN, SYN-ACK, ACK
> **Ans: (d) SYN, SYN-ACK, ACK** — client SYN → server SYN+ACK → client ACK; connection then established.

**286.** The IPv4 address 172.20.5.9 belongs to which class?  
(a) Class A (b) Class B (c) Class C (d) Class D
> **Ans: (b) Class B** — first octet 128–191 = Class B (A: 1–126, C: 192–223, D multicast: 224–239, E: 240–255).

**287.** Which of the following is a private IPv4 address (RFC 1918)?  
(a) 172.32.1.1 (b) 11.0.0.1 (c) 192.168.5.20 (d) 192.169.1.1
> **Ans: (c) 192.168.5.20** — private ranges: 10.0.0.0/8, 172.16.0.0–172.31.255.255 (/12), 192.168.0.0/16.

**288.** How many usable host addresses are available in a /26 subnet?  
(a) 62 (b) 64 (c) 30 (d) 126
> **Ans: (a) 62** — host bits = 32 − 26 = 6 → 2⁶ − 2 = 62 (network and broadcast addresses excluded).

**289.** What is the network address of host 192.168.10.77/27?  
(a) 192.168.10.0 (b) 192.168.10.96 (c) 192.168.10.72 (d) 192.168.10.64
> **Ans: (d) 192.168.10.64** — /27 mask 255.255.255.224, block size 32: 77 lies in 64–95 → network .64, broadcast .95 (verified with Python ipaddress).

**290.** The subnet mask corresponding to the prefix /20 is  
(a) 255.255.255.0 (b) 255.255.240.0 (c) 255.255.248.0 (d) 255.240.0.0
> **Ans: (b) 255.255.240.0** — 20 ones = 8 + 8 + 4 → third octet 11110000 = 240; it gives 2¹² − 2 = 4094 hosts.

**291.** The sizes of an IPv4 address, an IPv6 address and a MAC (Ethernet) address are respectively  
(a) 32, 128 and 64 bits (b) 32, 64 and 48 bits (c) 64, 128 and 32 bits (d) 32, 128 and 48 bits
> **Ans: (d) 32, 128 and 48 bits** — MAC is written as 6 hex-pairs (e.g. 00:1A:2B:3C:4D:5E).

**292.** Which protocol finds the MAC address corresponding to a known IP address on a LAN?  
(a) RARP (b) ICMP (c) ARP (d) DHCP
> **Ans: (c) ARP** — RARP does the reverse (MAC → IP); ICMP reports errors (ping); DHCP assigns IP configuration.

**293.** DNS is primarily used to  
(a) assign IP addresses dynamically (b) map domain names to IP addresses (c) transfer e-mail (d) encrypt web traffic
> **Ans: (b) map domain names to IP addresses** — DHCP is the protocol that assigns addresses dynamically.

**294.** RIP is a distance-vector routing protocol. The maximum hop count it treats as reachable is  
(a) 16 (b) 255 (c) 15 (d) 30
> **Ans: (c) 15** — a metric of 16 means "infinity/unreachable"; updates are sent every 30 seconds.

**295.** OSPF is classified as a  
(a) distance-vector protocol (b) path-vector protocol (c) static routing protocol (d) link-state protocol
> **Ans: (d) link-state protocol** — it floods link-state advertisements and runs Dijkstra's shortest-path algorithm; BGP (inter-domain) is path-vector.

**296.** In which switching technique is a dedicated physical path reserved for the entire duration of the communication?  
(a) Circuit switching (b) Packet switching (c) Message switching (d) Datagram switching
> **Ans: (a) Circuit switching** — e.g. traditional telephone network; packet switching shares links dynamically.

**297.** The Hamming distance between codewords 10101 and 11110 is  
(a) 2 (b) 3 (c) 4 (d) 5
> **Ans: (b) 3** — XOR = 01011 → three 1-bits. A code with minimum distance d detects d−1 errors and corrects ⌊(d−1)/2⌋.

**298.** A single even-parity bit can  
(a) correct any single-bit error (b) detect all burst errors (c) detect all two-bit errors (d) detect any odd number of bit errors but not correct them
> **Ans: (d) detect any odd number of bit errors** — an even number of flipped bits leaves parity unchanged and goes undetected.

**299.** Which error-detection technique uses polynomial (modulo-2) division with a generator polynomial?  
(a) Checksum (b) Simple parity (c) CRC (d) Two-dimensional parity
> **Ans: (c) CRC** — Cyclic Redundancy Check; the remainder is appended as the CRC bits.

**300.** Which multiplexing technique is used in fibre-optic links by assigning different light wavelengths to different signals?  
(a) TDM (b) WDM (c) FDM over copper (d) Statistical TDM
> **Ans: (b) WDM** — Wavelength Division Multiplexing is conceptually FDM for optical signals.

**301.** A noiseless channel of bandwidth 3000 Hz carries a signal with 4 signal levels. The Nyquist maximum bit rate is  
(a) 6000 bps (b) 24000 bps (c) 3000 bps (d) 12000 bps
> **Ans: (d) 12000 bps** — C = 2B log₂L = 2 × 3000 × log₂4 = 2 × 3000 × 2 = 12000 bps.

**302.** A channel has bandwidth 1 MHz and SNR = 63. According to Shannon's theorem, its capacity is  
(a) 6 Mbps (b) 63 Mbps (c) 1 Mbps (d) 2 Mbps
> **Ans: (a) 6 Mbps** — C = B log₂(1 + SNR) = 10⁶ × log₂64 = 10⁶ × 6 = 6 Mbps.

**303.** In the URL `https://www.npsc.example/exam/index.html`, the part `https` denotes the  
(a) host name (b) path (c) protocol (scheme) (d) port
> **Ans: (c) protocol (scheme)** — `www.npsc.example` is the host; `/exam/index.html` is the path.

**304.** A firewall is primarily used to  
(a) increase bandwidth (b) filter incoming and outgoing traffic according to security rules (c) assign IP addresses (d) convert digital to analog signals
> **Ans: (b) filter traffic according to security rules** — e.g. packet-filtering, stateful and application-level (proxy) firewalls.

**305.** In public-key (asymmetric) cryptography, a message to be read only by Bob is encrypted using  
(a) Bob's private key (b) the sender's private key (c) a shared secret key (d) Bob's public key
> **Ans: (d) Bob's public key** — only Bob's private key can decrypt it; signing uses the sender's private key.

## B5. Web Technologies (HTML & PHP)

**306.** Which is the usual order of the phases of website development?  
(a) Design → Planning → Testing → Development → Launch (b) Planning/analysis → Design → Development (coding) → Testing → Deployment/launch → Maintenance (c) Development → Design → Planning → Launch → Testing (d) Testing → Planning → Design → Development → Launch
> **Ans: (b) Planning → Design → Development → Testing → Deployment → Maintenance** — information gathering/planning first; the site goes live only after testing.

**307.** Which HTML element contains the page's title, meta tags and links to stylesheets, but not visible page content?  
(a) `<body>` (b) `<footer>` (c) `<head>` (d) `<main>`
> **Ans: (c) `<head>`** — visible content goes inside `<body>`; `<title>` is placed inside `<head>` and shows in the browser tab.

**308.** Which heading tag produces the largest default text?  
(a) `<h1>` (b) `<h6>` (c) `<head>` (d) `<h0>`
> **Ans: (a) `<h1>`** — HTML has six heading levels h1 (largest/most important) to h6 (smallest); there is no h0.

**309.** Which of the following HTML tags is an empty (void) element with no closing tag?  
(a) `<p>` (b) `<a>` (c) `<li>` (d) `<br>`
> **Ans: (d) `<br>`** — `<br>` (line break), `<hr>` (horizontal rule) and `<img>` are void elements.

**310.** Which tag displays text exactly as typed, preserving spaces and line breaks in a fixed-width font?  
(a) `<p>` (b) `<pre>` (c) `<code>` only (d) `<tt>`
> **Ans: (b) `<pre>`** — preformatted text; normal HTML collapses multiple spaces/newlines into one space.

**311.** To create a numbered list that uses capital Roman numerals (I, II, III …) you would write  
(a) `<ul type="I">` (b) `<ol type="a">` (c) `<ol type="I">` (d) `<dl type="I">`
> **Ans: (c) `<ol type="I">`** — ol type values: 1, A, a, I, i; ul is for bulleted (unordered) lists.

**312.** In a definition (description) list, which tags hold the term and its description respectively?  
(a) `<dt>` and `<dd>` (b) `<li>` and `<dd>` (c) `<dl>` and `<dt>` (d) `<td>` and `<th>`
> **Ans: (a) `<dt>` and `<dd>`** — enclosed in `<dl>…</dl>`.

**313.** Which attribute of the `<a>` tag makes a link open in a new browser tab/window?  
(a) `href="_new"` (b) `rel="new"` (c) `open="tab"` (d) `target="_blank"`
> **Ans: (d) `target="_blank"`** — href gives the destination URL; `href="#id"` links to an anchor on the same page; `href="mailto:..."` opens an e-mail client.

**314.** The `<font size="...">` attribute accepts values from 1 to 7. What is the default size?  
(a) 1 (b) 3 (c) 5 (d) 7
> **Ans: (b) 3** — `<font>` (attributes size, color, face) is deprecated/obsolete in HTML5; CSS is used instead.

**315.** The `alt` attribute of the `<img>` tag specifies  
(a) the image file path (b) the image width (c) alternate text shown if the image cannot be displayed and read by screen readers (d) the image border
> **Ans: (c) alternate text** — `src` gives the image path.

**316.** Which HTML tag defines a header cell in a table?  
(a) `<th>` (b) `<td>` (c) `<tr>` (d) `<thead>` only
> **Ans: (a) `<th>`** — `<tr>` = table row, `<td>` = data cell; th text is bold and centred by default.

**317.** Compared with the GET method, a form submitted with POST  
(a) shows the data in the URL (b) is limited to 255 characters (c) can be bookmarked with its data (d) sends data in the HTTP request body, not in the URL
> **Ans: (d) sends data in the request body** — better for sensitive or large data; GET appends name=value pairs to the URL query string.

**318.** The HTTP status code 404 means  
(a) OK (b) Internal Server Error (c) Not Found (d) Moved Permanently
> **Ans: (c) Not Found** — 200 = OK, 301 = Moved Permanently, 500 = Internal Server Error.

**319.** The default file extension of a PHP script and the standard opening/closing tags are  
(a) .php and `<?php ... ?>` (b) .ph and `<% ... %>` (c) .html and `<script php>` (d) .psp and `<php> ... </php>`
> **Ans: (a) .php and `<?php ... ?>`** — PHP is executed on the server; the browser receives only the generated HTML.

**320.** Which is TRUE about PHP variables?  
(a) Names are case-insensitive (b) They must be declared with a type (c) They start with `$` and their names are case-sensitive (d) Names may begin with a digit
> **Ans: (c) start with `$` and are case-sensitive** — `$x` and `$X` are different; a name must start with a letter or underscore.

**321.** What is the output of this PHP code?  
```php
<?php $a = "5"; $b = 3; echo $a . $b; ?>
```
(a) 8 (b) 53 (c) 5 3 (d) Error
> **Ans: (b) 53** — `.` is the string-concatenation operator; `$a + $b` would give 8 (verified with PHP 8.4).

**322.** What is the output of this PHP code?  
```php
<?php $name = "Kohima"; echo 'Hi $name'; ?>
```
(a) Hi $name (b) Hi Kohima (c) Hi (d) Parse error
> **Ans: (a) Hi $name** — single-quoted strings do not interpolate variables; `"Hi $name"` would print Hi Kohima (verified with PHP 8.4).

**323.** What is the output of this PHP code?  
```php
<?php $n = [10, 20, 30]; $s = "ab"; $s .= "cd"; echo $n[1] . $s; ?>
```
(a) 10abcd (b) 20ab (c) 30abcd (d) 20abcd
> **Ans: (d) 20abcd** — indexed arrays start at 0 so `$n[1]` = 20; `.=` appends, giving "abcd".

**324.** Which function defines a constant in PHP?  
(a) const_set() (b) define() (c) constant() only (d) let()
> **Ans: (b) define()** — e.g. `define("PI", 3.14);` constants are used without `$`. (The `const` keyword also works.)

**325.** Which PHP superglobal contains data sent with the POST method?  
(a) `$_GET` (b) `$_SERVER` (c) `$_POST` (d) `$_COOKIE`
> **Ans: (c) `$_POST`** — `$_REQUEST` collects GET and POST data (and COOKIE, depending on php.ini `request_order`); `$_SERVER` holds server/request headers info.

**326.** Before session variables can be stored in or read from `$_SESSION`, a script must call  
(a) session_start() (b) setcookie() (c) session_destroy() (d) header()
> **Ans: (a) session_start()** — session data is kept on the server; setcookie() stores data in the browser.

**327.** The difference between `include` and `require` in PHP is that if the file is missing  
(a) include gives a fatal error and stops; require only warns (b) both stop the script (c) both silently continue (d) require produces a fatal error and stops; include emits a warning and continues
> **Ans: (d) require → fatal error and stops; include → warning and continues.**

**328.** Which type of PHP error does NOT stop script execution by default?  
(a) Parse (syntax) error (b) Fatal error (c) Warning (d) Compile error
> **Ans: (c) Warning** — warnings and notices let execution continue; parse and fatal errors halt it.

**329.** What do `empty($v)` and `isset($v)` return when `$v = "";`?  
(a) true, true (b) false, true (c) true, false (d) false, false
> **Ans: (a) true, true** — `$v` is set (not NULL) so isset() is true, and "" is treated as empty so empty() is true (verified with PHP 8.4).

**330.** The main configuration file of PHP, and the function that displays the current PHP configuration, are  
(a) httpd.conf and phpconfig() (b) php.ini and phpinfo() (c) config.php and info() (d) php.conf and showconfig()
> **Ans: (b) php.ini and phpinfo()** — stacks like XAMPP (cross-platform), WAMP (Windows) and LAMP (Linux) bundle Apache, MySQL/MariaDB and PHP.

## B6. Artificial Intelligence

**331.** The Turing Test, proposed by Alan Turing in 1950, judges whether a machine  
(a) can solve NP-complete problems (b) has more memory than a human (c) can exhibit conversational behaviour indistinguishable from a human's to an interrogator (d) can play chess
> **Ans: (c) behaviour indistinguishable from a human's** — the "imitation game" via text-only conversation.

**332.** An agent that selects actions only on the basis of the current percept, ignoring percept history, is a  
(a) simple reflex agent (b) goal-based agent (c) utility-based agent (d) learning agent
> **Ans: (a) simple reflex agent** — uses condition–action rules; model-based reflex agents keep internal state.

**333.** In an expert system, the component that applies rules to the facts to derive conclusions is the  
(a) knowledge base (b) user interface (c) inference engine (d) explanation facility
> **Ans: (c) inference engine** — the knowledge base stores domain facts and rules; the inference engine reasons over them (forward/backward chaining).

**334.** Which knowledge-representation scheme represents knowledge as a graph of nodes (concepts) joined by labelled arcs such as IS-A and HAS-A?  
(a) Frames (b) Semantic networks (c) Production rules (d) Scripts
> **Ans: (b) Semantic networks** — supports inheritance along IS-A links.

**335.** A knowledge-representation structure with slots and fillers describing a stereotyped object (Minsky) is a  
(a) frame (b) script (c) production rule (d) predicate
> **Ans: (a) frame** — scripts (Schank) are similar but describe stereotyped sequences of events (e.g. a restaurant visit).

**336.** Knowledge represented as IF condition THEN action is called  
(a) a semantic net (b) an ontology (c) a script (d) production rules
> **Ans: (d) production rules** — used in rule-based expert systems; the most common way to represent knowledge in a knowledge base.

**337.** Which statement is TRUE about first-order (predicate) logic compared with propositional logic?  
(a) FOL cannot express relations (b) FOL adds objects, predicates, functions and quantifiers (∀, ∃) (c) Propositional logic has quantifiers (d) They are equally expressive
> **Ans: (b) FOL adds objects, predicates, functions and quantifiers** — e.g. ∀x Man(x) → Mortal(x) cannot be written as a single propositional sentence.

**338.** Reasoning that starts from a goal and works backwards to find facts that support it is  
(a) forward chaining (b) breadth-first search (c) backward chaining (d) resolution refutation
> **Ans: (c) backward chaining** — goal-driven (used by PROLOG and MYCIN); forward chaining is data-driven.

**339.** Resolution in logic proves a statement by  
(a) adding its negation to the knowledge base (in CNF) and deriving the empty clause (contradiction) (b) enumerating all truth tables (c) forward chaining only (d) using heuristics only
> **Ans: (a) refutation — add the negated goal and derive the empty clause** — clauses must first be converted to CNF.

**340.** Learning a general rule or concept from specific examples is called  
(a) deductive learning (b) rote learning (c) explanation-based learning (d) inductive learning
> **Ans: (d) inductive learning** — e.g. learning a decision tree from labelled training examples.

**341.** ID3 chooses the attribute to split on at each node of a decision tree using  
(a) the alphabetical order of attributes (b) the highest information gain (c) the lowest number of values (d) random selection
> **Ans: (b) the highest information gain** — Gain(S, A) = Entropy(S) − Σ (|Sᵥ|/|S|)·Entropy(Sᵥ). (C4.5 uses gain ratio; CART uses Gini.)

**342.** A training set has 9 positive and 5 negative examples. Its entropy is approximately  
(a) 0.940 (b) 1.000 (c) 0.643 (d) 0.500
> **Ans: (a) 0.940** — −(9/14)log₂(9/14) − (5/14)log₂(5/14) = 0.410 + 0.530 ≈ 0.940 (verified in Python).

**343.** A set S (9+, 5−) is split on attribute Outlook into Sunny (2+, 3−), Overcast (4+, 0−) and Rain (3+, 2−). The information gain of Outlook is approximately  
(a) 0.940 (b) 0.694 (c) 0.246 (d) 0.048
> **Ans: (c) 0.246** — E(Sunny) = E(Rain) = 0.971, E(Overcast) = 0; weighted = (5/14)(0.971)+(4/14)(0)+(5/14)(0.971) = 0.694; Gain = 0.940 − 0.694 ≈ 0.246.

**344.** Ockham's razor, as used in learning decision trees, prefers  
(a) the deepest tree (b) the tree with the most attributes (c) a tree that memorises every example (d) the simplest hypothesis consistent with the data
> **Ans: (d) the simplest hypothesis consistent with the data** — smaller trees generalise better and overfit less.

**345.** The four inputs to Explanation-Based Learning (EBL) are  
(a) goal concept, training example, domain theory and operationality criterion (b) training set, test set, validation set, loss (c) states, actions, rewards, policy (d) features, labels, weights, bias
> **Ans: (a) goal concept, training example, domain theory, operationality criterion** — EBL can generalise from a single example using its domain theory.

**346.** The chief advantage of Explanation-Based Learning over purely inductive learning is that it  
(a) needs no prior knowledge at all (b) can learn from very few (even one) examples because it uses domain knowledge (c) is always more accurate (d) works without any examples
> **Ans: (b) learns from very few examples by using domain knowledge** — its weakness is the need for a complete, correct domain theory.

**347.** In pattern recognition, describing an object by its parts and the spatial relationships among them (e.g. "a roof above a square") is a  
(a) structural (symbolic) description (b) numeric feature vector (c) template (d) histogram
> **Ans: (a) structural (symbolic) description** — statistical approaches instead use numeric feature vectors.

**348.** Matching an input pattern against stored prototype patterns and choosing the best match is called  
(a) feature extraction (b) clustering (c) template matching (d) segmentation
> **Ans: (c) template matching** — feature extraction reduces raw data to discriminating measurements before classification.

**349.** The smallest unit of sound that distinguishes one word from another, used as a basic unit in speech recognition, is the  
(a) syllable (b) phoneme (c) morpheme (d) frame
> **Ans: (b) phoneme** — e.g. /p/ vs /b/ in "pat"/"bat"; acoustic features such as MFCCs are extracted per frame, and HMMs model phoneme sequences.

**350.** LISP was developed by  
(a) Alain Colmerauer in 1972 (b) Dennis Ritchie in 1972 (c) Niklaus Wirth in 1970 (d) John McCarthy in 1958
> **Ans: (d) John McCarthy in 1958** — LISP = LISt Processing; programs and data are both S-expressions written in prefix notation.

**351.** What is the value of the LISP expression `(car '(a b c))`?  
(a) A (b) (B C) (c) C (d) (A)
> **Ans: (a) A** — car returns the first element of a list.

**352.** What is the value of the LISP expression `(cdr '(a b c))`?  
(a) A (b) (A B) (c) (B C) (d) C
> **Ans: (c) (B C)** — cdr returns the list without its first element.

**353.** What does the LISP expression `(+ 2 (* 3 4))` evaluate to?  
(a) 20 (b) 14 (c) 24 (d) 9
> **Ans: (b) 14** — prefix notation: inner (* 3 4) = 12, then (+ 2 12) = 14.

**354.** What does `(car (cdr '(a b c)))` return in LISP?  
(a) A (b) C (c) (B C) (d) B
> **Ans: (d) B** — (cdr '(a b c)) = (B C); car of that = B (this is `cadr`).

**355.** PROLOG was created by Alain Colmerauer in 1972. In a PROLOG rule, the symbol `:-` is read as  
(a) "and" (b) "if" (c) "or" (d) "not"
> **Ans: (b) "if"** — `head :- body.` means head is true if body is true; `,` means AND and `;` means OR.

**356.** Given the PROLOG program below, what is the answer to the query `?- grandparent(tom, W).`?  
```prolog
parent(tom, bob).
parent(bob, ann).
grandparent(X, Z) :- parent(X, Y), parent(Y, Z).
```
(a) W = bob (b) W = tom (c) W = ann (d) false
> **Ans: (c) W = ann** — unification: X = tom; parent(tom, Y) gives Y = bob; parent(bob, Z) gives Z = ann.

**357.** In PROLOG, the cut operator `!` is used to  
(a) prevent backtracking past the point where it appears (b) delete a fact (c) end the program (d) declare a variable
> **Ans: (a) prevent backtracking past that point** — it commits to the choices made so far in the clause.

**358.** Which search strategy uses f(n) = g(n) + h(n) and is optimal when h(n) is admissible?  
(a) Depth-first search (b) Greedy best-first search (c) Breadth-first search (d) A* search
> **Ans: (d) A* search** — an admissible heuristic never overestimates the true cost to the goal; greedy best-first uses only h(n).

**359.** Which uninformed search uses a FIFO queue and finds the shallowest goal first?  
(a) Breadth-first search (b) Depth-first search (c) Hill climbing (d) A*
> **Ans: (a) Breadth-first search** — DFS uses a LIFO stack and may go deep along one path.

**360.** Alpha–beta pruning applied to minimax  
(a) changes the final minimax decision (b) returns the same decision as minimax while pruning branches that cannot affect it (c) works only for one-player games (d) requires an admissible heuristic
> **Ans: (b) same decision as minimax, fewer nodes examined** — with perfect move ordering it examines about O(b^(d/2)) nodes.

## B7. Machine Learning

**361.** In Tom Mitchell's definition, "a program learns from experience E with respect to task T and performance measure P if its performance at T, as measured by P, improves with E." For a spam filter, E is  
(a) classifying e-mails as spam or not (b) the fraction of e-mails correctly classified (c) the e-mail server (d) watching the user label e-mails as spam or not spam
> **Ans: (d) watching the user label e-mails** — T = classifying e-mails, P = fraction correctly classified, E = labelled examples.

**362.** Learning from input–output pairs where the correct label is supplied for every training example is  
(a) supervised learning (b) unsupervised learning (c) reinforcement learning (d) clustering
> **Ans: (a) supervised learning** — unsupervised finds structure in unlabelled data; reinforcement learns from rewards/penalties.

**363.** Predicting tomorrow's maximum temperature in °C is an example of  
(a) classification (b) clustering (c) regression (d) association-rule mining
> **Ans: (c) regression** — the output is a continuous value; classification predicts a discrete class label.

**364.** Which statement best describes symbol-level learning as opposed to knowledge-level learning?  
(a) It adds genuinely new knowledge that changes what the system can conclude (b) It improves efficiency (e.g. speed-up, caching, chunking) without changing the deductive closure of what is known (c) It needs no knowledge base (d) It is the same as reinforcement learning
> **Ans: (b) improves efficiency without changing what is known** — knowledge-level learning (e.g. induction, being told new facts) changes the knowledge itself; EBL is the classic symbol-level example.

**365.** k-Nearest Neighbours (k-NN) is called a lazy / instance-based learner because  
(a) it trains a deep model slowly (b) it builds a decision tree (c) it stores the training data and defers all computation until a query must be classified (d) it uses only one neighbour
> **Ans: (c) it stores the training data and defers computation to query time** — there is no explicit training phase.

**366.** Training points: Class X at (1,1), (2,2), (3,1); Class Y at (4,3), (5,5). Using Euclidean distance and k = 3, the query point (3,2) is classified as  
(a) X (b) Y (c) a tie that cannot be broken (d) both X and Y
> **Ans: (a) X** — distances: (2,2) = 1, (3,1) = 1, (4,3) = √2 ≈ 1.41, (1,1) = √5 ≈ 2.24, (5,5) = √13 ≈ 3.61. The 3 nearest are X, X, Y → majority X.

**367.** In k-NN, an odd value of k is usually chosen for binary classification in order to  
(a) reduce memory use (b) avoid ties in the majority vote (c) make the algorithm eager (d) remove the need for normalisation
> **Ans: (b) avoid ties in the majority vote** — small k → noisy/overfitting; very large k → over-smoothing/underfitting.

**368.** Why are features normally scaled (normalised) before applying k-NN?  
(a) To make the data categorical (b) To increase the number of features (c) So that features with large numeric ranges do not dominate the distance computation (d) Because k-NN needs a probability output
> **Ans: (c) so large-range features do not dominate distances** — e.g. min–max scaling or z-score standardisation.

**369.** The Euclidean distance and Manhattan distance between points (1, 2) and (4, 6) are respectively  
(a) 7 and 5 (b) 5 and 5 (c) 25 and 7 (d) 5 and 7
> **Ans: (d) 5 and 7** — Euclidean = √(3² + 4²) = √25 = 5; Manhattan = |3| + |4| = 7.

**370.** The objective that K-means clustering tries to minimise is  
(a) the within-cluster sum of squared distances of points from their cluster centroid (b) the number of clusters (c) the distance between cluster centroids (d) the classification error
> **Ans: (a) within-cluster sum of squared errors (SSE / inertia)** — it alternates assigning points to the nearest centroid and recomputing centroids as means.

**371.** 1-D data {1, 2, 3, 8, 9, 10}, K = 2, initial centroids c₁ = 2 and c₂ = 3. After one assignment-and-update step the new centroids are  
(a) 2 and 9 (b) 1.5 and 7.5 (c) 2 and 3 (d) 1 and 10
> **Ans: (b) 1.5 and 7.5** — assign to nearer centroid: {1, 2} → c₁, {3, 8, 9, 10} → c₂; means = 3/2 = 1.5 and 30/4 = 7.5. (Further iterations converge to 2 and 9.)

**372.** The elbow method is used in K-means to  
(a) choose initial centroids (b) normalise features (c) choose a suitable number of clusters K by plotting SSE against K (d) measure classification accuracy
> **Ans: (c) choose K from the SSE-vs-K plot** — pick K where the decrease in SSE sharply flattens ("elbow").

**373.** Kernel K-means is preferred over standard K-means when  
(a) clusters are not linearly separable (e.g. concentric rings), because it implicitly maps data to a higher-dimensional feature space via a kernel such as RBF (b) the data are already spherical clusters (c) K is unknown (d) the data are labelled
> **Ans: (a) clusters are non-linearly separable** — the kernel trick computes inner products in feature space without explicit mapping, giving non-linear cluster boundaries.

**374.** Bagging (bootstrap aggregating) mainly  
(a) reduces bias by training models sequentially on misclassified points (b) reduces variance by training models in parallel on bootstrap samples and averaging/voting (c) increases variance (d) uses a single decision stump
> **Ans: (b) reduces variance via parallel models on bootstrap samples** — predictions combined by voting (classification) or averaging (regression).

**375.** Boosting algorithms such as AdaBoost  
(a) train learners independently in parallel (b) use only unlabelled data (c) select a random subset of features at every split (d) train weak learners sequentially, increasing the weights of misclassified examples, mainly reducing bias
> **Ans: (d) sequential weak learners with re-weighting of misclassified examples** — final prediction is a weighted vote; gradient boosting fits each new learner to the residual errors.

**376.** A Random Forest is best described as  
(a) a single deep decision tree (b) boosting with stumps (c) bagging of decision trees plus a random subset of features considered at each split (d) K-means applied to trees
> **Ans: (c) bagging + random feature subsets per split** — this de-correlates the trees; out-of-bag (OOB) samples (~37% left out of each bootstrap) give a built-in error estimate.

**377.** A model that performs very well on training data but poorly on unseen test data is said to be  
(a) overfitting (high variance) (b) underfitting (high bias) (c) well generalised (d) regularised
> **Ans: (a) overfitting (high variance)** — underfitting performs poorly on both training and test data.

**378.** In k-fold cross-validation, the data is divided into k parts and  
(a) the model is trained once on all data (b) each part is used once as the validation set while the other k − 1 parts train the model, and the k scores are averaged (c) only the first part is ever used for testing (d) k different algorithms are compared
> **Ans: (b) each fold serves once as validation; scores averaged** — gives a less variable estimate of generalisation performance.

**379.** A classifier gives TP = 40, FP = 10, FN = 20, TN = 30. Its precision and recall are  
(a) 0.67 and 0.80 (b) 0.80 and 0.80 (c) 0.70 and 0.67 (d) 0.80 and 0.67
> **Ans: (d) 0.80 and 0.67** — Precision = TP/(TP+FP) = 40/50 = 0.80; Recall = TP/(TP+FN) = 40/60 ≈ 0.67.

**380.** For the same classifier (TP = 40, FP = 10, FN = 20, TN = 30), the F1-score is approximately  
(a) 0.70 (b) 0.73 (c) 0.75 (d) 0.80
> **Ans: (b) 0.73** — F1 = 2PR/(P+R) = 2(0.8)(0.667)/(1.467) ≈ 0.727; (accuracy = (40+30)/100 = 0.70).
