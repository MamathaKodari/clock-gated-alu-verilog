# Clock Gated ALU using Verilog

## Overview

This project implements a **32-bit Arithmetic Logic Unit (ALU)** with **clock gating technique** using Verilog HDL.
Clock gating is used to **reduce power consumption** by disabling the clock signal when the circuit is not in use.

The design includes three modules:

* Clock Gating module
* Arithmetic Logic Unit (ALU)
* Top module integrating ALU with gated clock

This project can be simulated and synthesized using tools like **Vivado**.


## Features

* 32-bit ALU operations
* Clock gating for low power design
* Modular Verilog implementation
* Suitable for FPGA implementation
* Easy to simulate and extend


## ALU Operations

| Select (sel) | Operation            |
| ------------ | -------------------- |
| 000          | Addition (A + B)     |
| 001          | Subtraction (A - B)  |
| 010          | Bitwise AND          |
| 011          | Bitwise OR           |
| 100          | Bitwise XOR          |
| 101          | Bitwise NOT (A)      |
| 110          | Shift Left (A << 1)  |
| 111          | Shift Right (A >> 1) |


## Module Description

### 1. Clock Gating Module (`clk.v`)

This module generates a **gated clock (gclk)** using the main clock and enable signal.

gclk = clk & enable


When **enable = 0**, the clock is disabled to save power.


### 2. ALU Module (`alu.v`)

Performs arithmetic and logical operations based on the **select input (sel)**.

Inputs:

* `A` – 32-bit operand
* `B` – 32-bit operand
* `sel` – operation selector

Output:

* `Y` – 32-bit result


### 3. Top Module (`alu_clk_gated.v`)

This module connects the **Clock Gating module** and **ALU module**.
The ALU output is stored on the **gated clock edge**.

Inputs:

* `clk` – system clock
* `rst` – reset signal
* `enable` – clock enable
* `A`, `B` – operands
* `sel` – operation selector

Output:

* `Y` – ALU result

## Simulation

The design can be simulated using **Vivado Simulator**.

Steps:

1. Add all Verilog files to the project.
2. Compile the design.
3. Run the testbench.
4. Observe the waveform results.


## Applications

* Low power digital systems
* FPGA based processors
* Embedded system design
* VLSI low power architectures


## Author

MamathaKodari/ECE/Clock_Gated_Alu


## License

This project is open-source and available for educational purposes.
