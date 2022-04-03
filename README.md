# ATmega-SolderingStation-SMD

![image](https://user-images.githubusercontent.com/19898602/161411367-82505b68-44f8-4dbc-8081-3d66040bf90b.png)

Stand-alone High-Voltage Serial Programmer and Fuse Resetter for 8-Pin ATtinys


TinyHVSP is a stand-alone high-voltage serial programmer and fuse resetter for ATtiny 13/25/45/85. This project was superseded by the more versatile TinyCalibrator.

![image](https://user-images.githubusercontent.com/19898602/161411380-33ae840a-a475-418f-bb31-1a10526cb567.png)


# Hardware

The TinyHVSP is supplied with 5V via a Micro USB connector. The ATtiny24/44/84 was chosen as the microcontroller for the TinyHVSP because it has the necessary number of GPIO pins. To generate the 12V for the High-Voltage Serial Programmer, an inexpensive MT3608 boost converter IC was used.

The 12V is controlled by a BJT and applied to the RESET pin of the target ATtiny if necessary. The remaining programming lines to the target are protected against a short circuit with resistors. The user interface utilizes one button and a 128x64 pixels OLED display.

![image](https://user-images.githubusercontent.com/19898602/161411404-ca3d7238-95f0-4006-959d-fd46727fb77c.png)


# Software 

High-Voltage Serial Programmer
The code for the High-Voltage Serial Programmer (HVSP) is quite unspectacular. Simply put, for each action, a series of instructions are sent over the data lines to the target ATtiny and the corresponding response is read. 

The process and the instructions are well described in the data sheet.

![image](https://user-images.githubusercontent.com/19898602/161411416-38a443c3-2d49-41ba-a598-0775248571ee.png)


# I²C OLED Implementation

The I²C protocol implementation is based on a crude bitbanging method. 
It was specifically designed for the limited resources of ATtiny10 and ATtiny13, but it works with some other AVRs (including the ATtiny24/44/84) as well. The functions for the OLED are adapted to the SSD1306 OLED module, but they can easily be modified to be used for other modules. 

In order to save resources, only the basic functionalities which are needed for this application are implemented. For a detailed information on the working principle of the I²C OLED implementation visit TinyOLEDdemo.


# Compiling and Uploading

If using the Arduino IDE
Make sure you have installed ATtinyCore.
Go to Tools -> Board -> ATtinyCore and select ATtiny24/44/84(a) (No bootloader).
Go to Tools and choose the following board options:
Chip: ATtiny24(a) or 44(a) or 84(a) (depending on your chip)
Clock: 8 MHz (internal)
Millis/Micros: disabled
Leave the rest at the default settings
Connect your programmer to your PC and to the ICSP header of the device.
Go to Tools -> Programmer and select your ISP programmer (e.g. USBasp).
Go to Tools -> Burn Bootloader to burn the fuses.
Open TinyHVSP sketch and click Upload.


If using the precompiled hex-file
Make sure you have installed avrdude.
Connect your programmer to your PC and to the ICSP header of the device.
Open a terminal.
Navigate to the folder with the hex-file.
Execute the following command (if necessary replace "t84" with the chip you use and "usbasp" with the programmer you use)

# Operating Instructions

Connect a 5V power supply to the micro USB port.
Place the ATtiny13/25/45/85 in the IC socket. Use an SOP adapter for SMD parts.
Press OK-button and follow the instructions on the display.

![image](https://user-images.githubusercontent.com/19898602/161411455-269058c2-78ec-4a5c-a93b-0b54480e75d1.png)![image](https://user-images.githubusercontent.com/19898602/161411457-0b542154-a9d7-433f-813e-ab357963158b.png)![image](https://user-images.githubusercontent.com/19898602/161411459-fd80f207-b121-41aa-b3ab-6c18d7a477dc.png)


![image](https://user-images.githubusercontent.com/19898602/161411465-d1a48700-1156-40e6-8b36-1c7e60898e4d.png)

# CIRCUIT
![image](https://user-images.githubusercontent.com/19898602/161411477-c861b76e-66e8-4ff0-b3e7-d5ee2dfe98e6.png)

![image](https://user-images.githubusercontent.com/19898602/161411487-4d689823-aeda-4b6f-bb0f-219ecf9add38.png)

SMT Assembly service of [JLCPCB.com](https://jlcpcb.com/IAT) is cherry on top now get your PCB fully assembled and save your time and money
Select components for your PCB from there Parts Library of 200k+ in-stock components
they are offering $27 valued New User coupon  & $24 SMT coupons every month
$8.00 setup fee, and $0.0017  per joint

Now no need to order components separately for you PCB and get free from stress of soldering them on PCB just try PCB SMT assembly service and get you PCB with components pre assembled and ready for the project


👉 Try PCBA service of [JLCPCB.com](https://jlcpcb.com/IAT) and save your time and money, get PCB ready for project, 200K+ components in library of [JLCPCB.com](https://jlcpcb.com/IAT) as well as 3rd party         parts to choose from. 
    Assembly will support 10M+ parts from Digikey, mouser
    
👉 $27 valued New User coupons 

👉 $24 SMT coupons every month


For more detials & offers please visit [JLCPCB.com](https://jlcpcb.com/IAT)


[Click here to visit JLCPCB.com](https://jlcpcb.com/IAT)






