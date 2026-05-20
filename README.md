# CSE332: 16-bit and 24-bit MIPS Processor Architecture

This repository contains the complete implementation of custom **16-bit** and **24-bit MIPS Processor Architectures** designed in Logisim. Developed as part of the **CSE332 (Computer Architecture)** curriculum, this project showcases the step-by-step construction of a functional Central Processing Unit (CPU) from basic logic gates up to complete datapath and control unit integration.

---

## 🛠️ Project Overview

The project is split into two distinct processor architectures, each demonstrating key hardware concepts such as instruction decoding, register file management, Arithmetic Logic Unit (ALU) design, and memory interfacing.

### 1. 16-bit MIPS Architecture (`16 bit MIPS Architechture.circ`)

* **Word Size:** 16-bit registers and data path.
* **Core Philosophy:** A streamlined, compact MIPS variant optimized for teaching fundamental control signals, structural hazards, and custom instruction formats.

### 2. 24-bit MIPS Architecture (`24 bit MIPS Architechture.circ`)

* **Word Size:** 24-bit registers and data path.
* **Core Philosophy:** An expanded architecture that allows for a larger immediate field and more complex instruction sets, bridging the gap between simplified educational models and industry-standard 32-bit hardware.

---

## 🏗️ Architectural Components

Both CPU architectures are built modularly using sub-circuits within Logisim:

* **Control Unit (CU):** The brain of the processor. It parses the opcode of the current instruction and dynamically generates the exact control signals required for the datapath (e.g., `RegWrite`, `ALUSrc`, `MemRead`, `MemWrite`, `Branch`).
* **Arithmetic Logic Unit (ALU):** Performs core operations such as Addition (`ADD`), Subtraction (`SUB`), Bitwise `AND`, Bitwise `OR`, and Set on Less Than (`SLT`). It also feeds flag signals (like `Zero`) back to the Control Unit for conditional branching.
* **Register File:** A custom multi-register storage array supporting simultaneous dual-register reads and single-register writes on clock edges.
* **Program Counter (PC) & Instruction Memory:** Automatically increments to fetch the next instruction from ROM, or updates to a target address during `jump` or `branch` executions.
* **Data Memory:** Interfaced using Logisim’s RAM module to handle data persistence via Load Word (`LW`) and Store Word (`SW`) equivalent operations.

---

## 💾 Instruction Set Architecture (ISA) & Supported Formats

The processors support three classic MIPS instruction types, scaled appropriately to fit the 16-bit and 24-bit limits:

| Type | Format Fields | Common Instructions | Description |
| --- | --- | --- | --- |
| **R-Type** | `Opcode | Rs | Rt | Rd | Shamt | Funct` | `add`, `sub`, `and`, `or`, `slt` | Register-to-register arithmetic and logical operations. |
| **I-Type** | `Opcode | Rs | Rt | Immediate` | `lw`, `sw`, `beq`, `bne` | Operations involving a constant (immediate value) or memory offset. |
| **J-Type** | `Opcode | Jump Address` | `j` | Unconditional control flow redirection. |

---

## 🚀 Getting Started

### Prerequisites

* **Logisim** (Version 2.7.1 or compatible forks like Logisim-Evolution).
* Java Runtime Environment (JRE) installed on your machine.

### Execution Instructions

1. **Clone the repository:**
```bash
git clone https://github.com/YOUR_USERNAME/CSE332-16-and-24-bit-MIPS-Architecture-.git
cd CSE332-16-and-24-bit-MIPS-Architecture-

```


2. **Open the Circuit:**
* Launch Logisim.
* Go to `File -> Open` and select either `16 bit MIPS Architechture.circ` or `24 bit MIPS Architechture.circ`.


3. **Simulating Programs:**
* Right-click the **Instruction Memory (ROM)** component and select *Edit Contents* to load your custom MIPS machine code.
* Go to `Simulate -> Operating System Clock -> Enabled` (or press `Ctrl + K`) to start execution.
* Adjust the clock frequency (`Simulate -> Tick Frequency`) to observe step-by-step datapath state changes.

