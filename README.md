[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/UwCBxwld)
# project1-template
Making a heartbeat LED with delay loops and timers

## Intro
This project results in a "heartbeat" LED flash at of approximately one second. It implements this using a delay loop method (LED1) and interrupt method (LED2).

## Flowchart
Below is a flowchart showing a high level implementation of the delay loop as well as an interrupt.
![flowchart of delay loop and interrupt](/docs/assets/flowchart.svg)

## Delay Loop
The delay loop's inner value (R15) was initially 50000, and was lowered to 45000 as the resulting flash was visibly longer than one second. This value was later changed to 35150 to be closer to one second. The end result is approximately 1s per flash, according to the AD2 oscilloscope.

![LED1 oscilloscope reading](/docs/assets/LED1_oscilloscope.png)
    
## Interrupt
The interrupt uses CCR0, initially set to 32768, with the flash appearing to be close to one second. This value was later changed to 32875 to be closer to one second. The end result is approximately 1s per flash, according to the AD2 oscilloscope.

![LED2 oscilloscope reading](/docs/assets/LED2_oscilloscope.png)

## When to use each method
The delay loop is more suitable for events that occur after a set period of time and is able to wait at a particular point in the program. Interrupts should be used when a trigger requires attention more irregular intervals.
