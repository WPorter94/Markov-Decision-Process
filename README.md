# Markov-Decision-Process

## Gridworld MDP Solver
This repository contains Python code to solve a Gridworld MDP (Markov Decision Process). The code implements the Value Iteration algorithm to calculate the utilities for the states of the MDP and derive an optimal policy. The gridworld is represented as a 2D grid with specified rewards for each state. The agent can move in four directions: up, down, left, and right, with certain transition probabilities.

## Files:
mdp.py: This file contains the implementation of the MDP class, which represents the Gridworld MDP, along with the value_iteration function to calculate utilities and derive_policy function to derive the optimal policy from the utilities.

utils.py: This file contains helper functions for formatting and printing the gridworld, utilities, and policy in ASCII art.

main.py: This file contains example usage of the MDP solver. It demonstrates how to create a Gridworld MDP object, set rewards, and calculate utilities and the optimal policy.

## How to Use:
To use the MDP solver, follow these steps:

Create an MDP Object: Instantiate the MDP class with the desired grid size, rewards, terminal states, and transition probabilities.

from mdp import MDP

gridworld = MDP(num_rows, num_cols, rewards, terminals, prob_forw)
Calculate Utilities and Policy: Use the value_iteration function to calculate utilities and the derive_policy function to derive the optimal policy.


from mdp import value_iteration, derive_policy

utilities = value_iteration(gridworld, gamma, epsilon)
policy = derive_policy(gridworld, utilities)
Print Gridworld, Utilities, and Policy: Use the provided helper functions in utils.py to print the gridworld, utilities, and policy in ASCII art.


from utils import ascii_grid_utils, ascii_grid_policy

print("Gridworld Utilities:")
print(ascii_grid_utils(utilities))

print("Optimal Policy:")
print(ascii_grid_policy(policy))
Example Usage
python
Copy code
from mdp import MDP, value_iteration, derive_policy
from utils import ascii_grid_utils, ascii_grid_policy

Define the gridworld parameters
num_rows = 3
num_cols = 3
rewards = {(1, 1): -1, (3, 1): -1, (3, 2): -1, (1, 3): -1, (2, 3): -10, (3, 3): 20}
terminals = [(3, 3)]
prob_forw = 0.8
gamma = 0.8
epsilon = 0.01

Create the Gridworld MDP object
gridworld = MDP(num_rows, num_cols, rewards, terminals, prob_forw)

Calculate utilities and derive optimal policy
utilities = value_iteration(gridworld, gamma, epsilon)
policy = derive_policy(gridworld, utilities)

Print Gridworld Utilities and Optimal Policy in ASCII art
print("Gridworld Utilities:")
print(ascii_grid_utils(utilities))

print("Optimal Policy:")
print(ascii_grid_policy(policy))


## Requirements:
Python 3.x

## License
This project is licensed under the MIT License - see the LICENSE file for details.
