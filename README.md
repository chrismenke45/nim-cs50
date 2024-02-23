This is some practice with reinforcement learning for [CS50's Nim](https://cs50.harvard.edu/ai/2024/projects/2/heredity/). I wrote all the methods for the NimAI class. This class utilizes Q-learning to train the AI. Q learning creats a set of all states with their valid actions ( $Q(s,a)$ ) and gives them a value based on how well the action does, and how good the future actions after it could be. The algorithm used can be summarized in the equation below:

$$ Q_{new}(s,a) = Q_{old}(s,a) + \alpha\left[R + R_f - Q_{old}(s,a)\right] $$

Where:
- $Q_{new}$ is a the new, updated Q value for a state with a given action
- $Q_{old}$ is the old (known) value for a state with a given action
- $R$ is the reward for a given action from a state
- $R_f$ is the future reward possible for an action from state (I used the best possible Q value from the next states possibilities
- $\alpha$ is the learning rate (how much we value new information compared to information we already have)

This equation is used to update the Q values for each state and action everytime the AI makes a move in training. While training, an $\epsilon$-greedy algorithm is used to ensure that some randomness is entered into the model to learn new things.
