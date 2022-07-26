# DIY-Spray-Dryer-PID-Control

For my master thesis on the drying of microorganisms, I used a spray dryer from Büchi (B-290). Since spray dryers are on the one hand very expensive and on the other hand lack the function to keep the output temperature constant based on the pump rate, I had the idea to build a spray dryer with an automatic PID control. Thus, the output temperature could be kept at a constant level. For this purpose, an Arduino was used, which measures the temperature with the help of an NTC thermistor and then automatically adjusts the pump rate. At the same time, the measured values are transferred to a PC using an Excel macro in order to save the history for later analysis. With the help of an LCD display shield and the buttons on it, it is possible to switch between several menus and thus, for example, vary the target temperature during the process. In addition, common process parameters are shown on the LCD display.


## Basic Overview of the process

Air is sucked through a vent into the spray dryer (1). With heating coils (2) the air is heated to 150 - 300 °C, depening on the material. The hot air is now mixed in a 2-phase nozzle with the liquid (B) to be dried and sprayed in fine droplets into the drying chamber (4). The temperature at (3) is called the Inlet temperature. In the drying chamber the small droplets are dried through evaporation. Due to evaporative cooling effects, the temperature will fall quickly, which is measured at (5). Through a cyclone (6) the powder is seperated from the humid air and is collected in (8). The humid air is transported through (7) to the outside.

The temperature at the outlet is much more important than the temperature at the inlet. Therefore, a constant monitoring of the outlet temperature is necessary. Ideally this temperature is kept constant to increase quality and yield of the dried material.
The outlet temperature is most depended on the feeding rate of the pump, the air volume throughput and the inlet temperature. The inlet temperature can´t be changed rapidly and so is the air volume throughput, therefore the pump rate is the parameter we want to change. Unfortunately, most spray dryers do not have a PID controlled outlet temperature. In this project such a device was built and tested.

For this purpose, an Arduino was coupled with a pump, which measures the temperature and simultaneously adjusts the rotational speed of the motor or the pump with a PID control. For the temperature measurement two NTC thermistors were used, which were calibrated manually. As an interface an Arduino LCD Keypad Shield was used. The data were exported automatically through an template to a spreadsheet.

|Schematic drawing of the spray drying process|Schematic wiring scheme (made with Fritzing)|
|---------|--------|
|<img src="https://github.com/basti41a/DIY-Spray-Dryer-PID-Control/blob/main/img/SprayDryer.png" width="200">|<img src="https://github.com/basti41a/DIY-Spray-Dryer-PID-Control/blob/main/img/Fritzing%20schematic%20wiring.jpg" width="400">|







## Results
The PID control of the output temperature based on the pump rate went pretty well. Here is a picture of the output temperature (orange) and the pump rate (gray). The triangle indicates the start of spray drying with liquid yeast, before that only water was sprayed to bring the temperature to a constant level. The square indicates the end of the spraying with yeast.


<img src="https://github.com/basti41a/DIY-Spray-Dryer-PID-Control/blob/main/img/ResultYeast.jpg" width="500">
The PID control variables still have to be adjusted to prevent an oversteering, but overall the outlet temperature can be hold at a certain threshold.



## Special thanks to ##
### 3D-printed Arduino Keypad shield encasing
**AndreySamokhin** 

**https://www.thingiverse.com/thing:4194107**


### PLX-DAQ 2.0: Excel Makro for automatic transfer of Arduino data to a spreadsheet
**Netdevil** from the arduino.cc forum who provided this awesome tool!

**https://forum.arduino.cc/t/plx-daq-version-2-now-with-64-bit-support-and-further-new-features/420628**

|This it what the interface looks like|
|--|
|<img src="https://github.com/basti41a/DIY-Spray-Dryer-PID-Control/blob/main/img/PLX-DAQ%202%20Interface.jpg" width="200">|
