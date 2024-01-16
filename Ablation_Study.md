# Bipedal Walker Ablation Study

## Agent Behavior Progress

[Bipedal Walker at the Beginning of Training - Demo](https://youtu.be/4V1bZqYcNR8)

[Bipedal Walker First Strategy - Demo](https://youtu.be/xZtS8b5WNn8)

[Bipedal Walker Final Solution - Demo](https://youtu.be/c5yBVdc0XxE?si=2eEyG0A7GKeUksqZ)

## Tried Methods

* First Strategy:
    * Generating arrays for all possible movements of each knee and joint with continuous values between [-1, 1].
    * Utilizing a neural network with three dense layers to predict the agent’s next action, focusing on the movement of
      a single knee/joint.
    * Incorporating Q-learning and experience replay for reinforcement learning, but the outcome was not as expected.
* Second Strategy:
    * Generating an array containing possible movements with integer values from {-1, 0, 1}.
    * Using a neural network with three dense layers to predict the agent’s actions, covering the movements of each knee
      and joint.
    * Introducing ε-greedy exploration to balance exploration and exploitation during training. Despite these
      enhancements, this approach also fell short of achieving the desired outcomes.
* Final Solution:
    * Implementing an Actor-Critic approach - the Twin Delayed DDPG (TD3) algorithm.
    * It proved to be the only solution that conducted to the maximum reward of 300 points, in less that 1200 episodes,
      representing a viable solution from a computational point of view.

## Which changes influences the result the most

* Algorithmic Architecture: The adoption of the Actor-Critic model notably influences results in solving the bipedal
  walker problem.

* Hyperparameter Tuning: Changes to key hyperparameters, particularly those governing exploration and exploitation
  strategies, play a significant role in shaping the learning process and achieving success in the task. An illustrative
  example is the discount factor, which determines the importance of future rewards relative to immediate one. This
  parameter has undergone successive increments, reaching a value of 0.99 and amplifying agent's ability to consider
  long-term consequences.