# RVL Controller Board

_**Note:**_ This board is still in development, and documentation is currently sparse.

The RVL controller board is a custom board that runs the [RVL Firmware](https://github.com/rvl-system/rvl-firmware), and is intended for use as both a development board and an LED controller. This board features:

- ESP32 dual core processor
- Compatible with 3 or 4 pin 5V LED strips supported by [FastLED](http://fastled.io/)
  - Solder jumper for switching between 3 and 4 pin headers (optional)
- Can be powered from USB, or can be "backfed" power from the LED strip connected to it
- 3.3V to 5V level translation on LED control pins
- An LCD and tiny 5-way joystick for controlling the device directly
- A 16-pin header, with GPIO, UART, JTAG, I2C, and ADC pins exposed
- Can be programmed using JTAG + [OpenOCD](https://docs.espressif.com/projects/esp-idf/en/latest/api-guides/jtag-debugging/#jtag-debugging-setup-openocd) or UART + [esptool.py](https://github.com/espressif/esptool)
  - JTAG is the recommended way to interact with this device. The experience is a lot smoother, and you can also debug the device with breakpoints/variable inspection.
  - [RVL Firmware](https://github.com/rvl-system/rvl-firmware) includes a script that is preconfigured to use JTAG+OpenOCD with this device and the [FTDI C232HM-DDHSL-0](https://www.ftdichip.com/Products/Cables/USBMPSSE.htm) MSSPE cable 
  
## GPIO Header Pins

This data comes from the [ESP32 WROOM datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-wroom-32_datasheet_en.pdf).

|Pin|Functions|
|--|--|
| TMS | GPIO14, ADC2_CH6, TOUCH6, RTC_GPIO16, MTMS, HSPICLK, HS2_CLK, SD_CLK, EMAC_TXD2 |
| TDI | GPIO12, ADC2_CH5, TOUCH5, RTC_GPIO15, MTDI, HSPIQ, HS2_DATA2, SD_DATA2, EMAC_TXD3 |
| TCK | GPIO13, ADC2_CH4, TOUCH4, RTC_GPIO14, MTCK, HSPID, HS2_DATA3, SD_DATA3, EMAC_RX_ER |
| TDO | GPIO15, ADC2_CH3, TOUCH3, MTDO, HSPICS0, RTC_GPIO13, HS2_CMD, SD_CMD, EMAC_RXD3 |
| GND | Ground (shown as EN in the photo, will be changed in the next revision) |
| RXD | GPIO3, U0RXD, CLK_OUT2 |
| 26  | GPIO26, DAC_2, ADC2_CH9, RTC_GPIO7, EMAC_RXD1 |
| TXD | GPIO1, U0TXD, CLK_OUT3, EMAC_RXD2 |
| 25  | GPIO25, DAC_1, ADC2_CH8, RTC_GPIO6, EMAC_RXD0 |
| 27  | GPIO27, ADC2_CH7, TOUCH7, RTC_GPIO17, EMAC_RX_DV |
| 33  | GPIO33, XTAL_32K_N (32.768 kHz crystal oscillator output), ADC1_CH5, TOUCH8, RTC_GPIO8 |
| 17  | GPIO17, HS1_DATA5, U2TXD, EMAC_CLK_OUT_180 |
| 32  | GPIO32, XTAL_32K_P (32.768 kHz crystal oscillator input), ADC1_CH4, TOUCH9, RTC_GPIO9 |
| 16  | GPIO16, HS1_DATA4, U2RXD, EMAC_CLK_OUT |
| 3V3 | 3.3 volt power (limited to 500mA total including CPU) |
| GND | Ground  |

## Photos

Here is the front of the board:

<img src="https://user-images.githubusercontent.com/1141386/74892894-c1f00880-533f-11ea-85b2-5406611d7ab5.jpg" alt="Board front" width="480px"></img>

Here is the back of the board:

<img src="https://user-images.githubusercontent.com/1141386/74892908-ce746100-533f-11ea-830a-bf999217769f.jpg" alt="Board back" width="480px"></img>

Here is the board running with a WS2812b LED strip attached

<img src="https://user-images.githubusercontent.com/1141386/74892911-d0d6bb00-533f-11ea-85fa-5b57b07bd262.jpg" alt="Board running with LEDs attached" width="480px"></img>

And here is a video of an art piece I designed the lighting for using an older version of this board at Burning Man 2019:

<a href="https://www.youtube.com/watch?v=HZNM6n1g5n8" target="_blank">
  <img src="https://img.youtube.com/vi/HZNM6n1g5n8/0.jpg" alt="Video of the BRPL Deep Playa Branch at Burning Man 2019" width="480" height="360" border="10" />
</a>
