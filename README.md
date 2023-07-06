# MAX7456
OSD Module board for MAX7456 / AT7456

Datasheet: MAX7456 - https://www.analog.com/media/en/technical-documentation/data-sheets/MAX7456.pdf

This is a breakout board for the Maxim MAX7456 monochrome on-screen display chip. The board is set up with all supporting circuitry and RCA connectors to allow the user to easily interrupt and overlay text and/or graphics onto a video signal (PAL or NTSC).

## Scheme XIAO
![Scheme](images/xiao-scheme.png)

## KiCad XIAO
Board|PCB
----|----
![Board](images/xiao-board.png)|![View 1](images/xiao-preview.png)

## Scheme
![](images/scheme.png)

Board|PCB
----|----
![Board](images/board.png)|![View 1](images/preview.png)

## Code

There are several libraries for this project to work. 
Library: https://github.com/neomilium/arduino-max7456/

First you need to upload charset into MAX7456 in order to use it.

```c
#include <SPI.h>
#include <max7456.h>

Max7456       osd;

void setup() {
  SPI.begin();

  osd.init(10);
  osd.setDisplayOffsets(60, 18);
  osd.setBlinkParams(_8fields, _BT_BT);
  osd.activateOSD();
  osd.print("Hello world :)", 1, 3);
}
void loop() { }
```

## PCB Design

For PCB design i will use services from SeeedFusion. 

Seeed Fusion PCB Assembly Service offers one-stop prototyping for PCB manufacture, PCB assembly and as a result they produce superior quality PCBs and Fast Turnkey PCBA from 7 working days. When you prototype with Seeed Fusion, they can definitely provide Free DFA and Free functional tests for you! 

Check out their website to know about their manufacturing capabilities and service.
https://www.seeedstudio.com/pcb-assembly.html

Seeed Fusion Agile manufacturing: https://seeedstudio.com/fusion.htm

## Reasons to choose Seeed Studio
- They provide PCB services at extremely low pricing and with excellent quality.
- Their offer is structured in such a way that everyone may have these boards at a reasonable price.
- They have a highly knowledgeable crew that leads their clients to avail deals and guides them about the costs and rates of different services.
- A four-layer board with a comparable feature costs $5 for 10 pieces and is made in four days.
- SMT stencil with size (10cm x 13cm) is available for $8.00 per piece.
