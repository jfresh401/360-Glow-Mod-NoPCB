# 360 Glow Mod 

<p align="center">
  <img src="/Wiring Diagrams/attiny_GlowMod_Soldering.jpg"> 
</p> 

## Description
  
EDITED 2-15-2025: I've included some more files to help make this without a PCB.

Introducing the Glow Mod PCB-less for Xbox 360! A recreation of the TX Glow Mod that adds a cool fading/breathing animation to the Ring of Light module when the console is in standby mode. 

##DEMO Video of what this does: https://www.youtube.com/shorts/GjhiHA5iihQ?feature=share



                                                    ## How to flash the ATTiny85 for the Glowmod.  ##



Open IDE with pro micro connected and choose my Arduino ISP sketch. My ISP sketch will work for pro micro. 

Flash that sketch to the pro micro. Next, grab your attiny85 and wire it up accordingly.

     PRO MICRO                ATTINY85
   _______________________________________

        5V                      pin 8

       GND                      pin 4

       GPIO10                   pin 1   RESET

       GPIO16 MOSI              pin 5

       GPIO14 MISO              pin 6

       GPIO15 SCK               pin 7 



Now, in IDE... 

click "Tools" and enter these settings...
        
                      Board:  ATTiny25/45/85 (no bootloader)
                      Port: (your COM port)
                      Chip: ATTiny85
                      Clock Source: 8 MHZ internal 
                      Programmer: Arduino Leo/Micro as ISP(ATmega32U4) 
                 Now click "Burn Bootloader" in the bottom of that list.

That will burn the 8MHZ clock speed to the chip. It is still not ready, this just speeds it up a bit.


You can close out of the IDE.


Now open CMD.EXE and navigate to the Glowmod Program folder. (EXAMPLE:  C:\Users\YOU\OneDrive\Desktop\Glowmod Program )

Enter this command and hit enter.

                  avrdude -c arduino -b 19200 -p t85 -P COM17 -n

This will check the integrity of the attiny85 and return some info including a verification of the chips flash.

Once verified, enter this command and hit enter.
            
            avrdude -c arduino -b 19200 -p t85 -P COM17 -U flash:w:glowmod.hex

This flashes the actual hex file to the attiny85.

That's it! Your attiny85 can now be used for the GlowMod.            Enjoy!   


  
## Questions
✉️ Contact me with any questions: https://discord.com/invite/wbqec3tK8h

    
