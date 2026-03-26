# Assignment 2 — Genetic Algorithm: Knapsack Problem
## Observation Report

**Student Name  :** D.Navya sri 
**Student ID    :** 2310040049
**Date Submitted:** 21/03/2026  

---

## How to Submit

1. Run each experiment following the instructions below
2. Fill in every answer box — do not leave placeholders
3. Make sure the `plots/` folder contains all required images
4. Commit this README and the `plots/` folder to your GitHub repo

---

## Before You Begin — Read the Code

Open `ga_knapsack.py` and read through it. Then answer these questions.

**Q1. What does the `fitness()` function return? Why does an overweight solution score 0?**

```
The fitness() function calculates the total value of the selected items in the knapsack. 
If the total weight exceeds the maximum capacity of the knapsack, the solution is considered invalid and the fitness value becomes 0. 
This penalty prevents overweight solutions from being selected in the next generation.
```

**Q2. What does `tournament_select()` do? Why are higher-fitness individuals more likely to be chosen?**

```
The tournament_select() function randomly chooses a small group of individuals from the population and selects the one with the highest fitness. 
Since the individual with the best fitness wins the tournament, stronger solutions have a higher chance of being selected. 
This helps the genetic algorithm gradually improve the population over generations.
```

**Q3. Look at the `run_ga()` loop. Find this line:**
```python
next_gen = [best_chromosome[:]]
```
**What is this doing? Why is it important to always keep the best solution?**

```
This line copies the best chromosome from the current generation into the next generation. 
This technique is called elitism and ensures that the best solution found so far is not lost during crossover or mutation. 
Keeping the best solution helps maintain steady improvement in the genetic algorithm.
```

---

# Genetic Algorithm - Knapsack Problem

## Experiment 1

**Instructions:** Run the program without changing anything.

python ga_knapsack.py

**Fill in this table:**

| Metric                             | Your result |
| ---------------------------------- | ----------- |
| Number of generations              | 50          |
| Best value at generation 1         | 60          |
| Final best value                   | 77          |
| Total weight of best solution (kg) | 14.4 kg     |
| Is solution valid (Yes / No)       | Yes         |

**Copy the printed packing list here:**

Water bottle
First aid kit
Sleeping bag
Torch
Energy bars (x6)
Rain jacket
Map & compass
Cooking stove
Rope (10 m)
Sunscreen
Power bank

**Plot Observation:**

Observation: The graph shows a rapid increase in the fitness value during the first few generations, indicating that the genetic algorithm quickly finds better solutions. The biggest improvement happens in the early generations. After several generations, the curve flattens, showing convergence to a near optimal solution.

---

## Experiment 2

**Results table:**

| mutation_rate | Final best value | Weight (kg) | Valid? | Shape of curve                              |
| ------------- | ---------------- | ----------- | ------ | ------------------------------------------- |
| 0.01          | 75               | 14.9        | Yes    | Slow improvement, converges early           |
| 0.05          | 77               | 14.4        | Yes    | Smooth convergence                          |
| 0.30          | 78               | 14.1        | Yes    | More fluctuations but finds better solution |

**Comparison Observation:**

Observation: When the mutation rate is very low, the algorithm explores fewer solutions and may get stuck. A moderate mutation rate gives smooth convergence. A high mutation rate increases randomness and fluctuations but can discover better solutions due to higher diversity.

**Best Mutation Rate:**

The mutation rate of 0.30 gave the best result because higher mutation increases diversity and helps explore better solutions.

---

## Summary

| Experiment        | Key setting          | Final value | Main finding |
| ----------------- | -------------------- | ----------- | ------------ |
| 1 — Baseline      | mutation_rate = 0.05 | 77          | Fast convergence to stable solution |
| 2 — Mutation rate | mutation_rate = 0.30 | 78          | Higher mutation improved exploration |

**Conclusion:**

Conclusion: Genetic algorithms improve solutions over generations using selection, crossover, and mutation. Mutation rate is critical — too low causes stagnation, too high causes randomness. A balanced value ensures both exploration and convergence.

## Submission Checklist

- [x] Student name and ID filled in
- [x] Q1, Q2, Q3 answered
- [x] Experiment 1: table filled, packing list pasted, plot observation written
- [x] Experiment 2: results table filled (3 rows), observation and answer written
