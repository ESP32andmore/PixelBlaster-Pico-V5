# PixelBlaster Pico V5 and  PixelBlaster Pico V5 PD 

The PixelBlaster Pico V5 is the same great board as the PixelBlaster Pico, but in a smaller super compact form factor of 12 mm x 28 mm, making it the world’s smallest WLED controller.  It is a next-generation, feature-rich WLED controller with bypass power and optional USB Power Delivery 3.1 capabilities for any 5 volt addressable lighting project you may have. If you need a WLED controller that is super small to fit right in a LED channel, tight locations or battery applications, this is the controller for you. 

But you can’t stop there, because it is low-cost and uses the workhorse ESP32, it can be used in any application where power injection is used. If you want to power it from a USB-C Power Delivery supply, that integrated option is available in a stacked 12 mm x 42 mm package. 

It supports virtually all LED strips and serial matrices using single-wire protocols, such as the WS2811 and WS2812B, to SPI (clocked-data) protocol devices, such as the WS2813 and SK9822, 5 volt only. 

## Features (controller) 

- Uses the workhorse ESP32 dual-core 240MHz processor. 
- Two channels of 5-volt logic-level translated outputs using ultra-fast and high-current LVC technology with matched and modeled serial inline resistors for high quality signal drive over short or long cables. 
- Low-profile Wago push-button terminal block for easy and secure electrical connections. 
- Compact form factor of 12 mm x 28 mm fit right in a LED mounting channel. 
- High-quality 4-layer impedance-controlled PCB with gold-plated connectors (ENIG) for durability and corrosion resistance. 
- LMD2718T261 PDM 24-bit digital microphone with a sensitivity of -26 dB FS and SNR of 57 dBa. 
- Controller input power: 5 volts 
- Electrostatic Discharge (ESD) protection on all inputs. 
- Supports ESP-NOW based remote controls. 
- Easy flashing of custom firmware through onboard header or via USB-C with PD option. 
- Pads exposing three ESP32 GPIOs for custom functions. 
- Power and signal pads exposed for hardwired solder options. 
- Comes with a tiny custom 3D-printed PLA+ case (design files available upon request). 
- Comes pre-flashed with the latest version of WLED. 

### GPIO Mapping

| FUNCTION | GPIO |
| --------- | ---- |
| C1 | IO019 |
| D1 | IO22 |
| Relay | IO21 |
| I2S SCK | IO12 |
| I2S SD | IO13 |
| I2S WS | IO14 |
| USER1 | IO02 |
| USER2 | IO27 |
| USER3 | IO26 |

 ## Features (PD option) - available soon

- Onboard ATtiny1616 controller manages the AP33772S Power Delivery 3.1 sink controller. 
- Input power: 5 volts @ 5-amp max. via USB-C connector, up to 25 watts max. 
- Overvoltage and undervoltage protection on input power that shuts off power to LEDs and the board. 
- Overcurrent protection with 5-amp “electronic” fuse. 
- Over temperature protection of the board and moisture detection on USB-C connector. 
- Onboard 34-amp AlphaSGT MOSFET "relay" that reduces current draw to just 80mA @ 5V when LEDs are turned off. 
- Onboard LED reports Power Delivery negotiation results. 
- Electrostatic Discharge (ESD) protection on all inputs.  

## USB Power Charger/Supply Selection 

Key to using any USB charger or supply is its selection by way of the voltages and current it supports.  We suggest using a USB Power Delivery 3.1 certified supply, but it goes deeper than that. 

Standard USB BC 1.2 (Type-A and Type-C connectors) provides 5 volts at a rated current, the maximum of 1.5 amps, but sometimes your do see charge rate to 2 amps. 

Standard USB Type-C 1.2 provides 5 volts at a rated current, the maximum current is typically 3 amps. 

USB Type-C Power Delivery 3.0 added negotiation of voltage and current profiles (PDOs), called SPRs, between the source and sink with a maximum fixed voltage at 20 volts and 5 amps.  The standard also offers a programmable power supply (PPS) profile that from 3.3v to 21 volts, and up to 5 amps maximum current. 

USB Type-C Power Delivery 3.1 adds greater fixed voltage profiles, called EPRs, to 48volts at 5 amps, and a second programmable voltage range (called AVS) from 15 volts to 28 volts at up to 5 amps maximum current 

The PixelBlaster PD boards negotiates with the charger to provide the greatest current available at the selected voltage, either 5 volts, 12 volts, or 24 volts.  Upon plugging into your charger or switching to the desired voltage dymically, the PixelBlaster PD boards enumerate through the profiles and finds the maximum current for a given voltage first using PPO and AVS profiles, then the fixed voltage profiles. 

In selecting your charger/supply, it needs to have a profile that fits the voltage and current you will be running your LED strips at. 

The following are a few models that work well for different strip voltages: 

 ### AOHI Magcube 140W USB C Charger 

- PDO1: Fixed PDO: 5000mV 3.00A ~ 3.24A 
- PDO2: Fixed PDO: 9000mV 3.00A ~ 3.24A 
- PDO3: Fixed PDO: 12000mV 3.00A ~ 3.24A 
- PDO4: Fixed PDO: 15000mV 3.00A ~ 3.24A 
- PDO5: Fixed PDO: 20000mV 5.00A ~ (More than) 
- PDO6: PPS PDO: 3300mV~21000mV 5.00A ~ (More than) 
- PDO8: Fixed PDO: 28000mV 5.00A ~ (More than) 

### Anker 313 45W USB C Charger Block 

