# StehLight
## Vorbereitung
### Einkaufsliste
* WS2812B 1m 60 LEDs (ca 20 €, Ebay)
* Netzteil 5V-/4A (7,95 € , [Pollin](http://www.pollin.de/shop/dt/MDY0ODQ2OTk-/Stromversorgung/Netzgeraete/Steckernetzgeraete/Steckernetzteil_QUATPOWER_PSN5_4000H5_5_5_V_4_A_5_5_2_1_mm.html))
* Arduino UNO (ca. 20 €)
* Kondensator 1000µF / 6,3V (ca. 3 € für 10 Stück, Ebay)
* DC-Steckverbinder Hohlbuchse (ca. 1,50 €, [Pollin](http://www.pollin.de/shop/dt/ODgyODQ1OTk-/Bauelemente_Bauteile/Mechanische_Bauelemente/Steckverbinder_Klemmen/Hohlstecker_Adapter_5_5_2_1_2_Stueck.html))

*** 
* *Widerstand 470 Ohm (ca. 3 € für 20 Stück, Ebay)* - geht nicht

### Software
* Arduino IDE
* Adafruit NeoPixel Libary

### sonst noch?
* Litzen (habe 0,34² cm verwendet)
* Lötset

## Teil 1: alles zusammensetzen
* Kondensator: Langes Bein an -, Kurzes an +

## Teil 2: Programmierung

```java 
// Bibliothek einbinden
#include <Adafruit_NeoPixel.h>

// Variablen deklarieren
#define LED 60
#define PIN 6
 
// Parameter 1 = Anzahl der Pixel
// Parameter 2 = Pin auf dem Arduino
// Parameter 3 = pixel type flags, add together as needed:
//   NEO_KHZ800  800 KHz bitstream (most NeoPixel products w/WS2812 LEDs)
//   NEO_GRB     Pixels are wired for GRB bitstream (most NeoPixel products)
Adafruit_NeoPixel strip = Adafruit_NeoPixel(LED, PIN, NEO_GRB + NEO_KHZ800);

// Initialisierung der LED Kette
void setup() {
    strip.begin();
    strip.show(); // Initialize all pixels to 'off'
} // ENDE setup()

void loop(){
    // Parameter 1 = LED   (0 - 59)
    // Parameter 2 = red   (0 - 255)
    // Parameter 3 = green (0 - 255)
    // Parameter 4 = blue  (0 - 255)
	strip.setPixelColor(0, red, green, blue);
	
	// Zuvor gesetzte Farben anzeigen
	strip.show();
} //ENDE loop()
```

## Teil 3: Steuerung über Webseite
Vermutlich mit RaspberyPi aber noch keine genauen vorstellung.

## Quelle
+ [Adafruit NeoPixel Überguide Arduino](https://learn.adafruit.com/adafruit-neopixel-uberguide?view=all)
+ [Adafruit NeoPixel Überguide RaspberryPi](https://learn.adafruit.com/neopixels-on-raspberry-pi?view=all)
+ [Arduino Ethernet Tutorial](http://startingelectronics.com/tutorials/arduino/ethernet-shield-web-server-tutorial/)