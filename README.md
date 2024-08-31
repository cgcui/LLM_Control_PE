# LLM_Control_PE

Large Language Model-Based Multi-Agent Framework for Goal-Oriented Controller Design in Power Electronics

## Introduction

This project proposes a Large Language Model (LLM)-based multi-agent framework designed to revolutionize goal-oriented controller design in power electronics. By leveraging the reasoning capabilities of LLMs and a multi-agent workflow, this framework automates and optimizes the controller design process. The LLM agents interpret high-level instructions in natural language, adapting their actions according to engineering-specific requirements and practical implementation constraints. The effectiveness of this approach is demonstrated through a case study on a DC-DC boost converter, showcasing its potential to significantly enhance controller design in the field of power electronics.

## Project Structure (Dual-Loop PID Control Boost Example)

- `main.py`: The central script that orchestrates the optimization and simulation process.
- `simulation.py`: Contains functions dedicated to simulating the boost converter's performance.
- `optimization.py`: Implements the Particle Swarm Optimization (PSO) algorithm for controller parameter optimization.
- `utils.py`: Includes various utility functions.
- `controllers.py`: Implements the Proportional-Integral (PI) and PID controllers.

## Dependencies

- Python 3.9 and above
- `autogen`
- `numpy`
- `json`
- `gym`
- `pyfmi`
- `simple-pid`
- `matplotlib`
- `typing_extensions`
- `openai`
- `chainlit`
- `Cython`
- `pyautogen`
- `pybind11`
- `pyswarm`

## Installation

1. Clone the repository:
   ```bash
   git clone [repository URL]
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

To start the optimization process and simulate the boost converter with the optimized parameters, run the main script:

```bash
python main.py
```

The script will simulate the boost converter, optimize the controller parameters, and generate a chart of the output voltage.

## Key Components (Dual-Loop PID Control Boost Example)

- **PI Controller**: The `PIController` class in `controllers.py` implements a Proportional-Integral controller with an anti-windup mechanism.
- **PSO Optimization**: The `PSOOptimizeTool` function in `optimization.py` employs the Particle Swarm Optimization algorithm to fine-tune the PI controller parameters for the voltage and current control loops.
- **Boost Converter Simulation**: The `simulate_boost_converter` function in `simulation.py` uses an FMU model and the optimized PI parameters to simulate the boost converter's performance.
- **Performance Evaluation**: The `evaluate_performance` function in `simulation.py` assesses the control system's performance, including metrics such as settling time, overshoot, and integral error.

## Results

Upon completion of the optimization, the program will save a chart of the output voltage over time as `boost_converter_output.png`. The console will display the optimal parameters and the results of the performance evaluation.

## Citation

If you use this code in your research or project, please cite the following paper:

[1] Chenggang Cui, Jiaming Liu, Junkang Feng, Peifeng Hui, Amer M. Y. M. Ghias, Chuanlin Zhang. (2024). Large Language Models-Based Multi-Agent Framework for Objective-Oriented Control Design in Power Electronics. arXiv preprint arXiv:2406.12628. [Online]. Available: https://arxiv.org/abs/2406.12628

## Coming Soon

We are actively working on enhancing the framework with additional features, improved algorithms, and broader application support. Stay tuned for updates and new releases!

## Video Explanation

For a detailed walkthrough, please refer to the video linked below:

- **Link**: [Video Explanation](https://pan.baidu.com/s/1rQ-10BaxaThU0EGtI2uGMA)
- **Extraction Code**: q5s6

## Contribution

Contributions to this project are highly encouraged. Please adhere to the standard Git workflow and submit pull requests for review.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