- PDO1: Fixed PDO: 5000mV 3.00A ~ 3.24A 
- PDO2: Fixed PDO: 9000mV 3.00A ~ 3.24A 
- PDO3: Fixed PDO: 15000mV 3.00A ~ 3.24A 
- PDO4: Fixed PDO: 20000mV 2.25A ~ 2.49A 
- PDO5: PPS PDO: 3300mV11000mV 5.00A ~ (More than) 
- PDO6: PPS PDO: 3300mV16000mV 3.00A ~ 3.24A 
- PDO7: PPS PDO: 3300mV~21000mV 2.25A ~ 2.49A 

### AMEGAT Power Bank 140W, 27600mAh 3-Port Portable Charger 

- PDO1: Fixed PDO: 5000mV 3.00A ~ 3.24A 
- PDO2: Fixed PDO: 9000mV 3.00A ~ 3.24A 
- PDO3: Fixed PDO: 12000mV 3.00A ~ 3.24A 
- PDO4: Fixed PDO: 15000mV 3.00A ~ 3.24A 
- PDO5: Fixed PDO: 20000mV 5.00A ~ (More than) 
- PDO6: Fixed PDO: 0mV 0.00A ~ 1.24A (Less than) 
- PDO8: Fixed PDO: 28000mV 5.00A ~ (More than) 
- PDO9: AVS PDO: 15000mV~28000mV 5.00A ~ (More than) 

The AOHi Magcube works great for 5-volts and 12-volt strips giving a full 5 maps of current. The Anker is cost effective for 5-volt strips at 5 amps, but for 12-vot strips is limited to 3 amps.  The AMEGAT Power Bank is a great portable solution and although its literature and the back placard states it supports a PPO profile allowing 5 and 12-volts at 5amps, it does not. Unfortunately, at the time of writing there is only one charger that covers 5-volt, 12-volt, and 24-volt strips at a full 5 amps and that is the Framework 180watt USB-C Power Adaptor, but it is very pricey at over $100. 

### ESP32andmore GaN PD3.2 240W

Fortunately for our customers, EPS32andmore.com, in a few short weeks will make available a new and extremely capable power adaptor called the GaN PD3.2 240w. It has all the PD 3.1 fixed profiles from 5 volts to 48 volts at 5 amps, PPS: 5–21 volts at 5 amps, and AVS: 15–48 at 5 amps, making it the end all solution at a comfortable price of $39.99.  

- PDO1: Fixed PDO: 5000mV 5.00A ~ (More than) 
- PDO2: Fixed PDO: 9000mV 5.00A ~ (More than) 
- PDO3: Fixed PDO: 12000mV 5.00A ~ (More than) 
- PDO4: Fixed PDO: 15000mV 5.00A ~ (More than) 
- PDO5: Fixed PDO: 20000mV 5.00A ~ (More than) 
- PDO6: PPS PDO: 5000mV21000mV 5.00A ~ (More than) 
- PDO8: Fixed PDO: 28000mV 5.00A ~ (More than) 
- PDO9: Fixed PDO: 36000mV 5.00A ~ (More than) 
- PDO9: Fixed PDO: 48000mV 5.00A ~ (More than) 
- PDO10: AVS PDO: 15000mV~48000mV 5.00A ~ (More than) 

## USB Type-C Cables

The last component of any Power Delivery setup is a good quality PD3.1, 240 watt certified cable. Many fine cable are out there but we recommend the INIU USB C to USB C Cable, 240W Fast Charging Cable for its quality and fair price.

## Setting the Working Voltage

The PixelBlaster Nano PD sets the working voltage of the LEDs by way of the 3-switch block on the board. By default this is set to 5 volts. Setting to 12 volts and 24 volts is available with the correct swtich setting.  BE CERTAIN you have selected the correct voltage for your connected LEDs.

On powerup, USB-C connection, or changing the switches, based on the selected voltage, the PixelBlaster will ascertain the available voltages and currents of the charger, and set the charger's profile (PDOs) at the desired voltage to the maxmium current available with priority givien to any programable voltage PDOs. Using programmable voltage (PPS/AVS) PDOs also allows for the PixelBlaster to compensate for any cable losses maintaining a more accurate output voltage at your LEDs. Know your charger's capabilities before connecting your string. If your charger does not have voltage capabilities for your setting, it will default to 5 volts.

If you do exceed your charger's current capabilities, the overcurrent protection will intitiate, power will be shut off to the LEDs. As a safety measure, you will have to disconnect the the PxielBlaster from the USB and correct your overcurrent situation.

A slow flash on the Status LED indicates the board has successfully negociated a PDO with the charger but NOT THAT IT HAS negociated the selected voltage. To determine that make sure the power is turned on in WLED. A dim Voltage LED indicates 5 volts, a medium brightness on the Voltage LED indicates 12 volts, and a bright LED indicates 24 volts.

### 5 Volts
<img src="work/PixelBlaster_5v.JPG" width=200>

### 12 Volts
<img src="work/PixelBlaster_12v.JPG" width=200>

### 24 Volts
<img src="work/PixelBlaster_24v.JPG" width=200>

## Programming WLED

- The PixelBlaster Nano PD comes pre-programmed from the factory with the lastest version of WLED.  To update WLED, simply follow the instructions [here](https://kno.wled.ge/basics/getting-started/) under Software Update Procedure, Method 2.
- To reflash over the USB interface simply go [here](https://install.wled.me/). (Note: after reflashing due to a driver issue, disconnect the board from your PC and connect to a power adaptor where you can then enter in your WiFI credentials via the AP.
<img src="work/WLED-QR-Connect-WB.png" width=200>

- To access the webpage use http://wled.local
  
