# Buffer_Overflow_Vulnerability
## Introduction

Buffer overflow is defined as the condition in which a program attempts to write data beyond the boundaries of pre-allocated fixed length buffers. This vulnerability can be utilized by a malicious user to alter the flow control of the program, even execute arbitrary pieces of code. This vulnerability arises due to the mixing of the storage for data (e.g. buffers) and the storage for controls (e.g. return addresses): an overflow in the data part can affect the control flow of the program, because an overflow can change the return address.

## Task

A program that has the buffer-overflow vulnerability is given and we need to exploit the vulnerability to gain the root privilege. 

## Files

* stack.c (the vulnerable program)
* call_shellcode.c
* exploit.c
* exploit.py