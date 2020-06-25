# Handwashing_Timer_LED
Create a 20-second hand washing timer with an LED, random 20-music clip, activated with a motion sensor.

![ProjectGIF](https://github.com/carolinedunn/Handwashing_Timer_LED/blob/master/photos/demo.gif)

# Materials
Materials:
- Raspberry Pi Zero with Headers - https://amzn.to/2NncxP4
  - or Raspberry Pi 3B, 3B+ (3A, or 4) - https://amzn.to/2O9SxiO
- MicroSD card - https://amzn.to/2Nq5AN9
- Motion Sensor - https://amzn.to/32OPMaA
- Keyboard/Mouse/Monitor
- 3.5mm male-to-male audio cable - https://amzn.to/2LXhxrb
- Portable speaker with 3.5mm Aux Audio Jack - https://amzn.to/2ZDnyBb
- Small Breadboard - https://amzn.to/3d8jPiU
- LED & 330 ohm resistor - https://amzn.to/3c8Jhnc
- 2 Female to male jumper wires - https://amzn.to/2TIyXMj
- 3 Female to female jumper wires - 

# Prerequisites
1. Raspbian OS Setup on a microSD card - https://youtu.be/2Jfv9NO6J2Q

# Step 1 - Hardware Assembly
1. If you are using a Raspberry Pi Zero W, solder all GPIO header pins.

2. Attach PIR Motion sensor to the Raspberry Pi GPIO pins as shown in the diagram the PIR motion sensor. VCC to GPIO pin 2. GND to GPIO pin 6, and OUT to GPIO pin 11.

![WiringDiagram](https://github.com/carolinedunn/Handwashing_Timer_LED/blob/master/photos/Handwashing-Motion-LED-RPi-Wiring.jpg)

3. Attach LED and resistor to the breadboard. Attach positive (longer pin) of the LED to the resistor, then use the jumper wire to connect to GPIO pin 14 / Physical pin number 8. Attach Gnd to Gnd on GPIO. I am using physical pin number 14.

# Step 2 - Install Software
1. Install VLC for Python ```sudo pip install python-vlc```
1a. Install VLC ```sudo apt-get install vlc```

2. Git Clone this repository - ```git clone https://github.com/carolinedunn/Handwashing_Timer_LED```

3. Go into the directory you just created ```cd Handwashing_Timer_LED```

4. Test your setup by playing some music ```python test_music_led.py``` - If Music plays, then go to the next step, if not then go back and troubleshoot.

5. Run the script! ```python pir-led.py```

6. Wave your hand over the motion sensor. If music plays, move to the next step, otherwise, go back and trouble shoot.


# Step 3: Run on Boot

This step is optional if you'd like for this python script to run at boot.

- Open a Terminal
- Enter
```sudo nano /home/pi/.bashrc```

- Arrow down to the bottom of the file.
- Enter the following at the bottom of the .bashrc

```sudo python /home/pi/Handwashing_Timer_LED/pir-led.py```

- Ctrl-X to exit
- 'y' to Save
- Reboot your Raspberry Pi.
