


# Multi-Armed Bandit Problem

In the multi-armed bandit problem, at each time step \( t \), an agent selects an action \( a_t \) from a set of possible actions \( \mathcal{A} \). Each action \( a \) has an associated unknown reward \( r \), and the relationship between the reward and the action is governed by a probability distribution with a probability density function (pdf) \( p(r | a) \). The agent's goal is to maximize the cumulative reward over time.

The problem is formalized through a policy \( \pi(a) \) which determines the probability distribution over actions. The policy influences the agent's decision-making process. Our objective is to compute the maximum expected reward, either over time or across different phases, by choosing actions that will, in the long run, produce the highest expected reward.

Since \( E[p(r | a)] \) (the expected reward for an action \( a \)) is not known in advance, the problem is unsupervised. 

To address this, we use the action-value function \( Q_t(a) \), which estimates the expected reward of action \( a \) at time \( t \). This function is updated based on new information and is computed from the observed rewards.

**Policy Selection:**
- Choose a policy \( \pi(a) \) that maximizes \( \max_a Q_t(a) \).

#### Exploration vs. Exploitation

Instead of always selecting the action that maximizes \( Q_t(a) \) (exploitation), it is crucial to also explore other actions to potentially discover better options. 

**Epsilon-Greedy Strategy:**

To balance exploration and exploitation, the **epsilon-greedy** strategy is used. With probability \( \epsilon \), a random action is chosen (exploration), and with probability \( 1 - \epsilon \), the action that maximizes \( Q_t(a) \) is chosen (exploitation).

The action selection rule is:
$$
 a_t = \begin{cases} 
\text{Random action} & \text{with probability } \epsilon \\
\arg\max_a Q_t(a) & \text{with probability } 1 - \epsilon
\end{cases} 
$$

Here, \( \epsilon \) is a small number between 0 and 1, controlling the trade-off between exploration and exploitation. A higher \( \epsilon \) increases the likelihood of exploring less optimal actions.

**Softmax Strategy:**

The **softmax** strategy provides a probabilistic approach to action selection, where actions are chosen according to a probability distribution based on their estimated values. The softmax function is defined as:

$$
 P(a) = \frac{e^{Q_t(a) / \tau}}{\sum_{a' \in \mathcal{A}} e^{Q_t(a') / \tau}} 
$$

where \( \tau \) (temperature parameter) controls the level of exploration:
- High \( \tau \) results in more exploration (more uniform distribution).
- Low \( \tau \) results in more exploitation (more skewed distribution).

If two actions produce similar rewards, such as 9 and 10, the softmax function will assign probabilities to actions in proportion to their reward estimates. Actions with slightly higher rewards will have a higher probability of being chosen, but the difference is smoothed out by the temperature parameter.



---


# Contextual Bandits

## Associativity in Contextual Bandits

- **New State Introduction**: 
  - A new state `s` is introduced which represents the state of the world. The action now depends on both `s` and `a`.

- **Action Effects**: 
  - Actions can influence the probability distribution of the next state: \( p(s_{t+1} \mid s_t, a_t) \).
  - Rewards are also dependent on both the action and the current state: \( p(r \mid a_t, s_t) \).

## Markov Decision Process (MDP)

- **Policy Dependence**:
  - Policies are now dependent on the state: \( \pi(a \mid s) \).

- **Finite MDP**:
  - If the state and action spaces are finite, it is known as a Finite Markov Decision Process (Finite MDP).

- **Types of Tasks**:
  - **Episodic**: Tasks have a clear start and end.
  - **Continuing**: Tasks are infinite in length. For episodic tasks, we can unify them by setting the reward to zero after the last step to model continuous scenarios.

## Goal and Future Return

- **Objective**:
  - The goal is to maximize the future return rather than just the present reward.

- **Return Equation**:
  - The return \( G_t \) is defined as:
    $$
    G_t = r_t + \gamma r_{t+1} + \gamma^2 r_{t+2} + \cdots
    $$
  - Here, \( \gamma \) is the discount factor.

- **Discount Factor (\( \lambda \))**:
  - \( \lambda \) (ranging from 0 to 1) provides diminishing returns for more distant rewards.
  - For infinitely long sequences, \( \lambda \) should be chosen to be less than 1.

## Alternatives for Limitations

### Monte Carlo Techniques

- **Episodic Nature**:
  - Monte Carlo methods are typically used for episodic tasks.
  - No need for information about the dynamics of the environment; policies are learned arbitrarily.

- **Explanation**:
  - Monte Carlo methods estimate the value of a policy by averaging the returns from multiple episodes of the policy.

### Temporal Difference Learning

- **On-Policy Learning**:
  - Does not require information about the dynamics of the environment.
  - Follows a certain policy, uses this policy to observe rewards and states, and updates the state-value function based on observed rewards.

- **Update Rule**:
  - The state-value function \( V(s) \) is updated as follows:
    $$
    V(s_t) \leftarrow V(s_t) + \alpha \left[ r_t + \gamma V(s_{t+1}) - V(s_t) \right]
    $$
  - Here, \( \alpha \) is the learning rate.

- **Convergence**:
  - Temporal Difference (TD) learning converges to the optimal solution. A variant of TD learning is SARSA (State-Action-Reward-State-Action).

### Q-Learning

- **Off-Policy Learning**:
  - Does not require information about the dynamics of the environment.
  - Uses a policy derived from a greedy approach with respect to \( Q_t(s, a) \).

- **Update Rule**:
  - The Q-function \( Q(s, a) \) is updated as follows:
    $$
    Q(s_t, a_t) \leftarrow Q(s_t, a_t) + \alpha \left[ r_t + \gamma \max_{a} Q(s_{t+1}, a) - Q(s_t, a_t) \right]
    $$

## Universal Function Approximators and Policy Gradient

- **Reinforcement Learning with Policy Gradient**:
  - The idea is to parameterize the policy \( \pi \) with weights \( w \), i.e., \( \pi(s_t, a_t, w) \).
  - Use a loss function to compute and update gradients similar to traditional deep learning methods.
  - The policy is updated using gradient ascent to maximize the expected return.

- **Gradient Update**:
  - The policy gradient is computed to adjust the policy parameters to improve performance.

---

