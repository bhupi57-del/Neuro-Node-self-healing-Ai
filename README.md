# Neuro-Node-self-healing-Ai
#define BLYNK_TEMPLATE_ID "TMPL3NvbDRC_c"
#define BLYNK_TEMPLATE_NAME "keshav pandat new"
#define BLYNK_AUTH_TOKEN "ETQplm_sLP52atTXo9EQG1EgL3AsXfbR"

#define BLYNK_PRINT Serial

#include <WiFi.h>
#include <WiFiClient.h>
#include <BlynkSimpleEsp32.h>
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

// iPhone Personal Hotspot Details
char ssid[] = "iPhone";
char pass[] = "keshav1234";

// Relay Logic (Agar relay ulta chale toh LOW aur HIGH swap kar dena)
#define RELAY_ON  LOW
#define RELAY_OFF HIGH

// 3x LM393 LDR Sensors & LM35 Temp Sensor
const int LDR1_PIN = 13;
const int LDR2_PIN = 14;
const int LDR3_PIN = 27;
const int LM35_PIN = 34;

// 6 LEDs
const int RED1_LED   = 18;
const int RED2_LED   = 19;
const int BLUE1_LED  = 23;
const int BLUE2_LED  = 4;
const int GREEN_LED  = 16;
const int YELLOW_LED = 17;

// 2-Channel Relay (K1 = Main Motor, K2 = Backup Motor)
const int RELAY_MAIN   = 25;
const int RELAY_BACKUP = 26;

// Wire Cut Simulators (Normal mode mein GND se connect rakho)
const int CUT_RED1_PIN  = 32;
const int CUT_MOTOR
