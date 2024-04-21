# Práctica 5: BUSES DE COMUNICACIÓN

## Introducción de la práctica
El funcionamineto de la práctica es trabajar con los buses de comunicación.

En esta práctica nos centraremos en el bus I2C , donde trabajaremos con el especializándonos en el Escáner del bus de comunicación I2C.

## EJERCICIO 1: ESCÁNER I2C

Código:

```c++
#include <Arduino.h>
#include <Wire.h>
void setup()
{
Wire.begin();
Serial.begin(115200);
while (!Serial);
Serial.println("\nI2C Scanner");
}
void loop()
{
byte error, address;
int nDevices;
Serial.println("Scanning...");
nDevices = 0;
for(address = 1; address < 127; address++ )
{
Wire.beginTransmission(address);
error = Wire.endTransmission();
if (error == 0)
{
Serial.print("I2C device found at address 0x");
if (address<16)
Serial.print("0");
Serial.print(address,HEX);
Serial.println(" !");
nDevices++;
}
else if (error==4)
{
Serial.print("Unknown error at address 0x");
if (address<16)
Serial.print("0");
Serial.println(address,HEX);
}
}
if (nDevices == 0)
Serial.println("No I2C devices found\n");
else
Serial.println("done\n");
delay(5000);
}

```
### Funcionamiento y salida por la terminal 
El funcionamineto de este código se basa

#### Salida por el puerto serie:
```
```

## EJERCICIO PRÁCTICO 2:

### Funcionamiento y salida por la terminal 

#### Salida por el puerto serie:
```
```

