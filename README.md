# RISC-V-CPU-CORE
This repository contains all the code I executed at Makerchip.com to build a RISC-V CPU CORE. The course "Building a RISC-V CPU Core" offered by Linux Foundation through edx is an amazing resource for the same. The processor has a support of base integer RV32I instruction format written in TL- Verilog on Makerchip platform.
# RISC-V Overview
RISC-V (pronounced "risk-five") is an open standard instruction set architecture (ISA) based on established RISC principles.Unlike most other ISA designs, RISC-V is provided under open source licenses that do not require fees to use. RISC-V is also popular for it's simplicity and extensibility and infact RISC stands for Reduced Instruction Set Architecture.
It contains 32 registers and most instructions are read from or written to the register file. RISC-V is based on load-store architecture as load and store instructions tranfers between register file and the memory.
# CPU Microarchitecture

![image](https://github.com/SyedABJ/RISC-V-CPU-CORE/assets/127214057/750021b8-2321-4211-9fb7-c1a7eb654afd)

1.PC Logic
This logic is responsible for the program counter (PC). The PC identifies the instruction our CPU will execute next. Most instructions execute sequentially, meaning the default behavior of the PC is to increment to the following instruction each clock cycle. Branch and jump instructions, however, are non-sequential. They specify a target instruction to execute next, and the PC logic must update the PC accordingly.

2.Fetch
The instruction memory (IMem) holds the instructions to execute. To read the IMem, or "fetch", we simply pull out the instruction pointed to by the PC.

3.Decode Logic
Now that we have an instruction to execute, we must interpret, or decode, it. We must break it into fields based on its type. These fields would tell us which registers to read, which operation to perform, etc.

4.Register File Read
The register file is a small local storage of values the program is actively working with. We decoded the instruction to determine which registers we need to operate on. Now, we need to read those registers from the register file.

5.Arithmetic Logic Unit (ALU)
Now that we have the register values, it’s time to operate on them. This is the job of the ALU. It will add, subtract, multiply, shift, etc, based on the operation specified in the instruction.
Register File Write
Now the result value from the ALU can be written back to the destination register specified in the instruction.
DMem
Our test program executes entirely out of the register file and does not require a data memory (DMem). But no CPU is complete without one. The DMem is written to by store instructions and read from by load instructions.
#Instruction Set Architecture

![image](https://github.com/SyedABJ/RISC-V-CPU-CORE/assets/127214057/db55f71c-fb8c-4540-9605-aad78737a165)
# For Immediates

![image](https://github.com/SyedABJ/RISC-V-CPU-CORE/assets/127214057/faec60ab-44d7-41cf-ac27-e8a274a2ffae)

# Instruction Decode Table

![image](https://github.com/SyedABJ/RISC-V-CPU-CORE/assets/127214057/b2879a33-1b30-442d-b182-8825d4e274ad)



