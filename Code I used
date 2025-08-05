import Adafruit_DHT 
from RPLCD.i2c import CharLCD 
import time 
 
sensor = Adafruit_DHT.DHT11 
pin = 4  # GPIO4

# Change 0x27 if your I2C address is different
lcd = CharLCD('PCF8574', 0x27)  
 
while True: 
    humidity, temperature = Adafruit_DHT.read_retry(sensor, pin) 
    if humidity is not None and temperature is not None: 
        lcd.clear() 
        lcd.write_string(f'Temp: {temperature:.1f}C') 
        lcd.cursor_pos = (1, 0) 
        lcd.write_string(f'Hum: {humidity:.1f}%') 
    else: 
        lcd.clear() 
        lcd.write_string("Read error") 
    time.sleep(2)
