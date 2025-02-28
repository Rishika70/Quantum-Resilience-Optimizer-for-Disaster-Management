# Quantum Resilience Optimizer for Disaster Management (QRODM)

This project explores resource allocation optimization in disaster management, comparing classical and quantum-inspired approaches.  The goal is to efficiently allocate resources (e.g., medical supplies, personnel, infrastructure) to regions affected by a disaster, maximizing positive outcomes while minimizing costs.

## 1. Classical Approach

A classical method, employing a greedy algorithm and a reinforcement learning loop, simulates resource allocation.

*   **Data:**  A dataset (not included in this simplified demo) would typically provide information about affected regions, resource availability, and potentially historical data.  The provided code simulates this with a small random dataset.
*   **Cost and Reward Matrices:** These matrices quantify the cost of allocating resources and the benefit derived from that allocation. The classical method uses simulated feedback in the form of random noise to the cost matrix, mimicking real-world uncertainties and adjustments.
*   **Greedy Algorithm:**  The resource allocation process begins with a greedy algorithm that iteratively chooses the lowest-cost assignments. This strategy prioritizes immediate gains but may not yield the globally optimal solution.
*   **Reinforcement Learning Loop:** To improve the allocation, the classical method iterates using simulated reinforcement learning. The algorithm updates the cost matrix based on feedback, rewarding beneficial allocations and penalizing poor ones. The goal is to gradually converge towards a more effective allocation.
*   **Metrics:** The performance of the classical algorithm is measured by plotting the total cost over iterations, visualizing reward/cost matrices, charting resource utilization, and displaying the average reward across all iterations.

## 2. Quantum-Inspired Approach (QAOA)

This approach leverages the Quantum Approximate Optimization Algorithm (QAOA) to solve the resource allocation problem.  *Crucially, this demo utilizes a quantum simulator;  true quantum speedup would require a real quantum computer.*

*   **Data:** A simplified, small dataset is used within the code for demonstration purposes.  A larger, real-world dataset would be needed for meaningful problem instances.
*   **Quadratic Program (QP) Formulation:** The resource allocation is expressed as a quadratic program. Binary variables represent whether a resource is assigned to a region, with constraints ensuring each resource and each region receives exactly one assignment.  The objective function seeks to maximize reward minus cost.
*   **QAOA Implementation:** The QAOA algorithm (with the COBYLA optimizer and a `Sampler`) attempts to find the optimal solution for the formulated QP.  The `Sampler` primitive provides samples of possible solutions.
*   **Quantum Simulation:**  The QAOA algorithm is simulated on a classical computer using the AerSimulator.
*   **Metrics:**  Resource allocation results are presented in tabular form, detailing the allocation, cost, and reward for each region. Visualizations such as reward and cost matrices heatmaps, cost vs. reward plots, and total reward/cost calculation provide additional insight.
*   **Sensitivity Analysis:**  Variations in resource capacities and damage levels are introduced to test the robustness of the QAOA approach.
*   **Cost Minimization:** The code also demonstrates an alternative objective: minimizing cost using the same QAOA structure, showing the flexibility of the optimization approach.


## Classical vs. Quantum

The primary difference lies in the optimization engine.  The classical method uses a heuristic-based greedy algorithm augmented by simulated reinforcement learning, while the quantum method utilizes QAOA on a simulator.

*   **Scalability:** For very large and complex scenarios, QAOA holds potential to explore a larger solution space, but this is not fully realized with the small, simulated dataset used in the demo.
*   **Computational Efficiency:** Quantum computers could in principle offer a quantum speedup over classical algorithms, allowing for improved solution quality and runtime for resource-intensive problems. This remains a topic of future investigation given the current limited datasets and computational capability.


## Future Directions

*   **Real Quantum Hardware:** Running the QAOA algorithm on real quantum computers is necessary to validate the performance gains compared to classical methods and explore truly large, complex problems.
*   **Larger Datasets:** Real-world disaster management data requires significantly larger datasets that represent the real-world problems.
*   **Enhanced QAOA Parameters:** The performance of QAOA can depend on algorithm parameters (e.g., optimization method, depth of the circuit). Further experiments with more advanced configurations may improve solution quality.
*   **Hybrid Quantum-Classical Methods:** Investigate methods that combine the strengths of both quantum and classical optimization.
*   **Uncertainty Modeling:** Include more realistic models of uncertainty in the problem, such as probabilistic damage assessments and resource availability.
*   **Integration with Existing Systems:** The developed methods need to be integrated into existing disaster management systems for real-world use.
