# UART
Designed and simulated a UART protocol module using Xilinx Vivado, enabling serial data transmission and reception through HDL-based implementation. Implemented and verified UART transmitter and receiver logic using simulation tools, ensuring accurate timing, data integrity, and protocol compliance
Overview
This project implements UART communication using Verilog HDL and verifies it through simulation in Vivado, without using any hardware.

🎯 Features
UART Transmitter (TX) and Receiver (RX)
Serial data communication
Configurable baud rate
Fully simulation-based
🛠️ Tools Used
Vivado Design Suite
Verilog HDL
XSim Simulator
🔧 Working
UART sends data in frames:
Start Bit → Data (8-bit) → Stop Bit
TX converts parallel to serial
RX converts serial to parallel
▶️ How to Run
Open Vivado
Add source + testbench files
Run Behavioral Simulation
Observe waveform
Expected Simulation Output
TX sends serial data bit-by-bit
RX reconstructs the same data
Waveform shows correct timing and bit alignment
Future Enhancements
Implement parity bit support
Add configurable data width
Integrate FIFO buffers
Synthesize on FPGA hardware
