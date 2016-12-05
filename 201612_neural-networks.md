# December 2016

https://www.coursera.org/learn/neural-networks

## 2016/12/01

- Week7
- Equivalence between feed-forward nets and recurrent nets
- Review: backpropagation with weight constraints: compute separately and add up
- Extra issue: train 'initial states' of hidden/output units
- Toy example: binary addition
    - two input units, three fully-connected hidden units, one output
    - it learns four distinct patterns (activity vectors) corresponding to states in FSA
    - double the input: FSA -> square the states, NN -> double the hidden units

## 2016/12/02

- Week7
- Why is it hard to train an RNN
    - Backpropagation is linear! -> gradients shrinks or explode exponentially
    - Four effective ways: LSTM, Hessian Free Optimization, Echo State Networks, Good initialization with momentum
- Long Short Term Memory
    - A linear unit with self-lite, write gate, read gate, keep gate
    - 'We can backpropagate through this circuit because logistics have nice derivatives'
    - Handwriting recognition using LSTM

## 2016/12/03

- Week7 Quiz

## 2016/12/04

- Week8
- Modeling character strings with multiplicative connections
- An obvious recurrent NN:
    - Hidden(t) - (Character(86)+ Hidden(t-1)) -> multiplicative 86x1500x1500
- Multiplicative factors
     - product(weights\*Group b, weights\*Group a)\*weights

## 2016/12/05

- Week8
- (Sutskever et al. 2011) Generating Text with Recurrent Neural Networks
- How to generate character strings?
    - Give it a 'burn-in' sequence
    - Look at the probability distribution for the next character
    - Pick a character randomly from that distribution, and tell the net that's the character
    - Repeat
- Some examples
    - Sheila thrunge -> s  vs  People thrunge -> whitespace
- It can count brackets, generate unknown words that sound very plausible
- Tomas Mikolov et al trained large RNNs on quite large training set
