# Banker's Algorithm Operating Systems 

This project uses the Banker's Algorithm in C++ to determine whether a system is in a safe state. If the system is safe, it outputs the safe sequence of process execution; otherwise, it indicates that the system is not in a safe state.


## How to Compile and Run

### Linux/Unix
1. **Compile the Program**:
   ```bash
   g++ bankers_algorithm.cpp -o bankers_algorithm
2. **Run the Program**:
   ```bash
   ./bankers_algorithm
### Input File Format
The program reads the input from a file named `input.txt`. The file must contain the following:

1. **Allocation Matrix**:
   - Rows represent processes.
   - Columns represent resources allocated to each process.

2. **Max Matrix**:
   - Rows represent processes.
   - Columns represent the maximum resources each process might request.

3. **Available Resources**:
   - A single row indicating the currently available instances of each resource.

**Example Input (`input.txt`)**:
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
### Example Output
The program outputs whether the system is in a safe state and, if so, the safe sequence of processes.
The system is in a safe state.
Safe sequence is: P1 -> P3 -> P4 -> P0 -> P2
