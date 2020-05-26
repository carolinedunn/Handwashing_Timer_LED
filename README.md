# Handwashing_Timer_LED
Create a 20-second hand washing timer with an LED, random 20-music clip, activated with a motion sensor.

![ProjectGIF](https://github.com/carolinedunn/Handwashing_Timer_Music/blob/master/photos/handwashingtimer.gif)

# Materials
Materials:
- Raspberry Pi Zero with Headers - https://amzn.to/2NncxP4
  - or Raspberry Pi 3B, 3B+ (3A, or 4) - https://amzn.to/2O9SxiO
- MicroSD card - https://amzn.to/2Nq5AN9
- Motion Sensor - https://amzn.to/32OPMaA
- Keyboard/Mouse/Monitor
- Pimoroni Speaker PHAT

![SpeakerPHATnotsoldered](https://github.com/carolinedunn/Handwashing_Timer_Music/blob/master/photos/speaker-phat-unsoldered.jpg)

# Tools
Solder Iron

Solder

Solder Holder

# Prerequisites
1. Soldering Skills

2. Raspbian OS Setup on a microSD card - https://youtu.be/2Jfv9NO6J2Q

# Step 1 - Hardware Assembly
1. Assemble Pimoroni Speaker pHat and solder - https://learn.pimoroni.com/tutorial/sandyj/assembling-speaker-phat

2. If you are using a Raspberry Pi Zero W, solder all GPIO header pins.

3. Solder wires to pins 2, 4, and 11 of the Speaker Phat.

4. Solder or attach as shown in the diagram the PIR motion sensor.

![WiringDiagram](https://github.com/carolinedunn/SmartHome_MotionSensor_RPi/blob/master/Wiring%20Diagram-MotionSensor%20to%20RPi.jpg)

# Step 2 - Install Software
1. Install Pimoroni SPEAKER PHAT software ```curl -sS https://get.pimoroni.com/speakerphat | bash```

2. Hit 'y' twice and reboot when prompted. (Yes, you want the full install.)

[More info about Pimoroni SpeakerpHat here - https://github.com/pimoroni/speaker-phat ]

3. Test your install by playing a test file ```vlc /home/pi/Pimoroni/speakerphat/test/test.mp3```

If sound plays, you can move onto the next step. If not, ```sudo apt-get install vlc```

4. Install VLC for Python ```sudo pip install python-vlc```

5. Git Clone this repository - ```git clone https://github.com/carolinedunn/Handwashing_Timer_Music```

6. Go into the directory you just created ```cd Handwashing_Timer_Music```

7. Test your setup by playing some music ```python test_music.py``` - If Music plays, then go to the next step, if not then go back and troubleshoot.

8. Run the script! ```python pir.py```
9. Wave your hand over the motion sensor. If music plays, move to the next step, otherwise, go back and trouble shoot.


# Step 3: Run on Boot

This step is optional if you'd like for this python script to run at boot.

- Open a Terminal
- Enter
```sudo nano /home/pi/.bashrc```

- Arrow down to the bottom of the file.
- Enter the following at the bottom of the .bashrc

```sudo python /home/pi/Handwashing_Timer_Music/pir.py```

- Ctrl-X to exit
- 'y' to Save
- Reboot your Raspberry Pi.
