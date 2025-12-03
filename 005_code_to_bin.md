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
**Step 1.** C compiler translates it to Assembly
Assembly is somewhat human readable instrutions:
```asm
MOV R1, #5    ; Load immediate 5 into R1
MOV R2, #3    ; Load immediate 3 into R2
ADD R3, R1, R2; R3 <= R1 + R2 (should be 8)
```

**Step 2.** Assembler converts this to machine code  
Assembly is still not executable, so we need to convert it into something more simpler i.e., Binary:
```bin
00010000 00000001 00000000 00000101
00010000 00000010 00000000 00000011
00000001 00000011 00000001 00000010
```

**Step 3.** Linker combines machine code + libraries &rarr; final .exe file  
This will produce `<filename>.exe`  
This EXE is pure binary that CPU can directly understand.  
