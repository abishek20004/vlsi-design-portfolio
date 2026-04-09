# Mod-5 Counter (FPGA Implementation)

## Description
This project implements a Mod-5 counter using Verilog HDL. The design counts from 0 to 4 and resets back to 0. A clock divider is used to slow down the input clock for visible LED output on hardware.

## Key Features
- 3-bit sequential counter (0 → 4)
- Automatic reset after count reaches 4
- Clock divider for human-visible output
- Asynchronous reset support

## Design Architecture
The design consists of two modules:

### 1. top_mod5
- Generates a slow clock using a clock divider
- Connects FPGA inputs (clock, reset)
- Drives LED outputs

### 2. mod5_counter
- Implements MOD-5 counting logic
- Increments count on each clock edge
- Resets to 0 after reaching 4

## Simulation Results
The counter produces the expected sequence:

000 → 001 → 010 → 011 → 100 → repeat

Simulation verified using a testbench with clock-driven execution.

## FPGA Implementation
- Board: Artix-7 FPGA
- Tool: Xilinx Vivado
- Bitstream generated successfully
- Output observed on LEDs

## Timing Analysis
- Worst Negative Slack (WNS): 17.335 ns
- Total Negative Slack (TNS): 0 ns
- No timing violations

The design meets timing requirements with positive slack, indicating efficient implementation.

## Resource Utilization
- LUT: ~1%
- Flip-Flops: ~1%
- IO: ~3%

## Hardware Mapping
- Clock → 50 MHz onboard oscillator
- Reset → Push button
- Output → 3 LEDs (binary count)

## Key Learning
- Sequential logic design
- Counter implementation
- Clock division technique
- FPGA design flow (RTL → Synthesis → Implementation → Bitstream)
- Timing and resource analysis
