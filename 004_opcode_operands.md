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

~ Rest for tommorow cuz i'm busy with tests ~
