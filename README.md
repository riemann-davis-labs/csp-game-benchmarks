# CSP Game Benchmarks
Benchmarks to compare CSP solvers on classic Sudoku puzzles.

## Background

### NP-Hard Problems
NP-hard problems are computationally challenging problems where no known polynomial-time algorithm exists to solve them optimally. As problem size grows, solving time can increase exponentially in the worst case. Examples include the traveling salesman problem, job scheduling, and constraint satisfaction problems like Sudoku.

### Constraint Satisfaction Problems (CSPs)
CSPs are mathematical problems defined by:
- **Variables:** elements that need values assigned
- **Domains:** possible values for each variable
- **Constraints:** rules that restrict which value combinations are valid

The goal is to find assignments that satisfy all constraints simultaneously.

### Real-World Importance
Beyond games, CSP techniques solve critical business problems:
- **Scheduling:** employee shifts, manufacturing, project timelines
- **Resource allocation:** hospital bed assignment, classroom scheduling
- **Supply chain optimization:** warehouse placement, delivery routing  
- **Configuration:** product customization, network design
- **Planning:** airline crew scheduling, university course timetabling

These benchmarks help evaluate solver performance for such applications.

## Why these are CSPs
Each Sudoku instance is a **constraint satisfaction problem (CSP)**:
- **Variables:** 81 cells.
- **Domains:** values 1–9 for each cell.
- **Constraints:** all-different in every row, column, and 3×3 box.
- **Goal:** assign values to all variables while satisfying all constraints.

## Methods shown in the benchmark
- **Davis GPU / Davis GPU v2:** custom GPU-accelerated backtracking variants with heuristic ordering and pruning; v2 is an optimized revision.
- **Davis CPU:** CPU version of the same backtracking/heuristic approach.
- **DLX:** Knuth’s Algorithm X with Dancing Links (exact cover formulation).
- **DFS:** plain depth-first backtracking without advanced propagation.
- **CP:** constraint programming with domain propagation and search.

## Puzzle set (all are 9×9 Sudoku)
These are well-known “hardest” or minimal-clue instances used as benchmarks.

### AI Escargot (Inkala 2006)
**Game:** Classic Sudoku with very sparse clues and tricky dependencies.  
**Complexity:** Very high (hardest-known instance family).

### Inkala 2010
**Game:** Arto Inkala’s 2010 hardest Sudoku.  
**Complexity:** High to very high.

### Golden Nugget
**Game:** Notorious sparse Sudoku with deep inference chains.  
**Complexity:** High.

### Platinum Blonde
**Game:** Sparse, symmetry-heavy Sudoku with few direct deductions.  
**Complexity:** High.

### Tarek971
**Game:** Community benchmark puzzle with limited clues.  
**Complexity:** High.

### 17-clue Colin
**Game:** Minimal-clue Sudoku (17 is the proven minimum for 9×9).  
**Complexity:** Very high due to weak propagation.

### Escargot variant
**Game:** Modified AI Escargot instance with similar structure.  
**Complexity:** Very high.

### Norvig hard1
**Game:** Benchmark puzzle popularized by Peter Norvig.  
**Complexity:** High.

### Inkala (Norvig hardest)
**Game:** Inkala’s puzzle featured as “hardest” in Norvig’s set.  
**Complexity:** Very high.

### champagne 2010
**Game:** 2010 “Champagne” hardest list Sudoku.  
**Complexity:** High.

## Complexity note
Sudoku decision is NP-complete in general. These instances are 9×9, but the benchmark highlights solver behavior on hard, low-clue CSPs where worst-case search is exponential.
