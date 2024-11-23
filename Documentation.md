# Documentation: Banker's Algorithm for Deadlock Avoidance


This document provides a detailed explanation of the Banker's Algorithm implementation, the purpose of the program, its structure, and functionality.

---

## Algorithm Overview

The **Banker's Algorithm** is a resource allocation and deadlock avoidance algorithm used in operating systems. It checks whether the allocation of resources to processes leaves the system in a safe state.

### Key Concepts

1. **Safe State**:
   - A state is considered safe if the system can allocate resources to each process in some order without leading to a deadlock.
   
2. **Need Matrix**:
   - Represents the remaining resources each process might request to complete its execution:
     ```
     Need[i][j] = Max[i][j] - Allocation[i][j]
     ```
   
3. **Work Vector**:
   - Tracks available resources during the safety check simulation.

4. **Safety Check**:
   - Simulates resource allocation to determine if a safe sequence exists.

---

## Program Structure

The program is structured as follows:

1. **Input Parsing**:
   - Reads the `input.txt` file, which contains:
     - The Allocation matrix.
     - The Max matrix.
     - The Available resources vector.

2. **Need Matrix Calculation**:
   - Computes the `Need` matrix for each process using:
     ```
     Need[i][j] = Max[i][j] - Allocation[i][j]
     ```

3. **Safety Check**:
   - Simulates resource allocation to each process.
   - Checks whether all processes can finish in some order using available resources.

4. **Output**:
   - Prints whether the system is in a safe state.
   - If safe, outputs the safe sequence.

---

## Code Details

### Input File
The program reads from `input.txt`, which contains:

1. **Allocation Matrix**:
   - The resources currently allocated to each process.

2. **Max Matrix**:
   - The maximum resources each process might request.

3. **Available Resources**:
   - The resources currently available in the system.

**Example Input**:
0 1 0
2 0 0
3 0 2
2 1 1
0 0 2

7 5 3
3 2 2
9 0 2
2 2 2
4 3 3

3 3 2

---

### Functions in the Code

1. **`computeRequired`**:
   - Calculates the `Need` matrix for all processes.
   - Parameters:
     - `required`: The matrix to store calculated needs.
     - `maximum`: The Max matrix.
     - `allocated`: The Allocation matrix.

   ```cpp
   void computeRequired(vector<vector<int>>& required, vector<vector<int>>& maximum, vector<vector<int>>& allocated, int numProcesses, int numResources);

2. **`checkSafety`**:
    - Determines if the system is in a safe state.
    - Prints the safe sequence if one exists.
    - Parameters:
      - allocated: The Allocation matrix.
      - required: The Need matrix.
      - available: The Available resources vector
   
   ```cpp
   bool checkSafety(vector<vector<int>>& allocated, vector<vector<int>>& required, vector<int>& available, int numProcesses, int numResources);
   
4.  **`main`**:
    -reads input, calculates the Need matrix, and checks the system's safety.


 **`Limitations`**:
Limitations
  - The program assumes valid input formatting.
  - Edge cases, such as all resources being unavailable, may require additional error handling.

