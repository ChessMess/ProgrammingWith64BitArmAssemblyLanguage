# Chapter 1 - Getting Started
<p></p>

## Arm Architecural Elements

*Cpu Registers* - part of the cpu circuitry and thus the cpu has instant access to them, unlike memory which incurs transfer time.

The ARM processor is based on load/store architecture which consist of two type of instructions:

<ol>
  <li> Instructions that either <b>load memory</b> into registers or instructions that <b>store data</b> from registers into memory.</li>
  <br>
  <li> Instructions that perform arithmetical or logical operations between two registers.</li>
</ol>

64-Bit program on an ARM processor in user mode has access to 31 general-purpose registers, a program counter (PC), and a combination zero register/stack pointer:

<ol>
  <li> X0-X31 Registers </li>
  <li> SP (XZR) Stack pointer or zero register </li>
  <li> X30 (LR) Link register, holds the return address when calling a function.</li>
  <li> PC Program counter</li>
</ol>
 A register can hold 64 bits of data, but can hold less. 32 bits are often enough. All <b>X</b> registers can be operated on as 32 bit registers by referring tothem as W0-W30 and WZR. When addressed this way the instruction will user the *lower* 32 bits of the register and set the upper bits to zero.

<p><br></p>

## Arm Instruction Format
#### (pg 13)

Each instruction that takes registers can either use the 32 bit W version or the 64 bit Z version. You cannot mix the two register types.

Since there are 32 registers (plus stack pointer SP & zero register XZR), it takes 5 bits to specify a register.

> Bits 0-4 : Rd

> Bits 5-9 : Rn

> Bits 10-15 : imm6

> Bits 16-20 : Rm

> Bit 21 : 0

> Bits 22-23 : Shift

> Bits 24-28 : Opcode

> Bit 29 : Set Condition Code

> Bit 30 : Opcode

> Bit 31 : Bits

When things are running well an instruction takes one clock cycle. An instruction in isolation takes three clock cycles, namely, one to to load instuction from memory, one to decode the instruction, and one to execute the instruction.

## Computer Memory
#### (pg 16)

Instructions are 32 bits in size regardless of the mode the processor is running in (32 v 64).

Loading from memory using a register is called indirect memory addressing.
