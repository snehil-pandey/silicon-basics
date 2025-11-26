# How a Computer works &mdash; From absolute zero

Imagine computer as a company/factory that process information.

Now int this company/factory we have 4 main parts:
1. **CPU &ndash; the employees/workers** &rarr; performs our basic tasks related to logics and calculations
2. **RAM &ndash; the table/desks** &rarr; hoslds our temprorary data while wroking/using it
3. **Storage &ndash; the storeroom/warehouse** &rarr; stores long term information
4. **Input/Output &ndash; Doors/conveyer belt** &rarr; our I/O sources like keyboards, mouse, screen, etc.

## CPU (Central Processing Unit) &mdash; The brain
The CPU is like a very fast version of us which can do only simple tasks like:
- add two numbers
- compare numbers
- move data from one place to other place
- follow instructions one-by-one

It cannot store much  
It cannot think  
It only follows commands  

**CPU's basic actions are called:** *Instructions*  
Example of instructions:
- LOAD value
- ADD value
- STORE value
- JUMP to another instruction

These instruction are very small but the CPU performs *billions per seconds*, which is why computer feels fast.

## 2. RAM (Random Access Memory) &mdash; The Quick Work Memory
CPU is incapable of working directly from storage (too slow).  
So RAM is CPU's **temprorary working space**.

Simple analogy: think RAM as your work table:
- When you open a book &rarr; it's on table; think of opening book as opening computer apps
- When you close a book &rarr; it's on table; think of closing book as closing computer apps
- RAM disappear when power turns off (temporary memory).

RAM is super fast in comparison to storage but it cannot store things forever.

## 3. Storage (HDD/SDD) &mdash; The Warehouse
This the final resting place of data and information which we can store and handle as we want.  
Stuffs like Videos, Photos, Apps, OS, Code, etc. are stored here and RAM just takes a small part of it which is used for working when you open it.  

An SDD is like a fast warehouse.  
An HDD is like a slow warehouse.

When we open something, the OS takes it from storage &rarr; to RAM &rarr; for CPU to work on it.  

## 4. Input/Output (I/O) &mdash; Our Connection with computer
Everything that communicates with the computer is the I/O of the system: Keyboard, Mouse, Camera, Display, USB, etc.  
CPU sends/recives data through these channels.

# Real Question:
## How does electricity become "computation"?
Well since kids we know computer works on binary bits: 0's and 1's where,
- 0 = OFF
- 1 = ON

Everything on computer from videos, photos, programs are stored in patterns of 1's and 0's .  

The CPU contains millions of switches called **transistors**[<sup>\[1\]</sup>](https://en.wikipedia.org/wiki/Transistor#:~:text=Transistor%20as%20a%20switch "Wikipedia Article").  
A transistor can be ON or OFF &rarr; 1 or 0.  

By combining millions of transistors switching ON/OFF extremely fast, CPU performs calculation.

This is the fundamental idea behind computers.

## How programs run (the full cycle)
Let's say you went to open "Notepad".  
**Step 1: You click the icon (input)**  
> This sends an event to OS.

**Step 2: OS finds Notepad in storage**  
> Stored as Binary in SSD/HDD.

**Step 3: OS copies Notepad to RAM**  
> Now CPU can access it quickly.  

**Step 4: CPU starts reading Notepad's instructions**  
> These instruction are like:  
> - Creating window
> - Handle keyboard/mouse.

**Step 5: CPU processes each instruction**  
> Billions per seconds

**Step 6: Output is shown on screen**  
> The monitor renders pixels.

And that's how youu see notepad on your screen.

## How the Operating System fits in
The OS is the **manager** of the entire computer.  
As you have soul(*aka soul*) to operate on the body (*aka computer*)  

It handles:
- Who gets RAM
- Who gets CPU time
- When program can read/write files
- Internet access
- Security & permissions
- Sending output to screen

Without an OS, CPU would either be confuse or couldn't do anything.

Windows, Ubuntu, MacOS &rarr; are OS.  

## How computers communicates
When your browser accesses the internet:
- CPU asks the network card[<sup>\[2\]</sup>](https://ccm.net/computing/networks/9937-what-is-a-network-card/#:~:text=called%20a%20network%20adapter "Article at CCM.net") to send/recieve data
- Data travels in packets (small chunks)
- Packets contains binary 1s and 0s
- Server responds with HTML/CSS/JS
- Browser renders it on screen.
> This might go in-depth to Networking so maybe in future I'll share an article on that

# Recap
- CPU = Fast Worker
- RAM = Working Desk
- Storage = Warehouse
- Binary = Computer's langauage
- Instructions = CPU works with this
- OS = Soul of computer
- Programs = set of instructions
- I/O = Talking with computer

