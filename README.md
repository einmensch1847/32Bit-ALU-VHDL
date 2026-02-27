

# 32-Bit ALU (Arithmetic Logic Unit) in VHDL

[![VHDL](https://img.shields.io/badge/VHDL-IEEE--1076-blue)](https://en.wikipedia.org/wiki/VHDL)
[![FPGA](https://img.shields.io/badge/Target-Altera-orange)](https://www.intel.com/content/www/us/en/products/programmable.html)

A complete 32-bit Arithmetic Logic Unit (ALU) designed and implemented in VHDL. This project was developed using Altera Quartus II 13.0sp1 and is intended for FPGA implementation. The ALU supports basic arithmetic, logical, and comparison operations.

## ✨ Features

*   **32-bit Architecture**: Full 32-bit data path.
*   **Supported Operations**:
    *   Arithmetic: Addition, Subtraction
    *   Logical: AND, OR, XOR
    *   Comparison: Equality, Less Than (via subtraction)
*   **VHDL Implementation**: Synthesizable VHDL code (IEEE 1076).
*   **Modular Design**: Includes separate components for AND, ADD/SUB, and a final MUX for result selection.
*   **Altera Compatible**: Designed and tested with Altera Quartus II 13.0sp1.

## 🚀 Getting Started

### Prerequisites
*   **Software**: Altera Quartus II 13.0sp1 or later (Intel FPGA tools).
*   **Knowledge**: Basic understanding of VHDL and digital logic design.

### How to Use
1.  Clone the repository:
    ```sh
    git clone https://github.com/einmensch1847/32Bit-ALU-VHDL.git
    ```
2.  Open the project in Quartus II:
    *   Launch Quartus II.
    *   Select `File -> Open Project` and navigate to `32bit_ALU.qpf`.
3.  Compile the project:
    *   Click the **Start Compilation** button or select `Processing -> Start Compilation`.
4.  Review the results:
    *   Check the compilation report in the `output_files/` directory.

## 🧠 Design Overview

The ALU is constructed using three main stages:

1.  **Logical Unit**: Performs bitwise AND, OR, and XOR operations (though currently only AND module is present, others can be added).
2.  **Arithmetic Unit**: Uses an `lpm_add_sub0` megafunction to perform both addition and subtraction based on a select input.
3.  **Output Selector**: A multiplexer (`lpm_mux0`) chooses the final result from the different operation outputs based on a 2-bit opcode.

## ⚙️ Configuration

The ALU operation is controlled by a 2-bit select line. The current mapping is:

| Select (S1 S0) | Operation        | Description       |
| :-------------: | ---------------- | ----------------- |
|      0 0        | A AND B          | Bitwise AND       |
|      0 1        | A + B            | Addition          |
|      1 0        | A - B            | Subtraction       |
|      1 1        | (Reserved)       | For future use    |

## 📈 Future Improvements

*   Add VHDL source files for all logical operations (OR, XOR).
*   Implement a status register with flags (Zero, Carry, Overflow).
*   Add a testbench for simulation in ModelSim/Questa.
*   Extend to support shift operations.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/einmensch1847/32Bit-ALU-VHDL/issues).

## 📧 Contact

Project Maintainer: [Sadra Ghofran](https://github.com/einmensch1847)  
Personal Website: [SadraGhofran.ir](http://sadraghofran.ir)
