# Assignment 2 — Genetic Algorithm: Knapsack Problem
## Observation Report

**Student Name  :** D.Navya Sri  
**Student ID    :** 2310040049  
**Date Submitted:** 21/03/2026  

---

## Before You Begin — Read the Code

**Q1. What does the `fitness()` function return? Why does an overweight solution score 0?**

```
The fitness function returns the total value of selected items. If total weight exceeds the maximum capacity, it returns 0. This prevents invalid solutions from being selected.
```

---

**Q2. What does `tournament_select()` do? Why are higher-fitness individuals more likely to be chosen?**

```
It selects a few random individuals and returns the one with highest fitness. Higher fitness individuals are more likely to be chosen because they win the tournament.
```

---

**Q3. Look at the `run_ga()` loop. Find this line:**
```python
next_gen = [best_chromosome[:]]
```

```
This copies the best chromosome into the next generation. This is called elitism and ensures the best solution is not lost.
```

---

## Experiment 1 — Baseline Run

| Metric                             | Your result |
| ---------------------------------- | ----------- |
| Number of generations              | 50          |
| Best value at generation 1         | 60          |
| Final best value                   | 77          |
| Total weight of best solution (kg) | 14.4        |
| Is solution valid (Yes / No)       | Yes         |

**Copy the printed packing list here:**

```
================================================
  EXPERIMENT 1 - Baseline
================================================

  Best Packing List
--------------------------------------
  + Water bottle
  + First aid kit
  + Sleeping bag
  + Torch
  + Energy bars (x6)
  + Rain jacket
  + Map & compass
  + Cooking stove
  + Rope (10 m)
  + Sunscreen
  + Power bank
--------------------------------------
```

**Look at `plots/experiment_1.png` and describe what you see (2–3 sentences).**

```
The graph shows a rapid increase in fitness in early generations. The biggest improvement happens at the beginning. Later the curve flattens showing convergence.
```

---

## Experiment 2 — Effect of Mutation Rate

| mutation_rate | Final best value | Weight | Valid | Shape of curve |
| ------------- | ---------------- | ------ | ----- | -------------- |
| 0.01          | 75               | 14.9   | Yes   | Slow           |
| 0.05          | 77               | 14.4   | Yes   | Smooth         |
| 0.30          | 78               | 14.1   | Yes   | Fluctuating    |

**Compare the three plots. What happens when mutation is too low? Too high?**

```
Low mutation reduces diversity and may get stuck. High mutation increases randomness. Moderate mutation balances both and gives better results.
```

**Which mutation_rate gave the best result? Why do you think that is?**

```
Mutation rate 0.30 gave the best result because it explores more solutions and finds better combinations.
```

---

## Summary

| Experiment | Setting | Final value | Finding |
| ---------- | ------- | ----------- | ------- |
| Baseline   | 0.05    | 77          | Fast convergence |
| Mutation   | 0.30    | 78          | Better exploration |

**In your own words — what is the most important thing you learned about Genetic Algorithms from these experiments?**

```
Genetic algorithms improve solutions over generations using selection, crossover and mutation. Mutation rate controls diversity. Too low causes stagnation and too high causes randomness. Balanced mutation gives best results.
```

---

## Submission Checklist

- [x] Student name and ID filled in
- [x] Q1, Q2, Q3 answered
- [x] Experiment 1 completed
- [x] Experiment 2 completed
- [x] Summary completed
- [x] plots folder contains:
  - experiment_1.png
  - experiment_2a.png
  - experiment_2b.png
  - experiment_2c.png