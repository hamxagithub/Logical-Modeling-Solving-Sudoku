# Logical-Modeling-Solving-Sudoku
 
# 🧠 Sudoku Solver using Propositional and First-Order Logic

## 📌 Introduction

This project explores the power of **Propositional Logic** and **First-Order Logic (FOL)** in solving the classic **Sudoku puzzle** — a 9×9 combinatorial number-placement game.

In Sudoku:
> Every row, column, and each 3×3 subgrid must contain all digits from **1 to 9**, **exactly once**.

This puzzle, while recreational on the surface, serves as a great **constraint satisfaction problem** (CSP) and is ideal for demonstrating how formal logic can be used to encode and solve complex problems through inference, entailment, and resolution.

---

## 🎯 Problem Statement

You are tasked to:

- Encode a 9×9 Sudoku puzzle using **both**:
  - 🧩 **Propositional Logic**
  - 🧩 **First-Order Logic (FOL)**
- Use logical entailment and satisfiability techniques to **solve the puzzle consistently**.
- Demonstrate solutions on **two different Sudoku problems** using both reasoning paradigms.

Your implementation must reflect concepts covered in your AI and logic courses, focusing on knowledge representation and reasoning.

---

## 🔢 Propositional Logic Formulation

Let `X_{r,c,n}` be a propositional variable which is **true** iff the cell at row `r` and column `c` contains the number `n`.

Where:

- `r` = row (1 to 9)  
- `c` = column (1 to 9)  
- `n` = number (1 to 9)

### ✅ Constraints

1. **Each cell contains at least one number**  
   - ∨ X_{r,c,n} for n = 1 to 9

2. **Each cell contains at most one number**  
   - For all n ≠ m: ¬(X_{r,c,n} ∧ X_{r,c,m})

3. **Each number appears exactly once in each row**  
   - For each row r and number n: ∃! c such that X_{r,c,n}

4. **Each number appears exactly once in each column**  
   - For each column c and number n: ∃! r such that X_{r,c,n}

5. **Each number appears exactly once in each 3×3 subgrid**  
   - Enforce the same constraint within each 3×3 block

---

## 🔍 First-Order Logic (FOL) Formulation

Define a predicate:  
> **Filled(r, c, n)** – True if cell at (r, c) contains number `n`.

### ✅ Constraints

1. **Each cell contains exactly one number**  
   - ∃n Filled(r, c, n) ∧ ∀m ≠ n ¬Filled(r, c, m)

2. **Each number appears exactly once in each row**  
   - ∀r ∀n ∃!c Filled(r, c, n)

3. **Each number appears exactly once in each column**  
   - ∀c ∀n ∃!r Filled(r, c, n)

4. **Each number appears once in each 3×3 box**  
   - Apply uniqueness constraints for each subgrid

---

## 🧠 Reasoning & Solving Strategy

Sudoku rules are encoded using either propositional variables or first-order predicates. These rules are converted into a form suitable for logical reasoning:

- **Propositional Logic Approach**:
  - Convert all rules into **CNF (Conjunctive Normal Form)**
  - Use **SAT solvers** and **resolution** to derive a valid assignment

- **First-Order Logic Approach**:
  - Use **logical inference** and **entailment**
  - Optionally convert FOL to propositional logic using grounding

This approach demonstrates how AI techniques can **solve real-world problems** with high constraints.

---


## 🧪 Test Cases

✅ **Puzzle 1 (Easy)**  
✅ **Puzzle 2 (Medium)**  

Both puzzles must be solved using:
- [x] Propositional Logic
- [x] First-Order Logic

---

## 📤 Deliverables

- ✔️ Two working Sudoku solvers (one using each logic paradigm)
- ✔️ Two solved Sudoku puzzles as output
- ✔️ Commented code demonstrating logic encoding
- ✔️ This decorated `README.md`



 #OUTPUT
 ![image](https://github.com/user-attachments/assets/d82f2e90-cd5f-42f4-b9e0-db37bd551c77)
 ![image](https://github.com/user-attachments/assets/0da723ba-9904-404b-a3cd-55b94e0b57ab)


