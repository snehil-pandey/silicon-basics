# How instructions are structured (opcode + operands)?
You can say this the foundation of everything a CPU does.  
## 1. CPU speaks one language: Machine Language
A machine instruction is just a **binary pattern** the CPU recognises.  
Every instruction has two parts:  
1. Opcode
- *What to do?*
- Example: ADD, SUB, LOAD, STORE, JUMP
- CPU decodes it by looking at specific bits.

2. Operands
- *With what?*
- Can be registers, memory addresses, or constants.

Examples:
```asm
Opcode (ADD) | Operand1 (R1) | Operand2 (R2) | Destination (R3)
```
The CPU sees this and does:
```mlx
R3 = R1 + R2
```
All this is just bits, like:
```bin
0001 0001 0010 0011
```
But after decoding CPU translates into an ALU operation.  

## Why instructions need a fixed struture?
CPU needs to decode them fast every cycle. So formats are fixed, like:  
- **R-Type**: operations on registers
- **I-Type**: operations on immediate constants
- **J-Type**: jumps

Example R-Type format (*like RISC-V*):  
```asm
[opcode] [funct3] [rd] [rs1] [rs2] [funct7]
```
Each field has it's meaning:  
- opcode &rarr; kind of operation
- funct7/funct3 &rarr; sub-operation (*e.g. ADD vs SUB*)
- rs1/rs2 &rarr; input register
- rd &rarr; output register

