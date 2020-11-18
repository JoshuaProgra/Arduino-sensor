# Arduino-sensor
#include <DHT.h>
#include <DHT_U.h>

#define DHTPIN 3     
#define DHTTYPE DHT11   

DHT dht(DHTPIN, DHTTYPE);

//Variables
int chk;
float hum;  //Stores humidity value
float temp; //Stores temperature value

void setup()
{
    Serial.begin(9600);
    dht.begin();
    
}

void loop()
{
    //Read data and store it to variables hum and temp
    hum = dht.readHumidity();
    temp= dht.readTemperature();
    //Print temp and humidity values to serial monitor
    Serial.print("Humedad: ");
    Serial.print(hum);
    Serial.print(" %, Temperatura: ");
    Serial.print(temp);
    Serial.println(" Celsius");
    delay(2000); //Delay 2 sec
}
