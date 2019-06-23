# Anet A8 Cura configuration

## Printer Settings

* X (Width): `220mm`
* Y (Depth): `220mm`
* Z (Height): `240mm`
* Build plate shapre: `Rectangular`
* Origin at center: `false` (not checked)
* Heated bed: `true` (checked)
* G-code flavor: `Marlin`

## Printhead Settings

* X min: `0mm`
* Y min: `0mm`
* X max: `0mm`
* Y max: `0mm`
* Gantry Height: `0mm`
* Number of Extruders: `1`


## Extruder Settings

* Nozzle size: `0.4mm`
* Compatible material diameter `1.75mm`
* Nozzle offset X: `0mm`
* Nozzle offset Y: `0mm`
* Cooling Fan Number `0`

## Start G-Code

```
G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 X0 Y0 ;move X/Y to min endstops
G28 Z0 ;move Z to min endstops
G1 Z15.0 F9000 ;move the platform down 15mm
G92 E0 ;zero the extruded length
G1 F200 E3 ;extrude 3mm of feed stock
G92 E0 ;zero the extruded length again
G1 F9000;Put printing message on LCD screen
M117 Printing..0
```

## End G-Code

```
M104 S0 ;extruder heater off
M140 S0 ;heated bed heater off (if you have it)
G91 ;relative positioning
G1 E-1 F300 ;retract the filament a bit before lifting the nozzle, to release some of the pressure
G1 Z+0.5 E-5 X-20 Y-20 F9000 ;move Z up a bit and retract filament
G28 X0 Y0 ;move X/Y to min endstops, so the head is out of the way
M84 ;steppers off
G90 ;absolute positioning
```

# Automatic Bed Leveling

The only Cura configuration required after adding **Automatic Bed Leveling** is to add the `G29` G-code after `G28` in the Start G-Code

### Result

```
G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 X0 Y0 ;move X/Y to min endstops
G28 Z0 ;move Z to min endstops
G29 ;auto level
G1 Z15.0 F9000 ;move the platform down 15mm
G92 E0 ;zero the extruded length
G1 F200 E3 ;extrude 3mm of feed stock
G92 E0 ;zero the extruded length again
G1 F9000;Put printing message on LCD screen
M117 Printing..0
```
