## Summary of Completed Changes

### 1. VRP File Parser
- Add a function to parse .vrp files and extract:
- Node coordinates
- Demands
- Capacity
- Depot information

### 2. Solution Representation
- TSP: single permutation of all nodes
- VRP: multiple routes, each starting and ending at the depot (node 1)

### 3. Route Construction
- Must respect capacity constraints
- Each route must start and end at the depot
- Cannot exceed vehicle capacity

### 4. Objective Function
- Calculate total distance across all routes
- Ensure all customers are visited exactly once