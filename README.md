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

## try making agents have cost that added 


# Improved Schelling Method 


## Exponential Decay/Growth Model for Grid Price

Prices grow or decay exponentially based on the desirability of a location.

### Implementation:


### Price Update Formula

The price at location $(x, y)$ is updated using the following formula:

$$

\text{Price}_{x,y} = \text{Price}_{x,y} \cdot e^{\beta \cdot (\text{Desirability}_{x,y} - \text{Average Desirability})}

$$
#### Variables:
- $\beta$ : A growth/decay rate that controls how quickly prices adjust based on desirability.  
- $\text{Desirability}_{x,y}$: A measure of how desirable the location \((x, y)\) is. This could be based on factors such as the number of similar neighbors, proximity to amenities, or other location-specific attributes.  
- $\text{Average Desirability}$: The average desirability across all locations.


The formula adjusts the price at each location based on how its desirability compares to the average desirability. If a location's desirability is higher than the average, its price will increase exponentially. If a location's desirability is lower than the average, its price will decrease exponentially.



### Wage Growth Based on Job Opportunities

Wages are modeled based on proximity to economic centers.

#### Wage Function:

$$
W(x, y) = W_{\text{max}} - \alpha \cdot d(x, y)
$$

where:
- $W(x, y)$ is the wage at location $(x, y)$.
- $W_{\text{max}}$ is the maximum possible wage at an economic center.
- $\alpha $ is a decay factor that determines how quickly wages decrease with distance.
- $d(x, y) $ is the Euclidean distance from the nearest economic center, given by:

$$
d(x, y) = \min_{(c_x, c_y) \in C} \sqrt{(x - c_x)^2 + (y - c_y)^2}
$$

where \( C \) is the set of economic center coordinates.

#### Adjusting for Market Fluctuations:

To introduce randomness into the model:

$$
W'(x, y) = W(x, y) + \mathcal{N}(\mu, \sigma)
$$

where $ \mathcal{N}(\mu, \sigma) $ represents a normal distribution with mean $\mu $ and standard deviation $\sigma$, capturing market fluctuations.


