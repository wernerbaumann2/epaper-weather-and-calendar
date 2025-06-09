# ePaper Weather And Calendar

## What is this all about?

When my brother called me and had some questions on microcontrollers and ePaper, I was curious what this is all about. He found [Weatherman Dashboard for ESPHome](https://github.com/Madelena/esphome-weatherman-dashboard) on the Internet and wanted to build such an ePaper-Frame. And shortly afterwards, me too!

That is why I started out on this project. I had not tinkered a lot with microcontrollers in recent years. Because of a very old installation of Arduino on a PC, I started out to install [PlatformIO](https://platformio.org) (a plugin for Visual Studio Code) on my Mac. And I ran the famous blink program on a Sparkfun ESP8266 Thing the same evening.

## Goals
The goal of the Project for me was to 
- display the current weather including a forecast
- display the family calendar
- running it all with the least possible amount of energy

Once finalized, it looks like this: 
<img src="ePaper Weather And Calendar.jpg" alt="the finalized frame!" height="400">

## Bill of Material
- [Universal e-Paper Raw Panel Driver Board, ESP32 WiFi / Bluetooth Wireless](https://www.waveshare.com/e-paper-esp32-driver-board.htm)
- [7.5inch e-Paper (G) E-Ink Optical Bonding Display, 800×480, Black / White, SPI, without PCB](https://www.waveshare.com/7.5inch-e-Paper-G.htm)
- [IKEA Rödalm Frame, 13x18cm](https://www.ikea.com/ch/de/p/roedalm-rahmen-eichenachbildung-10566390/)

## Steps taken
- installed ESPHome on my HomeAssistant
- got inspired by the projects of @Madelena and @paviro, and copy/pasted from their projects (see References)
- what I did change
  - used optimized driver for the display which supports partial refreshes (faster!!)
  - my weather information is based on [openweathermap.org](https://openweathermap.org/)
  - added a touchpad sensor of ESP32 to wake up the panel from deep sleep
  - adapted code to read from ESP32s internal ADC
 
## What do you need to take care of?
- you can use the files in this repository, but note that e.g configuration.yaml only shows the entries needed by this project, i.e. probably you only need to add certain sections to your existing configuration.yaml.
- make sure you download the necessary fonts from the sources referenced in this repo.
- adapt the settings in epaper-weather-and-calendar.yaml to include your calenders defined in Home Assistant which you would like to shown on the frame
- adapt CALENDAR_NAMES in epaper_calendar_conversion.py if you need to rename calenders

## References
- [Waveshare Support Page for E-Paper ESP32 Driver Board](https://www.waveshare.com/wiki/E-Paper_ESP32_Driver_Board)
- inspired by [Weatherman Dashboard for ESPHome](https://github.com/Madelena/esphome-weatherman-dashboard) and [ESPHome ePaper Calendar](https://github.com/paviro/ESPHome-ePaper-Calendar)
