
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

## 2016/11/14

- Week5
- Why it's hard to recognize objects?
    - Change in viewpoint
        - Use redundant invariant features (e.g., pair of roughly parallel lines with a red dot between them)
        - Normalization doesn't work - we need to recognize the shape to get the box right

## 2016/11/15

- Week4 Quiz

## 2016/11/16

- Week5
- Convolutional neural networks
    - Replicated features (by convolution - inner product) with shared weights
    - Pooling (subsampling) by averaging or taking max
    - e.g., LeNet5 - used to read ~10% checks in North America
- Significance test between different systems
    - Is 30/10,000 errors better than 40 errors? --> it depends!
    - McNemar test - use cases where one system gets right but the other one gets wrong

## 2016/11/17

- Week5
- Convolutional neural networks for object recognition
    - Why is it difficult? Many classes, many pixels, cluttered scenes, multiple objects
    - ILSVEC-2012 competition on ImageNet - get the correct class in top 5 labels
    - Alex Krizhevsky (University of Toronto, 2012) 16.4% error rate
        - Used sub patches (224x224 out of 256x256) and left-right mirror images
        - Used dropout (half of the hidden units randomly removed)

## 2016/11/18

- Week6
- Stochastic gradient descent
    - Online vs mini-batch
    - Mini-batches are usually better (efficient on GPUs) big mini-batches are more efficient
    - On learning rate
        - Reduce it when error oscillates
        - Increase it when error is falling slowly

## 2016/11/19

- Week5 Quiz

## 2016/11/20

- Week6
- Tricks for mini-batch gradient descent
    - Initialize weights by small random values to break symmetry
    - Initialize weights to be proportional to sqrt(fan-in).
    - Shift the inputs to have zero-mean (e.g., tanh, not sigmoid)
    - Scaling the inputs
    - Decorrelate the input components (e.g., by PCA)

## 2016/11/21

- Week5 Programming Assignment

## 2016/11/22

- Week5 Programming Assignment

## 2016/11/23

- Week6
- The momentum method
    - The gradient increments the previous velocity
    - If the momentum (coefficient for the previous speed term) is close to 1, this is much faster than simple gradient descent
    - A better way: measure the gradient after making the move

## 2016/11/28

- Week6
- Adaptive learning rate for each neuron
    - Start with gain of 1.0
    - g \*= .95 if the sign of gradient is different from last time t
    - g += .05 if the sign is the same
- Variations:
    - Use the agreement between the current gradient and velocity

## 2016/11/29

- Week6
- rprop: using only the sign of the gradient
- rmsprop: keep a moving average of the squared gradient
- There is no simple recipe for learning method
    - depends on architecture, task

## 2016/11/30

- Week7
- Memoryless models for sequences
    - Autoregressive models (predict t from t-1 and t-2)
    - Feed-forward neural nets (predict t from t-1 and t-2 -> hidden unit)
- Compare: linear dynamic systems, HMMs
- A fundamental limitations of HMMs: N hidden states can only remember log(N) bits information
- Think of RNN hidden states as deterministic probability distribution
