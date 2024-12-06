#  Resource Contention
This project is an implementation of a system based on STM32 that analyze contention problems when tasks accessing shared resource function in a multitasking system and how simple way to eliminate it.

## Description
This project provides practical examples to understand how simple way to eliminate contention problems in the project Shared Data before. Using two FreeRTOS function to enable and disable interrupts, i.e by using taskENTER_CRITICAL() to disable interrupts and taskEXIT_CRITICAL() to enable interrupts. taskENTER_CRITICAL() works by disable interrupts globally, it ensures that no interrupt can preempt the running task while the critical section is being executed. And taskEXIT_CRITICAL() works by restore the interrupt state to what it was before taskENTER_CRITICAL() was called. It re-enables interrupts, allowing the processor to handle pending or new interrupts as they occur. 

## Task Overflow
1. **Initialization**
   - Configure GPIO of LED
   - Create tasks, with red LED task having highest priority
3. **Start Green Flashing Task**
   - Turn the Green LED ON
   - Accessing shared data function
   - Turn the Green LED OFF
   - Delay for 0.5 seconds
5. **Start Red Flashing Task**
   - Turn the Red LED ON
   - Accessing shared data function
   - Turn the Red LED OFF
   - Delay for 0.1 seconds
7. **Access Shared Data**
   - taskENTER_CRITICAL()
   - Check StartFlag
   - If StartFlag up (1), put it down (0)
   - Else show an alert
   - Simulate read/write operation
   - Set back StartFlag up
   - taskEXIT_CRITICAL()

## Hardware Used
- STM32 Microcontroller
- LED
- Resistor
