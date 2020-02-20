# RVL Controller Board

_**Note:**_ This board is still in development.

The RVL controller board is a custom board that runs the [RVL Firmware](https://github.com/rvl-system/rvl-firmware), and is intended for use as both a development board and an LED controller. This board features:

- ESP32 dual core processor
- Can be powered from USB, or can be "backfeed" power from the LED strip connected to it
- 3.3V to 5V level translation on LED control pins
- An LCD and tiny 5-way joystick 
- A 16-pin GPIO header, with GPIO, UART, JTAG, I2C, and ADC pins exposed
- Compatible with 3 or 4 pin LED strips supported by [FastLED](http://fastled.io/)
  - Solder jumper for switching between 3 and 4 pin headers

Here is the front of the board:

![front](https://user-images.githubusercontent.com/1141386/74892894-c1f00880-533f-11ea-85b2-5406611d7ab5.jpg)

Here is the back of the board:

![back](https://user-images.githubusercontent.com/1141386/74892908-ce746100-533f-11ea-830a-bf999217769f.jpg)

And here is the board running with a WS2812b LED strip attached

![running](https://user-images.githubusercontent.com/1141386/74892911-d0d6bb00-533f-11ea-85fa-5b57b07bd262.jpg)
