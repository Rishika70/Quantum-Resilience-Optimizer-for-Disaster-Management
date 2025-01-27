# Quantum Resilience Optimizer for Disaster Management (QRODM)

The Quantum Resilience Optimizer for Disaster Management (QRODM) is an innovative solution designed to enhance resource allocation and decision-making in disaster response scenarios. This project leverages the power of Quantum Approximate Optimization Algorithm (QAOA) to solve complex optimization problems in disaster management, where traditional methods may fall short due to the high-dimensionality and complexity of the decision-making space.


## Project Overview

This project explores a hybrid approach to disaster resource allocation, combining classical reinforcement learning simulations with a quantum-inspired optimization using QAOA.  The goal is to efficiently allocate resources to affected regions, minimizing costs and maximizing effectiveness.

**Key Components:**

1. **Classical Resource Allocation Simulation:**  Simulates a reinforcement learning process where an initial resource allocation is iteratively refined based on simulated human feedback (rewards). This classical simulation demonstrates how feedback can improve allocation strategies over time.

2. **Quantum-Inspired Optimization (QAOA):** Utilizes QAOA (implemented on a classical simulator) to directly solve the resource allocation problem formulated as a quadratic program. This section serves as a proof-of-concept for applying quantum optimization techniques to this complex problem.

3. **Visualization and Analysis:**  Visualizations are essential for understanding the results. Heatmaps, bar charts, and scatter plots are employed to illustrate cost matrices, reward distributions, resource usage patterns, and the relationships between rewards and costs.  Sensitivity analysis explores how changes in parameters impact the allocation.


## Setup and Dependencies

To run this code, you'll need the following:

* **Python 3.x**
* **Required Libraries:**
    ```bash
    !pip install qiskit qiskit-aer qiskit-algorithms qiskit-optimization pandas numpy matplotlib seaborn
    ```


## Usage

1. **Prepare Data:** Ensure your data (regions and resources) are in the correct format as described in the code (either Excel or CSV).

2. **Run the Code:** Execute the Python script. The output will display:
    * Allocation Results:  A DataFrame showing the allocation of resources to regions, along with costs and rewards.
    * Visualizations: Heatmaps illustrating the cost and reward matrices, bar charts displaying resource allocation frequencies, and line plots showing the total cost progression in the simulated reinforcement learning.
    * Analysis: Numerical summaries of total reward and cost, as well as sensitivity analyses.


## Quantum Optimization Section

The quantum optimization part employs QAOA on a classical simulator (AerSimulator) to demonstrate the potential of quantum computing.  This part focuses on a simplified dataset and solves a quadratic program to maximize reward minus cost, subject to constraints ensuring each region and resource is allocated only once.

## Future Directions

* **Real Quantum Hardware:** Run the QAOA algorithm on real quantum hardware to compare its performance with the simulated results.
* **Larger Datasets:** Test the algorithms with larger and more realistic datasets to better evaluate scalability.
* **Advanced Optimization Techniques:** Explore other quantum algorithms (e.g., Variational Quantum Eigensolver) or hybrid classical-quantum approaches.
* **Sensitivity Analysis Expansion:** Conduct a more comprehensive sensitivity analysis to identify critical parameters affecting allocation decisions.
* **Real-Time Feedback Integration:** Develop a system to integrate real-time human feedback into the optimization process.


## Contributing

Contributions are welcome! If you encounter issues or have suggestions for improvement, feel free to open an issue or submit a pull request.
