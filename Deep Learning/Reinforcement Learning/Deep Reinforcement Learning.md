

## Universal Function Approximators and Policy Gradient

- **Reinforcement Learning with Policy Gradient**:
  - The idea is to parameterize the policy \( \pi \) with weights \( w \), i.e., \( \pi(s_t, a_t, w) \).
  - Use a loss function to compute and update gradients similar to traditional deep learning methods.
  - The policy is updated using gradient ascent to maximize the expected return.

- **Gradient Update**:
  - The policy gradient is computed to adjust the policy parameters to improve performance.
(add equation for gradient update for policy gradient )


see slide 38 for applicability of Deep Q netoworks on atari games