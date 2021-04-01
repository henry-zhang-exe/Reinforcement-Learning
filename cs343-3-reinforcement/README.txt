Michael Rodriguez-Labarca
mr55397

Henry Zhang
hz3953

Question 2 was straight forward. Changing noise to a value of 0.0 makes our agent deterministic and 
thus able to decide the optimal policy in 100 iterations.

Our approach for 3a and 3b was to give the agents very small living rewards of 0.01 so it is not beneficial 
to stay alive, with discount rates of 0.1 so rewards that are steps in the future are not heavily prioritized. 
This made the two agents prioritize the close exit rather than the far one. To make b avoid the cliff, we 
simply added a noise of 0.1 so that there was a chance that b ends up taking the less risky path as opposed 
to the more rewarding risky path. 

3c and 3d were both given discounts of 0.9 so that future rewards can be prioritized, and a higher living 
reward of 0.1 so that it is more rewarding to travel beyond the first exit. We applied the same thought 
process with the noises for c and d as we did for a and b, and it worked the same. 

3e was very easy. Our thought process was to grant our agent a large living reward and a discount rate of 
1, so that way the agent never loses sight of previous rewards gained from living, and the best way to 
maximize the score is to simply exploit the living reward by staying alive.

For question 4, we made a dictionary to store the q values as they corresponded to a state action pair. getQValue
returned the q value for a specific state action pair. computeValueFromQValues returned the maximum q value for
the given state and given possible action from that state. computeActionFromQValues returns the maximum q value 
action for the given state. update is called so that a transistion can occur and the q values
are updated.

For question 5, getAction computes the best action to take. It chooses between a random action or 
an action based on the best probability. We used util.flipcoin to pick randomly between the two options.

For question 6, we began testing on a host of different values before we realized that it was probably not 
possible to achieve this result in 50 iterations. We decided it was not possible to achieve this result, 
as it probably requires more iterations for the epsilon-greedy algorithm to learn the proper policies.

For question 8, we implemented approximate q learning by simply following the formulas given use in the
class handout. We used these formulas to implement getQValue and update.