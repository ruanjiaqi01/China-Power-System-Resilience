# China-Power-System-Resilience
## Overview
This is to analyze the future data of climate change on the resilience impact of the power system in China, we mainly analyzed the data of 2020, 2030, 2040, 2050, 2060 including SSP245, SSP370, SSP460 and SSP585 four scenarios, in each subfolder has the corresponding name indication. The data submitted by us can be used to optimize the OPF model to analyze the resilience of China's power system in the future, including wind_gen, node_false, gen, branch_false, load and structure, as well as the average monthly wind speed and monthly temperature of each province based on each SSP scenario, named wind_month and temp.
## Data description
### wind_month
The average monthly wind speed of each province under different SSP scenarios and years, the horizontal axis is the province, and the vertical axis is 12 months. We embed the data from five models from CMIP6 to get a more stable result. The determination of the provinces is obtained by entering latitude and longitude by the geographic inverter code function of Amap, the unit is m/s.
### wind_gen
The hourly wind speed simulation value of each generator under different SSP scenarios and years, the horizontal axis is the province where the generator set is located, and the vertical axis is the time 365*24. We calculate the monthly mean of the past hour data, and then use the future monthly mean to mean align the past data, and then use the Weibull distribution fitting and then randomly generate them according to the generation set plan and generation set location. Past hour data is from ERA5, the unit is m/s.
### node_false
The fault simulation values of each province in different SSP scenarios and years, the horizontal axis is the province, the vertical axis is the time 365*24, 0 indicates no fault, and 1 indicates fault. Based on the simulated wind speed data of each generator set, we calculate the failure rate through the Logistic function (parameter a=-13, parameter b=0.4), which is defined as a fault if it is greater than the random number compared to the random number generation.
### gen
The scale value of wind power simulated according to the wind speed value in different SSP scenarios and years in each generator set, the horizontal axis is the province where each generator set is located, the vertical axis is 365*24. The function of generator power has been given in the article, where V_cut_in = 2, V_rated = 8, V_cut_out = 20, the unit is MW.
### branch_false
For each branch simulated according to the wind speed value in different SSP scenarios and years, the first two branches connect the provinces, and the vertical axis is 365*24, 0 indicates no fault, and 1 indicates fault. Based on the simulated wind speed data of each branch, we calculate the failure rate through the Logistic function (parameter a=-13.2, parameter b=0.4), which is defined as a fault if it is greater than the random number compared to the random number generation.
### temp
The temperature values of each province under different SSP scenarios and years, and the unit is K, the data is from five models from CMIP6 to get a more stable result.
### load
Load scale of each province simulated according to temperature and random fluctuation, the horizontal axis is the province, the vertical axis is 365*24, the unit is MW, The relationship between temperature and load has already been explained in the article, in addition we have increased volatility by 5%.
### structure
Includes the model architecture of lines number and connection, nodes, and generators at each point in time, which may be different in different years.
