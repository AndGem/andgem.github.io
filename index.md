## Collection of Thoughts About My Projects

### Visualizing the Road Network of a City

Ever wanted to get the **road network** of a city, a country or some other region in the world?
This project might help you to do this faster by providing a *simple* way to parse an **Open Street Map (OSM)** file and generate a simple structured graph file.

[[OsmToRoadGraph on Github]](https://github.com/AndGem/OsmToRoadGraph)

On example of what can be done with the output of this script is to use the processed data to generate a visualization. In the picture below, you can see the **road network** of the city of **Bremen, Germany**.

<img src="https://raw.githubusercontent.com/AndGem/andgem.github.io/master/assets/bremen.png" width="450">

The **color** indicates the maximum speed a car is allowed to drive (the darker, the higher this maximum is):

#### How can this be done?

For a description on how this can be done, please take a look [here](https://github.com/AndGem/OsmToRoadGraph/tree/master/examples/pycgr-to-png).
