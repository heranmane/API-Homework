# Python API - What's the Weather Like?

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what we've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what we may be thinking: _"Duh. It gets hotter..."_

But, if pressed, how would we **prove** it?

![Equator](Images/equatorsign.png)


5. Push the above changes to GitHub.

## Part I - WeatherPy

In this example, we'll be creating a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, we'll be utilizing a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

Our first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot add a sentence or too explaining what the code is and analyzing.

Our second requirement is to run linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots explain what the linear regression is modeling such as any relationships we notice and any other analysis we may have.

**Optional** We will be creating multiple linear regression plots. To optimize our code, write a function that creates the linear regression plots.

Our final notebook must:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Now let's use out skills in working with weather data to plan future vacations. Use jupyter-gmaps and the Google Places API for this part of the assignment.

* **Note:** if we having trouble displaying the maps try running `jupyter nbextension enable --py gmaps` in your environment and retry.

* Create a heat map that displays the humidity for every city from the part I of the homework.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find our ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't contain all three conditions. We want to be sure the weather is ideal.

  * **Note:** Feel free to adjust to our specifications but be sure to limit the number of rows returned by our API requests to a reasonable number.

* Using Google Places API to find the first hotel for each city located within 5000 meters of our coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)

As final considerations:

* Create a new GitHub repository for this project called `API-Challenge` (note the kebab-case). **Do not add to an existing repo**
* We must complete our analysis using a Jupyter notebook.
* We must use the Matplotlib or Pandas plotting libraries.
* For Part I, we must include a written description of three observable trends based on the data.
* We must use proper labeling of our plots, including aspects like: Plot Titles (with date of analysis) and Axes Labels.
* For max intensity in the heat map, try setting it to the highest humidity found in the data set.

## Hints and Considerations

* The city data we generate is based on random coordinates as well as different query times; as such, our outputs will not be an exact match to the provided starter notebook.

* We may want to start this assignment by refreshing ourself on the [geographic coordinate system](http://desktop.arcgis.com/en/arcmap/10.3/guide-books/map-projections/about-geographic-coordinate-systems.htm).

* Next, spend the requisite time necessary to study the OpenWeatherMap API. Based on our initial study, we should be able to answer  basic questions about the API: Where do we request the API key? Which Weather API in particular will we need? What URL endpoints does it expect? What JSON structure does it respond with? Before we write a line of code, we should be aiming to have a crystal clear understanding of our intended outcome.

* A starter code for Citipy has been provided. However, if we're craving an extra challenge, push ourself to learn how it works: [citipy Python library](https://pypi.python.org/pypi/citipy). Before we try to incorporate the library into our analysis, start by creating simple test cases outside our main script to confirm that we are using it correctly. Too often, when introduced to a new library, students get bogged down by the most minor of errors -- spending hours investigating their entire code -- when, in fact, a simple and focused test would have shown their basic utilization of the library was wrong from the start. Don't let this be we!

* Part of our expectation in this challenge is that we will use critical thinking skills to understand how and why we're recommending the tools we are. What is Citipy for? Why would we use it in conjunction with the OpenWeatherMap API? How would we do so?

* In building our script, pay attention to the cities we are using in our query pool. Are we getting coverage of the full gamut of latitudes and longitudes? Or are we simply choosing 500 cities concentrated in one region of the world? Even if we were a geographic genius, simply rattling 500 cities based on our human selection would create a biased dataset. Be thinking of how we should counter this. (Hint: Consider the full range of latitudes).

* Once we have computed the linear regression for one chart, the process will be similar for all others. As a bonus, try to create a function that will create these charts based on different parameters.

* Remember that each coordinate will trigger a separate call to the Google API. If we're creating our own criteria to plan our vacation, try to reduce the results in our DataFrame to 10 or fewer cities.

* Lastly, remember -- this is a challenging activity. Push ourself! If we complete this task, then we can safely say that we've gained a strong mastery of the core foundations of data analytics and it will only go better from here. Good luck!

### Copyright

Trilogy Education Services © 2019. All Rights Reserved.
