
#### **I. General Introduction to Organic Computing (OC) / Swarm Intelligence (SI)**

**From `2021-07-31_SI_Wanka_Gedaechtnisprotokoll.pdf` (and `2023-04-06_SI_Wanka_Gedaechtnisprotokoll.pdf` - identical questions):**

  * **A1 a) Name 3 reasons for increasing complexity of technical systems.** (3 Points)
  * **A1 b) Name 3 self-\*-properties.** (3 Points)
  * **A1 c) Define the term Emergence.** (3 Points)
  * **A1 d) Which research question was discussed in the lecture in relation to the term Emergence and which Algorithm was used therefore? (hint: think about web-pages)** (2 Points)

**From `braindump-si-ss21.pdf` (Part 1: General Questions):**

  * **1. What is organic computing? Which directions can be identified?**
  * **2. What are the three main reasons which lead to complexity in a system?**
  * **3. a) What is the liveness-property?**
  * **3. b) What does it mean for a system to be self-configuring?**
  * **3. c) Name four other self-\*-properties.**
  * **3. d) What are two advantages of systems with self-\*-properties? What is a disadvantage?**
  * **4. Name three patterns of organization.**
  * **5. a) What is emergence?**
  * **5. b) Name two examples of emergent behavior.**
  * **5. c) What are two properties for emergent phenomena?**
  * **6. a) Which research question for emergence was discussed in greater detail? Which algorithm was examined? Hint: Swarm of webpages**
  * **6. b) Name three other research questions.**

**From `si-tasks-2021.pdf` (Part 1: General Questions):**

  * **1. What is organic computing? Which directions can be identified?**
  * **2. What are the three main reasons which lead to complexity in a system?**
  * **3. a) What is the liveness-property?**
  * **3. b) What does it mean for a system to be self-configuring?**
  * **3. c) Name four other self-\*-properties.**
  * **3. d) What are two advantages of systems with self-\*-properties? What is a disadvantage?**
  * **4. Name three patterns of organization.**
  * **5. a) What is emergence?**
  * **5. b) Name two examples of emergent behavior.**
  * **5. c) What are two properties for emergent phenomena?**
  * **6. a) Which research question for emergence was discussed in greater detail? Which algorithm was examined? Hint: Swarm of webpages**
  * **6. b) Name three other research questions.**

-----

#### **II. Particle Swarm Optimization (PSO)**

**From `2021-07-31_SI_Wanka_Gedaechtnisprotokoll.pdf` (and `2023-04-06_SI_Wanka_Gedaechtnisprotokoll.pdf` - identical questions):**

  * **A2 a) How is the continuous function given in the PSO?** (1 Point)
  * **A2 b) Which 2 different heuristics are needed for good results at PSO? (hint: two similar-sounding words)** (2 Points)
  * **A2 c) Which components do the particle consist of and which does the swarm have in addition?** (2 Points)
  * **A2 d) Show the components of a particle and the swarm graphically (without parameters). Include the next position of the particle additionally.** (4 Points)
  * **A2 e) Write down the Movement Equations with all parameters and variables. Name the dimensionalities and what kind of parameters they are (random, ...).** (4 Points)

**From `braindump-si-ss21.pdf` (Part 2: Particle Swarm Optimisation):**

  * **1. a) What properties does the objective function have?**
  * **1. b) Give and explain two similarly but opposing goals.**
  * **1. c) List all the attributes of a particle and a swarm.**
  * **1. d) Draw a particle with its components, and how it changes in the next time step.**
  * **1. e) Give the exact formula for operating on a particle. Explain each parameter and type (random, dimensions, ...).**

**From `si-tasks-2021.pdf` (Part 2: Particle Swarm Optimization):**

	  * **1. Which of these functions can be optimized on the interval $[-1,1]^{n}$ using PSO as discussed in the lecture?** (Multiple choice options with function definitions)
  * **2. a) Give two characteristics of a particle.**
  * **2. b) Give two characteristics of a swarm.**
  * **2. c) What is the objective function F (a.k.a. fitting function) for PSO? What property does it have?**
  * **2. d) Draw a particle and its change during a step.** (This matches the image in the notes).
  * **3. Give the movement equations for the position and velocity. Describe all the variables and parameters in it, especially what kind of parameters they are (random, ...).**

-----

#### **III. PSO Convergence**

