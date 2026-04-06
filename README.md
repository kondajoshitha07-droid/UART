# UART
Designed and simulated a UART protocol module using Xilinx Vivado, enabling serial data transmission and reception through HDL-based implementation. Implemented and verified UART transmitter and receiver logic using simulation tools, ensuring accurate timing, data integrity, and protocol compliance.
📌 Overview

This project implements a UART (Universal Asynchronous Receiver-Transmitter) protocol using Verilog HDL and simulates it entirely in Xilinx Vivado without requiring any physical hardware. The design includes both UART Transmitter (TX) and UART Receiver (RX) modules and verifies communication through simulation.

🎯 Objectives
Design UART protocol using Verilog HDL
Simulate serial communication in Vivado
Understand asynchronous data transmission
Verify TX and RX functionality using testbench
⚙️ Features
UART Transmitter and Receiver modules
Configurable baud rate
Start, data, and stop bit handling
Fully simulated communication (no hardware needed)
Testbench for functional verification
🛠️ Tools & Technologies
Vivado Design Suite
Verilog HDL
Simulation (XSim)
🔧 Design Description
UART Transmitter (TX)
Converts parallel data into serial format
Adds start bit (0) and stop bit (1)
Sends data at defined baud rate
UART Receiver (RX)
Detects start bit
Samples incoming bits
Reconstructs parallel data
🔄 Working Principle

UART communication is asynchronous, meaning no clock signal is shared between transmitter and receiver.

Data frame format:

Start Bit → Data Bits (8-bit) → Stop Bit
Idle state = HIGH
Transmission starts with LOW (start bit)
Ends with HIGH (stop bit)
▶️ Simulation Steps (Vivado)
Open Vivado
Create a new RTL project
Add source files (uart_tx.v, uart_rx.v)
Add testbench file (uart_tb.v)
Run Behavioral Simulation
Observe waveform in XSim
📊 Expected Simulation Output
TX sends serial data bit-by-bit
RX reconstructs the same data
Waveform shows correct timing and bit alignment
🔍 Applications
Serial communication protocol design
Digital system verification
VLSI design learning
FPGA-based communication systems
⚠️ Limitations
Simulation only (no real hardware validation)
Timing depends on simulation constraints
No real-world noise or interference considered
🚀 Future Enhancements
Implement parity bit support
Add configurable data width
Integrate FIFO buffers
Synthesize on FPGA hardware
