# first-esp8266-sketch
A Hello World sketch for ESP8266 using the Arduino ESP8266 Core

#include<ESP8266WiFi.h>
void setup() {
  // put your setup code here, to run once:
  // the nodemcu will try to connect to the WiFi
  Serial.begin(9600);
  pinMode(D4, OUTPUT);
  WiFi.mode(WIFI_AP_STA);
  WiFi.begin("JioFi2_D0A17D", "dudefood");
  Serial.println("Connecting to the WiFi \n");
  while(WiFi.waitForConnectResult() != WL_CONNECTED){
    Serial.print(" . ");
    delay(500);
  }
  Serial.println("Connected!");
}

// only when it connects, the LED will start blinking
void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(D4, HIGH);
  delay(500);
  digitalWrite(D4, LOW);
  delay(500);
}