**From `2021-07-31_SI_Wanka_Gedaechtnisprotokoll.pdf` (and `2023-04-06_SI_Wanka_Gedaechtnisprotokoll.pdf` - identical questions):**

  * **A3 a) What applies to the particles at convergence? (2 simple conditions)** (2 Points)
  * **A3 b) Calculate the eigenvalues of the Matrix A: $A=(\\begin{matrix}1-b\&a\\ -b\&a\\end{matrix})$** (4 Points)
  * **A3 c) What is the condition for the eigenvalues to hit convergence?** (2 Points)
  * **A3 d) How does the convergence look for one eigenvalue is real-valued and negative and the other one is a real-valued and positive?** (2 Points)
  * **A3 e) How does the convergence look for complex-valued eigenvalues?** (2 Points)
  * **A3 f) What values for a and b are suggested by Bratton and Kennedy?** (2 Points)
  * **A3 g) What condition must be met by a and b that the condition from c) holds? Draw this area in a coordinate system.** (3 Points)

**From `braindump-si-ss21.pdf` (Part 3: Convergence of PSO):**

  * **1. a) When does PSO converge? Hint: You only need reference two variables**
  * **1. b) Let the Matrix A be $A=(\\begin{matrix}1-b\&a\\ -b\&a\\end{matrix})$ where the variables a and b may have any value.**
      * **i) (4 Points) Compute the eigenvalues of the matrix A.**
      * **ii) (2 Points) Which condition must hold for the eigenvalues to ensure convergence?**
      * **iii) (2 Points) Describe the behaviour of the swarm if one eigenvalue is real and negative and the other is real and positive.**
      * **iv) (2 Points) Describe the behavior of the swarm if the eigenvalues are complex valued.**
      * **v) (3 Points) Draw the area in a coordinate system which satisfies the convergence criterion.**
      * **vi) (2 Points) Which values are recommended for a and b by Bratton and Kennedy?**

**From `si-tasks-2021.pdf` (Part 3: Convergence of PSO):**

  * **1. What properties do the particles have when they converge?**
  * **2. a) Compute the eigenvalues of the matrix $A = (\\begin{smallmatrix} 1-b & a \\ -b & a \\end{smallmatrix})$**
  * **2. b) What conditions must the eigenvalues satisfy to guarantee convergence?**
  * **2. c) Describe the behavior of the swarm in the following cases:**
      * **i. The eigenvalues are real-valued, one is negative and one is positive.**
      * **ii. The eigenvalues are complex-valued.**
  * **2. d) What are the conditions on a and b that ensure convergence? Draw the area.**
  * **2. e) Give the values of a and b suggested by Bratton and Kennedy.**

-----

#### **IV. HITS Algorithm**

**From `2021-07-31_SI_Wanka_Gedaechtnisprotokoll.pdf` (and `2023-04-06_SI_Wanka_Gedaechtnisprotokoll.pdf` - identical questions):**

  * **A4 a) What is a hub and what is an authority?** (2 Points)
  * **A4 b) When and how do authorities and hubs reinforce each other?** (2 Points)
  * **A4 c) Why is the (intermediate) normalization needed?** (2 Points)
  * **A4 d) What do you have to do to get convergence?** (2 Points)
  * **A4 e) How does the relation between the principal eigenvector and the (result) vectors look?** (2 Points)

**From `braindump-si-ss21.pdf` (Part 4: HITS Algorithm):**

  * **1. a) Define the terms authority and hub and show how they affect each other.**
  * **1. b) Why is it necessary to normalize the hub and authority vectors?**
  * **1. c) Which mathematical theorem ensures the convergence of the algorithm?**
  * **1. d) Explain the process of generating the base graph in detail. Why is it constructed in this way?**

**From `si-tasks-2021.pdf` (Part 4: HITS Algorithm):**

  * **1. a) What is an authority?**
  * **1. b) What is a hub?**
  * **1. c) Why do authorities and hubs affect each other?**
  * **1. d) Why must the vectors be normalized at the end of each step?**
  * **1. e) Which theorem ensures convergence?**
  * **1. f) Explain in detail how the base graph for the HITS algorithm is constructed.**

-----

#### **V. Ant Colony Optimization (ACO)**

**From `2021-07-31_SI_Wanka_Gedaechtnisprotokoll.pdf` (and `2023-04-06_SI_Wanka_Gedaechtnisprotokoll.pdf` - identical questions):**

  * **A6 a) Given $s\_a = (1,3,2,5)$, $\\mathcal{N}(s\_a)={4,6}$. Assuming the distance between every node is 1. Give the set of admissible extensions for ant a visiting node 5.** (1 Point)
  * **A6 b) Compute the probabilities that ant a visiting the node 5 will choose these vertices. Assume the pheromone values are $\\tau\_{45}=\\tau\_{25}=3$ and $\\tau\_{56}=\\tau\_{15}=\\tau\_{35}=2$.** (6 Points)
  * **A6 c) Write down the general formula for the probability that an ant chooses a specific extension. Explain all variables and parameters in it.** (4 Points)
  * **A6 d) Which two mechanisms are used to update the pheromone values? Explain their purpose.** (4 Points)

