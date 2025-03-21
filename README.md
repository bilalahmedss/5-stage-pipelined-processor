
# 5-Stage Pipelined Processor to Execute a Single Array Sorting Algorithm

---
## Contributors
- **Hammad Malik**
- **Ahtisham Uddin**

## Project Overview

This project, developed as part of the **Computer Architecture** course, involves the design and implementation of a **5-stage pipelined processor** using **Verilog HDL**. The goal is to convert a single-cycle processor into a pipelined processor to improve performance and efficiency. 

The processor is designed to execute a **Bubble Sort** algorithm, written in **RISC-V assembly**. The project focuses on the application of pipelining techniques to optimize the execution of sorting operations, thereby demonstrating the advantages of pipelined architecture over single-cycle processors.

---
### Key Features:
- **RISC-V Assembly**: Implementation of the **Bubble Sort** algorithm in RISC-V assembly language.
- **Pipelining**: The project transitions a single-cycle processor into a **5-stage pipelined processor**, improving execution efficiency.
- **Hazard Detection**: Implemented hazard detection and control circuitry to handle data hazards during the execution.
- **Forwarding Unit**: Introduced a forwarding unit to manage data dependencies and optimize instruction throughput.

## Installation

1. **Prerequisites**:
   - **Verilog HDL** 
   - **RISC-V Assembly** 


2. **Simulation**:
   - Simulate the processor using your preferred Verilog simulator.
   - Load the RISC-V assembly code for **Bubble Sort** and run it on the simulated pipelined processor.

## Methodology

### Task 1: Implementing the Bubble Sort in RISC-V Assembly

- The **Bubble Sort** algorithm is written in **RISC-V assembly**.
- The assembly code is executed on a **single-cycle processor**, and the algorithm sorts an array of integers.
- Various modifications were made to the processor’s instruction memory, ALU, and data memory to support the sorting operation.

### Task 2: Transitioning to a Pipelined Processor

- We enhanced the **single-cycle processor** by adding pipelining.
- A **5-stage pipeline** was implemented with the following stages:
  1. **IF (Instruction Fetch)**
  2. **ID (Instruction Decode)**
  3. **EX (Execution or Address Calculation)**
  4. **MEM (Memory Access)**
  5. **WB (Write Back)**
  
  Four new pipeline registers were introduced to handle the transition between stages:
  - **IF/ID** Register
  - **ID/EX** Register
  - **EX/MEM** Register
  - **MEM/WB** Register

### Task 3: Hazard Detection and Forwarding

- **Hazard Detection**: The pipelined processor was designed to detect data hazards that could occur when instructions depend on previous instructions.
- **Forwarding Unit**: A forwarding unit was added to handle data forwarding between stages to resolve hazards and optimize the pipeline's performance.

## Code Details

### Code Changes

1. **Instruction Memory**:
   - The instruction memory was modified to include the **Bubble Sort** RISC-V assembly code.
   
2. **Data Memory**:
   - Changes were made to handle the data being sorted and ensure proper memory read and write operations.

3. **Branching Unit**:
   - Added logic to manage branching conditions, essential for handling loops in the sorting algorithm.

### Pipelined Processor

The pipelined processor consists of five stages:
1. **IF/ID Register** stores instruction and program counter values.
2. **ID/EX Register** holds the data read during instruction decode.
3. **EX/MEM Register** holds the results of the execution stage.
4. **MEM/WB Register** holds memory and write-back results.

### Hazard Detection

A **Hazard Detection Unit** was implemented to manage control hazards and ensure that the pipeline does not continue to execute instructions that depend on previous instructions that are not yet available.

### Forwarding Unit

The forwarding unit ensures that the correct data is forwarded through the pipeline stages to avoid stalls and optimize the performance of the processor.

## Results

The pipelined processor executed the **Bubble Sort** algorithm in **800 nanoseconds**, compared to the **990 nanoseconds** taken by the non-pipelined processor.

## Challenges

- Implementing pipelining required modifying multiple stages and registers, which introduced complexity in managing control hazards.
- Implementing the **hazard detection** and **forwarding unit** involved debugging dependencies and managing stalls.
- Despite challenges, the pipelined processor was able to sort an array efficiently and showed significant performance improvement over the non-pipelined processor.

## Conclusion

This project demonstrates the transition from a single-cycle processor to a **pipelined processor**, optimizing the execution of tasks. The implementation of **hazard detection** and **data forwarding** further enhanced the efficiency of the processor.
