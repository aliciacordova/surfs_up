# surfs_up

## Overview

W. Avy asked us to create an analysis to determine if the surf and ice cream shop business is sustainable year-round. So we help Avy to analyze the temperature trends for the months of June and December in Oahu, in order to evaluate the year-round sustainability of a surf and ice cream shop business.


## Results

### January Summary Statistics

 ![Junetobs](https://user-images.githubusercontent.com/87447639/137515195-d835418c-0537-4fed-a3fb-146db383b7cd.PNG)

### December Summary Statistics

 ![Decembertobs](https://user-images.githubusercontent.com/87447639/137515204-f05ff6b7-128d-4c82-917a-ac69718db7c1.PNG)


1- June temperatures range from 64 to 85 degF whereas December Temps range from 56 to 83 degF.

2- The average temperature in June is 75 degF whereas in December it is 71 degF. Also 50% of June and December temperatures are above 75 and 71 degF respectively.

3- Temperature in December are more spread out than in June since the standard deviation for December temperatures is higher.


## Summary

We suggest that W. Avy look at two additional queries that he would run to collect more weather data for June and December. The following queries may be used to analyze the meteorological data:

- The amount of precipitation at the most active station 'USC00519281' for June and December:

session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 6).all()

session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 12).all()


- The total precipitation scores levels for June and December:

session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()

session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()