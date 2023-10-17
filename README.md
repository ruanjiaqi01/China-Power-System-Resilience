# China-Power-System-Resilience
## wind_month
The average monthly wind speed of each province under different SSP scenarios and years, the horizontal axis is the province, and the vertical axis is 12 months
## wind_gen
The hourly wind speed simulation value of each generator under different SSP scenarios and years, the horizontal axis is the province where the generator set is located, and the vertical axis is the time 365*24
## node_false
The fault simulation values of each province in different SSP scenarios and years, the horizontal axis is the province, the vertical axis is the time 365*24, 0 indicates no fault, and 1 indicates fault
## gen
The scale value of wind power simulated according to the wind speed value in different SSP scenarios and years in each generator set, the horizontal axis is the province where each generator set is located, the vertical axis is 365*24, and the maximum P is 1e6
## branch_false
For each branch simulated according to the wind speed value in different SSP scenarios and years, the first two branches connect the provinces, and the vertical axis is 365*24, 0 indicates no fault, and 1 indicates fault
## temp
The temperature values of each province under different SSP scenarios and years, and the unit is K
## load
Load scale of each province simulated according to temperature and random fluctuation, the horizontal axis is the province, the vertical axis is 365*24, the unit is % (csv)
Forecast future load demand for each province （mat）
## structure
Includes the model architecture of lines, nodes, and generators at each point in time
