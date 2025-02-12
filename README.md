<<<<<<< HEAD
version https://git-lfs.github.com/spec/v1
oid sha256:2e5b1e2f63b082a2e855de23217a2518b4ba6da7c979dd7cca573e4f62015752
size 3644
=======
# China-Power-System-Resilience
## Overview
This is to analyze the future data of climate change on the resilience impact of the power system in China, we mainly analyzed the data of 2020, 2030, 2040, 2050, 2060 including SSP126, SSP245, SSP370 and SSP585 four scenarios, in each subfolder has the corresponding name indication. The data submitted by us can be used to optimize the OPF model to analyze the resilience of China's power system in the future, including wind_gen, node_false, gen, branch_false, load and structure, as well as the average monthly wind speed and monthly temperature of each province based on each SSP scenario, named wind_month and temp.
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
### load
Load scale of each province simulated according to temperature, social development and random fluctuation, the horizontal axis is the province, the vertical axis is 365*24, the unit is MW. The relationship between temperature and load has already been explained in the article, in addition we have increased volatility by 5%.
### structure
Includes the model architecture of lines number and connection, nodes, and generators at each point in time, which may be different in different years.
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
