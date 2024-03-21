![Screenshot 2024-03-21 113255](https://github.com/suganjoker/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/105915942/e5b746f6-3c96-495b-a3a5-3acfb4ced6a8)![image](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/36288975/739cc470-48c8-4873-a730-6319b4afc602)
###  DATE: 21/03/2024

###  NAME: SUGAVARATHAN.L
###  ROLL NO :212221220051
###  DEPARTMENT:INFORMATION TECHNOLOGY
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
![Screenshot 2024-03-21 113309](https://github.com/suganjoker/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/105915942/7b4190b5-9a68-4944-a3b1-478bd71138a6)

FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
![Screenshot 2024-03-21 113255](https://github.com/suganjoker/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/105915942/40f59a77-4169-4317-875e-81e3f47b33a4)

TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 

int enable=6;
int input1=3;
int input2=4;

void setup()
{
  pinMode(enable, OUTPUT);
   pinMode(input1, OUTPUT);
   pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable ,255);
  delay(1000); 
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(5000); 
  digitalWrite(input1, LOW);
   digitalWrite(input2, HIGH);
   delay(5000);
}

### OUTPUT
![Screenshot 2024-03-21 113309](https://github.com/suganjoker/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/105915942/a20bc35f-5160-45a8-9297-6a739bdf719c)
![Screenshot 2024-03-21 113241](https://github.com/suganjoker/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/105915942/ba01a57f-7329-4a05-9984-1efa6f6a8ba8)

### GRAPH AND TABULATION 

![Screenshot 2024-03-21 113229](https://github.com/suganjoker/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/105915942/466e5f4d-fb35-4951-95f5-ae27162606bd)






### RESULTS AND DISCUSSION 

