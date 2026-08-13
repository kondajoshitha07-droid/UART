UART Communication System using Verilog HDL

📌 Project Overview

This project implements a Universal Asynchronous Receiver-Transmitter (UART) communication system using Verilog HDL.

The design demonstrates serial data transmission and reception, including parallel-to-serial conversion at the transmitter and serial-to-parallel conversion at the receiver. The complete design was developed and functionally verified using Xilinx Vivado through RTL simulation.

🎯 Objectives

- Design a UART communication system using Verilog HDL.
- Implement serial data transmission and reception.
- Generate the required baud-rate timing.
- Convert parallel data into serial data during transmission.
- Convert received serial data back into parallel data.
- Verify UART functionality through simulation in Vivado.

🏗️ System Architecture

                 UART Communication System
                         │
          ┌──────────────┴──────────────┐
          │                             │
     TRANSMITTER                    RECEIVER
          │                             │
   Parallel Data                  Serial Data
          │                             │
       Tx Unit                     Rx Unit
          │                             │
   Parallel → Serial          Serial → Parallel
          │                             │
          └────────── UART Line ─────────┘

🔧 Main Modules

1. TxUnit

The transmitter module accepts parallel data and converts it into a serial UART frame.

It is responsible for:

- Loading the input data.
- Generating the serial output.
- Sending start, data and stop bits.
- Transmitting data according to the generated baud clock.

2. RxUnit

The receiver module receives serial UART data and reconstructs the original parallel data.

It performs:

- Detection of the incoming serial frame.
- Sampling of received data.
- Serial-to-parallel conversion.
- Generation of received data output.

3. SIPO — Serial-In Parallel-Out

The SIPO module shifts incoming serial bits into a register and produces the received data in parallel form.

Serial Input
     │
     ▼
┌───────────────┐
│ Shift Register│
└───────┬───────┘
        │
        ▼
 Parallel Data

4. BaudGenT

The transmitter baud-rate generator produces the timing required by the UART transmitter.

5. BaudGenR

The receiver baud-rate generator generates the sampling timing required by the UART receiver.

The design supports different baud-rate configurations through selectable parameters.

6. DeFrame

The DeFrame module handles the UART frame structure and separates the received data from the serial frame.

7. Duplex

The Duplex module combines the transmitter and receiver functionality to provide two-way UART communication.

8. Testbench

The testbench provides clock, reset and test data to verify the complete UART design through simulation.

📡 UART Frame

The UART transmission follows the standard asynchronous frame structure:

Idle | Start | Data Bits | Stop | Idle
  1     0       8 Bits       1      1

For an 8-bit data configuration:

        ┌────── Data Bits ──────┐
        │                       │
Start   D0 D1 D2 D3 D4 D5 D6 D7   Stop
  0     ───────────────────────     1

💻 Tools Used

Tool| Purpose
Verilog HDL| RTL design
Xilinx Vivado| Design and simulation
Vivado Simulator| Functional verification
GitHub| Version control and project hosting

📁 Project Structure

UART-Communication/
│
├── RTL/
│   ├── TxUnit.v
│   ├── RxUnit.v
│   ├── SIPO.v
│   ├── BaudGenT.v
│   ├── BaudGenR.v
│   ├── DeFrame.v
│   └── Duplex.v
│
├── Simulation/
│   └── DuplexTest.v
│
└── README.md

«File names can be changed to match the exact names in your Vivado project.»

🔄 Working Principle

Transmission

Parallel Data
      ↓
   TxUnit
      ↓
Parallel → Serial
      ↓
UART Serial Line

The transmitter accepts parallel data and sends it serially, one bit at a time, synchronized with the baud-rate clock.

Reception

UART Serial Line
      ↓
    RxUnit
      ↓
Serial → Parallel
      ↓
Received Data

The receiver samples the incoming serial data and reconstructs the original parallel byte.

🧪 Verification

The UART design was verified using a Verilog testbench in Xilinx Vivado.

The simulation verifies:

- Clock generation
- Reset operation
- UART transmission
- UART reception
- Baud-rate timing
- Serial-to-parallel conversion
- Parallel-to-serial conversion
- Correct received data

The expected result is that the data transmitted by the transmitter is correctly reconstructed by the receiver.

📊 Simulation

The Vivado waveform can be used to observe signals such as:

Clock
Reset
Tx Data
Tx Serial
Rx Serial
Rx Data
Baud Clock

A successful simulation should show the transmitted data appearing correctly at the receiver output.

🚀 Future Enhancements

Possible improvements include:

- Configurable baud rates
- Parity-bit support
- Framing-error detection
- Overrun-error detection
- FIFO-based UART buffering
- AXI4-Lite interface
- FPGA hardware implementation
- UART-to-PC communication
- Full-duplex continuous data transfer

📚 Concepts Demonstrated

This project demonstrates practical understanding of:

- Verilog RTL design
- Sequential and combinational logic
- Finite-state/control logic
- Shift registers
- Serial communication
- UART protocol
- Baud-rate generation
- Parallel-to-serial conversion
- Serial-to-parallel conversion
- RTL simulation and verification

