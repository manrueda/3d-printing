# Anet A8 Marlin configuration

When the latest version of Marlin is downloaded, an Anet A8 configuration is provided in `Marlin/example_configurations/Anet/A8`. The default values work perfectly.

# Automatic Bed Leveling

The following changes are required if you install automatic bed leveling in front of the head/nozzle fan.

* Uncomment to enable `FIX_MOUNTED_PROBE`. `//#define FIX_MOUNTED_PROBE` -> `#define FIX_MOUNTED_PROBE`
* Define the offset from the probe to the nozzle. `#define X_PROBE_OFFSET_FROM_EXTRUDER 0` -> `#define X_PROBE_OFFSET_FROM_EXTRUDER -21`
* Define the offset from the probe to the nozzle. `#define Y_PROBE_OFFSET_FROM_EXTRUDER 0` -> `#define Y_PROBE_OFFSET_FROM_EXTRUDER -45`
* Uncomment to enable `Z_MIN_PROBE_REPEATABILITY_TEST`. `//#define Z_MIN_PROBE_REPEATABILITY_TEST` -> `#define Z_MIN_PROBE_REPEATABILITY_TEST`
* Uncomment to enable `AUTO_BED_LEVELING_BILINEAR`. `//#define AUTO_BED_LEVELING_BILINEAR` -> `#define AUTO_BED_LEVELING_BILINEAR`
* Define the probe position . `#define LEFT_PROBE_BED_POSITION MIN_PROBE_EDGE` -> `#define LEFT_PROBE_BED_POSITION MIN_PROBE_EDGE + 10`
* Define the probe position . `#define RIGHT_PROBE_BED_POSITION (X_BED_SIZE - MIN_PROBE_EDGE)` -> `#define RIGHT_PROBE_BED_POSITION 179`
* Define the probe position . `#define FRONT_PROBE_BED_POSITION MIN_PROBE_EDGE` -> `#define FRONT_PROBE_BED_POSITION MIN_PROBE_EDGE + 10`
* Define the probe position . `#define BACK_PROBE_BED_POSITION (Y_BED_SIZE - MIN_PROBE_EDGE)` -> `#define BACK_PROBE_BED_POSITION 155`
* Uncomment to enable `Z_SAFE_HOMING`. `//#define Z_SAFE_HOMING` -> `#define Z_SAFE_HOMING`