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

## 2016/12/06

- Week8
- Echo state networks
    - Fix input->hidden and hidden->hidden weights at random values and only learn hidden->output connections
    - Choose connection weights very carefully: use sparse connectivity
    - A sample network: train sine wave from input frequency

## 2016/12/07

- Week9
- How to prevent overfitting
    - By far the best approach: get more (training) data!
    - Other ways: use a model with the right capacity, model averaging, Bayesian
- Controlling capacity: architecture, early stopping, weight-decay, noise
- Cross-validation (N folds are *not* independent!)

## 2016/12/08

- Week9
- Limiting the size of the weights
    - Cost = Error + L2 Penalty Term
- Weight constraints
     - Put limit on length of input vector; scale down if exceeded
- Adding noise to input
    - Equivalent to an L2 penalty
- Adding noise to hidden units
    - Make logistic units binary and stochastic, but backpropagate as usual
    - Does significantly better on test set (unpublished result)

## 2016/12/09

- Week9
- Bayesian approach
    - Coin-tossing example: prior * likelihood -> normalize -> posterior

## 2016/12/10

- Week8 Quiz

## 2016/12/11

- Week9
- The Bayesian interpretation of weight decay
    - Assume output is the net's output value + Gaussian noise
    - MAP: max p(W | D) = min -log p(W | D) = Squared Error + weight decay
    - The weight decay parameter = ratio of two variances
- MacKay's trick to determine weight costs
    - Use the variance of residual errors

## 2016/12/12

- Week9 Quiz

## 2016/12/13

- Week9 Programming Assignment

## 2016/12/14

- Week10
- Bias/Variance decomposition
    - By combining models we can lower variance
    - Make individual predictors disagree
- For cross entropy (discrete predictions), average probability
- Bagging - train different models on different subsets (e.g., random forests)
- Boosting - train weak predictors

## 2016/12/15

- Week10
- Mixture of experts
    - A spectrum of models   nearest neighbors <-> polynomial fit
    - An error function that encourages specialization
        - Squared error times prob. of the manager picking expert i
        - Manager = softmax gating network
    - A better cost function: Gaussian mixture centered at target values

## 2016/12/16

- Week10
- Full bayesian learning is computationally intensive
- Overfitting is a frequentist's illusion? Amount of data shouldn't affect priors
- Approximation: split parameter space into grids, and evaluate p(W | D) in each grid
- Better alternative: Sample weight vectors with p(W | D) -> MCMC

## 2016/12/17

- Week10
- Dropout
    - Randomly omit each hidden unit with 50% prob.
    - A form of (2^H) model averaging
    - At test time: use 'mean net' with outgoing weights from hidden layer halved
- Week10 quiz

## 2016/12/18

- Week11
- Hopfield Nets
    - Binary threshold units with symmetric connections have a global energy function
    - Energy function: states (0, 1) x bias + states (0, 1) x weights between two unites
    - Update one state at a time to find local minimum
