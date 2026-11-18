# Ex. 19: Addition and Subtraction using Embedded C

## Aim
To write an Embedded C program that performs addition and subtraction of two 8-bit numbers using the 8051 microcontroller.

## Apparatus Required
- PC with Keil µVision IDE (C51 compiler)
- Proteus simulator (or an 8051 trainer kit)
- 8051 (AT89C51) microcontroller
- LEDs or a virtual terminal on ports P1 and P2 (for the output display)

## Procedure
1. Open Keil µVision and create a new project.
2. Select the device AT89C51 (Atmel).
3. Create a new C file, type the program, and save it as `addsub.c`.
4. Add the file to the project, then build it (the HEX file is generated).
5. Load the HEX file into the 8051 in Proteus, or burn it to the kit.
6. Run the simulation and observe the output on P1 (sum) and P2 (difference).

## Program
```c
#include <reg51.h>

void main(void)
{
    unsigned char a = 0x09;
    unsigned char b = 0x05;
    unsigned char sum, diff;

    sum  = a + b;    // addition
    diff = a - b;    // subtraction

    P1 = sum;        // show sum on Port 1
    P2 = diff;       // show difference on Port 2

    while(1);        // stop here
}
```

## Output
| Quantity | Hex | Binary | Decimal |
|---|---|---|---|
| a | 09H | 00001001 | 9 |
| b | 05H | 00000101 | 5 |
| Sum (P1) | 0EH | 00001110 | 14 |
| Difference (P2) | 04H | 00000100 | 4 |

## Result
The Embedded C program for addition and subtraction was written, executed and verified on the 8051 microcontroller.

---

## Viva Questions

1. **What is an embedded system?**
   A computer system dedicated to a specific function within a larger device (e.g., washing machine, ATM).

2. **Why use Embedded C instead of assembly?**
   It is easier to write, read, debug and port, and it is still close to the hardware.

3. **What does `#include <reg51.h>` do?**
   It includes the header file that defines the 8051 SFRs and ports (P0 to P3).

4. **What is the size of the 8051 ports?**
   Each port is 8 bits wide (P0, P1, P2 and P3).

5. **What is the data type `unsigned char`?**
   An 8-bit variable with a range of 0 to 255.

6. **Why is `while(1)` used at the end?**
   An embedded program must never exit, otherwise the controller would run into undefined code.

7. **Which register holds the result in assembly?**
   The accumulator (A).

8. **What happens if the result exceeds 255?**
   The 8-bit result overflows and the carry is lost, unless a larger data type such as `unsigned int` is used.

9. **Which compiler/IDE was used?**
   Keil µVision with the C51 compiler.

10. **How is this related to IoT?**
    The same microcontroller logic reads sensors and processes data, and the data is then sent to the cloud by a module such as ESP8266 or NodeMCU.
