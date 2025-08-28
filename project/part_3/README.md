# Project Part 3: Simple Instruction Set Computer (SISC)

## Overview
This project was part of the ECE:3350 Computer Architecture and Organization course for Spring 2025. It involved implementing a Simple Instruction Set Computer (SISC) using Verilog HDL.

## Goals
Part 3 had two main objectives:
1. **Completed the datapath** by adding data memory and modifying the control unit to support new load/store instructions: LDX, LDA, STX, and STA.
2. **Wrote and tested two machine-language programs**: a bubble sort and a multiply routine, using the SISC architecture.

## Created Files
- `imem.data`: Program used to test all instructions from Parts 1, 2, and new Part 3 instructions.
- `dmem.data`, `sort_data.data`, `mult_data.data`: Example data memory files for testing.
- `dm.v`, `mux4.v`, `mux16.v`: Data memory and multiplexers (not modified).
- All Verilog source files for the SISC processor and control logic.

## Tasks Completed
- Modified `ctrl.v` and `sisc.v` to support LDX, LDA, STX, and STA instructions.
- Added new control lines and modules for load/store operations.
- Simulated the design using the provided `imem.data` to verify correct operation.
- Wrote two machine-language programs:
	- **Bubble Sort**: Sorted a list of N signed 32-bit integers in memory (see `sort_data.data`). Saved instructions as `sort_instr.data`.
	- **Multiply**: Multiplied two unsigned 32-bit integers in memory and stored the 64-bit result (see `mult_data.data`). Saved instructions as `mult_instr.data`.

## Implementation Notes
- STX required two outputs from the register file: Rs (address computation) and Rd (data to write). The `mux4` module and `RB_SEL` control signal were used for this.
- To run the sort or multiply programs, `im.v` and `dm.v` were modified to load the correct instruction/data files.

## Algorithms
- [bubble sort](../part_3/verilog/sort_instr.data)
- [multiplication](../part_3/verilog/mult_instr.data)