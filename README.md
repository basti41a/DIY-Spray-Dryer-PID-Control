# DIY-Spray-Dryer-PID-Control

For my master thesis on the drying of microorganisms, I used a spray dryer from Büchi (B-290). Since spray dryers are on the one hand very expensive and on the other hand lack the function to keep the output temperature constant based on the pump rate, I had the idea to build a spray dryer with an automatic PID control. Thus, the output temperature could be kept at a constant level. For this purpose, an Arduino was used, which measures the temperature with the help of an NTC thermistor and then automatically adjusts the pump rate. At the same time, the measured values are transferred to a PC using an Excel macro in order to save the history for later analysis. With the help of an LCD display shield and the buttons on it, it is possible to switch between several menus and thus, for example, vary the target temperature during the process. In addition, common process parameters are shown on the LCD display.


## Basic Overview of the process
https://en.wikipedia.org/wiki/Spray_drying

## Excel Makro for automatic transfer of Arduino data to a spreadsheet
Special thanks to **Netdevil** from the arduino.cc forum who provided this awesome tool!

**https://forum.arduino.cc/t/plx-daq-version-2-now-with-64-bit-support-and-further-new-features/420628**

## 3D-printed Arduino Keypad shield
Special thanks to **AndreySamokhin** from which I could print the casing for the Keypad Shield to hide the cables and make it look better.

**https://www.thingiverse.com/thing:4194107**

## Results
The PID control of the output temperature based on the pump rate went pretty well. Here is a picture of the output temperature (orange) and the pump rate (gray). The triangle indicates the start of spray drying with liquid yeast, before that only water was sprayed to bring the temperature to a constant level. The square indicates the end of the spraying with yeast.
