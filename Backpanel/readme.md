## Print instructions:
For the backpanel with honeycomb inside, swap the color on layer 3 and 11.

## Config adjustment for automated color change
Implement M600 in your config.cfg if you have not done yet:
```
[gcode_macro M600]
gcode:
    {% set X = params.X|default(50)|float %}
    {% set Y = params.Y|default(0)|float %}
    {% set Z = params.Z|default(10)|float %}
    SAVE_GCODE_STATE NAME=M600_state
    PAUSE
    G91
    G1 E-.8 F2700
    G1 Z{Z}
    G90
    G1 X{X} Y{Y} F3000
    G91
    G1 E-100 F1000                           ; adjust for your your hotend
    RESTORE_GCODE_STATE NAME=M600_state
```
