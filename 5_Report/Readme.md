# Requirements
## Introduction
The DC motor is an electrical machine with a rotating part termed as a rotor which has to be controlled. For example, consider the DC motor whose speed or direction of rotation of DC motor can be controlled using programming techniques which can be achieved by interfacing with microcontroller.
## Research
To control DC motors using L293 half H-bridge integrated circuit as a motor driver which is controlled by ATmega328 microcontroller. L293 is a quadruple half-H bridge device designed used to drive DC motors and Stepper motors. It is designed to be used with a microcontroller like ATmega328 because microcontroller do not have sufficient output voltage and current to drive motors. The L293 and operating voltage of 4.5V to36V while it can output current of 600mA upto peak current of 1.2A. It can drive two DC motors and one stepper motor(or a two phase motor) at the same time and independently.
## Features
simple and high efficiency rate, DC motor controller that aims to overcome many problems industries and improves the industrial works and the system is based on ATMEGA 328.

## SWOT Analysis
**Strength:**
- The advantage of  DC motor contoller is DC motors are suitable for traction systems for driving heavy loads.

**Weakness:**
- Its operation cost and maintenance cost is very high due to the presence of commutator and brush gear.
- Risk in commutation failure because due to the sparking occurs at brush it cannot operate in explosive and hazard conditions. 

## What
A DC motor controller is needed which will control the speed.
## When
It will be very useful for solving most of the industrial works.
## Who
The industrial workers who used to control the speed of the motor for preferable work in the industry.
## Where
The DC motor controller is enhanced to generate speed based on the machine on the industry at that particular instant.
## How
The DC motor controller is controlled by Atmega328  microcontroller. The designed motor is implemented, tested to ensure its performance and other design factors.
## High level requirements
| ID | Description | Status |
|------| ------| ------|
| HLR1 | When the industrial works to be vary with the speed of motor . | Implemented
| HLR2 | In the traction systems ,the DC motor controller used for driving heavy loads. | Implemented
## Low Level Requirements
| ID | Description | Status |
|-------|------|------|
| LLR1 | The DC motor controller  runs effectively on linux but it will also run equally well on other.  | Implemented
| LLR2 | The Motor runs based on the speed we control.| Implemented 

![image](https://user-images.githubusercontent.com/94506952/144384965-312716c6-d339-40e8-a1ef-33539f05748c.png)

![image](https://user-images.githubusercontent.com/94506952/144385950-f819b529-418b-4a88-b130-5247fa7ce632.png)

https://user-images.githubusercontent.com/94506952/144386281-9173f1b9-07aa-4d1f-925c-02bef5a01654.mp4

## High Level Test plan
| ID    | Description                             | Expected O/P | Actual O/P | Type of Test |
|-------|-----------------------------------------| ------------ | ---------- | ------------ |
| H_01  |DC motor runs                |PASSED        |SUCCESS     | Requirement  |
| H_01  |Speed of the Motor                  |PASSED        |SUCCESS     | Scenario     |
| H_03  | control the speed           |PASSED        |SUCCESS     | Boundary     |

## Low Level Test Plan
| ID    | Description           | Expected O/P | Actual O/P | Type of Test | 
|-------|-----------------------| ------------ | -----------| ------------ |
| L_01  |DC motor speed variation     | PASSED       |SUCESS      | Requirement  |
| L_02  |View the rotation of the motor | PASSED       |SUCESS      | Scenario     |
| L_03  |motor runs at industrial condition | PASSED       |SUCCESS     | Boundary     |

#ifndef F_CPU
#define F_CPU 4000000UL
#endif

#include <avr/io.h>    
#include <util/delay.h>  

#define en12  (1<<PD2)
#define a1 (1<<PD4)
#define a2 (1<<PD5)
 

