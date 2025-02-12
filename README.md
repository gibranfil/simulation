# simulation
## Components
 - Agents
 - Grids
 - Similarity Threshold
 - Use moore Neighbourhood


## Agent Movement
If an agent is unsatisfied, it will attempt to move to a new location:

Finding Empty Cells:

The model identifies all empty cells on the grid.

Random Relocation:

The unsatisfied agent is moved to a randomly selected empty cell.

The agent's position in the self.agents list and the grid is updated accordingly.

## Interesting Notes

- Sometimes it converges however left one agents wandering around
- Some threshold never converge at al?
- Might check diffferent type of neighbohood
- Too big agents move randomly
- Maybe a better movement rule?

## About Movements

- The original paper use random
### Movement to the Nearest Satisfactory Location
For each unsatisfied agent, calculate the distance to all empty cells.
Move the agent to the closest empty cell where it would be satisfied.

## agents move with a probability based on their level of dissatisfaction.