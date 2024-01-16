# Bipedal Walker Benchmark Performance

## Techniques Used

The **Actor-Critic** architecture in reinforcement learning is built on the following components:

* The **Actor** is a neural network responsible for deciding the actions an agent takes based on
  its current observation of the environment.

* In contrast, the **Critic** is another neural network that evaluates the effectiveness of the chosen actions,
  providing
  feedback to guide the learning process by estimating the value of state-action pairs.

For solving the Bipedal Walker problem, we implemented an Actor-Critic approach, the Twin Delayed DDPG (TD3) algorithm.
Built upon the foundation of DDPG, TD3 incorporates several key refinements to enhance stability, robustness, and
overall performance during
training.

Twin Delayed DDPG (TD3) addresses this challenge through the implementation of three key enhancements:

* Clipped Double-Q Learning: TD3 adopts the concept of "twin" Q-functions, training two instead of one. The smaller of
  the two Q-values is utilized to shape targets, contributing to a more stable learning process.
* Delayed Policy Updates: TD3 strategically reduces the frequency of policy updates (and target network updates)
  compared to Q-function updates. The recommended ratio is one policy update for every two Q-function updates.
* Target Policy Smoothing: TD3 introduces randomness to the target action, making it challenging for the policy to
  exploit errors in the Q-function by introducing a smoothing effect on Q-values during changes in action.

## Evaluation metrics

The **reward** helps the agent figure out what actions are
good (earning positive points) and what actions are bad (resulting in losing points). As the walker accumulates more
points, it
refines its walking skills, learning to
avoid errors and progress more effectively.

![TD3_BipedalWalker-v3_0_training_score.png](results%2FBipedalWalker-v3_run_2%2FTD3_BipedalWalker-v3_0_training_score.png)
![TD3_BipedalWalker-v3_0_training_avg_score.png](results%2FBipedalWalker-v3_run_2%2FTD3_BipedalWalker-v3_0_training_avg_score.png)
![testing_score.png](results%2FBipedalWalker-v3%2Ftesting_score.png)

## Results Analysis

Graphs illustrate the agent's progress in training, displaying rewards per episode, average rewards over time, and test
rewards. The agent quickly reaches a reward of 300 in less than 1000 episodes, showcasing effective training. High and
consistent test rewards indicate the algorithm's adaptability to the Bipedal Walker challenges.

## Agent Behavior

[Bipedal Walker Demo](https://youtu.be/c5yBVdc0XxE?si=2eEyG0A7GKeUksqZ)