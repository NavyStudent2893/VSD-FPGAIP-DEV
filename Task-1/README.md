# VSD-FPGAIP-DEV
# Task-1: RISC-V Environment Setup & Reference Bring-Up

## About This Repository
This repository records my work for **Task-1**, where the goal was to get a working RISC-V development environment up and running and verify that the reference flow behaves as expected.

Rather than jumping into hardware or FPGA work, this task was about building confidence in the **toolchain, execution flow, and system structure** that will be used in later stages.

---

## Environment Used
- **GitHub Codespaces** (primary working environment)
- Reference repository: `vsd-riscv2`
- Lab repository: `vsdfpga_labs`

The setup was intentionally kept aligned with the provided reference environment to avoid configuration-specific issues.

---

## What Was Done

### 1. Reference Environment Setup
- Forked the `vsd-riscv2` repository
- Launched a GitHub Codespace from the fork
- Confirmed that the environment builds and opens cleanly

This ensured a stable and reproducible base before running any programs.

---

### 2. RISC-V Program Bring-Up
- Followed the reference flow inside the Codespace
- Built and ran the provided RISC-V program
- Verified correct execution through console output

This step confirmed that the compiler, simulator, and runtime setup were functioning correctly.

---

### 3. VSDFPGA Labs Validation
- Cloned the `vsdfpga_labs` repository inside the same environment
- Ran the labs that do not require FPGA hardware
- Checked logs/output to confirm successful execution

This helped validate a multi-repository workflow and ensured readiness for upcoming RTL and IP-level tasks.

---

## Understanding & Observations

### Where the RISC-V program lives
The program is located within the samples folder.

---

### How the program runs
The source is compiled using a RISC-V cross-compiler. The resulting binary is loaded into the system’s memory model, from where the core fetches and executes instructions.

---

### Memory and I/O access
The RISC-V core interacts with memory and peripherals using memory-mapped accesses. Instructions, data, and I/O are all handled through the same addressable space.

---

### Where new IP would fit
Any new FPGA IP would naturally sit on the system bus as a memory-mapped block, allowing the RISC-V core to communicate with it using standard load/store operations.

---

## Proof of Execution
- Logs and screenshots showing successful execution of:
  - The RISC-V reference program
  - VSDFPGA lab(s)
- **Photos of the required tool check are included**

---

## Notes
- No FPGA tools were installed at this stage
- Local setup was reviewed using the provided Dockerfile as a reference for required tools
- This task helped clarify system structure before making any modifications

---

## References
- https://github.com/vsdip/vsd-riscv2  
- https://github.com/vsdip/vsdfpga_labs  
