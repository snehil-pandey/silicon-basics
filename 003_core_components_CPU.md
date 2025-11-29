# Before we start
We may regard this as one of the most smallest and core knowledge of any system.  
Let's break CPU internals into 4 components:
1. **Registers**: smallest & fastest storage
2. **ALU**: the calculator
3. **Control Unit**: instruction manager
4. **Clock**: the heartbeat ot the CPU

# Registers &mdash; CPU's Ultrafast Scratchpad
Registers are tiny high-speed storage locations inside the CPU.  
- Extremely fast (faster than RAM)
- Hold only small amounts of data (like 8, 16, 32 or 64 bits)
- Use for immediate calculations

Think of them as **pockets that hold numbers** CPU is using right now.  

Examples of regiters:
- **ACC/A (Accumulator)** &mdash; main calculation register
- **PC (Program Counter)** &mdash; holds address of next instruction
- **IR (Instruction Register)** &mdash; current instruction
- **MAR (Memory Data Register)** &mdash; address to read/write
- **MDR (Memory Data Register)** &mdash; data being read/written
- **General Purpose Registers** &mdash; R0, R1, R2 ...

When CPU wants to add `5 + 3`:
- It loads 5 into R0
- It loads 3 into R1
- ALU reads R0 & R1
- Result goes into ACC

Everything happens throught *register &rarr; ALU &rarr; registers*.  

# ALU &mdash; The Calculator
ALU &rarr; Arithmetic Logic Unit  
It is the part which performs:  
* **Arithmetic**
  - addition
  - subtraction
  - multiplication (*via repeated add or hardware multiplier*)
  - division (*via repeated subtract or dedicated unit*)
* **Logic**
  - AND
  - OR
  - NOT
  - XOR
  - Compare

### How ALU adds numbers using binary?  
Example: Add  
`0101 (5) + 0011 (3)`  
ALU does bit by bit addition:  
```
 0101
+0011
-----
 1000 => 8
```
Binary additon uses:  
- Half adders
- Full adders
- Carry bits

These are made of transistor acting as logic gates.

