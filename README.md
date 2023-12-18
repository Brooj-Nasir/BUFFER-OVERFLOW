# BUFFER-OVERFLOW
# Details of Vulnerability and How it arises:

# 1. Buffer OverFlow:
A buffer overflow is a type of software vulnerability that occurs when a program writes more data to a block of memory, or buffer, than it was allocated for. This can lead to the overflow of adjacent memory space, potentially causing unintended consequences such as crashes, unpredictable behavior, or even unauthorized access to the system.
**For Example:** a programmer declares array of integer 4 for string input, as in string last bit is left for null character *\0* .
> | A | B | C | \0|
> 
Now an attacker overflows the buffer by entering 4 characters:
> | W | X | Y | Z |
# 2. Languages vulnerable to this Attack:
- In **Python** and **Java** it is impossible to have buffer overflow because they use Run Time Bounds Checking( How Many Spaces Left.).
- There is performance cost for te extra code we are running everytime we want to insert an element into the array .Thus **C** and **C++** hae chosen not to use runtime bounds checking by default.
# 3. Damage it can cause:
The extra data that the attacker over writes is called **return address**. Following can be the results of buffer overflow:
- Normally buffer overflow results in a ***Program Crash***. Because return address does not points to a valid program instruction.
  > Just like package addressed to a place that does not exists.
- If someone were able to control the contents of return address they can litterally do anything . That return address could be anything:
  1. Reading a file
  2. Dumping a Password
  3. Starting a shell
  4. Eexecuting a malicious code etc.
# 4. How it Arises:
**1. Input with Excessive Data:** An attacker provides input that exceeds the allocated space in a program's buffer. This input can come from user inputs, network data, or other external sources.
>
**2. Lack Of Input Validation:** The program fails to check the size of the input data against the size of the buffer. As a result, when the input is copied into the buffer, it overflows beyond the allocated memory.
>
**3. Overwriting Adjacent Memory:** The excess data overwrites adjacent memory locations, including critical data structures like return addresses, function pointers, or control flags.
>
**4. Exploiting Control Flow:** By carefully crafting the overflowed input, an attacker can manipulate the program's control flow. This might involve overwriting a return address to redirect program execution to a malicious code snippet injected into the input.
>
**5. Executing Malicious Code:** With control flow manipulated, the attacker's injected code gets executed by the compromised program, potentially leading to unauthorized access, privilege escalation, or other malicious actions.
# 5. Goals:
The attacker uses the control gained through the buffer overflow to achieve their specific objectives, which may include stealing sensitive data, compromising the system's integrity, or disrupting normal operation.
# 6. Simple Example:
 Here's a simple example code of buffer overflow.

 https://github.com/Brooj-Nasir/BUFFER-OVERFLOW/blob/main/Example.cpp
