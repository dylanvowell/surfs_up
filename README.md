# OVERVIEW
By analyzing the temperature statistics from both June and December, W. Avy will be able to determine how sustainable his business model would be in Oahu. In order to convince the board that his business idea will succeed year-round, it is important to compare the temperature stats for both June and December to see how much variation in weather occurs on two opposite ends of the year, and then determine if the temps in December are high enough to sustain ice-cream sales. By looking at the two different dataframes, we can determine that the temps for this location is perfect to help support an ice cream/surf shop. 
# RESULTS
Below are the two summary statistic tables for December and June:

![DEC](https://github.com/dylanvowell/surfs_up/blob/main/Dec%20Temps.png?raw=true)
![JUNE](https://github.com/dylanvowell/surfs_up/blob/main/June%20Temps.png?raw=true)

We can infer three things from these statistics: 
- The avg temps are relatively close to one-another
- The distribution of temps are slightly on the lower side for December, indicating more colder days than warmer
- The number of data points for Decmeber is 183 less than June, which could further impact the temp stats

# SUMMARY
The results of this query on temps reveals that while December is colder than June, you could most likely sustain an ice cream/surf shop year-round. However, there are some variables missing in this analysis that would be important to any projections made. You would need to consider other weather patterns aside from temperature - namely precipitation and sunny days.

Precipitation query: 
```
june_rain = []
june_rain = session.query(Measurement).filter(extract('month', Measurement.date) == 6)
june_rain_list = [rain.prcp for rain in june_rain]
print(june_rain_list)
```
There is no column for sunny days, so it's not possible to query for this. However, if there were a sunny days column labled "sun", below is how you would query for this and create a datafram from it: 
```
june_sun = []
june_sun = session.query(Measurement).filter(extract('month', Measurement.date) == 6)
june_sun_list = [sun.prcp for sun in june_sun]
print(june_sun_list)
```

