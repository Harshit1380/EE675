# Multi-Agent Reinforcement Learning for Maximum Independent Set (MIS)

This repository contains Python code for solving the Maximum Independent Set (MIS) problem using Multi-Agent Reinforcement Learning (MARL) with Proximal Policy Optimization (PPO) algorithm. The MIS problem is a classic combinatorial optimization problem where the goal is to find the largest set of non-adjacent vertices in a graph.

## Table of Contents

- [Introduction](#introduction)
- [Comparision](#comparision)
- [Features](#features)
- [Requirements](#requirements)
- [Usage](#usage)
- [References](#references)

## Introduction

The MIS problem is represented as an environment in which multiple agents interact. Each agent is equipped with an actor-critic neural network trained using the PPO algorithm. The agents learn policies to select actions (vertices to include in the independent set) and evaluate the value function of being in a state.

## Comparision

The main distinction between the paper's approach and your implementation lies in the solution strategy. While the paper discusses a centralized solution where optimization is coordinated by a central entity, your implementation provides a decentralized solution with each graph node acting as an independent agent. In the centralized approach, decisions are made collectively considering the global state, possibly using a shared neural network architecture. Conversely, your decentralized approach employs separate actor-critic networks for each agent, allowing autonomous decision-making based on local observations. While the paper may focus on global metrics and centralized coordination, your implementation emphasizes individual agent performance and decentralized interactions, offering scalability and robustness in solving the maximum independent set problem.

## Features

- Implementation of the GraphEnvironment class representing the environment for the MIS problem.
- Implementation of the PPOAgent class for training agents with actor and critic networks.
- The training function (`train_multi_agent`) is used to train agents using the PPO algorithm.
- The evaluation function (`find_MIS`) uses trained agents to find the MIS.
- Helper functions for generating random graphs and finding MIS using greedy and exact methods.
- Testing function (`testing`) to compare greedy, MARL, and exact methods results.

## Requirements

- Python 3.x
- TensorFlow
- NetworkX
- tqdm

## Usage

1. Clone the repository:

```bash
git clone https://github.com/Harshit1380/EE675
```

2. Navigate to the project directory

3. Install the required dependencies

```bash
pip install -r requirements.txt
```

4. Run the file using Jupyter Notebook

## References

- https://proceedings.mlr.press/v119/ahn20a/ahn20a.pdf
- https://ieeexplore.ieee.org/document/10092874
- https://faculty.cc.gatech.edu/~vigoda/RandAlgs/MIS.pdf