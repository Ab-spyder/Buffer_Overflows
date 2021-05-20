# Return-to-libc Attack
## SEED Labs
### Introduction

Return-to-libc Attack is an attack that can bypass an existing protection scheme currently implemented in Linux operating systems. A common way to exploit a buffer-overflow vulnerability is to overflow the buffer with a malicious shellcode, and then cause the vulnerable program to jump to the shellcode that is stored in the stack. To prevent this kind of attacks, some operating systems, such as Fedora Linux, allow system administrators to make stacks non-executable; therefore, jumping to the shellcode will cause the program to fail.

Unfortunately, the above protection scheme is not fool-proof; there exists another type of attacks, the return-to-libc attack, which does not need an executable stack; it does not even use shell code. Instead, it causes the vulnerable program to jump to some existing code, such as the system() function in the libc library, which is already loaded into the memory. 

### Task

A program that has the buffer-overflow vulnerability is given and we need to develop a return-to-libc attack to exploit the vulnerability and gain root privilege. 

### Files

* retlib.c: the vulnerable program
* exploit.py: the skeleton exploit code in Python
* exploit.c: the skeleton exploit code in C

*Credit: Seed Labs - https://seedsecuritylabs.org/Labs_16.04/Software/Return_to_Libc/*
