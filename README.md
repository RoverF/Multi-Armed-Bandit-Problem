# Multi-Armed-Bandit-Problem

## Results 
For our solution, we implemented an epsilon-greedy algorithm where epsilon can be specified. This allows us to compare the greedy algorithm (epsilon = 0) to other values of epsilon that allow for exploration. For each step we randomly generate a number from 0 to 1, if this number is less than our epsilon value, we randomly choose an arm. If the number is greater than epsilon, we will pull the arm with the highest estimated value. When epsilon is greater than 0, this method allows us to avoid getting stuck doing the same action. Once the arm has been pulled, we record the reward amount and update our estimated value for the arm pulled. The updated estimate is the old estimate + ((reward - the old estimate) divided by the number of pulls of said arm). This method is then repeated for the specified number of plays. 

## Discussion 
Looking at the plots for average rewards for each n value, we notice that the greedy algorithm (or epsilon = 0) performs the worst over time. This is because it can get stuck on an arm that may be performing okay, but isn’t the best option. Epsilon = 0.1 Improves quickly but then plateaus in all three graphs. This algorithm has a chance to quickly identify the best action, due to the large amount of randomness, but then is limited by the ability to only select the best action 90% of the time. In contrast, an epsilon of 0.01 slowly increases the average reward over time, and trends toward a better average than epsilon = 0.1. The lower randomness means that it takes longer to explore and find the most optimal action, but it will choose this action more often once it is found. The higher the number of arms, the more drastic the difference between the three lines. This difference is due to the increase of options available to the algorithm, meaning it takes more time to sort through them all. 

Now we consider the % optimal action graphs.  For a n of 5 and 10, and epsilon of 0.1, the percentage takes off quickly and then plateaus around 80-85%. This shows that the epsilon = 0.1 algorithm finds the optimal action earlier on, but doesn’t always take it. This is because 10% of the time this algorithm will act randomly. We see that epsilon = 0.01 slowly improves at almost a linear rate in all three graphs. We can theorize that given a greater step count, this epsilon value would reach a higher % of optimal action than epsilon equal to 0.1. In all three graphs. It’s also notable that the performance of the greedy algorithm almost plateaus immediately, getting significantly worse the more arms there are. This is due to the tendency of the greedy algorithm to get stuck doing the same action over and over. 

Based on the results, the most optimal epsilon value depends on the number of plays allowed for our constructed bandit. For fewer plays, a higher epsilon, like epsilon = 0.1, is more likely to perform better. For a large number of steps, a lower epsilon is likely to perform better. It should be pointed out that the variance for our experiment was set to 1, if it had been higher or lower we would have seen a different performance from the algorithms. This may change what epsilon values perform better.

## Exploration and Exploitation
### Exploitation 
Basically greedy algo bc you’re always exploiting your current knowledge 

### Exploration 
Occurs when you have epsilon not equal to 0 bc then you explore other arms past ur current knowledge
 
## Action-Value Methods
Estimated values for each arm, change when arm is pulled 
