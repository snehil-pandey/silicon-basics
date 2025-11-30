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

# Control Unit &mdash; The Boss
The Control Unit (*CU*) manages everything inside the CPU.  
It performs a cycle called:  
### Fetch &rarr; Decode &rarr; Execute
### FETCH
CU takes the next instruction from memory (RAM) using PC.
### DECODE
IT breaks the instructions into:  
- operation (add, jump, load, store ...)
- operands (numbers or memory addresses)
### EXECUTE
ALU performs the required action.
This process happens *billions of time per second*.

# Clock &mdash; CPU's Heartbeat
Clock is an electronic pulse generator that ticks at a fixed frequency.  
Examples:  
- 1Ghx = 1 billion ticks per second
- Each tick = a step of computation

Every operation (fetch, decode, execute) happens in sync with the clock pulses.  
Clock speed determines how fast instrutions flow.  

More GHz => more operations per second => faster processing  

# Puttin it all together (full cycle example)
Let's say you run this instrution:  
```asm
ADD R1, R2 -> R0
```
Here is what actually happens inside the CPU:  
### Step 1: Clock Ticks
Start next cycle.
### Step 2: Fetch
- PC contains the address of this ADD instruction
- CU reads instrution from the memory
- Puts it into the IR
### Step 3: Decode
CU analyses:
- Operation: ADD
- Source registers: R1, R2
- Destination: R0
### Step 4: Execute
ALU:
- reads the values of R1 & R2
- add them
- stores the result back in R0
### Step 5: Updates PC
PC = next instruction address.

# How CPU performs basic operations?
* **LOAD** &mdash; move data from RAM to register
  - CU copies data from RAM
  - Puts it in a register
  - Might take multiple clock cycles
 
* **STORE** &mdash; move data from register to RAM
  - CU copies the register value
  - Writes it to memory

* **JUMP** &mdas; change to next instruction
  - CU sets PC to a different address
  - CPU executes a different part of code

* **COMPARE** &mdash; compares teo values & set [flags](https://en.wikipedia.org/wiki/FLAGS_register#:~:text=All%20FLAGS%20registers%20contain%20the%20condition%20codes%2C%20flag%20bits%20that%20let%20the%20results%20of%20one%20machine%2Dlanguage%20instruction%20affect%20another%20instruction)
  - Zero Flag
  - Carry Flag
  - Negative Flag  
These flags are used in if/else or loops

# Inference
Let's try mapping whatever we learnt by understanding the BTS of a simple code:  
```C
a = b + c;
```
CPU performs like:  
1. LOAD b &rarr; R1
2. LOAD c &rarr; R2
3. ADD R1, R2 &rarr; R0
4. STORE R0 &rarr; a

Each step = multiple clock cycles.

# Why understanding CPU matters?
- You can understand why a code is fast/slow
- You can grasp the understanding of assembly
- You understand OS scheduling (if you read further about this)
- You understand compiler optimizations
- You become better at DSA, AI, system design


...there might be much more but I can think of this much only.
