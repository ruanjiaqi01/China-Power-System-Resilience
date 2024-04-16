# el_code
## Overview
Here we offer the explanation for the function of every code.

### code_for_gen_ini.m
The code is used to initialize the generation condition, including the code settings in the following decades.

### code_for_hydro_ini.m
The code is used to initialize the hydrogen generation condition, in order to highlight hydrological changes during the year.

### code_for_load_ini.m
The code is used to initialize the load condition, in order to highlight the daily changes on the load during the year.

### code_for_PV_ini.m
These four codes are used to initialize the PV condition.

### code_for_raw_data.m
Integrate all the generation information, and write into a single system.

### code_for_sys_ini_outstore.m & code_for_sys_ini_withstore.m
To give the operation condition at 1st hour. Then it can be used for further simulation. The difference is whether the system set the BESS.

### code_for_wind_false.m
The code is used to initial the wind false condition.

### code_for_main_outstore.m & code_for_main_withstore.m
The code is designed to simulate the operation of a power system. It can model the system's performance over an entire year, across different years. This simulation is based on DC optimal power flow. The key variation depends on whether the Battery Energy Storage System (BESS) is incorporated into the system.
