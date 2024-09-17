## Probability

Probability is a measure of how likely an event is to occur.

The probability $P$ of an event is expressed at the number of elements in the sample space for which the event occurs over the sample space:

$P = \frac{event}{sample\space space}$

The complement of an event is the probability of an event NOT occurring. 

The complement rule states that the probability of an event not happening and the probability of it happening must add up to 1. Therefore:

$P(A') = 1 - P(A)$

## Sum of probabilities 

If two events A and B are **disjointed** (that is, if they can't both happen at the same time) then the probability of either of them happening is the sum of its individual chances:

$P(A \cup B) = P(A) + P(B)$ 

when the events can happen at the same time (**joint events**) the sum rule applies:

$P(A \cup B)= P(A) + P(B) - P(A \cap B)$

where:
- $P(A \cup B)$ is the probability of either of the events happening
- $P(A \cap B)$ is the probability of both of them happening

for independent events, the product rule allows us to know the probability of both happening at the same time:


$P(A \cap B)= P(A) \cdot P(B)$

There is a more complete version that applies to both dependent and independent events, the general product rule:

$P(A \cap B)= P(A) \cdot P(B|A)$

The last part, $P(B|A)$, is read as 'probability of B given A', and represents the conditional probability of B happening if we assume A has already happened. For independent events, $P(B|A) = P(B)$ since, by definition, A happening will not affect the chances of B happening. 

### Bayes theorem

Bayes theory is a fundamental formula that describes how to update the probability of a hypothesis based on new evidence.

The formula is as follows:

$$P(H|E) = \frac{P(E|H) \cdot P(H)}{P(E)}$$

where:

- $H$ is the hypothesis
- $E$ is the evidence
- $P(H|E)$ is the posterior probability - the probability of the hypothesis given the evidence
- $P(E|H)$ is the likelihood - the probability of observingi the evidence if the hypothesis is true.
- $P(H)$ is the prior probability - the initial probability of the hypothesis before observing the evidence
- $P(E)$ is the evidence - the total probability of observing the evidence in all possible hypotheses.

For an example, asuming that 

- H is the hypothesis of having contracted a disease
- E is the evidence of a positive test
 
then $P(H|E)$, the probability of having the disease having tested positive, equals $P(E|H)$ (the possiblity of testing positive if sick) times $P(H)$ (posibility of contracting the disease in general) divided by $P(E)$ (the posiblity of testing positive in general)

When only two mutually exclusive events ($A$ and $A'$) are considered,  the bayser theorem can be expressed in this longer form:

$$P(A|B) = \frac{P(A) \cdot P(B|A)}{P(A) \cdot P(B|A) + P(A') \cdot P(B|A')}$$

This comes from the Law of total probability, which states that the  probability of an event B is equal to the probability of B and A happening plus the probablity of B and A' happening:

$P(B) = P(B \cap A) + P(B \cap A')$

This version is longer, more cumbersome and applies to fewer cases, but it is used in some situations due to increased clarity.

### Random variables

a random variable is a variable whose possible values are numerical outcome of a random pehonemon. They represent non deterministic outcomes. They are a function that assign a numerical value to each outcome in the sample space of a random experiment.

Random variables can be either **discrete** or **continuous**.

### Probability distributions

Random variables have associated probability distributions, that describe how probabilities are assinged to all possible outcomes of a random variable.

#### Probability Mass Function (PMF)

In the case of discrete random variables, the probability distribution can be described using the probability mass function. It is a function that provides the probability of each possible discrete value of the variable.

the PMF is denoted as ${P(X = x)}$.

It has to validate two properties:

- all probabilities are 0 or larger: $P(X=x) \geq 0$ for all $x$
- the sum of all probabilities add up to 1: $\sum_xP(X =x) = 1$

For example, for the experiment of throwing a dice, $X$ can be the random variable for the result, and the probability of the dice landing in 1 can be written as:

$P(X = 1) = \frac{1}{6}$


The whole mass function is described as:

$P(X =x) = \frac{1}{6}$ for $x \in \{1,2,3,4,5,6\}$