# OK County Clustering Codes

Python codes for Oklahoma State House Redistricting and Oklahoma State Senate Redistricting. 

The Task:
- partition Oklahoma into _k_ districts (where _k_=48 for State Senate and _k_=101 for State House)
- each district should be contiguous on the map
- each district's population should be within 5% (+/-2.5%) of the ideal district population.

The population lower and upper bounds are designated by _L_ and _U_. We will also try to keep counties intact, where possible. 

# State Senate

For State Senate, the ideal district population is 81,835. We allow populations between _L_=79,887 and _U_=83,983. 

For example, 
- Payne County (population 81,815) can be its own district
- Logan County (population 46,683) and Lincoln County (population 34,895) can form a district together (total population 81,578)
- Tula County (population 646,419) can be split into 8 districts (average population 80,802.375)
- Blaine County, Kingfisher County, and Canadian County can form two districts (average population 82,852.5)

# State House

For State House redistricting, the ideal district population is 38,939. We allow populations between _L_=37,966 and _U_=39,912.

For example,
- Okmulgee County (population 38,749) can be its own district
- Seminole County (population 24,832) and Hughes County (population 13,372) can form a district together (total population 38,204)
- Oklahoma County (population 787,216) can be split into 20 districts (average population 39,360.8)
- Stephens County, Cotton County, and Garvin County can form two districts (average population 38,670) 

# The Approach

We take a two-step approach. 

1. The first step is to group the counties into clusters. Each cluster should be contiguous, and its population should be an integer multiple of the ideal district population (or within the +/-2.5% bounds). The examples given above all follow this rule. We use optimization software (Gurobi) to maximize the number of clusters. The hope is that this will give many clusters, each having a small number of counties.
2. The second step is to split each county cluster into the requisite number of districts. This is done by hand using Dave's Redistricting App. I tried my best to keep them compact. A better approach may be to try to keep cities and communities intact.


