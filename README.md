# Evolutionary Path Planner

A genetic algorithm that evolves paths for a campus delivery robot on a 10x10 grid with random obstacles, written from scratch in Python.

Built for the Evolutionary AI course in the Applied Data Science & AI program at Zuyd University of Applied Sciences.

## How it works

Each individual is a fixed-length sequence of moves (up, down, left, right). Every generation the algorithm:

1. scores each path on how close it gets to the goal while avoiding obstacles,
2. picks parents with tournament selection,
3. combines them with crossover and applies random mutation,
4. keeps the best individuals through elitism.

Default settings: population 100, path length 25, 60 generations, tournament size 3, mutation rate 0.1, fixed random seed for reproducibility.

## Experiments

- **Convergence**: best and mean fitness tracked per generation.
- **Visualisation**: the best evolved path drawn on the obstacle grid.
- **Parameter sensitivity**: mutation rate (0.02, 0.05, 0.1), population size (10, 20, 40) and tournament size (2, 3, 5), each averaged over 10 seeded runs.

Main findings: lower mutation converges faster but gets stuck more often, larger populations give more stable results, and larger tournaments raise selection pressure at the cost of diversity.

## Files

- `part_a_ea_components.ipynb`: the individual building blocks (representation, fitness, selection, crossover, mutation) and their tests
- `evolutionary_path_planner.ipynb`: the full algorithm, visualisations and sensitivity study

## Tech stack

Python, NumPy, Matplotlib, Jupyter

## How to run

```bash
pip install -r requirements.txt
jupyter notebook evolutionary_path_planner.ipynb
```
