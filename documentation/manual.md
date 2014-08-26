# T4-DataLogger

## Product overview
### Features
The Pax Instruments T400 dataLogger is designed for the ammature and professional maker toolbox.

* 1 Hz samples rate
* ± 0.5 °C accuracy
* 0.1 °C resolution
* Replacable, rechargable 24 mAh LiPo battery
* Charges via microUSB port
* MicroSD card for data storage
* Connects through a USB serial port for live data acqusition

### Specifications
#### Electrical
* **Connections** MicroUSB, mini thermocouple, microSD
* **Thermocouple channels**	 4
* **Supported thermocouple type** K-type
* **Temperature measurement range** -270 to 1370 C
* **Temperature resolution** 0.1 C
* **Accuracy** ± 0.5 °C
* **Samples rate** 1, 2, 5, 10, 30, 60 seconds
* **Recording length** limited to MicroSD memory
* **Memory** MicroSD card FAT16 formatted
* **Communication** USB virtual serial port
* **Power source** 850 mAh LiPo battery
* **Battery life** > 50 hour battery life
* **Power consumption** <12 mA, <20 mA with backlight

#### Microcontroller
* **Processor** Atmel ATmega32U4 QFN
* **Clock speed** 8 MHz
* **Operating voltage** 3.3 V
* **Arduino compatibility** Arduino LilyPad USB

#### Mechanical
* **Dimensions** ???
* **Weight** ???
* **Vibration** ???
* **Shock** ???

#### Environmental
* **Operating temperature**	 ???
* **Storage temperature** ???

## Buttons
This section describes the button functions and locations.
![Primary Screenshot](enclosure-front-buttons.png?raw=true)

### ![Primary Screenshot](cycle_icon.png?raw=true =28x)Toggle channels
This button cycles through which thermocouple channels are grpahed. The device defaults to displaying all four channels when thermocouples are present. Otherwise, pressing this button cycles through displaying each channel individually or all four at once.

### ![Primary Screenshot](power_icon.png?raw=true =28x) Power
This button turns on the unit or turns it off. States: on or off.

### ![Primary Screenshot](brightness_icon.png?raw=true =28x) Backlight
This button toggle the backlight on and off. States: on, off, or always on.

### ![Primary Screenshot](logging_icon.png?raw=true =28x) Logging
This button starts logging. The button must be pressed and held for a moment for the logging to begin. Once logging begins the fine name will be displayed.

### Δ Interval
This cycles through a eries of logging intervals. Default is one second. While logging this value cannot be changed. States (s): 1, 5, 10, 30, 60.

### °C°FK Temperature units
This button cycles through the celclus, fahrenheight, and kelvin scales. While logging this value cannot be changed. States: °C, °F, K.

## Screens
### Default screen
On device boot the screen should default to the image below.

![Primary Screenshot](screenshot-default-big.png?raw=true)

* Thermocouples default to NoTC
* Ambient temperature sensor shows --.-C
* Reading interval is one second
* Battery is empty
* Temperature axis is centered arount 30 C
* No data is graphed
* No graph labels along the right side


### Without thermocouples
After the first screen frame is drawn the device determines the ambient temperature and the battery charge level.

![Primary Screenshot](screenshot-notc-big.png?raw=true)

* The ambient temperature is displayed. In this example the ambient temperature is 27.5C.
*  The battery charge level is displayed. In this example the battery charge level is approximately 75%.

### One thermocouple
When one thermocouple is connected to the datalogger the screen should appear as below.

![Primary Screenshot](screenshot-onetc-big.png?raw=true)

* The first thermocouple is now 27.5 C. In this example both the thermocouple and datalogger are at room temperature.
* The graph displays data for thermocopule 1. In this example thermocouple 1 has been connected and at room temperature for ten seconds
* A label for the thermocouple 1 data appears on the right of the screen.

### Four thermocouples


![Primary Screenshot](screenshot-fourtc-big.png?raw=true)

### Cycle through graph modes
Pressing the graph button cycles through displaying each of the thermocouple data sets.

![Primary Screenshot](screenshot-fourtc-1-big.png?raw=true)

* Thermocouple 1 is displayed

