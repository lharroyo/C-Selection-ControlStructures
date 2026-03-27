# Selection and Control Structures in C

**Course:** Introduction to Programming  
**Language:** C (ISO C99)  
**Topic:** Decision-Making and Iteration Constructs  

---

## Overview

This repository contains a curated set of illustrative examples designed to introduce students to the fundamental **selection** and **control flow** structures of the C programming language. Each example has been carefully written to be minimal, readable, and pedagogically sound, with inline commentary to facilitate comprehension.

Mastery of these constructs is essential, as they constitute the building blocks of virtually every non-trivial program. Students are strongly encouraged to study each example in order, compile and execute it locally, and modify the source code to observe how behavioral changes manifest at runtime.

---

## Prerequisites

Before working with this material, the student is expected to have:

- A working installation of a C compiler (e.g., **GCC** via MinGW on Windows, or native GCC/Clang on Linux/macOS).
- Basic familiarity with the C compilation process (`gcc`, terminal usage).
- An understanding of variables, data types, and standard I/O (`printf`, `scanf`).

---

## Repository Structure

```
C-Selection-ControlStructures/
│
├── Examples/
│   ├── seleccion_if.c            # Simple if statement
│   ├── seleccion_if_else.c       # if-else and else-if chains
│   ├── seleccion_switch.c        # switch-case statement
│   ├── control_for.c             # for loop
│   ├── control_while.c           # while loop
│   └── control_do_while.c        # do-while loop
│
├── .gitignore
├── LICENSE
└── README.md
```

---

## Compilation and Execution

To compile any of the provided examples, navigate to the `Examples/` directory and use the following command:

```bash
gcc -std=c99 -Wall -o <output_name> <source_file>.c
```

**Example:**

```bash
gcc -std=c99 -Wall -o seleccion_if seleccion_if.c
./seleccion_if
```

> **Note for Windows users:** If using MinGW, replace `./seleccion_if` with `seleccion_if.exe`.

---

## Contents and Learning Objectives

### Part I — Selection Structures

Selection structures allow a program to make decisions based on the evaluation of one or more Boolean conditions. The execution path diverges depending on whether a condition holds true or false.

---

#### 1. `seleccion_if.c` — The Simple `if` Statement

**Concept:** The most elementary form of conditional execution. A block of code is executed **only if** a specified condition evaluates to true (`1`). If the condition is false (`0`), the block is skipped entirely.

**Syntax:**
```c
if (condition) {
    // Executed only when condition is true
}
```

**Example in this file:** Determines whether an integer entered by the user is even or odd using the modulo operator (`%`).

---

#### 2. `seleccion_if_else.c` — The `if-else` and `else if` Chain

**Concept:** Extends the simple `if` by providing an alternative execution path (`else`) when the condition is false. Multiple mutually exclusive conditions can be chained using `else if`.

**Syntax:**
```c
if (condition_1) {
    // Executed when condition_1 is true
} else if (condition_2) {
    // Executed when condition_2 is true
} else {
    // Executed when all previous conditions are false
}
```

**Example in this file:** Compares a user-provided integer against the value `10`, printing whether it is greater than, less than, or equal to it.

---

#### 3. `seleccion_switch.c` — The `switch` Statement

**Concept:** A multi-branch selection structure used when a single variable must be compared against several discrete constant values. It is generally preferred over long `else if` chains when dealing with enumerable cases, as it improves readability.

> **Important:** Each `case` block must end with a `break` statement to prevent **fall-through**, which causes execution to continue into subsequent cases unintentionally.

**Syntax:**
```c
switch (expression) {
    case constant_1:
        // ...
        break;
    case constant_2:
        // ...
        break;
    default:
        // Executed when no case matches
}
```

**Example in this file:** Maps an integer (1–7) to its corresponding day of the week, with a `default` case to handle invalid input.

---

### Part II — Control Structures (Iteration / Loops)

Iteration structures allow a block of code to be executed repeatedly, either a fixed number of times or as long as a given condition remains true. Choosing the appropriate loop construct is a matter of both clarity and correctness.

---

#### 4. `control_for.c` — The `for` Loop

**Concept:** The `for` loop is the preferred construct when the **number of iterations is known in advance**. It consolidates initialization, condition evaluation, and increment/decrement into a single, compact header.

**Syntax:**
```c
for (initialization; condition; update) {
    // Loop body
}
```

**Example in this file:** Prints the integers from `1` to `5` using a counter variable `i`.

---

#### 5. `control_while.c` — The `while` Loop

**Concept:** The `while` loop evaluates its condition **before** each iteration. If the condition is false from the outset, the loop body is never executed. It is best suited for scenarios where the number of iterations depends on a runtime condition rather than a fixed count.

**Syntax:**
```c
while (condition) {
    // Loop body
}
```

**Example in this file:** Prints the integers from `1` to `5`, incrementing the counter manually within the loop body.

---

#### 6. `control_do_while.c` — The `do-while` Loop

**Concept:** The `do-while` loop evaluates its condition **after** each iteration, guaranteeing that the loop body executes **at least once**, regardless of whether the condition is initially true or false. This makes it particularly suitable for input validation routines.

**Syntax:**
```c
do {
    // Loop body
} while (condition);
```

**Example in this file:** Prints the integers from `1` to `5`, with condition verification deferred until after the first execution of the body.

---

## Key Differences at a Glance

| Construct     | Condition Evaluated | Minimum Executions | Ideal Use Case                          |
|---------------|---------------------|--------------------|------------------------------------------|
| `if`          | Before execution    | 0                  | Single conditional block                 |
| `if-else`     | Before execution    | 0 or 1             | Binary or multi-branch decisions         |
| `switch`      | Before execution    | 0                  | Discrete multi-case comparisons          |
| `for`         | Before each iter.   | 0                  | Known iteration count                    |
| `while`       | Before each iter.   | 0                  | Unknown count, pre-check condition       |
| `do-while`    | After each iter.    | **1**              | At least one execution required          |

---

## Academic Integrity

All code in this repository is provided strictly for educational purposes. Students are expected to study these examples, understand the underlying logic, and write their own original implementations for any assigned work. Submitting any portion of this code as original work in an academic assessment without proper attribution constitutes a violation of academic integrity policies.

---

## License

This project is distributed under the terms of the [MIT License](LICENSE). You are free to use, copy, modify, and distribute this material, provided that appropriate credit is given to the original author.

---

*Repository maintained for academic use. Students with questions are encouraged to consult their course instructor or teaching assistant during scheduled office hours.*
