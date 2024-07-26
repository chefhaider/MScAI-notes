
# GRU (Gated Recurrent Unit)

GRU is a simplified variant of the Long Short-Term Memory (LSTM) network. It addresses some of the complexities associated with LSTMs, particularly in terms of the number of parameters and ease of training.

## Key Points

- **Simplification of LSTM**: GRU reduces the complexity of LSTMs by eliminating the need for separate memory cells and gating mechanisms, which can make it easier to train.
  
- **Parameters and Training**: Despite being simpler, GRUs still have many parameters and can be challenging to train effectively, especially on large datasets.

- **Hidden State**: Unlike LSTMs, GRUs have only one hidden state. This hidden state flows through the network in a linear chain, which simplifies the network architecture.

- **Control Over Hidden State Memory**: GRUs provide more control over the hidden state memory compared to simpler RNNs, but the hidden state directly manages memory operations.

## GRU Mechanism

The hidden state in a GRU is managed through the following gates:

1. **Reset Gate**:
   - **Function**: Controls how much of the previous hidden state should be forgotten.
   - **Purpose**: Determines the influence of the previous hidden state on the current hidden state.

2. **Update Gate**:
   - **Function**: Controls how much of the new information (from the current input) should be incorporated into the hidden state.
   - **Purpose**: Balances between the previous hidden state and the new information to produce the updated hidden state.

3. **New Hidden State**:
   - **Computation**: The reset gate helps compute the candidate for the new hidden state, while the update gate decides how much of this candidate should be included in the final hidden state.

4. **Updated Hidden State**:
   - **Outcome**: The final hidden state is a combination of the previous hidden state and the candidate hidden state, regulated by the update gate.

