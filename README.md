# Etere Documentation 
This page describes etereshop controller software.
During time this software changed multiple times, this documentation version describes 8th software version.  
Due to backwards compatibility this instructions can be applied to previous software versions.

## Simple mode
<details>
Available for controllers:

    -ESP8266
    -ESP32

### Сonfiguration file
For a simple stand-alone mode with switching the effect using a button, the configuration file should contain the following line:

    play.default=0;

    or

    play.default=Manual;

    or nothing
</details>
## Auto-switch mode
<details>
When the mode is active, your controller will cycle through effects in an endless loop every N seconds.
To activate this mode, set the following line in the configuration file:

    play.default=2;

    or

    play.default=Auto;

You also need to create an `auto.txt` file and write the time value in milliseconds to this file. Example: 

    15000 - effects will switch every 15 seconds.

To activate automatic switching of effects after turning on the product, you just need to press the button of the switching effect.

To activate the blackout effect, you need to press and hold any button for about 1.5-2 seconds.
Blackout effect - the effect at which all LEDs go out

> **Note:** LEDs continue to consume power while playing the blackout effect
</details>
## Playlist mode
You also can program your own show. 
To activate this mode, set the following line in the configuration file:

    play.default=1;
    
    or
    
    play.default=Playlist;

Also, you need to create an auto.txt file and write the number of effects and the time when the effect should be switched after the start of the show in this file. The show starts after clicking the switch effect button.
    
`show.txt` file example:
    
    1, 0:00
    2, 0:10			| Effect with the name S2 can't be found on sd Card -> ignoring
    3, 0:25			| Activate effect S3 after 25 seconds from click.
    0, 0:30			| Activate blackout at 30th second from click.
    4, 0:31			| Activate S4 at second 31
    12, 0:35:541		| Activate S12 at 35.541
    1, 40100		| Activate S1 in 41.1 seconds after click (time in msec)
    0, 0:50			| Activate blackout at 50th second
    3, 1:05			| Activate S3 at 1:05, this effect will be active until you turn off the controller.

How it works:

    Set S1 effect at the start (0th second) from button click
    Set S2 effect at 10th second.
    Set S3 effect at 25th second.
    Set blackout effect at 30th second.
    ...
    
Remember to set the dimming effect (number 0) at the end if you want to turn off the LEDs at the end of the show.    
To do this, press and hold the button for about 1.5-2 seconds.

If the controller cannot find an effect by the sequence number specified in the playlist, that effect will be ignored. The previous effect will continue to play.
</details>
## Test mode
<details>
Service mode for testing and detecting problems with LEDs.

> **Note:** This mode is not custom

    play.default=3;
    or
    play.default=Test;
</details>    

    
    
    
    
    


    
    
    
    
    
