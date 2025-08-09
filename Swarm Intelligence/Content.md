1. Introduction
	1. Principles of Organic Computing as Super-ordinate concepts of swarm intelligence
	2. Self-\*-properties
	3. Pattern of Organisation, Emergence
2. Particle Swarm Optimisation
	1. PSO algorithm
	2. Convergence Criteria
3. Searching the Swarm and measuring Emergence
	1. The HITS algorithm
4. Ant Algorithm
	1. The meta-heuristic
	2. Example:Travelling Salesman problem
5. Genetic Evolutionary Algorithm
	1. Example: Travelling Salesman Problem
	2. Mathematical Analysis of a (1,1)-EA of sorting
	3. Edge Recombination Crossover

---

This course, "Swarm Intelligence," explores how to solve complex computational problems by drawing inspiration from the collective, decentralized behavior observed in natural systems like ant colonies and bird flocks. It delves into the principles of **Organic Computing**, focusing on concepts such as **self-organization** and **emergence**, where complex system properties arise from simple local interactions.

Key algorithms covered include:

- **Particle Swarm Optimization (PSO):** Mimics the social behavior of bird flocking or fish schooling to find optimal solutions.

- **HITS Algorithm:** Applies swarm intelligence concepts to web page ranking, identifying "authorities" and "hubs" based on link structures.

- **Ant Colony Optimization (ACO):** Inspired by ants finding shortest paths, using pheromone trails to guide problem-solving.

- **Genetic/Evolutionary Algorithms (EA):** Utilizes principles of biological evolution (reproduction, mutation, selection) for optimization tasks.


Essentially, the course teaches you to design and analyze algorithms that leverage collective intelligence for robust and adaptive problem-solving in complex systems.

---
The first chapter, "Introduction to Swarm Intelligence," lays the groundwork for the entire course by introducing **Organic Computing (OC)** as a broader concept. It explains why traditional computing struggles with increasing system complexity (miniaturization, interconnection, embedding) and proposes learning from living systems.

The core of this chapter is defining **"self-*-properties"** (like self-configuring, self-healing, self-optimizing) which enable systems to manage themselves automatically. It also deeply explores **"emergence"**, the key phenomenon where complex, unpredictable behaviors arise from simple local interactions, highlighting its presence in both natural and artificial systems, with a specific focus on its application in web search. Finally, it outlines current **research questions and directions** in the field.

---
The second chapter focuses entirely on **[[Particle Swarm Optimization (PSO)]]**. It introduces PSO as an ==evolutionary==, ==decentralized optimization== algorithm inspired by social animal behavior (like bird flocking).

This chapter details the fundamental components of PSO, including:

- **Individual particles:** Their ==position==, ==velocity==, and ==local best solution==.
    
- **The swarm:** Its global best solution.
    

It then presents the ==**movement equations**== that govern how ==particles update their velocity== and ==position==, incorporating various parameters and randomization. A significant portion is dedicated to the ==**convergence analysis**== of PSO, examining the mathematical conditions (specifically related to eigenvalues of a system matrix and parameter choices) that ensure the swarm converges to a solution and how different parameter settings affect its dynamic behavior (e.g., oscillating vs. non-oscillating convergence).

---
The third chapter of your notes, which was titled "Searching the Swarm and Measuring Emergence," focuses on the **HITS (Hyperlink-Induced Topic Search) Algorithm**.

This chapter explains how HITS addresses the challenges of web search by going beyond simple text matching. It introduces the key concepts of **"Authorities"** (pages providing definitive information) and **"Hubs"** (pages linking to many authorities), showing how these two types of pages mutually reinforce each other. The core of the chapter describes the **iterative algorithm** used to compute authority and hub scores for web pages, emphasizing the crucial role of **normalization** for convergence and demonstrating its mathematical basis using **eigenvectors** of related matrices. It also details the process of constructing the **"base graph"** for the algorithm.

---
The fourth chapter focuses on **Ant Colony Optimization (ACO)**. It introduces ACO as a metaheuristic inspired by the foraging behavior of real ants, particularly their use of pheromone trails to find the shortest paths.

The chapter explains how ACO is applied to **combinatorial optimization problems**, where artificial "ants" collectively construct solutions by probabilistically choosing components based on **pheromone values** and optional **heuristic information**. It details the **probabilistic rule** ants use for decision-making and emphasizes the crucial role of **pheromone update mechanisms** (emission and evaporation) in guiding the search towards optimal solutions and preventing premature convergence. The Traveling Salesperson Problem (TSP) often serves as a key example to illustrate ACO's application.

---

The fifth chapter, titled "Genetic/Evolutionary Algorithms (EA)," provides an overview of this powerful metaheuristic. It explains that EAs are inspired by **biological evolution** (reproduction, variation/mutation, and selection) to solve various optimization problems.

The chapter differentiates between an individual's **genotype** (its coding) and **phenotype** (the coded individual itself). It details the **Evolutionary Cycle** and the general **(µ, λ)-EA algorithm**, outlining how populations of solution candidates are iteratively improved across generations. Key components like **selection operators** (e.g., tournament, rank selection, elitism), **crossover operators** (e.g., one-point, PMX, edge recombination), and **mutation operators** (e.g., swap, inversion) are discussed, often using the **Traveling Salesperson Problem (TSP)** as a practical example. Finally, it delves into the **mathematical analysis** of EA for sorting permutations, introducing concepts like inversion count, Hamming distance, and longest ascending subsequence, and deriving **expected running time bounds** for certain mutation types.

---
