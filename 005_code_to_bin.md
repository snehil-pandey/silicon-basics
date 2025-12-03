Everything ultimately becomes binary machine instruction that machine can understand and execute. The C, Java, C++, Python, Ruby, JS... ultimately ends as **machine code** inside CPU.  

# Why we need conversion?
The reason is very simple we need something that is easy for us to understand and computer understands only *machine code*, which is binary instruction:  
```bin
10110100 00011100 11001100
```
So we need tools that converts the code to machine understandable format.  
*Now, if you ask why so it's because we have already achieved something called **High Level Language***
These languages use tools like:  
- Compiler
- Interpreter
- JIT (Just in time compiler)
- Assembler
- Linker

Let's cover it one-by-one.

# What happens when you write something in C language?
Remember C is a Compiled language => uses **Compiler**  

Example:
```C
int x = 5 + 3;
```
#### **Step 1.** C compiler translates it to Assembly
Assembly is somewhat human readable instrutions:
```asm
MOV R1, #5    ; Load immediate 5 into R1
MOV R2, #3    ; Load immediate 3 into R2
ADD R3, R1, R2; R3 <= R1 + R2 (should be 8)
```

#### **Step 2.** Assembler converts this to machine code  
Assembly is still not executable, so we need to convert it into something more simpler i.e., Binary:
```bin
00010000 00000001 00000000 00000101
00010000 00000010 00000000 00000011
00000001 00000011 00000001 00000010
```

#### **Step 3.** Linker combines machine code + libraries &rarr; final .exe file  
This will produce `<filename>.exe`  
This EXE is pure binary that CPU can directly understand.  

# What if you code in Python?
Well then remember Python is interpreted language => uses **Interpreter**  
Example:  
```py
x = 5 + 3
```
#### **Step 1:** Python compiler converts code into Bytecode  
Bytecode is not CPU code.  
It's instructions for **Python Virtual Machine (PVM)**  
Example bytecode:  
```bytecode
LOAD_CONST 5
LOAD_CONST 3
BINARY_ADD
STORE_NAME x
```

#### **Step 2:** Interpreter executes bytecode
The interpreter reads bytecode and performs operations one-by-one.  
No final EXE is generated.  

*Python is interpreted, not compiled to machine code. Even though we have mentioned compiler it's within the interpreter.*

# What if you are the ultimate nerd and use Java?
> PS: Don't worry I'm also the same type of nerd

Remember Java is hybrid: Compiled + Interpreted + JIT

Example:  
```java
int x = 1 + 2;
```
#### **Step 1.** Java Compiler converts to Bytecode (for JVM)  
```bytecode
iload_1
iload_2
iadd
istore_3
```
#### **Step 3.** JVM Interpreter runs the bytecode
At runtime, the JVM interpreter reads the bytecode sequentially, simulating execution on the host machine. It pushes/pops values on the stack, performs operations, and handles the virtual machine's memory model (heap, stack, etc.). This is portable but slower for simple code.  
#### **Step 3.** JIT compiler converts *hot code* to Machine Code  
Hot code = code that runs repeatedly (loops, heavy functions).  
JIT optimizes it during runtime and creates fast machine code.  

*This hybrid approach (interpret + JIT) makes Java "write once, run anywhere" while achieving near-C performance for hot paths.*

# Javascript?
Remember browser related codes use JIT.  
Modern JS engine (V8, SpiderMonkey) do this:  
1. Parse JS
2. Produce bytecode
3. JIT compiles heavy parts into machine code
4. Optimize on the fly.

JS is also not puerly interpreted anymore.  

~ few more stuffs for tomorrow ~
