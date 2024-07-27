there is a forward pass in the encoder which takes the input, from that we compute the hidden state - which is used as a context vector for the decoder network which is the representation or actual meaning of the state, ht is decoded by the decoder which generates a new sequence which computes own hidden state - which also generates an output sequence
problem?
the encoding is difficult because the entire meaning has to be represented in one context vector

Attention: Seq2Seq context vector
the context vecctor is produced at the end and and by that the initial inputs donot play much role, so a biderectional RNN is used so after on forward pass the input is reveresed for the another forward pass, from the two passes the hidden states are concatenated, and a weighted average is calculated of each hidden state with alpha - weight which provides a dynamic context for decoder so this allows to model different lengths in input and output

how to produce those alphas  - alignment weights, if the states are relevant for the current observation then you get  a high score

the score funtion is trained also allows interpretation through visualisation

kinds of attention:
Soft Attention vs Hard Attention
sofft attentions is not effiecent for large inputs
for hard attention we sample from distibution (patches)  but since it is not differnetiable


show-attned-tell
different rois trigger different keys which is used for caption generation


Self-Attentions
to compute the attention of its sequence to itself

which can be used for machine translation

Attention is all you need
no rnn or cnvolution required, iteratively improve the representation oy it self attention mechanism

encoder blocks
- self attention step
- local fully connected layers

input emeddings for the encoder
one hot encoding is ver coars and attention networks needs  emebedic algorithim (general function approximator)  which compresses and produced an embedding and then it produces self attention for each token 

for each token we compute, q,k,v

and allignment between q, and k determine the influence 
(add attention formula here  )