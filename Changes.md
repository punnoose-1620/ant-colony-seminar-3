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

---

## Additional Changes and Improvements

### 5. Real-Time Visualization
- Added interactive visualization during optimization process
- **Route Visualization**: Real-time display of best solution routes with different colors for each route
- **Convergence Plot**: Track and display best and average solution quality over generations
- **Route Statistics**: Display detailed statistics for each route (customers, demand, distance, utilization)
- Configurable update frequency to balance visualization quality and performance
- Support for both standard and detailed visualization modes

### 6. Error Handling and Robustness
- **Division by Zero Prevention**: 
  - Added epsilon checks (1e-10) for probability normalization
  - Minimum value thresholds (0.0001) for tau and n_ij to prevent zero values
  - Fallback to uniform distribution when all probabilities are zero
- **Index Error Handling**:
  - Try-except blocks around `np.random.choice()` with fallback mechanisms
  - Validation of route indices before visualization
  - Graceful handling of empty feasible node lists
- **Type Conversion**:
  - Convert numpy int64 types to Python int to avoid type-related issues
  - Ensure routes are stored as lists of integers
- **Visualization Error Handling**:
  - Try-except blocks around visualization code to prevent crashes
  - Continue execution even if visualization fails
  - Suppress runtime warnings for cleaner output

### 7. Enhanced Route Construction Algorithm
- Improved probability calculation with safety checks
- Better handling of edge cases (single feasible node, zero probabilities)
- More robust node selection mechanism
- Validation of route feasibility before adding nodes

### 8. Code Quality Improvements
- Added comprehensive error handling throughout the codebase
- Improved code documentation with detailed docstrings
- Better separation of concerns (visualization, optimization, parsing)
- Warning suppression for cleaner console output
- Enhanced logging and status reporting during optimization

### 9. Visualization Features
- **Interactive Plots**: Real-time updates using matplotlib's interactive mode
- **Color Coding**: Different colors for each route using tab20 colormap
- **Depot Highlighting**: Special marker (red star) for depot location
- **Route Annotations**: Route numbers displayed on the map
- **Convergence Tracking**: Visual representation of algorithm progress
- **Statistics Display**: Text-based route statistics panel