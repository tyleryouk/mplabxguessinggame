 
Figure 7-60
Correct state diagram for the guessing game.
From Digital Design: Principles and Practices, Fourth Edition, John F. Wakerly, ISBN 0-13-186389-4. 02006, Pearson Education, Inc., Upper Saddle River, NJ. All rights reserved.

In this assignment, we will use MPLabX to develop and simulate an assembly language program for the 
PIC microcontroller that plays the guessing game, as described in Section 12.7 of the Wakerly textbook, 5th ed. The assembly language program is to be tested using MPLab to apply the sequence of inputs given below.  
This state machine has 4 inputs and 5 outputs. Students should use the PIC16F84A. The required pin assignments are given in the following table. 
Required Pin Assignments 
Inputs 	Right Outputs 
Function 	PIC 	Function 	PIC 
G1 	RB0 	L1 	RA0 
G2 	RB1 	L2 	RA1 
G3 	RB2 	L3 	RA2 
G4 	RB3 	L4 	RA3 
 	 	ERR 	RA4 
A high output is used to turn on a light while a low output signifies that the light is off. 
Programs should initialize to state S1 and include a delay of ~1.0 second from one state to the next in the rotating light pattern. This delay could be created in different ways, for example, using a simple program loop, or using a timer with or without interrupts. It need not be precise, but should be accurate to ±0.05 seconds. You may choose your processor clock frequency to adjust the state delay. 
The program should be tested using a stimulus workbook (“guess_stimuli_Spring2022.sbs”) that has been posted on Canvas with this assignment. This external stimulus is applied using   	Stimulus  open a stimulus workbook (from icons to the left of the Stimulus window) being sure to “Apply” the stimulus. 
Your solution to this homework should include your documented assembly language code and watch window to demonstrate that your game responds properly to stimulus. This example shows a watch window following the first wrong guess. Your solution should show this watch window following each state change. This can be done most easily by setting breakpoints immediately following each state change in your code, then running the processor, which will automatically stop at each state change. You need to use a processor frequency of 100kHz. 
 
 
Sample Display window following the first wrong guess 
   
Hints and Suggested Approach This general outline can be used. 
Main:  ; start of the main program 
           ; initialize the state machine 
Mloop: ; beginning of one state machine cycle 
            ; compute the next state 
            ; compute new outputs 
            ; delay for ~ 1.0 second – adjust for 1.0 second, state to state goto Mloop 
 
Computation of the next state could potentially follow the approach used in the textbook which is geared for implementation using Verilog and logic hardware. There are other approaches, however, which are more sensible for a byte oriented, general purpose machine such as the PIC. For example, the state could be “one-hot encoded” to match the outputs, and the next-state could be computed using the table look-up or by if-then statements that consider the present state and the inputs. 
