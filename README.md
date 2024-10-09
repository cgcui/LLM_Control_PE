# Project for Power Electronics Controller Design Based on Large Language Models

## Introduction
This letter is aiming to propose an Large Language Model (LLM) based multi-agent framework for goal oriented control design in power electronics. The framework leverages the reasoning capabilities of LLM and a multi-agent workflow to develop an efficient and autonomous controller design process. The LLM agent is able to understand and respond to high-level instructions in natural language, adapting its behavior based on the engineering specific requirements and constraints from a practical implementation point of view. The efficacy of the proposed framework is demonstrated through a case study on a DC-DC boost converter, highlighting its potential to revolutionize the controller design framework for power electronics field.
![image](https://github.com/user-attachments/assets/2f67e5e4-e265-47e0-8bfe-9851a556efda)

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
This will start simulate the boost converter using the optimized parameters, and generate a chart of the output voltage.

## Key Components
- `ModelDesignAgent`: This agent is responsible for configuring the model based on the design requirements. It reports on the model configuration and provides the model address. (Implemented in `ModelDesignAgent.py`)
- `ObjectiveAgent`: This agent is responsible for defining control objectives and constraints. (Implemented in `ObjectiveAgent.py`)
- `ControlParameterDesignAgent`: This agent is responsible for designing the control parameters. It uses the Particle Swarm Optimization (PSO) algorithm for optimization. (Implemented in `ControlParameterDesignAgent.py`)
- `ControlAlgorithmDesignAgent`: This agent is responsible for designing the control algorithm. It currently implements a Proportional-Integral-Derivative (PID) controller. (Implemented in `ControlAlgorithmDesignAgent.py`)
- `ControlVerificationAgent`: This agent is responsible for verifying the control design. It uses a Functional Mock-up Unit (FMU) model for the simulation of the boost converter. (Implemented in `ControlVerificationAgent.py`)
- `ManagerAgent`: This agent is responsible for managing the workflow and instructing other agents. (Implemented in `ManagerAgent.py`)
- `ConversableAgent`: This agent is responsible for managing the conversation between the user and the assistant. It uses the `autogen` library for this purpose. (Implemented in `ConversableAgent.py`)
- `main.py`: This is the main entry point of the application. It sets up the agents, initiates the conversation, and starts the control design process.
## Group Chat Workflow
The conversation between the agents follows this order:

Human (you): Initiate the design request.
ManagerAgent: Broadcasts design requirements and instructs the ModelDesignAgent.
ModelDesignAgent: Configures the model, reports on it, and provides the model address.
ManagerAgent: Acknowledges the model configuration and instructs the ObjectiveAgent.
ObjectiveAgent: Defines control objectives and constraints.
ManagerAgent: Acknowledges the objectives and instructs the ControlAlgorithmDesignAgent.
ControlAlgorithmDesignAgent: Selects and configures a suitable control algorithm.
ManagerAgent: Acknowledges the control algorithm and instructs the ControlParameterDesignAgent.
ControlParameterDesignAgent: Designs the control parameters using the PSO algorithm.
ManagerAgent: Acknowledges the control parameters and instructs the ControlVerificationAgent.
ControlVerificationAgent: Verifies the controller design and reports the results.
ManagerAgent: Analyzes the verification results and concludes the conversation.
Please adhere to this order and only provide information relevant to your specific task.

## Results
After the optimization is completed, the program will generate a chart of the output voltage over time, saved as 'boost_converter_output.png'. In addition, the console output will display the best parameters and performance evaluation results.

## Video

https://github.com/user-attachments/assets/25c64567-393d-48b0-bc87-1d0396ea27ac


## Contribution
Contributions to this project are welcome. Please follow the standard Git workflow, submit pull requests for review.

License
