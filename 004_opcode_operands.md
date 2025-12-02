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

# 3. How CPU actually executes the bits?
Well if you remember seeing the procedure inside our 3<sup>rd</sup> module[<sup>\[1\]](https://github.com/snehil-pandey/silicon-basics/blob/main/003_core_components_CPU.md#:~:text=what%20actually%20happens%20inside%20the%20CPU "Steps involved in CPU").  
*We skip the first and last step of the five CPU steps—it's just for physical repetition. The Control Unit runs Fetch, Decode, and Execute to guide code flow, while the ALU handles actual computations (with CU support).*  

The three steps are:  
**1. Fetch**
- Instruction is loaded from RAM into CPU's instruction register.

**2. Decode**  
- Instruction are split into fields (opcode, operands)
- Control signals are generated.
 
**3. Execute**  
- CPU runs the operation using ALU + registers.

Example instruction:  
```asm
ADD R3, R1, R2
```
Execution steps:
1. Fetch bits from memory.
2. Decode: opcode = ADD, source = R1, R2, destination = R3
3. ALU performs R1 + R2.
4. Result stored in R3.  

That's the entire cycle.  

# A Quick Recap
#### 1. What is the purpose of the opcode inside an instruction?  
**Ans:** It tells the CPU what operation to perform (ADD, SUB, JUMP, etc)  
#### 2. What are operands?
**Ans:** These are the inputs the operation works on: registers, memory addresses or constants  
#### 3. Why do instructions need a fixed binary structure?  
**Ans:** CPU can decode and execute instruction in a single predictable cycle because it'll know where to look for opcode and operands  
#### 4. What do you think ALU does when it recievs any operation?  
**Ans:** It reads, computes and write to the destination.
