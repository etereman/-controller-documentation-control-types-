Simple mode

Available for:
-ESP8266
-ESP32

For a simple stand-alone mode with switching the effect using a button, the configuration file should contain the following line:

play.default=0;
or
play.default=Manual;
or nothing

If you want to use the mode of infinite auto-switching of effects at regular intervals, this line should look like this:

play.default=Auto;

Auto-switch mode

When the mode is active, your controller will cycle through effects in an endless loop every N seconds.
To activate this mode, set the following line in the configuration file:


play.default=2;
or
play.default=Auto;

You also need to create an auto.txt file and write the time value in milliseconds to this file. Example: 15000 - effects will switch every 15 seconds.
To activate automatic switching of effects after turning on the product, you just need to press the button of the switching effect.

To activate the blackout effect, you need to press and hold any button for about 1.5-2 seconds.

Playlist mode

You also can program your own show. To activate this mode, set the following line in the configuration file:
play.default=1;
or
play.default=Playlist;

Also, you need to create an auto.txt file and write the number of effects and the time when the effect should be switched after the start of the show in this file. The show starts after clicking the switch effect button.

show.txt file example:
1, 0:00
