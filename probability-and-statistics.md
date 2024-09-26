## Probability

Probability is a measure of how likely an event is to occur.

The probability $P$ of an event is expressed at the number of elements in the sample space for which the event occurs over the sample space:

$$P = \frac{\text{event}}{\text{sample space}}$$

The complement of an event is the probability of an event NOT occurring. 

The complement rule states that the probability of an event not happening and the probability of it happening must add up to 1. Therefore:

$$P(A') = 1 - P(A)$$

## Sum of probabilities 

If two events A and B are **disjointed** (that is, if they can't both happen at the same time) then the probability of either of them happening is the sum of its individual chances:

$$P(A \cup B) = P(A) + P(B)$$

when the events can happen at the same time (**joint events**) the sum rule applies:

$$P(A \cup B)= P(A) + P(B) - P(A \cap B)$$

where:
- $P(A \cup B)$ is the probability of either of the events happening (or both)
- $P(A \cap B)$ is the probability of both of them happening

The reason for substracting the intersection is that, otherwise, we end up double-counting the probability of both happening at the same time.


for independent events, the product rule allows us to know the probability of both happening at the same time:


$$P(A \cap B)= P(A) \cdot P(B)$$

There is a more complete version that applies to both dependent and independent events, the general product rule:

$$P(A \cap B)= P(A) \cdot P(B|A)$$

The last part, $P(B|A)$, is read as 'probability of B given A', and represents the conditional probability of B happening if we assume A has already happened. For independent events, $P(B|A) = P(B)$ since, by definition, A happening will not affect the chances of B happening. 

### Bayes theorem

The Bayes theorem is a fundamental formula that describes how to update the probability of a hypothesis based on new evidence.

As a starting example, asuming that: 

- H is the hypothesis of having contracted a disease
- E is the evidence of a positive test

Then we need to update our prior probability $P(H)$, the chance of having the disease, as $P(H|E)$ , the probability of having it after having tested positive.

The new probability, as always, equals the cases where the event happens over all cases. In this case, all cases are $P(E)$ (it's a fact we tested positive) and the ones where the event happens are $P(H\cap E)$, the onces where both testing positive and having the sickness have happened.

$$P(H|E) = \frac{P(H\cap E)}{P(E)}$$

and since $P(A \cap B)= P(A) \cdot P(B)$, then the former can be written as:
 

$$P(H|E) = \frac{ P(H) \cdot P(E|H)}{P(E)}$$

which is the Bayes theorem formula.

In general:

- $H$ is the hypothesis
- $E$ is the evidence
- $P(H|E)$ is the posterior probability - the probability of the hypothesis given the evidence
- $P(E|H)$ is the likelihood - the probability of observing the evidence if the hypothesis is true.
- $P(H)$ is the prior probability - the initial probability of the hypothesis before observing the evidence
- $P(E)$ is the evidence - the total probability of observing the evidence in all possible hypotheses.


When only two mutually exclusive events ($A$ and $A'$) are considered,  the Bayes theorem can be expressed in this longer form:

$$P(A|B) = \frac{P(A) \cdot P(B|A)}{P(A) \cdot P(B|A) + P(A') \cdot P(B|A')}$$


This comes from the Law of total probability, which states that the  probability of an event B is equal to the probability of B and A happening plus the probablity of B and A' happening:

$$P(B) = P(B \cap A) + P(B \cap A')$$

This version is longer, more cumbersome and applies to fewer cases, but it is used in some situations due to increased clarity.

### Random variables

A random variable is a variable whose possible values are the numerical outcome of a random pehonemon. They represent non deterministic outcomes. They are a function that assigns a numerical value to each outcome in the sample space of a random experiment.

Random variables can be either **discrete** or **continuous**.

### Probability distributions

Random variables have associated probability distributions, that describe how probabilities are assigned to all possible outcomes of a random variable.

#### Probability Mass Function (PMF)

In the case of discrete random variables, the probability distribution can be described using the probability mass function. It is a function that provides the probability of each possible discrete value of the variable.

the PMF is denoted as ${p(X = x)}$.

It has to validate two properties:

- all probabilities are 0 or larger: $p(X=x) \geq 0 \text{ for all } x$
- the sum of all probabilities add up to 1: $\sum_xp(X =x) = 1$

For example, for the experiment of throwing a dice, $X$ can be the random variable for the result, and the probability of the dice landing in 1 can be written as:

$$P(X = 1) = \frac{1}{6}$$


The whole mass function is described as:

$$P(X =x) = \frac{1}{6} \text{ for } x \in \{1,2,3,4,5,6\}$$

#### Binomial distribution

If we consider how many ways there are to order a set of numbers, the result follows $k!$, where k is the number of elements in the set. For example, for 5 elements there are $5!$ possible combinations.

 When we want to pick $k$ numbers from a set (of size $n$), then we make a choice with $n$ options following by one with $n-1$ options, all the way to the last one which will have $n-(k-1)$ options. The total possible choices are then:

$$
\frac{n!}{(n-k)!}
$$

however, choices that are the same in different order are double counted. We need to divide by $k!$ to account for that. Thus we have the binomial coefficient formula:

$$
{n\choose k} = \frac{n!}{k! (n-k)!}
$$

which is read 'n choose k' - binomial coefficients.

The binomial distribution makes use of binomial coefficients, accounting for the possibility of each success:

$$
P(X = k) = {n \choose k} p^k(1-p)^{n-k}
$$

where $p^k$ is the probability of getting $k$ successes  and $(1-p)^{n-k}$ is the probability of getting $n-k$ failures.

### Continuous distributions

when dealing with continous values, we can't ask for the probability of one specific value (for example a point in time) since the chance will be 0 (too many values). Therefore, we consider a probability function, whose area must total 1 - just like the sum of probabilities of all possible discrete events added to one with discrete distributions.

The requirements for a probability density function (PDF) $f_X(x)$ are straightforward:

- it is defined for all numbers
- all values should be positive 
- the total area under f_X(x) must equal 1

To calculate the probability of falling in a certain range we calculate the area in that range.

### Cumulative distribution function

Since calculating areas is not always convenient, the cumulative distribution is an alternative.

It uses the concept of cumulative probability: the probability that an event happened before a reference point.

The function starts at 0 and ends at 1 (or limits there, if the domain includes stretches to the infinite). It is denoted by $F_X(x)$ (uppercase F)

### Normal distribution (aka Gaussian)

The normal distribution is bell-shaped. it is centered around the mean ($\mu$) and with a spread equal to the standard deviation ($\sigma$).

When $\mu$ is - and $\sigma$ is 1, the distribution is called the standard normal distribution.