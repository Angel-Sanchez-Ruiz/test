
# Report

## Algorithm


The methodology employed in this setting involves [Deep Q-Learning](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf), an algorithm crucial in approximating the optimal action-value function. Additionally, the implementation incorporates fixed Q-targets facilitated by soft updates and experience replay mechanisms. 

This framework aids in stabilizing and enhancing the learning process by reducing the correlation between consecutive experiences, allowing the agent to effectively learn from past experiences and minimize the impact of noisy transitions.

#### Hyperparameters

|Name|Value|
|---|---:|
|Episodes|400|
|Epsilon Start|1.0|
|Epsilon Decay|0.95|
|Epsilon Min|0.01|
|Learning Rate|0.0005|
|Gamma|0.995|
|Tau|0.001|
|Buffer Size|100000|
|Batch Size|64|
|Goal|10.0|

#### Model Architecture

The model uses 4 fully-connected layers:
- state_size -> 256 -> ReLU
- dropout for regularization
- 256 -> 256 -> ReLU
- dropout for regularization
- 256 -> 128 -> ReLU
- dropout for regularization
- 128 -> action_size

A convolutional net is not used as the agent does not learn directly from the pixels of the environment, but a prepared vector of relevant information.

## Performance
The agent solved the environment (by reaching an average reward of 10 over 100 episodes) in **330** episodes, before the 500 episode limit.

### Reward vs. Episode

![reward](https://github.com/Angel-Sanchez-Ruiz/udacity_DRL_Navigation/blob/main/reward_vs_episode.png)

## Improvements

- Using a double DQN
- Using a dueling DQN
- Using a distributional DQN
- Adding more fully-connected layers / more hidden units to the layers
- Design a CNN for the agent
- Training past the target average reward of 10 and seeing what the limit is
