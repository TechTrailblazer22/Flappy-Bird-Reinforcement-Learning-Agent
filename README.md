# Flappy bird reinforcement learning agent
This code provides an environment for the game flappy. The game can be run using different agents:
- User agent: User played game
- Random agent: Agent which performs random actions
- DQN agent: Agent using a deep Q-Network for performing actions
Additionally the code provides a procedure for training the DQN agent.

The game and its agent is run by initializing with
```python
game = game.Game("agent_name", "computing devide")
```
To run a game execute the main function
```python
game.main("draw_game")
```
If using a DQN agent one can train with
```python
game.train_agent("draw_game", episodes, batches_per_episode, hyperparameters)
```

## Deep Q-learning setup
The game environment returns three features as input for the DQN agent:
- Horizontal distance to next pipe
- Vertical distance to lower next pipe
- Speed of bird
The returned reward from the environment after performing an action is either 0.1 for surviving or -10 for colliding.__
The whole states/rewards are stored in an experience buffer of the agent used for training after each episode.__
The DQN agents architecture is a neural network with one hidden layer of size 128.

## Required packages
- numpy
- pytorch
- pygame
- tqdm
