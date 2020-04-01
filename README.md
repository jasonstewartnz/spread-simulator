# Outbreak simulator

reproduce simulator similar to [this](https://www.washingtonpost.com/graphics/2020/world/corona-simulator/)

## Basic model

* Agents move
* Disease is transmitted between "touching" agents (distance less than some threshold)
* Agents are infected for 14 days
* At day 14, agents either recover or die
* Agents that move out of bounds are moved to the 

* Out of scope: agents angle changes upon collision

# Future features

* Ability to play with parameters, 
    * plot stacked area of statuses over time with different features. 
    * Compare through change in parameter at time x (e.g. number of people infected at day 100 or max people infected during a simulation, for different values of parameter (e.g. # static agents))
    
* Geo-plots
    * NYC taxi data set to simulate agents moving around city [here](https://data.cityofnewyork.us/Transportation/2018-Yellow-Taxi-Trip-Data/t29m-gskq)
    * Mapbox to plot
    * Airline data
    * Restaurants [here](https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j) (What does shutdown do?)
    * Subway entrances (would be nice to get commute info)
    
* Use real data to model by city
    * E.g. transmission rates, population sizes. Can we model future rates?
    * Census data to get age distribution. Can we adjust recovery probability?

* Newly infected agents show as larger, or a different color.
* Calc probability of being infected as rolling average (e.g. 5 day average) of (# new cases)/(# uninfected) 
* Run scenarios for centralized response/interventions: Test and Quarantine, 
* Factor in hospital capacity: Set some threshold. If the number of active cases is higher than that, the mortality probability goes up.

# Refactors
* Move underlying update functions to external script
* Host on server/ webpage
* split into server side feed built in Python (Django) and client-side app in Javascript (D3)