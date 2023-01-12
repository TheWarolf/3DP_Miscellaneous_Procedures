This is a list of initial calibration steps for a new ERCF, using the Happy Hare driver.

First step is to home with ERCF_HOME

### Selector calibration
Check position of selector for feeding filaments.
Command is ERCF_CALIBRATE_SELECTOR TOOL=[0,1,2,...], this will report back the effective distance.

### Calibrate gear stepper
Check that the gear motor is effectively working as intended (rotation distance).
Use ERCF_TEST_MOVE_GEAR macro with optional param LENGTH=..[200]
Measure extruded filament and eventually update rotation_distance param in config.

### Calibrate encoder
Check if the stepping of the encoder gear is correct.
Use macro ERCF_CALIBRATE_ENCODER macro with optional params: 	DIST=(mm) REPEATS=.. SPEED=.. ACCEL=..
This will give statistic on encoder performance and step value.

### Calibrate each gate
This will test each gate and give info on performance and calibration of each gate.
Macro is ERCF_CALIBRATE_SINGLE TOOL=... or ERCF_CALIBRATE to calibrate all tools.
This will update the ercf_vars cfg.

### Preliminary test of all channels
This is a running test for each channel.
Macro to use is ERCF_TEST_LOAD_SEQUENCE with params LOOP=.. RANDOM=[0/1] FULL=[0/1]
A version of this macro with FULL=0 can be use in PRINT_START macro or right after that.



