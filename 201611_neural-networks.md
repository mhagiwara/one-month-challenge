
# November 2016

https://www.coursera.org/learn/neural-networks

## 2016/11/1

- Number of synapses in a typical brain = 10^15 (10^11 neurons x 7000 connections)
- Brain damage makes functions (audio, visual, etc.) relocate
- Some simple neural models: linear, binary threshold, rectified linear, sigmoid

## 2016/11/2

- Week1
- Three types of learning task: supervised, reinforcement, unsupervised
- Reinforcement learning is difficult because 1) rewards are delayed and 2) a scalar reward lacks information
- Unsupervised learning has been largely ignored by the community

## 2016/11/3

- Week1
- Types of neural network architectures: feed-forward, recurrent (with loops), symmetrically connected networks
- Boltzmann machines: symmetrically connected networks with hidden units
- Perceptrons: Minsky and Paper (1969) "Perceptrons" showed what they can do and their limitation

## 2016/11/4

- Week2
- Informal proof of perceptron convergence: a "generously feasible" weight vector
    - a weight vector that lies in the feasible region ('correct' side of all training vectors)
    - by a margin = (length the input vector)
- After each update, the squared distance of all those generously feasible weight vectors is always decreased

## 2016/11/5

- Week2
- Limitations of perceptrons
    - XOR (discriminate if feature values are the same or not)
    - In general: different patters that have the same number of pixels on, if we allow translation with wrap-around (Minsky and Papert: "Group Invariance Theorem")

## 2016/11/6

- Week3
- "Multi-layer" neural networks cannot be optimized by perceptron learning algorithm (don't call them "multi-layer" perceptrons)
- Update weights of linear neurons iteratively: the "delta-rule" delta w = learning rate * input * residual.

## 2016/11/7

- Week3
- Online vs batch learning: steepest descent on the error surface vs alternatively zig-zag towards constraints defined by training examples
- For a logistic neuron: delta rule x slope of logistic (y*(1-y))
- Learning by perturbing weights: number of weights (or number of neurons) times less efficient than backpropagation

## 2016/11/8

- Week3
- Outline of backpropagation algorithm:
    - dE/dw(i, j) = dE/dy(j) * dy(j)/dz(j) * dz(j)/dw(i,j)
    - First factor: dE/dy(j) = -(t(j) - y(j))
    - Second factor: dy(j)/dz(j) = y(j) * (1-y(j))
    - Third factor: dz(j)/dw(i,j) = y(i)
- How to update weights: online, full-batch, mini-batch
- Dropout: making NNs more robust by randomly omitting hidden units

## 2016/11/9

- Week3 Quiz

## 2016/11/10

- Week3 Programming Assignment

## 2016/11/11

- Week4
- Learning relational data
    - input: (person1, relationship) -> person2
    - distributed encoding of person1 and relationship as a by-product
- What is a concept?
    - The feature theory <-> The structuralist theory
    - Distributed representation -> many to many mapping between concepts and neurons

## 2016/11/12

- Week4
- Squared error not suited for logistic unit -> cross-entropy (- \sum target * log output)
- Softmax: exp(logit(i)) / \sum j exp(logit(j))
- Language modeling:
    - Problem of the trigram model: does not understand similarities between words
    - Bengio's neural net: input distributed encoding of word t-2 and t-1 -> layer -> softmax

## 2016/11/13

- Week4
- Ways to deal with large number of outputs
    - A serial architecture which takes a candidate word and outputs logit
    - Use a binary tree (with words as leaves), train a prediction vector v, calc 1 - sigmoid(inner product) at every branch
    - (Collobert and Weston, 2008) input between t-2 and t+2, replace word at t randomly
