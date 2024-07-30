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

for independent events, the product rule allows us to know the probability of both happening at the same time:


$P(A \cap B)= P(A) \cdot P(B)$

There is a more complete version that applies to both dependent and independent events, the general product rule:

$P(A \cap B)= P(A) \cdot P(B|A)$

The last part, $P(B|A)$, is read as 'probability of B given A', and represents the conditional probability of B happening if we assume A has already happened. For independent events, $P(B|A) = P(B)$ since, by definition, A happening will not affect the chances of B happening. 