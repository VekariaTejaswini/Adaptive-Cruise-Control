**ADAPTIVE CRUISE CONTROL WITH SIMULINK**
**GROUP 22**
**12TH OF AUGUST 2020**
**KURUKULASURIYA DIAS, JITEN BHATT, TEJASWINI VEKARIA**
**GENG8030-2-R-2020S**
**PROFESSOR ROOZBEH RAZAVI FAR**
***********************************************************************
***********************************************************************
**SOFTWARE REQUIREMENT**
MATLAB and SIMULINK version R2020A
***********************************************************************
**ADDONS REQUIRED FOR THE SYSTEM**
SIMULINK support package for Arduino
************************************************************************
**ARDUINO PINS USED FOR COMPONENTS**

*ULTRASONIC SENSOR - HCSR04*
Trigger - Digital Pin 11
Echo  - Digital Pin 12
------------------------------------------------------------------------
*4 DIGIT 7 SEGMENT DISPLAY - MODEL NO - 5641AS*
A - Digital Pin 2
B - Digital Pin 3
C- -Digital Pin 4
D - Digital Pin 5
E - Digital Pin 6
F - Digital Pin 7
G - Digital Pin 8
D1 - Digital Pin 9
D2 - Digital Pin 10
--------------------------------------------------------------------------
*PUSHBUTTONS*
--NOTE---------------------------------------------------
Set Pushbuttons in Active High format (pulldown switch)
--------------------------------------------------------
SET_SPEED - Analog Pin A5
ADAPTIVE MODE - Analog Pin A3
CANCEL - Analog Pin A2
INCREASE - Analog Pin A1
DECREASE - Analog Pin A0
***************************************************************************
**FUNCTIONS USED AND DESCRIPTION**
*MATLAB FUNCTION BLOCK - SIMULINK**
A matlab function block named 'logic_control' has been used
as the first subsystem to program the Adaptive Cruise Control System.
The function accepts input from all five pushbuttons: Set_Speed, 
Adaptive Mode, Cancel, Increase, and Decrease. The function also
have inputs such as speed_memory,current_speed, cruise, adapt and 
cancel which also have their corresponding outputs. These are stored
in 'data store' blocks where 'data read' and 'data write' blocks are
used to handle their input and output. The function check for pushbuttons
pressed or unpressed, ultrasonic input 'time' and handles the control of
speed and object detection when adaptive cruise mode in turned on. The 
speed and adaptive mode settings are sent to the second subsystem which
is a stateflow chart for LED display control and output.
----------------------------------------------------------------------------
*Stateflow Chart*
The stateflow chart is the second subsystem of the program. This is used to
control the display of the 4 digit 7 segment display and control blink rate 
adaptive mode is turned on. A calculation seperates the tens and units of 
speed and through controlling the segments of each digit displays relevant 
numbers. If the adaptive mode is turned on then the blink rate is increased.
Rate transition blocks and delay commands have been used to control the 
iteration sample time units and delay iteration to achieve this.
***********************************END******************************************
