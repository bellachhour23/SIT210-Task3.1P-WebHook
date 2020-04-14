# Light-Sensor

int led = A5;
int lightSensor = A0;
int analogValue;

void setup() 
{
    pinMode(led, OUTPUT);
}

void loop() 
{
    digitalWrite(led, HIGH);
    
    String light = String(analogRead (lightSensor));
    Particle.publish("light", light, PRIVATE);
    delay(30000);
    
    digitalWrite(led, LOW);
    delay(30000);
}
