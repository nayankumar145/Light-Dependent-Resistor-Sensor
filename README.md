This Arduino code is used to turn an LED ON and OFF automatically based on the amount of 
light detected by an LDR (Light Dependent Resistor) sensor. Here’s how it works: 

1.Declaring Variables 

int ldr = 7; // LDR sensor is connected to pin 7

int x; //Variable to store sensor reading

int led = 13; // LED is connected to pin 13

▪ ldr is assigned to pin 7, where the LDR sensor is connected. 

▪ led is assigned to pin 13, where the LED is connected. 

▪ x is used to store the value read from the sensor. 

2.Setup Function (Runs Once at Start) 

void setup()

{ 

Serial.begin(9600); // Starts serial communication to see output 

pinMode(7, INPUT); // Sets pin 7 as input (LDR sensor) 

pinMode(13, OUTPUT); // Sets pin 13 as output (LED) 

}

▪ Serial.begin(9600); starts serial communication so we can see sensor values on the 
Serial Monitor. 

▪ pinMode(7, INPUT); sets pin 7 as an input to read the sensor. 

▪ pinMode(13, OUTPUT); sets pin 13 as an output to control the LED

3.Loop Function (Runs Continuously) 

void loop() 

{ 

x = digitalRead(7); // Reads LDR sensor value(1 or 0)

Serial.println(x); // Prints the value in Serial Monitor

▪ The LDR sensor is read using digitalRead(7);. It gives 1 (HIGH) if it's dark and 0 (LOW) 
if it's bright. 

▪ Serial.println(x); prints the value on the Serial Monitor to check the sensor’s reading. 

4.Controlling the LED 

// If it is dark

if(x == HIGH) 

{ 

digitalWrite(13, HIGH); // Turn ON the LED 

} 

// If it is bright 

if(x == LOW) 

{ 

digitalWrite(13, LOW); // Turn OFF the LED 

} 

} 

▪ If it’s dark, the sensor outputs 1 (HIGH), and the LED turns ON. 
▪ If it’s bright, the sensor outputs 0 (LOW), and the LED turns OFF.
