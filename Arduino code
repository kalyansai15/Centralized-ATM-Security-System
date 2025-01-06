#include <Arduino.h>
#include <ESP8266WiFi.h>
#include "SinricPro.h"
#include "SinricProSwitch.h"
#define WIFI_SSID "12"
#define WIFI_PASS "12345678"
#define APP_KEY "4e8be083-d73d-4c55-9d22-610ed2bff8b8"
#define APP_SECRET "5feab028-ea77-4936-a37a-f4825415c4f4-f99fcd4c-0ba6-49be-9a83-b8a6785a37d7"
#define DEVICE_ID "660feef33019d22c418749b4“
#define HALL_SENSOR_PIN D1
#define ALARM_PIN D2
#define SYSTEM_LED_PIN D3
#define ALARM_LED_PIN D4
bool securitySystemEnabled = false;
void setupWiFi() {
Serial.println("\r\n[Wifi]: Connecting");
WiFi.begin(WIFI_SSID, WIFI_PASS);
while (WiFi.status() != WL_CONNECTED) {
Serial.print(".");
delay(250);
}
Serial.println("connected!");
13
}
bool onPowerState(String deviceId, bool &state) {
Serial.printf("%s: %s\r\n", deviceId.c_str(), state ? "on" : "off");
securitySystemEnabled = state;
digitalWrite(SYSTEM_LED_PIN, securitySystemEnabled ? HIGH : LOW);
return true;
}
void setupSinricPro() {
SinricProSwitch &mySwitch = SinricPro[DEVICE_ID];
mySwitch.onPowerState(onPowerState);
SinricPro.begin(APP_KEY, APP_SECRET);
SinricPro.restoreDeviceStates(true);
}
void setup() {
Serial.begin(9600);
pinMode(HALL_SENSOR_PIN, INPUT_PULLUP);
pinMode(ALARM_PIN, OUTPUT);
pinMode(SYSTEM_LED_PIN, OUTPUT);
pinMode(ALARM_LED_PIN, OUTPUT);
setupWiFi();
setupSinricPro();
}
void loop() {
SinricPro.handle();
if (digitalRead(HALL_SENSOR_PIN) == HIGH && securitySystemEnabled) {
digitalWrite(ALARM_PIN, HIGH);
14
digitalWrite(ALARM_LED_PIN, HIGH);
delay(1000);
digitalWrite(ALARM_PIN, LOW);
digitalWrite(ALARM_LED_PIN, LOW);
}
}
