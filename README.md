# LLM_Control_PE
Large Language Model based Multi-Agent Framework for Goal Oriented Controller Design in Power Electronics


## Introduction
This project aims to optimize the parameters of the boost converter's dual-loop PI controller through automated tools and Particle Swarm Optimization (PSO) algorithm, and simulate to evaluate its performance. The project uses the `autogen` library to manage and automate the optimization process.

## Project Structure (Taking the dual-loop pid control boost in groupchat as an example)
- `main.py`: The main program file, which includes the implementation of the optimization and simulation process.
- `simulation.py`: Contains functions for simulating the boost converter.
- `optimization.py`: Contains the implementation of the PSO optimization tool.
- `utils.py`: Contains utility functions.
- `controllers.py`: Contains the implementation of the pid controller.

## Dependencies
- Python 3.9 and above
- autogen
- numpy
- json
- gym
- pyfmi
- simple-pid
- matplotlib
- typing_extensions
- openai
- chainlit
- Cython
- pyautogen
- pybind11
- pyswarm

## Installation
- Clone the repository:
```git clone [repository URL]```
- Install the required dependencies:
```pip install -r requirements.txt```
- Usage
Run the main script to start the optimization process:
```python main.py```
This will start the PSO optimization, simulate the boost converter using the optimized parameters, and generate a chart of the output voltage.

## Key Components (Taking the dual-loop pid control boost as an example)
- PI Controller
The `PIController` class in `controllers.py` implements a Proportional-Integral controller with anti-integral saturation mechanism.
- PSO Optimization
The `PSOOptimizeTool` function in `optimization.py` uses the Particle Swarm Optimization algorithm to find the optimal PI parameters for the voltage and current control loops.
- Boost Converter Simulation
The `simulate_boost_converter` function in `simulation.py` uses the FMU (Functional Model Unit) model and the optimized PI parameters to simulate the boost converter.
- Performance Evaluation
The `evaluate_performance` function in `simulation.py` evaluates the performance of the control system, including settling time, overshoot, and integral error.

## Optimization Process
- The optimization process uses the PSO algorithm to adjust the parameters of the PI controller. This process includes:
- Initializing the particle swarm
- Evaluating the performance of each particle in each iteration
- Updating the best position of each particle and the global best position
- Repeating this process until the specified number of iterations is reached

## Results
After the optimization is completed, the program will generate a chart of the output voltage over time, saved as 'boost_converter_output.png'. In addition, the console output will display the best parameters and performance evaluation results.

## Video Explanation
Link: https://pan.baidu.com/s/1rQ-10BaxaThU0EGtI2uGMA Extraction code: q5s6

## Contribution
Contributions to this project are welcome. Please follow the standard Git workflow, submit pull requests for review.

License
