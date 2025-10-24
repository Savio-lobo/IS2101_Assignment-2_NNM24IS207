
# Interrupt Controller Simulation in Java

[![Java](https://img.shields.io/badge/Java-17-blue)](https://www.oracle.com/java/)  
[![License](https://img.shields.io/badge/License-MIT-green)](https://opensource.org/licenses/MIT)

## Overview
This Java program simulates the behavior of an **Interrupt Controller** managing multiple I/O devices with **priorities and masking**. The simulation demonstrates how interrupts are triggered, handled by an **Interrupt Service Routine (ISR)**, and optionally ignored if the device is masked.

The goal is to understand how **priority, masking, and asynchronous ISR handling** work in a real computer system.

## Features
- **Three I/O devices**:  
  - Keyboard (High Priority)  
  - Mouse (Medium Priority)  
  - Printer (Low Priority)  
- **Priority-based interrupt handling**: Higher priority devices are served first.  
- **Interrupt masking**: Devices can be temporarily ignored.  
- **Multithreaded ISR handling**: Interrupts are processed asynchronously using threads.  
- **Execution logging**: ISR executions are recorded with timestamps.  
- **Crisp console output**: Clear display of triggered, handled, or ignored interrupts.  

## How It Works
1. Random interrupts are simulated for the three devices.  
2. The Interrupt Controller checks if the device is masked:  
   - **If masked**: Interrupt is ignored.  
   - **If unmasked**: Interrupt is queued according to priority.  
3. The **ISR handler thread** continuously processes queued interrupts.  
4. After the simulation, a **log of all executed ISRs** is displayed.

## Usage Instructions
1. **Compile** the Java program:
```bash
javac Main.java
````

2. **Run** the simulation:

```bash
java Main
```

3. **Observe output**:

* Triggered interrupts and ISR completions appear in the console.
* Ignored interrupts are also indicated.
* The execution log summarizes all ISRs with timestamps.

## Sample Output

```
KEYBOARD → ISR Completed at 10:33:35
MOUSE → ISR Completed at 10:33:36
PRINTER Ignored (Masked)
...
--- ISR Log ---
10:33:35 - KEYBOARD executed
10:33:36 - MOUSE executed
```

## Code Structure

* **Device enum**: Represents I/O devices and their priorities.
* **InterruptController class**: Manages masking, interrupt queue, ISR handling, and logging.
* **Main class**: Starts ISR handler and simulates random interrupts.


