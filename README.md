# 6D Snake Game with Multi-Agent Deep Q-Learning

This project implements a 6-dimensional Snake game using Deep Q-Learning (DQN). It features three agents that navigate a 6D grid environment, compete to consume food, and avoid collisions. The training leverages reinforcement learning, and the visualization is rendered using OpenGL.

## Features

- **6-Dimensional Snake Game Environment**: Each snake moves in a 6D grid space, where food and other snakes dynamically affect the game state.
- **Multi-Agent DQN**: Three independent agents trained with Deep Q-Learning to maximize their scores.
- **OpenGL Visualization**: Real-time 3D rendering of the snake game using OpenGL and Pygame.
- **Training and Testing Pipelines**: Episodes for agent training and evaluation of their learned behavior.
- **Score Plotting**: Visualize training and testing results using Matplotlib.

## Prerequisites

Ensure the following dependencies are installed:

```bash
pip install numpy torch pygame PyOpenGL matplotlib
```

## Project Structure

- `DQN`: Deep Q-Learning neural network model.
- `Snake6D`: Environment class implementing the 6D snake game logic.
- `Agent`: DQN-based agent with replay memory and target network.
- `Visualizer`: OpenGL-based class for real-time game rendering.
- `train`: Function to train agents over multiple episodes.
- `test_agents`: Function to evaluate trained agents.
- `plot_scores`: Function to visualize training and testing scores.

## How to Run

1. **Train Agents**:
   To train the agents, run the `train` function. You can specify the number of episodes as required:

   ```python
   episodes = 1000
   agents, scores_history = train(episodes)
   ```

2. **Test Agents**:
   After training, evaluate the agents using the `test_agents` function:

   ```python
   test_scores_history = test_agents(agents, episodes=10)
   ```

3. **Plot Results**:
   Visualize the training and testing performance:

   ```python
   plot_scores(scores_history, test_scores_history)
   ```

## Gameplay Controls

The game logic is entirely controlled by the trained agents, and no user interaction is required during gameplay.

## Key Parameters

- **Environment**:

  - `GRID_SIZE`: Size of the 6D grid.
  - `DIMENSIONS`: Number of dimensions (6).
  - `N_AGENTS`: Number of agents (3).
  - `N_ACTIONS`: Number of possible actions (12, corresponding to 6 dimensions and 2 directions).

- **DQN**:

  - `LEARNING_RATE`: Learning rate for the optimizer.
  - `EPSILON_START`, `EPSILON_END`, `EPSILON_DECAY`: Exploration parameters.
  - `MEMORY_SIZE`: Replay memory size.
  - `BATCH_SIZE`: Batch size for training.
  - `TARGET_UPDATE`: Interval for updating the target network.

- **Training**:

  - `episodes`: Number of training episodes.
  - `GAMMA`: Discount factor for Q-learning.

## Visualization

The game environment is rendered in 3D using OpenGL. Key features include:

- Each snake is visualized with a distinct color.
- Food is represented as a white cube.
- An enclosing wireframe cube represents the boundaries of the 6D grid.

## Output

- **Training Logs**: Displays episode scores and progress.
- **Score Plots**: Visualizes the scores over time for both training and testing phases.
- **Training Results File**: Saves the plot as `training_results.png`.
-

## Future Improvements

- Enhance reward function for more complex behaviors.
- Introduce cooperative/competitive dynamics among agents.
- Expand visualization for higher dimensions.

## License

This project is open source.

