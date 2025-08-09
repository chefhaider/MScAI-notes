- Inspired from ants releasing pheromones to lead the trail for other ants, the key idea the pheromones evaporate after a while but amplifies with other ants crossing it
- This phenomena is artificially reconstructed with pheromones traces serving as distributed numerical information, during the search information is updated to reflect the ants previous information to guide the search in the correct path
- a randomised search heuristic is applied
- can be applied to any discrete optimisation problem

**see notes for the algorithm**

---

## 1. a) What kind of problems does ACO solve?
Ant Colony Optimization (ACO) solves **combinatorial optimization problems** — problems where the goal is to find an optimal object from a finite but very large set of possible solutions.  
Examples: Traveling Salesperson Problem (TSP), scheduling, routing.

---

## 1. b) What is the inspiration for ACO?
Inspired by the **foraging behavior of real ants**, especially how they find the shortest path between their nest and a food source by laying down and following **pheromone trails**.  
Shorter paths accumulate more pheromones faster, leading to positive feedback where most ants eventually choose the shortest route.

---

## 1. c) Three general steps of ACO
1. **Initialization** – Set initial pheromone values $\tau_{ij}(0)$ and parameters.
2. **Generate candidate solutions** – Ants build solutions step-by-step based on pheromone and heuristic information (optional: apply local search to improve them).
3. **Update pheromone values** – Increase pheromones on good solutions (emission) and reduce them globally (evaporation).

---

## 1. d) Admissible solution in ACO
For a given input $I$ from the problem domain $D$, the set of **admissible solutions** $S(I)$ contains all solutions that satisfy the problem constraints.  
In ACO:
- Each ant starts with a **partial admissible solution** and extends it by adding **solution components** $c_i^j$ (assigning a value $v_i^j \in D_i$ to variable $X_i$) from the set $C$.
- The partial solution must always remain in $S(I)$, meaning it must not violate the constraints.

---

## 2. a) Most used rule for choosing the next extension
The **probabilistic transition rule**:

$$
\Pr(c_i^j \mid s_p; t) =
\begin{cases}
\dfrac{\tau_{ij}(t)^{\alpha} \cdot [\eta(c_i^j)]^{\beta}}
{\sum\limits_{c_i^x \in N(s_p)} \tau_{ix}(t)^{\alpha} \cdot [\eta(c_i^x)]^{\beta}}, & \text{if } c_i^j \in N(s_p) \\
0, & \text{otherwise}
\end{cases}
$$

Where:  
- $\tau_{ij}(t)$ = pheromone value for $c_i^j$ at iteration $t$  
- $\eta(c_i^j)$ = heuristic desirability of $c_i^j$  
- $\alpha$ = influence of pheromone  
- $\beta$ = influence of heuristic  
- $N(s_p)$ = admissible extensions for partial solution $s_p$

---

## 2. b) Increasing exploration of the search space
Before applying the probability rule:
1. Generate $r \in [0,1]$
2. If $r \le Q$: use the probability rule (exploit).
3. If $r > Q$: choose any admissible extension uniformly at random (ignore pheromone and heuristic).  
This forces **exploration**.

---

## 3. a) Two mechanisms to update pheromone values
1. **Emission of new pheromones** – reward good solutions by increasing pheromone on their components.
2. **Evaporation of old pheromones** – reduce pheromones globally to avoid premature convergence.

---

## 3. b) i. Pheromone update equation
$$
\tau_{ij} := \rho \cdot \tau_{ij} + \Delta \tau_{ij}
$$

Where:  
- $\rho \in (0,1)$ = evaporation factor  
- $\Delta \tau_{ij}$ = sum of pheromones deposited by all ants that used $(i,j)$

---

## 3. b) ii. Condition for uniform randomness of tours
If all $\tau_{ij}$ are equal and $\beta = 0$ (heuristic ignored), all moves are equally probable $\Rightarrow$ tour is **uniformly random**.

---

## 3. c) Examples
- **Heuristic $\eta(c_i^j)$**: For TSP, $\eta_{ij} = \frac{1}{\text{dist}(i,j)}$
- **Emission functions $g_{ij}^{\langle p\rangle}(t,t+1)$**:
    1. **Ant Density**:
       $$
       g_{ij}^{\langle p\rangle}(t,t+1) =
       \begin{cases}
       Q_1 & \text{if ant } p \text{ goes from } i \text{ to } j \\
       0 & \text{otherwise}
       \end{cases}
       $$
    2. **Ant Cycle**:
       $$
       g_{ij}^{\langle p\rangle}(t,t+1) =
       \begin{cases}
       \frac{Q_3}{L^{\langle p\rangle}} & \text{if ant } p \text{ goes from } i \text{ to } j \\
       0 & \text{otherwise}
       \end{cases}
       $$
       Where $L^{\langle p\rangle}$ is the length of ant $p$'s best tour so far.
