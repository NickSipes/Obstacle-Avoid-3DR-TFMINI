# Obstacle-Avoid-3DR-TFMINI
Arduino and 3DR Smart Shot code to enable an air brake triggering sensor

# Setup
Connect your TFMini sensor to you Ardunio board using this tutuorial (https://learn.sparkfun.com/tutorials/tfmini---micro-lidar-module-hookup-guide). You will need the logic converter since the TFMini runs at 3.3V. Since we are using Firmata we cannot use SoftwareSerial. Therefore you must use a board that has extra serial ports like the Mega 2560.

# Enable Communication
Use this tutorial (https://www.hackster.io/djnugent/solo-servo-sweep-465164) to enable Firmata communication and enable PyMata with your 3DR Solo.

# Hardware
After the TFMini is connected to the Ardunio and communicating, load the Arduino code provided onto it. Ensure your pins match the code or modify to match. Connect the Ardunio using a serial cable and a micro USB OTG cable to the 3DR breakout board USB port (https://store.brownieboards.com/product/3dr-solo-breakout-board/). Ensure the Ardunio turns on when the 3DR is powered on and the TFMini is on.

# Software
After the .ino file is loaded onto the Arduino, you can copy the Custom_Files_For_3DR onto the IMX6 board from a terminal window. Connect to the 3DR Solo's Wifi and ssh into the drone using "ssh root@10.1.1.10" and the password "TjSDBkAu". Then copy the files from their directory to the IMX6 using the command "scp file.py root@10.1.1.10:/usr/bin". After that you can reboot the drone and everything should be working properly.

# Testing
When the drone is above 1M the obstacle avoidance system will be able to be activated. A long press of the paddle will activate the system. If the TFMini detects an obstacle within the threshold (3M is the preset) then it will send the 3DR into "BRAKE" mode. Click the "FLY" button to exit "BRAKE" mode.
