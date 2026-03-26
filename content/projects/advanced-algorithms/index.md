---
title: "Advanced Algorithms & Data Structures"
date: 2025-11-01
summary: "Implementation and experimental benchmarking of sorting algorithms, hash tables, Bloom filters, string matching automata, and dynamic programming in Python — with empirical complexity verification."
tags:
  - Python
  - Algorithms
  - Data Structures
  - Performance Analysis
tech_stack:
  - Python
  - Matplotlib
  - NumPy
links:
  - type: github
    url: https://github.com/ad25aderram/algorithme-avance
    label: Code
featured: false
status: "Completed"
role: "Solo Developer"
duration: "2 months"
team_size: 1
highlights:
  - "7 sorting algorithms benchmarked across 4 data distributions"
  - "Hash tables benchmarked on datasets up to 100,000 elements"
  - "Bloom filter false positive rate analysis for k = 2, 3, 4"
  - "Empirical Big-O verification via normalised runtime plots"
---

A series of algorithm implementations focused on understanding performance trade-offs through experimental analysis. Rather than relying on theoretical Big-O alone, every implementation is benchmarked and visualised against real data.

## Sorting & search complexity

Seven sorting algorithms benchmarked across four data distributions — random, ascending, descending, and identical values:

| Algorithm | Complexity | Best case |
|---|---|---|
| Quick sort (dual-pivot) | O(n log n) avg | Random data |
| Merge sort | O(n log n) | Consistent |
| Heap sort | O(n log n) | Consistent |
| Insertion sort | O(n²) | Nearly-sorted data |
| Selection sort | O(n²) | — |
| Bubble sort | O(n²) | — |
| Binary search | O(log n) | — |

Runtime was normalised against T(n)/n, T(n)/(n log n), and T(n)/n² to empirically verify complexity classes. Key finding: insertion sort consistently outperforms O(n log n) algorithms on nearly-sorted data — a result that only becomes intuitive when you see it in a plot.

## Hash tables

- Chaining with linked lists for collision handling
- Open addressing: linear probing, quadratic probing, double hashing
- Benchmarked on datasets up to 100,000 elements — collision rates and lookup times compared across all strategies

## Probabilistic filters

- **Bloom filter** with k = 2, 3, 4 hash functions — false positive rate vs. memory trade-off
- **Count-Min Sketch** for frequency estimation — precision vs. hash function count

## String pattern matching

- Naïve search vs. **deterministic finite automaton (DFA)** — transition function computation and pattern recognition on randomly generated text
- Performance comparison shows DFA's advantage grows with text length

## Dynamic programming

- Fibonacci: naïve recursion vs. memoisation — exponential-to-linear improvement demonstrated empirically
- Coin change: minimum coin count with full optimal solution reconstruction

## Tech stack

- **Language**: Python
- **Libraries**: Matplotlib, NumPy
- **Focus**: Algorithm design, complexity analysis, experimental benchmarking
