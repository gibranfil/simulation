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


### Exponential Decay/Growth Model for Grid Price

Prices grow or decay exponentially based on the desirability of a location.

**Implementation:**

Define desirability as a function of the number of similar neighbors, amenities, or other factors. Update prices using:

```latex
Price_{x,y} = Price_{x,y} \cdot e^{\beta \cdot (Desirability_{x,y} - Average Desirability)}
```

Where:
- `β` is a growth/decay rate.
- `Desirability_{x,y}` is a measure of how desirable the location is (e.g., based on the number of similar neighbors or amenities).

---

### Wage Growth Based on Job Opportunities

Wages are determined by proximity to economic centers:

```latex
W(x, y) = W_{\text{max}} - \alpha \cdot d(x, y)
```

Where:
- `W(x, y)` is the wage at location `(x, y)`.
- `W_{\text{max}}` is the maximum possible wage at an economic center.
- `α` is a decay factor that determines how quickly wages decrease with distance.
- `d(x, y)` is the Euclidean distance from the nearest economic center, given by:

```latex
d(x, y) = \min_{(c_x, c_y) \in C} \sqrt{(x - c_x)^2 + (y - c_y)^2}
```

Where `C` is the set of economic center coordinates.

The wage is then adjusted with some randomness to simulate real-world fluctuations:

```latex
W'(x, y) = W(x, y) + \mathcal{N}(\mu, \sigma)
```

Where `\mathcal{N}(\mu, \sigma)` represents a normal distribution with mean `μ` and standard deviation `σ`, capturing market fluctuations.

---

### Rendering in GitHub `README.md`

Since GitHub does not support LaTeX rendering directly, you can use the following workarounds:

1. **Use Code Blocks:**
   Wrap your equations in triple backticks (```) with `latex` syntax highlighting to make them more readable.

   Example:
   ```latex
   Price_{x,y} = Price_{x,y} \cdot e^{\beta \cdot (Desirability_{x,y} - Average Desirability)}
   ```

2. **Embed Images:**
   Use an external LaTeX rendering tool (e.g., [QuickLaTeX](https://www.quicklatex.com/)) to generate images of your equations and embed them in your `README.md`.

   Example:
   ```markdown
   ![Price Equation](https://www.quicklatex.com/cache3/ef/your_equation_image.png)
   ```

3. **Use Plain Text:**
   Write the equations in plain text with clear formatting.

   Example:
   ```
   Price_{x,y} = Price_{x,y} * e^(β * (Desirability_{x,y} - Average Desirability))
   ```

