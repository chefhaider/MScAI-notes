https://chatgpt.com/share/688d32ec-7590-8005-b326-5f7b7417835b
https://chatgpt.com/share/688d32fd-8d10-8005-b818-87df9744335f


The swarm parameters in the equation directly control the exploration (ability of swarm to explore the search space completely) and exploitation (ability of the swarm to find good solutions)

| Parameter  | Role                                                                                                                                    |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **a**      | **Inertia weight** — controls how much of the previous velocity is kept (momentum). Helps balance **exploration** vs. **exploitation**. |
| **bₗₒc**   | Local influence — how strongly the particle is attracted to **its own best position**. Encourages **individual learning**.              |
| **b𝓰ₗₒb** | Global influence — how strongly the particle is attracted to the **swarm’s best position**. Encourages **collective learning**.         |
| **c**      | Damping factor on the old position (usually set to 1, often omitted).                                                                   |
| **d**      | Scaling factor for how much the velocity affects the new position (often set to 1).                                                     |

### The Algorithm

for each i In N
	initiliasie the position x_i, and v_i
	set personal best p = x_i
set global best p_i_glob = argmin{F(pi)i = 1...N}

for each i in N
	compute x and v from the swarm equations and update the pi and pi_glob form the computed new x_i 
	(see the criteria in the hand written notes)


### Convergence Criteria
the objective is that the swarm convergance, i.e the swarm agrees on a single solution. the swarm parameters are important for this.

convergance at point p where the particles no longer move i.e v -> 0

from the final reduced equation (see notes) - we can say that the system converges if the eigen values lambda 1, 2 are smaller then 1

relation between eigen values and a,b swarm parameters
https://chatgpt.com/c/688d2d00-e5dc-8324-814a-a99e104921de#:~:text=explain%20this%20part%20of%20the%20convergance%20criteria%20for%20the%20SPO

- If eigenvalues are **real**, the system **decays smoothly** (no oscillation).
- If eigenvalues are **complex conjugates** (i.e., have imaginary parts), then **oscillatory behavior appears**.
- If eigenvalues are **on or near the unit circle** (i.e., ∣λ∣≈1|\lambda| \approx 1∣λ∣≈1), the oscillations **persist or decay slowly**.
- If ∣λ∣>1|\lambda| > 1∣λ∣>1, the oscillations **grow** (divergence).

**a** controls how aggressive the updates are, b is damping factor between weights. high a and poor b causes osculations