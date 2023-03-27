# barcode-scanner-for-esphome

#
## Benötigte Bauteile
**D1 Mini-ESP32:** https://amzn.to/3kLEt1s *  
**Barcode Scanner GM60:** https://amzn.to/3mq6vA2 *  
**Active Piezo Buzzer:** https://amzn.to/3Zps3eM *  
**0,96" OLED Display:** https://amzn.to/3kH2Ld7 *  
#    


## Installation
- ESP mit USB verbinden
- Installieren über Web-Installer
- WLAN Daten für über Web-Installer setzen
- Gerät in Home Assistant adoptieren
- Generierten Code um Substitutions anpassen
- Über ESPHome flashen
- In Home Assistant als Integration hinzufügen (Einstellungen - Geräte)


Den Web-Installer findet Ihr auf der Projektseite unter:  
https://smarthomeyourself.de/home-assistant-einkaufsliste-ueber-barcode-scanner-fuellen-mit-esphome/
  
#    

### Mögliche Einstellungen (Substitutions)
Mit den folgenden optionalen Substitutions habt Ihr die Möglichkeit, die Standard-Konfiguration an Eure Bedürfnisse anzupassen.

```
substitutions:
  friendly_name: "Barcode Scanner"

  # Query ID für opentindb (https://opengtindb.org/api.php)
  rest_opentindb_queryid: "400000000"

  # I2C-Pins fürs Display
  display_i2c_sda: GPIO21
  display_i2c_scl: GPIO22

  # I2C-Adresse des OLED Displays
  ssd1306_i2c_address: "0x3C"

  # UART-Pins für den Barcode-Scanner
  uart_tx_pin: GPIO09
  uart_rx_pin: GPIO10

  # Pin des Buzzer/Beeper
  beeper_pin: GPIO16
```
  
#  
  
  
  
### Dienste
#### esphome.[YOUR_DEVICENAME]_request_ean  
> Über diesen Dienst lässt sich die gleiche Anfrage auslösen, wie wenn ein Barcode über den Scanner gescannt wird.  
> Wird der Code von den APIs erkannt, werden Hersteller und Produktname genau wie beim echten scan über die Sensoren zurückgeliefert.  
>  
>**Parameter**
> | Parameter | Beschreibung |
> | --- | --- |
> | **eancode** | *EAN/GTIN nach der gesucht werden soll* |  
>  
> **Beispiel:**  
> ```
> service: esphome.bcs_request_ean
> data:
>   eancode: "40084060"
> ```


#### 
*\* Bei allen Amazon Links handelt es sich um Affiliate-Links. Heißt für jeden Kauf über die Links erhalte ich eine kleine Provision. Ihr bezahlt natürlich weiterhin den selben Preis wie sonst auch. 
Vielen Dank für eure Unterstützung!*
