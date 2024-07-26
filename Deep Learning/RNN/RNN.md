
## Sequences
For sequences such as audio, video, speech, language, etc., applicable to arbitrarily long inputs.

## Types of Recurrent Neural Networks (RNNs)
- **LSTM (Long Short-Term Memory)**
- **GRUs (Gated Recurrent Units)**

## Feedforward Networks
- Used for single inputs, such as a single image.
- Not effective for sequential or time-dependent signals, such as speech or music.
- Snapshots are not informative; temporal context is required.
- Inefficient to feed the entire input to the neural network without considering the temporal dimension.

**Goal:** Model sequential behavior.

## RNN (Recurrent Neural Network) aka Elman Network
*See slide 3.*

- The main idea is to introduce a hidden state that is carried over time and returns to the original cell.
- The hidden state encodes temporal information.


- Feedforward networks only feed information forward.
- RNNs can model loops, memory, and experience.
- RNNs can learn sequential data and provide continuous prediction.
- In the figure, input \(x\) is multiplied by some weight.
- The hidden state from the previous configuration \(h_{t-1}\) is used.
- The feedback loop uses information from the present and past to compute \(y_t\).
- The previous input can influence later outputs because information is stored in the hidden state.

*See slides 7 and 8.*

## Activation Functions
- Tangent hyperbolic (tanh)
- Sigmoid function

### Updating the Hidden State
### Combining the Input and Hidden State


*See slide 10.*

## Types of Sequential Relationships
- **One to one:** Image classification
- **One to many:** Image captioning
- **Many to one:** Sentiment analysis
- **Many to many:** Video captioning

*See slide 13.*

- Stacking up RNNs: Along with time \(t\), we have index \(i\) which represents the layer.

## RNN Training
*See slide 17.*

- We achieve training weights through the algorithm "Backpropagation Through Time" (BPTT).
- One forward pass through the full sequence results in a loss.
  - Events happening at the end can influence the beginning.
- Then, a backward pass through the full sequence updates the weights.

**See notes for derivation of backpropagation through time for all the gradients.**

### Problems with the Normal Method
- Need to unroll the entire sequence, which can be very memory-consuming and complex.
- Expensive for single updates.

### Ideas to Address Problems

#### Naive BPTT
- Try splitting approach.
- Split into batches.
- Initialize the hidden state, but this can lose dependency over long periods of time.

#### Truncated BPTT
- Keeps processing the sequence as a whole but adopts the frequency and depth of the update.
- Every \(k_1\) time steps, BPTT runs \(k_2\) times with \(k_2\) being small, making updates cheap.

*See slide 24.*

- Always keep the hidden state and don't discard it.
- Issues: For long temporal contexts, it won't be able to update effectively.
  - Example: If \(k\) is 4 for sequence "a_sequence", if \(k\) is at the end of "u", it won't be able to learn "s".
- Leads to vanishing gradient and exploding gradient problems.
- Another problem is memory overwriting, making detecting long dependencies even more problematic.
