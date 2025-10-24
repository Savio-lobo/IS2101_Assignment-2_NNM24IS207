# Interrupt Controller Simulation in Java

## Overview
This Java program simulates the behavior of an **Interrupt Controller** managing multiple I/O devices with **priorities and masking**. The simulation demonstrates how interrupts are triggered, handled by an **Interrupt Service Routine (ISR)**, and optionally ignored if the device is masked.

### Features
- **Three I/O devices**:  
  - Keyboard (High Priority)  
  - Mouse (Medium Priority)  
  - Printer (Low Priority)  
- **Priority-based interrupt handling**: Higher priority devices are serviced first.  
- **Interrupt masking**: Devices can be temporarily ignored.  
- **Multithreaded ISR handling**: Interrupts are processed asynchronously.  
- **Execution logging**: Timestamps of ISR executions are recorded.  
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
