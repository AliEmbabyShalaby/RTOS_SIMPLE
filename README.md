
# Simple RTOS Implementation on STM32C8 - Project Report

## Table of Contents

1. **Introduction**
2. **Project Description**
3. **System Design**
   3.1. **Hardware Configuration**
   3.2. **RTOS Configuration**
4. **Implementation**
   4.1. **Scheduler Logic**
   4.2. **LED Tasks**
5. **Usage**
6. **Results**
   6.1. **Red LED**
   6.2. **Green LED**
   6.3. **Blue LED**
7. **Conclusion**
8. **Acknowledgments**

## 1. Introduction

This report details the design and implementation of a simple Real-Time Operating System (RTOS) on an STM32C8 microcontroller to control three LEDs with distinct blinking intervals. The project aims to showcase the functionality of an RTOS in managing tasks with different priorities and timings.

## 2. Project Description

The project focuses on controlling three LEDs (Red, Green, and Blue) with specific blinking intervals:

- Red LED blinks every 1 second.
- Green LED blinks every 2 seconds.
- Blue LED blinks every 5 seconds.

## 3. System Design

### 3.1. Hardware Configuration

The project relies on the STM32C8 microcontroller for controlling the LEDs. The GPIO pins are configured for Red, Green, and Blue LEDs as output pins. Additionally, the SysTick timer is configured to generate interrupts every 1ms.

### 3.2. RTOS Configuration

We implement a simple RTOS framework using SysTick and a scheduler. Tasks are assigned priorities based on their blinking intervals, with higher priority tasks executing more frequently.

## 4. Implementation

### 4.1. Scheduler Logic

The scheduler is responsible for managing the execution of LED tasks. It is called from the SysTick interrupt handler at 1ms intervals. The scheduler logic is based on priority, and tasks are executed when their delay counters reach zero.

### 4.2. LED Tasks

Three tasks are created for the Red, Green, and Blue LEDs, each responsible for toggling their respective LEDs at the specified intervals.

## 5. Usage

To use the system, build and flash the code onto the STM32C8 microcontroller. The SysTick timer generates interrupts at 1ms intervals, invoking the scheduler to manage LED tasks.

## 6. Results

### 6.1. Red LED

The Red LED blinks every 1 second, demonstrating precise timing and task execution.

### 6.2. Green LED

The Green LED blinks every 2 seconds, also showing accurate timing and synchronization with other tasks.

### 6.3. Blue LED

The Blue LED blinks every 5 seconds, confirming the RTOS's capability to manage tasks with various intervals.

## 7. Conclusion

This project successfully implements a simple RTOS on the STM32C8 microcontroller to control LEDs with different blinking intervals. The system leverages SysTick and a scheduler to achieve precise task execution and demonstrate the power of RTOS in real-time applications.
