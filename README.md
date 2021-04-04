# OK County Clustering Codes

Python codes for Oklahoma State House Redistricting and Oklahoma State Senate Redistricting. 

The Task:
- partition Oklahoma into _k_ districts (where _k_=48 for State Senate and _k_=101 for State House)
- each district should be contiguous on the map
- each district's population should be within 5% of ideal (+/-2.5%)

We also try to keep counties intact, where possible. 

For State Senate redistricting, the ideal district population is 81,835. We allow a window around this of [79887,83983].


For State House redistricting, the ideal district population is 38,939. We allow a window around this of [37966,39912].



These codes are used for a certain districting problem. With primary aim to keep counties intact, 
These codes group counties into district clusters. 
Code to group counties into district clusters. Each cluster should have population that is an integer multiple of the desired district size. 
