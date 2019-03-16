# What are the Airbnb listings within a walkable distance of Boston T-stops?
----------
Work from MIT 6.894 Interactive Data Visualization course
----------

This visualization shows a map of the Boston T-stop and all Airbnb listings within a walkable 1,000-meter radius around any given T-stop. You can mouse over any given T-stop and see the number of Airbnb listings and their average price based on your selection criterion. Additionally, the size of the circles reflect the magnitude of the number of Airbnb listings that fulfill the selected criterion. Through this interactive visualization, you can actually identify patterns and draw some inference from the data, such as the correlation between location in the city and Airbnb pricing. Another example would be the correlation between concentration of Airbnb listings and tourist attractions.

## Design rationale

Being an avid traveler, we wanted to work with some Airbnb data and visualize Airbnb listing data in a way to help tourists plan for their trip ahead. We decided to choose the city of Boston since we already live there and have an understanding of the city landscape and how neighborhoods are different from each other.

Boston is a very walkable city with many popular touristy spots clustered around certain areas in the city. With this visualization tool, we hope to help travelers plan their trip and book their Airbnb stay close to T-stops to minimize travel costs while exploring the city and sightseeing.

This prototype focuses on a high-level view of the city that enables users to interact with the map and select Airbnb listings based on their preferences such as price range and room types.


## Development Process

Our first idea was to show Airbnb listings that are close to tourist attractions in big cities such as Paris. But we could not find the data for any attractions site for big cities. We finally came up with the metro idea thanks to a project discovered on GitHub with Yelp restaurant reviews data (see sources).

Data transformation:

We had 2 data sets (see sources): Boston Airbnb listings and MBTA stops geographical data. In the data processing part, we wanted to get the closest T-stop within a one-kilometer radius from each listing (could be a Null value). We converted latitude and longitude in both datasets into distances between stations and listings, and found the closest station within 1km to each listing.

The main steps of the development process were:

* Collect the data
* Process the data
* Build an SVG map showing T-stops
* Link stations’ coordinates to the map
* Filter and count listings based on price and room type selection, grouping by station, making the aggregated data update when filtering conditions change
* Link the previous aggregated data to map station elements
* Create circles with radius proportionate to the count of listings per station on the map
* Create a tooltip box showing Station Name, Number of Listings, Mean Price for a station when the mouse hovers over a circle
* Integrate and check for consistency between data filtering and visualization rendering
* Adapt style for the different visualization elements

## Sources

* Data:

    - [Airbnb listings](http://insideairbnb.com/get-the-data.html)
    - [MBTA stops](https://github.com/sbemagx/CS171-Metro-Boston-Food-Exploration/blob/master/data/mbta_metadata.json)

* [Design inspiration](http://sbemagx.github.io/CS171-Metro-Boston-Food-Exploration/code/)

* Libraries
    
    - D3.js
    - jQuery UI
    - D3-tip.js
    
    
