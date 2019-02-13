# Microprocessor
A Microprocessor is a digital device on a chip which can fetch instruction from memory, decode and execute them and give results.

Microprocessor performs three basic things while executing the instruction:
1. Using its Arithmetic and Logical Unit(ALU) to perform basic operations like addition, subtraction, multiplication, deletion and some logical operations.
2. Data in Microprocessor can move from one location to another.
3. It has a Program Counter (PC) register that stores the address of next instruction based on the value of PC, Microprocessor jumps from one location to another and takes decision.

![Microprocessor structure](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/3333-3.png)

## Carry Flag
Carry Flag is a flag when:
1. Two unsigned numbers were added and the result is larger than "capacity" of register where it is saved.
2. Two unsigned numbers were subtracted and we subtracted the bigger one from the smaller one.

## Auxiliary Flag

## Overflow Flag
* When two signed 2's complement numbers are added, overflow is detected if:
  1. both operands are positive and the result is negative, or
  2. both operands are negative and the result is positive.

* When two unsigned numbers are added, overflow occurs if
  1. there is a carry out of the leftmost bit.
