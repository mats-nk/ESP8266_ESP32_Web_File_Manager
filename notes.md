# Notes - hardware agnostic code

This is notes about how to create a code that is agnostic to hardware platform 

The example code is `ESP_Web_File_Manager.ino`.

## Code example for `#includes` depending on hardware
```
#if defined(ARDUINO_ARCH_ESP32)        // --- ESP32 ---
#include <WiFi.h>                      // ESP32 WiFi lib
#include <WebServer.h>                 // ESP32 WebServer lib
WebServer server(80);                  // Webserver Initialization
#elif defined(ESP8266)                 // --- ESP8266 ---
#include <ESP8266WiFi.h>               // ESP8266 WiFi lib
#include <ESP8266WebServer.h>          // ESP8266 WebServer lib
ESP8266WebServer server(80);           // Webserver Initialization
#endif

#include <LittleFS.h>
#include <time.h>
```

