# collatz-entropy-funnel
# On the Asymptotic Decay of Collatz Trajectories and the Emergence of Parity-Driven Entropy

**Author:** Ayush Yadav  
**Email:** ayush.nyx@gmail.com  
**GitHub:** [@ayush-thecoder](https://github.com/ayush-thecoder)  
**License:** CC BY-NC-SA 4.0  
**Date:** 2025

---

## Abstract

This repository investigates the Collatz Conjecture through the lens of information theory, proposing the concept of **parity entropy** as a measure of the inherent structure within Collatz trajectories. We explore a novel phenomenon we call the **Entropy Funnel**, an observable decay of randomness as numbers converge toward 1 under the Collatz process. While the conjecture remains unproven, our approach provides a fresh lens through which its dynamics can be better understood, simulated, and visualized.

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Background](#2-background)
3. [Parity Entropy](#3-parity-entropy)
4. [The Entropy Funnel Hypothesis](#4-the-entropy-funnel-hypothesis)
5. [Mathematical Formulation](#5-mathematical-formulation)
6. [Computational Experiments](#6-computational-experiments)
7. [Implications and Further Research](#7-implications-and-further-research)
8. [Conclusion](#8-conclusion)
9. [License]

---

## 1. Introduction

The **Collatz Conjecture** (also called the 3n + 1 problem) is deceptively simple:

> Start with any positive integer *n*.  
> If *n* is even, divide it by 2.  
> If *n* is odd, multiply it by 3 and add 1.  
> Repeat the process.  
> The conjecture asserts that *every* starting number eventually reaches 1.

Despite its simplicity, this problem has resisted proof for decades. Our approach reframes the trajectory as a process of **entropy decay**, governed by the statistical behavior of parity (even vs. odd) transformations.

---

## 2. Background

The Collatz sequence is deterministic but unpredictable. Traditional number-theoretic tools haven’t yielded a general proof. Rather than trying to solve it directly, we ask:

> Can we *measure* something meaningful about how sequences behave on their way to 1?

We borrow tools from **information theory** — particularly the idea of entropy — to quantify the “randomness” in each sequence.

---

## 3. Parity Entropy

For a Collatz sequence S = [n_0, n_1, n_2, \dots, n_k], define:

- p_0: proportion of even steps  
- p_1 = 1 - p_0: proportion of odd steps

Then the **parity entropy** is:

\[
H(S) = -p_0 \log_2 p_0 - p_1 \log_2 p_1
\]

This entropy ranges from 0 (all even or all odd) to 1 (perfectly balanced). We observe that as numbers evolve under the Collatz map, entropy trends downward — *forming a funnel*.

---

## 4. The Entropy Funnel Hypothesis

**Hypothesis:**  
_All Collatz sequences exhibit a natural decrease in parity entropy, which acts as a funnel guiding trajectories toward deterministic convergence._

### Key Observations:
- Higher starting numbers have higher initial entropy.
- Entropy decays rapidly before flattening out.
- Most sequences trend toward a parity ratio of ~2:1 (even:odd).

We define the **Entropy Funnel** as the phase of the sequence during which entropy drops steeply before stabilizing.

---

## 5. Mathematical Formulation

Let n \in \mathbb{N}. Define the Collatz transformation:

\[
T(n) = \begin{cases}
\frac{n}{2} & \text{if } n \equiv 0 \mod 2 \\
3n + 1 & \text{if } n \equiv 1 \mod 2
\end{cases}
\]

Define the trajectory:

\[
S_n = \{ n, T(n), T^2(n), \dots, 1 \}
\]

Let E_n be the parity entropy of S_n. Define the entropy decay rate:

\[
\Delta E_n = \frac{E_n - E_{n+1}}{n}
\]

Numerically, we observe:

\[
\lim_{n \to \infty} \Delta E_n < 0
\]

This negative trend suggests a global funneling effect.

---

## 6. Computational Experiments

We simulate 1 \leq n \leq 10^6:

- Compute full Collatz sequences
- Count parity transitions
- Track entropy vs. number of steps

### Visualization ideas:
- Entropy vs. n (scatter plot)
- Histogram of parity ratios
- Funnel curve over sequence index

Code is in `/src/collatz_tools.py` and Jupyter notebooks under `/notebooks`.

---

## 7. Implications and Further Research

- **Structure within chaos**: Entropy decay suggests Collatz sequences aren’t random — they have hidden structure.
- **Entropy bounds**: Can we prove a minimum entropy threshold for all sequences?
- **Generalization**: What happens if we modify the function to 5n + 1, 7n + 1, etc.? Does the funnel still exist?
- **Symbolic entropy flow**: Use algebraic techniques to describe entropy as a symbolic function of n.

---

## 8. Conclusion

While not a proof, the entropy funnel gives us a powerful heuristic. By thinking in terms of information and compression, we reveal a subtle, statistical order beneath the surface chaos of the Collatz problem.

This project aims to provide tools and language to frame the problem in a new light — one that may eventually lead to breakthroughs or at least greater understanding.

---

## 9. License 
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License

You are free to:
- Share — copy and redistribute the material in any medium or format
- Adapt — remix, transform, and build upon the material

Under the following terms:
- Attribution — You must give appropriate credit, provide a link to the license, and indicate if changes were made.
- NonCommercial — You may not use the material for commercial purposes.
- ShareAlike — If you remix, transform, or build upon the material, you must distribute your contributions under the same license.

Full license: https://creativecommons.org/licenses/by-nc-sa/4.0/
