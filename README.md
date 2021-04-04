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
- Tulsa County (population 646,419) can be split into 8 districts (average population 80,802.375)
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

# State Senate Clusters

********************************
********************************
Cluster rooted at node 0 ( Payne  County ) has total population 81815 and should be split into 1 district(s).
Cluster nodes are [0] which correspond to counties: ['Payne']
Average district in this cluster should have population 81815.0
********************************
********************************
Cluster rooted at node 2 ( Delaware  County ) has total population 83477 and should be split into 1 district(s).
Cluster nodes are [2, 36] which correspond to counties: ['Delaware', 'Mayes']
Average district in this cluster should have population 83477.0
********************************
********************************
Cluster rooted at node 11 ( Choctaw  County ) has total population 82740 and should be split into 1 district(s).
Cluster nodes are [11, 34, 37, 55] which correspond to counties: ['Choctaw', 'Pushmataha', 'Bryan', 'Latimer']
Average district in this cluster should have population 82740.0
********************************
********************************
Cluster rooted at node 15 ( Oklahoma  County ) has total population 1138644 and should be split into 14 district(s).
Cluster nodes are [15, 67, 75] which correspond to counties: ['Oklahoma', 'Cleveland', 'Pottawatomie']
Average district in this cluster should have population 81331.71428571429
********************************
********************************
Cluster rooted at node 16 ( Le Flore  County ) has total population 83042 and should be split into 1 district(s).
Cluster nodes are [16, 76] which correspond to counties: ['Le Flore', 'McCurtain']
Average district in this cluster should have population 83042.0
********************************
********************************
Cluster rooted at node 18 ( Texas  County ) has total population 82793 and should be split into 1 district(s).
Cluster nodes are [12, 18, 21, 24, 33, 41, 42, 48] which correspond to counties: ['Harper', 'Texas', 'Roger Mills', 'Beckham', 'Beaver', 'Cimarron', 'Ellis', 'Woodward']
Average district in this cluster should have population 82793.0
********************************
********************************
Cluster rooted at node 19 ( Okfuskee  County ) has total population 83494 and should be split into 1 district(s).
Cluster nodes are [19, 57] which correspond to counties: ['Okfuskee', 'Creek']
Average district in this cluster should have population 83494.0
********************************
********************************
Cluster rooted at node 20 ( Pontotoc  County ) has total population 82714 and should be split into 1 district(s).
Cluster nodes are [5, 6, 7, 20] which correspond to counties: ['Coal', 'Seminole', 'Murray', 'Pontotoc']
Average district in this cluster should have population 82714.0
********************************
********************************
Cluster rooted at node 23 ( Tulsa  County ) has total population 646419 and should be split into 8 district(s).
Cluster nodes are [23] which correspond to counties: ['Tulsa']
Average district in this cluster should have population 80802.375
********************************
********************************
Cluster rooted at node 45 ( Grady  County ) has total population 165800 and should be split into 2 district(s).
Cluster nodes are [35, 44, 45, 65] which correspond to counties: ['Stephens', 'McClain', 'Grady', 'Garvin']
Average district in this cluster should have population 82900.0
********************************
********************************
Cluster rooted at node 47 ( Pittsburg  County ) has total population 82405 and should be split into 1 district(s).
Cluster nodes are [25, 47, 58, 72] which correspond to counties: ['Atoka', 'Pittsburg', 'Hughes', 'Johnston']
Average district in this cluster should have population 82405.0
********************************
********************************
Cluster rooted at node 51 ( Comanche  County ) has total population 164275 and should be split into 2 district(s).
Cluster nodes are [1, 9, 51, 52] which correspond to counties: ['Caddo', 'Tillman', 'Comanche', 'Cotton']
Average district in this cluster should have population 82137.5
********************************
********************************
Cluster rooted at node 53 ( Custer  County ) has total population 82897 and should be split into 1 district(s).
Cluster nodes are [4, 22, 28, 40, 53, 56] which correspond to counties: ['Greer', 'Kiowa', 'Harmon', 'Jackson', 'Custer', 'Washita']
Average district in this cluster should have population 82897.0
********************************
********************************
Cluster rooted at node 54 ( Garfield  County ) has total population 83555 and should be split into 1 district(s).
Cluster nodes are [14, 29, 54, 70] which correspond to counties: ['Dewey', 'Major', 'Garfield', 'Woods']
Average district in this cluster should have population 83555.0
********************************
********************************
Cluster rooted at node 60 ( Haskell  County ) has total population 81423 and should be split into 1 district(s).
Cluster nodes are [39, 60] which correspond to counties: ['Muskogee', 'Haskell']
Average district in this cluster should have population 81423.0
********************************
********************************
Cluster rooted at node 61 ( Logan  County ) has total population 81578 and should be split into 1 district(s).
Cluster nodes are [61, 66] which correspond to counties: ['Logan', 'Lincoln']
Average district in this cluster should have population 81578.0
********************************
********************************
Cluster rooted at node 64 ( Wagoner  County ) has total population 250025 and should be split into 3 district(s).
Cluster nodes are [10, 26, 59, 63, 64, 69] which correspond to counties: ['McIntosh', 'Adair', 'Sequoyah', 'Cherokee', 'Wagoner', 'Okmulgee']
Average district in this cluster should have population 83341.66666666667
********************************
********************************
Cluster rooted at node 68 ( Canadian  County ) has total population 165705 and should be split into 2 district(s).
Cluster nodes are [46, 50, 68] which correspond to counties: ['Blaine', 'Kingfisher', 'Canadian']
Average district in this cluster should have population 82852.5
********************************
********************************
Cluster rooted at node 71 ( Carter  County ) has total population 81045 and should be split into 1 district(s).
Cluster nodes are [3, 8, 32, 71] which correspond to counties: ['Marshall', 'Jefferson', 'Love', 'Carter']
Average district in this cluster should have population 81045.0
********************************
********************************
Cluster rooted at node 73 ( Pawnee  County ) has total population 82393 and should be split into 1 district(s).
Cluster nodes are [13, 27, 30, 38, 73] which correspond to counties: ['Grant', 'Noble', 'Alfalfa', 'Kay', 'Pawnee']
Average district in this cluster should have population 82393.0
********************************
********************************
Cluster rooted at node 74 ( Rogers  County ) has total population 246631 and should be split into 3 district(s).
Cluster nodes are [17, 31, 43, 49, 62, 74] which correspond to counties: ['Nowata', 'Craig', 'Ottawa', 'Washington', 'Osage', 'Rogers']
Average district in this cluster should have population 82210.33333333333
********************************
********************************
