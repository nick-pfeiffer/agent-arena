# Agent Arena

### Q-Learning vs. Genetic Algorithms in a Competitive Tank Environment

[GIF / screenshot here]

## Overview

Agent Arena is a competitive tank game designed to compare Q-learning and genetic algorithms for learning game-playing policies.

Two agents compete on a grid-based environment containing walls and line-of-sight combat. Agents can move, rotate their weapon, and fire, with the objective of eliminating their opponent with a single shot.

We trained both approaches against a consistently trained opponent and compared their training speed, exploration, and resulting strategies.

## Approaches

### Q-Learning

The reinforcement learning agent uses a Q-table mapping game states to action values. We experimented with different decay rates to study the effect of exploration on training time and learned strategies.

### Genetic Algorithm

The genetic algorithm maintains a population of policies. Policies are evaluated using a fitness function, with higher-performing policies selected for combination and mutation to produce subsequent generations.

## Results

| Agent | Episodes to 90% Win Rate | Unique States |
|---|---:|---:|
| Q-Learning — Low Decay | ~4,566 | 511 |
| Q-Learning — High Decay | ~317,843 | 849 |
| Genetic Algorithm | ~3,085 | — |

The low-decay Q-learning agent converged substantially faster than the high-decay agent, while the high-decay agent explored more unique states. The genetic algorithm reached the 90% win threshold in fewer episodes than either Q-learning configuration.

When evaluated against one another, the trained agents developed different strategies depending on their training configuration.

## Running the Project

### Requirements

- Python
- Pygame

### Run

    python main.py <mode>

Available modes:

- `rlvrl` — RL vs. RL
- `rlvga` — RL vs. GA
- `gavrl` — GA vs. RL
- `gavga` — GA vs. GA
- `optvga` — Optimal vs. GA
- `optvrl` — Optimal vs. RL
- `optvrl_10` — 10 Optimal vs. RL games
- `optvga_10` — 10 Optimal vs. GA games
- `training_opt` — Train the optimal agent

Append `reset` to supported training commands to retrain an agent from scratch.

Set `gui_flag = True` in `main.py` to display the game while it runs.

## Project Structure

- `Board.py` — game board and environment
- `Character.py` — agent representation and behavior
- `State.py` — game state representation
- `Action.py` — available agent actions
- `Direction.py` — movement and weapon directions
- `RL.py` — Q-learning implementation
- `GA.py` — genetic algorithm implementation
- `ActionFunction.py` — agent action interface
- `main.py` — program entry point

## Team & Contributions

This was a four-person team project at Northeastern University, developed collaboratively using VS Code Live Share.

**Collaborators:**
- Kanav Bengani
- Nathan Yan
- Ryan Saperstein

## Technical Report

The full project report, including the methodology, experimental setup, results, and analysis, is available here:

[**Read the full technical report**](report/project-report.pdf)
