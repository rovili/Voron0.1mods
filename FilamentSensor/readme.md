## You need
- 1x micro-switch
- 2xM3x4/6/8
- 1x JST-XH 2pin male

## Micro-switch preparation
- shorten the lever until it fits in the housing
- bend the lever at the end, bend it so far that you can pull back a filament with a tip
- solder flex to two outer pins and crimp the JST-XH

![FilamentSensor](https://github.com/rovili/Voron0.1mods/blob/main/Pictures/IMG_0671.png)

## Add in your config
```
[filament_switch_sensor filament_sensor]
switch_pin: P1.27   ; adjust to your end-stop port
pause_on_runout: True
runout_gcode:
    M117 Out of Filament
insert_gcode:
    M117 Resuming
event_delay: 3.0 
pause_delay: 0.5  
```

## Placement of the sensor
- I would place it in the meantime right after the feet, then you can pull back the filament when it is out of the extruder.
- Glue the tube into the housing, makes it easier to swap the filament

![FilamentSensor](https://github.com/rovili/Voron0.1mods/blob/main/Pictures/IMG_0670.png)
