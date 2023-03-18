### EPICclimatedata
## GettingFormattedEPICclimatedata

This code is designed to retrieve climate data for a specific location and time period with focus on using it in the Environmental Policy Integrated Climate (EPIC) model , it calculates yearly means of selected climate variables, and then plot the yearly means for each variable on separate y-axes.

The code begins by defining a function called get_power_data which takes four arguments: start_date, end_date, lon, and lat. The start_date and end_date arguments specify the range of dates for which climate data should be retrieved, while lon and lat specify the longitude and latitude of the location for which data is desired. The function uses the get_power function from the nasapower package to retrieve daily climate data for the specified time period and location. The function retrieves six climate variables: relative humidity at 2 meters above the ground (RH2M), maximum 2-meter air temperature (T2M_MAX), minimum 2-meter air temperature (T2M_MIN), total precipitation (PRECTOTCORR), 10-meter wind speed (WS10M), and surface downwelling shortwave radiation (CLRSKY_SFC_SW_DWN). The retrieved data is then rearranged to make it easier to work with, with columns renamed to more descriptive labels.

The yearly_means data frame is created by grouping the data by year and taking the mean of each climate variable. The tidyr package is used to reshape the data, with the variables variable and year spread into separate columns.

The plot_var function is defined to plot each variable on a separate y-axis, with data, x, y, and y_label as arguments. The function uses the ggplot2 package to create a line plot of the yearly means of the specified variable. The x and y arguments are passed to aes_string to allow for dynamic variable selection. The function also sets the y-axis label using the scale_y_continuous function.

Finally, the plot_grid function from the cowplot package is used to combine the plots for each variable into one figure.

Overall, this code provides a useful framework for retrieving and analyzing climate data for a specific location and time period, and it can be adapted to analyze other climate variables or to plot data for different locations or time periods.
