# China-Power-System-Resilience
## Overview
This is to analyze the future data of climate change on the resilience impact of the power system in China, we mainly analyzed the data of 2020, 2030, 2040, 2050, 2060 including SSP126, SSP245, SSP370 and SSP585 four scenarios, in each subfolder has the corresponding name indication. The data submitted by us can be used to optimize the OPF model to analyze the resilience of China's power system in the future, including wind_gen, node_false, gen, branch_false, load and structure, as well as the average wind speed and monthly temperature of each province based on each SSP scenario, named wind_base and temp.
## Data description
### wind_base
The average wind speed of each province under different SSP scenarios and years. We embed the data from RCM and the downscaling to get a more stable result. The determination of the provinces is obtained by entering latitude and longitude by the geographic inverter code function of Amap, the unit is m/s.
### wind_gen
The hourly wind speed simulation value of each generator under different SSP scenarios and years, the horizontal axis is the province where the generator set is located, and the vertical axis is the time hourly. Past hour data is from ERA5, the unit is m/s.
### node_false
The fault simulation values of each province in different SSP scenarios and years, the horizontal axis is the province, the vertical axis is the time hourly, 0 indicates no fault, and 1 indicates fault. Based on the simulated wind speed data of each generator set, we calculate the failure rate through the Logistic function, which is defined as a fault if it is greater than the random number compared to the random number generation.
### gen
The scale value of wind power simulated according to the wind speed value in different SSP scenarios and years in each generator set, the horizontal axis is the province where each generator set is located, the vertical axis is hourly. The function of generator power has been given in the article, the unit is MW.
### branch_false
For each branch simulated according to the wind speed value in different SSP scenarios and years, the first two branches connect the provinces, and the vertical axis is hour, 0 indicates no fault, and 1 indicates fault. Based on the simulated wind speed data of each branch, we calculate the failure rate through the Logistic function , which is defined as a fault if it is greater than the random number compared to the random number generation.
### temp
The temperature values of each province under different SSP scenarios and years, and the unit is K, the data is from 20 models from CMIP6 to get a more stable result.
### load
Load scale of each province simulated according to temperature, social development and random fluctuation, the horizontal axis is the province, the vertical axis is hourly, the unit is MW. The relationship between temperature and load has already been explained in the article, in addition we have increased volatility by 5%.
### oper_data
This is the data that we will eventually use to evaluate the stability of the power system, and the detailed description of each data is in the readme file in the folder.
## Code description
### ec_code
This is the code for processing climate data, the exact file description is in the readme file in the folder
### climate_code
This is the code for assessing climate risk, described in the readme file in the folder
## Data download
The cmip6 data can be download through https://aims2.llnl.gov/search/cmip6/ and the era5 data can be download through https://cds.climate.copernicus.eu/cdsapp#!/search?type=dataset.
>>>>>>> f760520828474302575a622dce9f7b5944024294