**From `braindump-si-ss21.pdf` (Part 6: Ant Colony Optimisation):**

  * **a) (1 Point) Give the set of vertices ant a visiting the node 5 is allowed to consider next $\\mathcal{N}(s\_a)={$...** (Partial question, likely from the same TSP example as A6a/b above)
  * **b) (6 Points) Compute the probabilities that ant a visiting the node 5 will choose these vertexes. Assume the pheromone values are $\\tau\_{45}=\\tau\_{25}=3$ and $\\tau\_{56}=\\tau\_{15}=\\tau\_{35}=2$.** (Matches A6b)
  * **c) Give the exact formula for the probability that an ant chooses a specific extension. Explain all the parameters and variables.** (Matches A6c)
  * **d) Which two mechanisms are used to update the pheromone values? Explain their purpose.** (Matches A6d)

**From `si-tasks-2021.pdf` (Part 5: Ant Colony Optimization):**

  * **1. a) What kind of problems does ACO solve?**
  * **1. b) What is the inspiration for ACO?**
  * **1. c) Which three general steps does the algorithm consist of?**
  * **1. d) Explain the definition of an admissible solution in the context of ACO.**
  * **2. a) Which rule is most used for choosing the next extension in the context of ACO? Explain all variables and parameters.**
  * **2. b) How can the exploration of the search space be increased?**
  * **3. a) Explain the two mechanisms to update the pheromone values.**
  * **3. b) i. How does the pheromone update equation look like?**
  * **3. b) ii. Which condition must hold for the pheromone values such that the tour produced by the ant is uniformly random of all tours?**
  * **3. c) Give one example for choosing a heuristic information $\\eta(c\_i^3)$ and two examples (and their name) of emission functions $g\_{ij}^{\<k\>}(t,t+1)$ at the traveling salesperson problem.**

-----

#### **VI. Genetic / Evolutionary Algorithms (EA)**

**From `2021-07-31_SI_Wanka_Gedaechtnisprotokoll.pdf` (and `2023-04-06_SI_Wanka_Gedaechtnisprotokoll.pdf` - identical questions):**

  * **A5 a) Draw the evolutionary cycle. What do the parameters $\\mu$ and $\\lambda$ mean? What does F mean?** (4 Points)
  * **A5 b) Execute a one-point crossover using the parents (1 2 3 4 5 6 7 8) and (6 2 8 4 7 5 3 1). Crossover point after 5. Draw the resulting offspring.** (3 Points)
  * **A5 c) Execute a partially matched crossover (PMX) using the parents (1 2 3 4 5 6 7 8) and (6 2 8 4 7 5 3 1). Crossover points after 2 and 6. Draw the resulting offspring.** (4 Points)
  * **A5 d) Given is the permutation (3 2 6 8 4 1 7 5). Calculate INV and HAM.** (2 Points)
  * **A5 e) Give the exact values of INV and HAM for a sorted sequence of length n.** (2 Points)

**From `braindump-si-ss21.pdf` (Part 6: Evolutionary Algorithms):**

  * **1. a) What is an evolutionary algorithm?**
  * **1. b) What does reproduction involve?**
  * **1. c) What is the difference between genotype and phenotype?**
  * **1. d) Draw the evolutionary cycle. What do the parameters $\\mu$, $\\lambda$ and F mean?**
  * **2. a) Name and explain one possible selection operator.**
  * **2. b) What is elitism?**
  * **3. a) Execute an one point crossover using the parents and crossover-point:** (Example with 10 elements)
      * `Parent 1: 1 3 2 4 6 10 9 5 8 7`
      * `Parent 2: 1 2 3 4 5 6 7 8 9 10`
      * `Crossover point: after 5`
  * **3. b) Execute a partially matched crossover using the parents and crossover-points:** (Example with 10 elements)
      * `Parent 1: 1 3 2 4 6 10 9 5 8 7`
      * `Parent 2: 1 2 3 4 5 6 7 8 9 10`
      * `Crossover points: after 2 and 6`
  * **3. c) What is the goal of the edge recombination crossover? How does it work?**
  * **4. a) Draw the tour which is encoded by the following array: (1 2 3 4 5 6 7 8 9 10)** (This asks for drawing a TSP tour from a permutation)
  * **4. b) Use the swap mutation operator on the entries 4 and 10. How does the tour change?** (for the permutation from 4a)
  * **4. c) Use the inversion mutation operator on the entries 1 and 10. How does the tour change?** (for the permutation from 4a)
  * **5. a) What properties of a permutation do the following functions measure?**
      * **$INV(\\pi)$**
      * **$HAM(\\pi)$**
      * **$LAS(\\pi)$**
  * **5. b) What is the value of these functions for a sorted sequence of length n?**
  * **5. c) For which mutation operators were the lower and upper bounds derived? How do they work?**
  * **5. d) What are the lower and upper bounds on the expected running time for sorting an arbitrary permutation of length n?**


-----

