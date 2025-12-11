# CS321-Project
SAT Solver 
# Boolean SAT Solver in Python

This project implements a **Boolean Satisfiability (SAT) Solver** in Python that evaluates whether a given propositional logic formula in **CNF (Conjunctive Normal Form)** is satisfiable. The solver also finds **all possible satisfying assignments** for the variables.

---

## Features

- Works on any CNF formula represented as **clauses**.
- Evaluates all possible variable combinations to determine satisfiability.
- Prints **all satisfying assignments**, not just the first one.
- Reports `UNSATISFIABLE` if no combination satisfies the formula.
- Fully implemented in Python with **no external libraries**.

---

## Formula Representation

- Each **variable**: `x1, x2, ..., xn`  
- Each **literal**: positive integer = variable, negative integer = negation (e.g., `-1 = ¬x1`)  
- **Clause**: OR of literals, e.g., `[1, -2, 3] = x1 ∨ ¬x2 ∨ x3`  
- **Formula**: AND of clauses, e.g., `[[1, -2, 3], [-1, 3, 2], [2, -3]]`  
  This represents:
(x1 ∨ ¬x2 ∨ x3) ∧ (¬x1 ∨ x3 ∨ x2) ∧ (x2 ∨ ¬x3)


---

## Code Structure

### **Cell 1 — Define the formula and evaluation functions**
- `eval_clause(clause, assignment)` → evaluates a single clause.
- `eval_formula(clauses, assignment)` → evaluates the full formula.

### **Cell 2 — Find all SAT assignments**
- Generates all possible combinations of True/False assignments for the variables.
- Collects all assignments that satisfy all clauses.

### **Cell 3 — Display results**
- Prints all SAT assignments.
- Prints `UNSATISFIABLE` if no assignment satisfies the formula.

---

## Usage Example

```python
# Define variables and clauses
variables = 3
clauses = [
  [1, -2, 3],
  [-1, 3, 2],
  [2, -3]
]

# Run the SAT solver
# Cell 2 computes all satisfying assignments
# Cell 3 displays the results

Expected Output:
SATISFIABLE
All satisfying assignments:
x1=True, x2=True, x3=False
x1=True, x2=True, x3=True
x1=True, x2=False, x3=True
x1=False, x2=True, x3=True

Notes

This is a brute-force SAT solver, suitable for small formulas.

The execution time grows exponentially with the number of variables.

The project demonstrates practical understanding of propositional logic and SAT solving.

Requirements

Python 3.x
No additional packages required
