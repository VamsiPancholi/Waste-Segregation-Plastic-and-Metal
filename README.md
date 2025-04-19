# Waste-Segregation-Plastic-and-Metal
#include <Servo.h>

Servo tap_servo;
const int Pin=2;
int tap_servo_pin =5;
void setup() {
    pinMode(Pin, INPUT);
    tap_servo.attach(tap_servo_pin);
    Serial.begin(9600);
}
 
void loop() {
    int sensorValue = digitalRead(Pin);
    if(sensorValue==LOW){ 
        Serial.println("it is plastic");
        delay(200);
        tap_servo.write(0);
        delay(600);
        tap_servo.write(90);
        delay(500);
    }
    else{
        Serial.println("it is metal");
        delay(200);
        tap_servo.write(180);
        delay(600);
        tap_servo.write(90);
        delay(500);
        
    }
    delay(3000);
}