![Primary Screenshot](screenshot-fourtc-2-big.png?raw=true)

* Thermocouple 2 is displayed

![Primary Screenshot](screenshot-fourtc-3-big.png?raw=true)

* Thermocouple 3 is displayed

![Primary Screenshot](screenshot-fourtc-4-big.png?raw=true)

* Thermocouple 4 is displayed

### Cycle through large display
NOTE: This feature is BEYOND SCOPE.

The Toggle Channels button will also cycle through displaying each thermocouple channel in large digits in place of the graph.g

![Primary Screenshot](screenshot-largenums-1-big.png?raw=true)

* Thermocouple 1 is displayed in large digits.

![Primary Screenshot](screenshot-largenums-2-big.png?raw=true)

* Thermocouple 2 is displayed in large digits.

![Primary Screenshot](screenshot-largenums-3-big.png?raw=true)

* Thermocouple 3 is displayed in large digits.

![Primary Screenshot](screenshot-largenums-4-big.png?raw=true)

* Thermocouple 4 is displayed in large digits.

### Battery charge indicator

While charging the interior of the battery status indicator blinks. When fully charged the battery status indicator should be full and solid.

![Primary Screenshot](screenshot-battery-bigger.png?raw=true)

* 0% < battery < 25%
* 25% < battery < 50%
* 50% < battery < 75%
* 75% < battery < 90%
* 90% < battery

### Operating the SD card
The SD card is only used while logging. On boot the LCD displays an SD card icon if an SD card is present. If no SD card is present, no icon is displayed.

When the user pressed the logging button ![Primary Screenshot](logging_icon.png?raw=true =28x) the system checks for the presence of an SD card. If the SD card is not present, the LCD displays an X and and SD card icon. If an SD card is present, the LCD displays the log file name, SD card icon, and and arrow pointing from the file name to the SD card icon.

![Primary Screenshot](screenshot-sd-pre-big.png?raw=true)

* SD card is not present as indicated by the lack of an SD card icon.
* Logging has not been started

![Primary Screenshot](screenshot-sd-no-big.png?raw=true)

* The logging button ![Primary Screenshot](logging_icon.png?raw=true =28x) has been pressed while the SD card is not present.
* An X and SD card is displayed indicating the SD card cannot be found.

![Primary Screenshot](screenshot-sd-present-big.png?raw=true)

* An SD card is placed in the device.
* SD card presence is indicated by and SD card icon.

![Primary Screenshot](screenshot-sd-logging-big.png?raw=true)

* With an SD card in place the logging button ![Primary Screenshot](logging_icon.png?raw=true =28x) is pressed.
* The automatically-selected file name is shown with an arrow indicating it is being saved to the SD card.

## User stories

### Alice makes coffee
Alice likes to make coffee in her French press. She used to bring water to a boil and wait a few minutes as it cooled. However, she could not determine if the water was at her ideal brewing temperature of 93°C. In addition to the temperature uncertainty, this wasted extra time and energy needlesly heating the water beyong 93°C and waiting for it to cool. Now the uses the Pax Instruments T4-DataLogger to monitor her water temperature to achieve her ideal brewnig temperature of 93°C.

Alice Removes here Pax Instruments DL-T4 and stainelss steel temperature probe from the kitchen drawer. She turns on the unit and is presented with the screen below.

![Primary Screenshot](screenshot-notc-big.png?raw=true)

She then plugs her temperature probe connector into the DL-T4 and places the stainless steel probe into the room temperature water. Her screen appears below.

![Primary Screenshot](screenshot-onetc-coffee-big.png?raw=true)

Once the water reaches 93°C Alice removees it from the heat and begins brewing her coffee. Victory for Alice!

### Bob boils water
Bob wants to boil water, so we does it. After some time the water reaches a boil. Victory!

![Primary Screenshot](screenshot-onetc-boiling-big.png?raw=true)

### Sous Vide Sally
Sally enjoys cooking various dishes sous vide style. To do this she must monitor the temperature of her dish as she moves around the kitchen.

## Other bits to add in above
- Opensource design based on the Arduino Leonardo
- Four channels of K-type thermocouple input
- MicroSD card for data storage
- 1232x64 graphic ST7567 COG LCD
- Internal rechargeable  LiPo battery
- Real-time clock with backup battery

