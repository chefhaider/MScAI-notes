
## Overview

In neural networks, the attention mechanism allows models to focus on different parts of the input sequence when producing each element of the output sequence. This mechanism addresses the limitations of using a fixed-size context vector in encoder-decoder architectures.

## Encoder-Decoder Architecture

1. **Forward Pass in the Encoder**: The encoder processes the input sequence and computes a series of hidden states.
2. **Hidden State as Context Vector**: The final hidden state (context vector) represents the entire input sequence's meaning.
3. **Decoder**: The decoder uses this context vector to generate a new sequence. It computes its own hidden states and generates the output sequence.

### Problem with Basic Encoder-Decoder

The primary issue is that encoding the entire input sequence into a single context vector can be challenging, especially for long sequences. This fixed-size context vector must capture all relevant information, which is often infeasible.

## Attention Mechanism

### Context Vector in Seq2Seq

In standard Seq2Seq models, the context vector is produced at the end of the encoder. This makes initial inputs less influential. To address this, a bidirectional RNN is used:

1. **Bidirectional RNN**: The input sequence is processed in both forward and backward directions.
2. **Concatenation of Hidden States**: Hidden states from both passes are concatenated.
3. **Weighted Average (Alpha Weights)**: A weighted average of each hidden state is calculated using alpha weights, providing a dynamic context for the decoder. This enables modeling of different input and output lengths.

### Producing Alpha Weights

Alignment weights (alphas) determine the relevance of encoder states for each decoder time step:

1. **Relevance Scores**: High scores indicate states relevant to the current observation.
2. **Training the Score Function**: The score function is trained and can be interpreted through visualization.

## Types of Attention

### Soft Attention vs. Hard Attention

1. **Soft Attention**: Efficient for small to moderate input sizes.
2. **Hard Attention**: Samples from a distribution (patches) and is not differentiable, making it less efficient but useful for larger inputs.

## Applications of Attention

### Show-Attend-Tell

Different regions of interest (ROIs) trigger different keys, which are used for generating captions.

### Self-Attention

Computes the attention of a sequence to itself and can be used for tasks like machine translation.

## "Attention is All You Need"

This model, known as the Transformer, eliminates the need for RNNs or convolutions. It iteratively improves the representation through self-attention mechanisms.

### Encoder Blocks

1. **Self-Attention Step**
2. **Local Fully Connected Layers**

### Input Embeddings for the Encoder

1. **One-Hot Encoding**: Very coarse and not suitable for attention networks.
2. **Embedding Algorithm**: Compresses the input and produces an embedding. The model then computes self-attention for each token.

### Computing Q, K, V

For each token in the sequence, we compute:

- **Q (Query)**
- **K (Key)**
- **V (Value)**

The alignment between Q and K determines the influence of tokens on each other.

### Attention Formula

The attention mechanism can be mathematically described as:

$$ \text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V $$

where \(d_k\) is the dimension of the key vectors.