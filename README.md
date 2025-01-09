# RISC-V Pipelined Processor with Hazard Unit

This project implements a RISC-V 5-stage pipelined processor, enhanced with a Hazard Unit to address data, control, and memory hazards. By eliminating the need for manually inserted nop instructions, the processor achieves efficient instruction execution at maximum throughput. The implementation includes support for advanced hazard handling techniques such as register forwarding, stalling, and pipeline flushing.

<img width="1284" alt="Screenshot 2025-01-09 at 1 10 09 PM" src="https://github.com/user-attachments/assets/b65d4a59-2dcc-43eb-8772-436ad129bec2" />

## Project Features
- **Hazard Unit**: Automatically handles data, control, and memory hazards.
- **Register Forwarding**: Enables data dependencies to be resolved without stalling the pipeline.
- **Stalling Mechanism**: Safely handles memory read dependencies by pausing the pipeline when necessary.
- **Pipeline Flushing**: Clears instructions for jumps and branches to handle control hazards effectively.
- **Test Cases**: Passes 25 complex test cases, including recursive Fibonacci computation, linked list traversal, and insertion sort.

## Technology Stack
- **RISC-V Assembly**: Used for test case programs.
- **Digital Circuit Design**: Developed using circuit simulation tools.
- **Logisim**: For designing and testing the processor architecture.

## Pipeline Overview
The processor follows a standard 5-stage pipelined architecture:
1. **Instruction Fetch (IF)**: Fetches instructions from memory.
2. **Decode (DR)**: Decodes instructions and reads registers.
3. **Execute (EX)**: Executes operations and computes addresses.
4. **Memory Access (MEM)**: Handles data memory operations.
5. **Write Back (WB)**: Writes results back to registers.

## Key Enhancements
1. **Data Hazards**: Resolved through forwarding from MEM/WB stages to EX stage using MUXes and control logic.
2. **Control Hazards**: Flushed the pipeline to handle branch and jump instructions using updated PC control logic.
3. **Memory Hazards**: Implemented stalling when data dependencies occur with memory reads.

## How to Run
To execute the processor with a program:
1. Open the project07.dig file in [Digital](https://github.com/hneemann/Digital)
2. Load the appropriate .hex file (e.g., decoder-inst-rom.hex) into the instruction memory.
3. Start the simulation and monitor the processor's behavior as it executes the program.

## Future Work
- Optimize hazard handling for more complex programs.
- Extend functionality to support additional RISC-V instructions.
- Improve clock cycle efficiency further for large-scale applications.
- Extend the processor to support simultaneous execution of multiple threads by implementing hardware threads (Hyperthreading). This would involve adding thread-specific registers, thread scheduling mechanisms, and additional hazard handling logic.

## Acknowledgments
This project was completed as part of a course, CS315 at USFCA, focusing on advanced processor design concepts using the RISC-V architecture. Special thanks to Prof. Greg Benson for providing guidance, resources, and insights throughout the project.
