---
layout: home
parent: Programming
title: P vs NP
---

# P vs NP

![image](https://github.com/ftuyama/cracking-the-tech-interview/assets/11530478/72be97ee-9572-40ca-a144-4bcb7934006f)

- P represents problems solvable efficiently
- NP represents problems with efficiently verifiable solutions
- NP-complete represents the hardest problems in NP
- NP-hard represents problems at least as hard as the hardest problems in NP, possibly including problems that are not in NP.

## P (Polynomial)

- Problems in P are those for which there exists an efficient (polynomial-time) algorithm that can solve the problem in a reasonable amount of time.

Examples:

- Sorting a list of numbers
- Finding the shortest path in a weighted graph

## NP (Non-deterministic Polynomial)

- Problems in NP are those for which a candidate solution can be verified in polynomial time.
- It is unknown whether all problems in NP can be solved in polynomial time (P = NP is one of the most important and unresolved questions in computer science).
NP-complete (NP-Complete):

## NP-complete 

- NP-complete problems are a special subset of problems in NP that are somehow as hard as the hardest problems in NP.
- If an NP-complete problem can be solved in polynomial time, then all problems in NP can be solved in polynomial time, implying P = NP.

Examples:

- The Hamiltonian circuit problem
- The traveling salesman problem are examples of NP-complete problems

## NP-hard:

- NP-hard problems are those that are at least as hard as problems in NP but may not necessarily be in NP.
- This means they may not have verifiable solutions in polynomial time.
