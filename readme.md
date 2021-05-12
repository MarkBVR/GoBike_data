# GoBike Explanation Project

## Dataset Overview
The dataset is for Ford GoBike usage in San Fancisco over the month of February, 2019. There are around 183,000 entries in the dataset. Each entry is a single ride that includes start/end time, duration, bike ID, and start/end points. As well as general user information: birth year, gender, subscriber status, and bike share for all status. The only cleaning I did to the data was changing the start/end time from a string to datetime.

## Summary of Findings

In my exploration of the dataset I found a strong correlation between commuting times and GoBike use. Bike traffic is as high on any single weekday as it is  over the entire weekend. When I investigated bike use on individual days of the week there are consistant spikes in usage at 8am and 5pm for workdays, while weekends have a more consistant distribution centering on mid-day. This also showed in average distance of bike rides. Weekends had consistant trip lengths throughout the day, while there were spikes at commuting times on weekdays. This means that at commuting times more users are taking longer rides than at any other time. It should be noted that the distances were as the crow flies, and rides that started and ended in the same location would be 0km long. There were not significant numbers of 0km trips: 4000 out of the 183,000 trips.

I then investigated individual bike use, and found that the vast majority of bikes are ridden on average around 1.5km. This is much different to the total distances bikes covered. There was a group of about 1000 bikes that are used much more than the others. When they are ignored there is a logrithmic trend in the plot. If bikes are numbered as they enter the fleet, then it shows a user preference toward newer bikes. there is much more variability at night most likely due to less use at those hours.

I used the Maps JavaScript API from Google Cloud and gmaps to create a heat map of starting and ending points of each ride, and separate heat maps for the 1000 standout bikes. The heatmap of all bikes showed heavy usage in San Fancisco, Oakland, Berkeley, and San Jose. The 1000 standout bikes were not located in San Jose at all and had a higher relative dencity of trips ending in Oakland and Berkely. Berkely hot spots are located around UC Berkely buildings meaning Students and faculty commute to campus on those bikes.

## Key Insights for Presentation

I will focus on the commuting I discovered in my exploration. Since I have increasingly smaller incremints of time, I will start wide by looking at the whole month then the week, and finally the hour. This will introduce the differences in weekdays and weekends, and then the spikes in traffic at commuting times. Then, to show that the bimodal distribution is not maintained I'll show the violin plot of usage each day by hour.

Next I will explain how distance continues to support the arguement that bikes are used mainly for commuting. With the previously determined increased usage, average distances being at 2km in the morning is a 0.3km, or 15%, increase per ride.

Lastly I will show average and total distances traveled by each bike. This further emphasizes the spikes in average rides from the previous plot. As well as, the relationship between # of rides and the total distance a bike is ridden. 

# Resources
- jupyter-gmaps: https://jupyter-gmaps.readthedocs.io/en/latest/install.html#installing-jupyter-gmaps-with-conda
- Maps JavaScript API on Google Cloud Platform
- Answer by ImportanceOfBeingErnest to create color bar in last graph: https://stackoverflow.com/questions/49761221/make-seaborn-show-a-colorbar-instead-of-a-legend-when-using-hue-in-a-bar-plot/49772083#49772083
