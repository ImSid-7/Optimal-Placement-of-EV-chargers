Usage:

execute the "candidate_optimization.py" in the Folder!


Problem Statement :

Design an algorithm which will tell you where to deploy charging stations in a city. 
Some examples of inputs to your algorithm will be traffic on that route, connectivity of the route (inner city v/s highway), 
presence of other charging stations nearby, installation of types of charging station (fast v/s battery swapping v/s …) etc.


Modules Used:

1. Numpy
2. pomegranate
3. Scipy


Objectives:

Minimize distance to POIs:

For each potential new charging station location, we compute the average distance to all POIs on the map. Using this value as a linear bias on each binary variable, our program will prefer locations that are (on average) close to the POIs. Note that this constraint could be replaced by an alternative one depending on the real world scenario for this problem.

Maximize distance to existing charging stations:

For each potential new charging station location, we compute the average distance to all existing charging locations on the map. Using the negative of this value as a linear bias on each binary variable, our program will prefer locations that are (on average) far from existing chargers.

Maximize distance to other new charging stations:

For the pair of new charging station locations, we would like to maximize the distance between them. To do this, we consider all possible pairs of locations and compute the distance between them. Using the negative of this value as a quadratic bias on the product of the corresponding binary variables, our program will prefer locations that are far apart.