### Specifications
The specifications below are subject to change.

#### Electrical
Connections                     MicroUSB, mini thermocouple, microSD
Thermocouple channels		4
Supported thermocouple type	K-type
Temperature measurement range	-270 to 1370 C
Temperature resolution		0.01 C
Accuracy			+/- 1 C
Samples rate			1, 2, 5, 10, 30, 60 seconds
Recording length		limited to MicroSD memory
Memory				MicroSD card FAT16 formatted
				> 1M samples per gigabyte
Communication			USB virtual serial port
Power source			850 mAh LiPo battery
Battery life                    > 80 hour battery life
				MicroUSB
Power consumption		<12 mA, <20 mA with backlight

#### Microcontroller
Processor			Atmel ATmega32U4 QFN
Clock speed			8 MHz
Operating voltage		3.3 V
Arduino compatibility		Arduino LilyPad USB

#### Mechanical
Dimensions			???
Weight				???
Vibration			???
Shock				???

#### Environmental
Operating temperature		???
Storage temperature		???

### Pin assignments

LumberDAQ-0.4    Arduino    ATmega32U4 pin
-------------    -------    --------------
SW_PWR           D7          1 PE6 (INT.6/AIN0)
NC               +5V         2 UVcc
USB D-           RD-         3 D-
USB D+           RD+         4 D+
GND              UGND        5 UGnd
3.3V             UCAP        6 UCap
VBUS             VUSB        7 VBus
RXLED            D17/RXLED   8 PB0 (SS/PCINT0)
SCK              D15/SCK     9 PB1 (PCINT1/SCLK)
MOSI             D16/MOSI   10 PB2 (PDI/PCINT2/MOSI)
MISO             D14/MISO   11 PB3 (PDO/PCINT3/MISO)
PWR_ON/OFF       D11        12 PB7 (PCINT7/OC0A/OC1C/~RTS~)
RESET            RESET      13 ~RESET~
3.3V             +5V        14 VCC
GND              Ground     15 GND
XTAL2            XTAL2      16 XTAL2
XTAL1            XTAL1      17 XTAL1
SCL              D3/SCL     18 PD0 (OC0B/SCL/INT0)
SDA              D2/SDA     19 PD1 (SDA/INT1)
SW_D             D0         20 PD2 (RXD1/INT2)
SW_E             D1         21 PD3 (TXD1/INT3)
TXLED            TXLED      22 PD5 (XCK1/~CTS~)
GND              Ground     23 GND
3.3V             AVCC       24 AVCC
SW_A             D4         25 PD4 (ISP1/ADC8)
SW_B             D12        26 PD6 (T1/~OC4D~/ADC9)
SW_C             D6         27 PD7 (T0/OC4D/ADC10)
SD_CS            D8         28 PB4 (PCINT4/ADC11)
NC             **D9         29 PB5 (PCINT5/OC1A/~OC4B~/ADC12)
RTC_INT          D10        30 PB6 (PCINT6/OC1B/OC4B/ADC13)
TEMP_INT         D5         31 PC6 (OC3A/~OC4A~)
BUZZER           D13        32 PC7 (ICP3/CLK0/OC4A)
GND              HWB        33 PE2 (~HWB~)
3.3V             +5V        34 +5V
GND              Ground     35 GND
BATT_STAT        A0         36 PF7 (ADC7/TDI)
VBAT             A1         37 PF6 (ADC6/TDO)
LCD_BL           A2         38 PF5 (ADC5/TMS)
LCD_CS           A3         39 PF4 (ADC4/TCK)
LCD_RST          A4         40 PF1 (ADC1)
LCD_A0           A5         41 PF0 (ADC0)
3.3V             AREF       42 AREF
GND              AGND       43 GND
3.3V             AVCC       44 AVCC

### I2C Addresses
IC i2c addresses for LumberDAQ-0.4.

Chip         Description  Address Address structure
----         -----------  ------- -----------------
MCP3424      ADC                  1101+ADDR
MCP9800/02A0 Temp sensor          1001000
DS3231       RTC                  1101000
HTU21D       Humidity
MPL3115A2    Pressure


