Overview
--------

This is a NetLogo model that simulates the movement of vehicles on a road network. The model includes three types of agents: nodes, buildings, and vehicles. Nodes represent intersections in the road network, buildings represent buildings in the environment, and vehicles move along the links between nodes. The model includes features such as speed limits, random maximum speeds for vehicles, and collision avoidance.

Design Concepts
--------------

* **Spatial Extent:** The model is defined on a two-dimensional grid, with nodes, links, and buildings representing intersections, roads, and buildings, respectively.
* **Temporal Extent:** The model operates in discrete time steps, or ticks. At each tick, vehicles move along the links between nodes and update their speed based on local conditions.
* **Stochasticity:** The model includes randomness in the form of random maximum speeds for vehicles and the selection of destinations.
* **Collectives:** The model simulates the collective behavior of vehicles moving on a road network.
* **Observation:** The model includes a visualization of the road network, buildings, and the movement of vehicles.

Details
-------

Details
-------

### Entities, States, and Variables

* **Nodes:** Nodes represent intersections in the road network. They have a position on the grid, a list of links connected to them, and a unique ID.
* **Links:** Links represent roads between intersections. They have a distance to the destination, a speed limit, a color, a thickness, and a unique ID.
* **Buildings:** Buildings represent physical structures in the environment. They have a position on the grid, a unique ID, and a type (e.g. residential, commercial, etc.).
* **Vehicles:** Vehicles represent individual agents moving on the road network. They have a position on the grid, a destination, a maximum speed, a current speed, a local speed restriction, a journey distance to their destination, a remaining journey distance, a path to the ultimate destination, and a flag indicating whether they are moving.

### Process Overview and Scheduling

The model operates in two main procedures: `setup` and `go`. `Setup` initializes the nodes, buildings, and vehicles, and `go` advances the simulation by one tick.

### Initialization

At the beginning of the simulation, the setup procedure initializes the nodes, buildings, and vehicles. The load-network procedure generates a network of nodes and links using the network extension and the links CSV file. It then sets the links. The load-buildings procedure creates a specified number of buildings and assigns them random starting points and destinations. It also calculates the shortest path between the starting point and destination and sets the initial speed and remaining journey distance. A journey is between a home (blue) and a building (red).
   
When the vehicles start their journey, they can only move to the nearest road node if it is unoccupied by other vehicles. This ensures that the vehicles do not collide with each other as they begin their travels, promoting a more realistic simulation of traffic flow.

### Input

The user can specify the number of vehicles in the model by setting the number_of_vehicles sliders in the interface. Additionally, you can set the speed of the slowest vehicle and the overall run speed, which is the maximum speed of any vehicle. This helps to speed up the simulation for experimental purposes only.

### Submodels

The `go` procedure advances the simulation by one tick. It first checks whether any vehicles have reached their destinations and stops them if they have. It then moves the remaining vehicles along the links between nodes and updates their speed based on local conditions.

The `check-ahead` procedure checks whether there are any vehicles ahead of the calling vehicle and adjusts its speed accordingly. The `move-at-correct-speed` procedure checks whether the speed of the vehicle is greater than the speed limit for the road and adjusts it if necessary.

### Output

The model includes a visualization of the road network, buildings, and the movement of vehicles. The user can observe the behavior of the vehicles and the impact of different parameters on their movement.
