# barcode-scanner-for-esphome

```
substitutions:
  devicename: barcode-ext
  friendly_name: Barcode Scanner

  # WLAN Zugangsdaten
  wifi_ssid: !secret wifi_ssid
  wifi_password: !secret wifi_password

  # ESPHome API Schlüssel
  api_encryption_key: "Rd9kYjTg0g6K25ROWgl13MMdvmWYAX+8UhsvOSEDiys="

  # Query ID für opentindb (https://opengtindb.org/api.php)
  rest_opentindb_queryid: "400000000"

  # I2C-Pins fürs Display
  display_i2c_sda: GPIO21
  display_i2c_scl: GPIO22

  # I2C-Adresse des OLED Displays
  ssd1306_i2c_address: "0x3C"

  # UART-Pins für den Barcode-Scanner
  uart_tx_pin: GPIO1
  uart_rx_pin: GPIO3

  # Pin des Buzzer/Beeper
  beeper_pin: GPIO16


esp32:
  board: wemos_d1_mini32

packages:
  barcode: github://SmartHome-yourself/barcode-scanner-for-esphome/barcode.yaml@main
```
