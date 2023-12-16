# PRACTICA-2-SENSOR-DHT-ESP32
## Introducción 
### Descripción 
¿Qué se puede hacer con ESP32
Controla a distancia la humedad, la ventilación, el nivel de CO2 y la luminosidad con la gama de PLC ESP32. De este modo, mantendrás un ambiente óptimo y obtendrás lo mejor de tu instalación. La industria necesita monitorizar y controlar docenas de elementos críticos en sus instalaciones.

### Material de trabajo 
WOKWI
TARJETA ESP 32
SENSOR DHT11

### INSTRUCCIONES 
Entrar a la plataforma WOKWI para poder usar el sensor
Posterior colacamos abrimos el programa y colocamos el codigo de programación 

#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}

Siguiente instlamos la libreria **DHT sensor library for ESPx**

Por ultimo hacemos la conexion de los sensores **DHT11** con la **ESP32**

### RESULTADOS
Cuando haya funcionado, verás los valores dentro del monitor serial como se muestra en la siguente imagen.
