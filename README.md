# Maze Runner Game with Q-Learning

## Table of Contents
1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Prerequisites](#prerequisites)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Implementation Details](#implementation-details)
   - [CustomMazeEnv Class](#custommazeenv-class)
   - [Environment Registration](#environment-registration)
7. [Next Steps](#next-steps)
8. [Contributing](#contributing)
9. [License](#license)
10. [Contact](#contact)
11. [Acknowledgements](#acknowledgements)

## Project Overview

This project implements a basic version of a maze runner game trained using the Q-learning algorithm. The game is built using [OpenAI Gym](https://gym.openai.com/), providing a customized environment for reinforcement learning. The main components include a [custom environment](#custommazeenv-class) and a [usage example](#usage).

## Features

- Custom maze environment with configurable grid size
- Walls and goal position
- Four possible actions: up, right, down, left
- Reward system: positive reward for reaching the goal, small negative reward for each step
- Visualization of the maze and agent's position

## Prerequisites

Before you begin, ensure you have met the following requirements:
* You have installed [Python](https://www.python.org/downloads/) 3.7 or later
* You have a Windows/Linux/Mac machine
* You have installed the required [dependencies](#acknowledgements)

## Installation

To install the Maze Runner Game, follow these steps:

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/maze-runner-qlearning.git
   ```
2. Navigate to the project directory:
   ```
   cd maze-runner-qlearning
   ```
3. Create a virtual environment (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```
4. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

For more details on the project structure and implementation, see the [Implementation Details](#implementation-details) section.

## Usage

To use the Maze Runner Game:

1. Run the main script:
   ```
   python main.py
   ```

2. To use the environment in your own script:

```python
import gym
env = gym.make('CustomMaze-v0')
env.reset()

done = False
while not done:
    action = env.action_space.sample()  # Take random action
    state, reward, done, _ = env.step(action)
    env.render()
    print(f"State: {state}, Reward: {reward}, Done: {done}")
```

This example demonstrates how to interact with the [CustomMazeEnv](#custommazeenv-class) using the Gym interface.

## Implementation Details

### CustomMazeEnv Class

The `CustomMazeEnv` class extends `gym.Env` and implements the following methods:

- `__init__()`: Initializes the environment with a 5x5 grid, sets the goal and wall positions.
- `reset()`: Resets the environment to the initial state.
- `step(action)`: Executes the given action and returns the new state, reward, and done flag.
- `render()`: Visualizes the current state of the maze.

For usage examples, see the [Usage](#usage) section.

### Environment Registration

The custom environment is registered with Gym using the ID 'CustomMaze-v0'. This allows you to create the environment using `gym.make('CustomMaze-v0')` as shown in the [Usage](#usage) section.

## Next Steps

1. Implement the [Q-learning algorithm](https://en.wikipedia.org/wiki/Q-learning)
2. Train the agent to navigate the maze efficiently
3. Experiment with different maze configurations and learning parameters
4. Analyze and visualize the learning progress
5. Implement a more advanced reinforcement learning algorithm (e.g., [Deep Q-Network](https://arxiv.org/abs/1312.5602))

For more information on how to contribute to these next steps, see the [Contributing](#contributing) section.

## Contributing

Contributions to this project are welcome. To contribute:

1. Fork the repository.
2. Create a new branch: `git checkout -b <branch_name>`.
3. Make your changes and commit them: `git commit -m '<commit_message>'`
4. Push to the original branch: `git push origin <project_name>/<location>`
5. Create the pull request.

Alternatively, see the GitHub documentation on [creating a pull request](https://help.github.com/articles/creating-a-pull-request/).

Before contributing, please review the [project features](#features) and [next steps](#next-steps) to align your contributions with the project goals.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the [LICENSE.md](LICENSE.md) file for details.

## Contact
Author- Chirag Sindhwani

If you want to contact me, you can reach me at `sindhwanichirag17@gmail.com`. For bug reports or feature requests, please use the [GitHub issue tracker](https://github.com/yourusername/maze-runner-qlearning/issues).

## Acknowledgements

- [OpenAI Gym](https://gym.openai.com/) for the reinforcement learning framework
- [NumPy](https://numpy.org/) for numerical computing
- [Matplotlib](https://matplotlib.org/) for visualization

These libraries are essential for running the project. Make sure to install them as described in the [Installation](#installation) section.
