
## Introduction to LSTM Gates and Cell State Operations

### Overview
The focus is on gates that control access to writing and accessing memory in additional state cells. 

*See Slide 31* (LSTM Diagram)

### LSTM Elements
- **Input**
- **Hidden State (h)**
- **Cell State (c)**
- **Output**

Each cell state consists of:
- **Forget Gate**
- **Input Gate**
- **Cell Update**
- **Hidden State Computation**

*See Slide 33* for details on the inner cell state.

### Cell State Dynamics
- **Cell State Changes**: The cell state undergoes only linear changes (i.e., no activation function). The cell state can remain constant over multiple time steps.
- **Operations Within Cell State**:
  - **Forgetting Information**: The forget gate (f_t) determines which parts of the cell state should be forgotten.
  - **Adding New Information**: The input gate decides how new information is added to the cell state.

### Forget Gate
- **Calculation**: The forget gate \( f_t \) is calculated using a sigmoid function applied to \( h_{t-1} \) (the previous hidden state) and \( x_t \) (the current input) plus a bias term.
- **Range**: The output value is between 0 and 1. This value is used to scale the cell state, determining what information should be retained (1) or removed (0).

### Input Gate
- **Calculation**: Similar to the forget gate, the input gate \( i_t \) is computed using a sigmoid function. Additionally, a candidate cell state \( \tilde{C}_t \) is produced using the tanh function.
  - **Equation and Graph**: Refer to the equations and graphs on the corresponding slide for a detailed representation.
- **Operation**: The input gate's output is multiplied by the candidate cell state \( \tilde{C}_t \). The tanh function provides a new candidate value for the cell state.

### Cell State Update
- The updated cell state is computed by:
  $$
  C_t = f_t \cdot C_{t-1} + i_t \cdot \tilde{C}_t
  $$
  where \( C_{t-1} \) is the previous cell state, \( f_t \) is the forget gate output, \( i_t \) is the input gate output, and \( \tilde{C}_t \) is the candidate cell state.

### Output Gate
- **Hidden State Computation**: The output is dependent on the hidden state.
- **Calculation**: 
  - The hidden state is updated with non-linearity using a sigmoid function.
  - The updated hidden state is multiplied by the cell state to produce the final output.
- **Equation**: The output \( h_t \) is given by:
  $$
  h_t = o_t \cdot \text{tanh}(C_t)
  $$
  where \( o_t \) is the output gate and \( \text{tanh}(C_t) \) represents the updated cell state passed through the tanh function.
