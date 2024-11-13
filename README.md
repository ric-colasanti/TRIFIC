# A Simple Network-Based Vehicle Simulation

## Abstract:
This NetLogo model simulates a simple network of nodes and vehicles. Vehicles move between nodes along the network's edges, following a random path. The model incorporates traffic-aware speed control and local speed restrictions to provide a more realistic simulation of traffic flow and congestion..

## Model Description:

Agents:

Nodes: Static agents representing locations on the network. They are connected by links to form the network topology.
Vehicles: Vehicles:
Mobile agents that move between nodes. Each vehicle has a current location, a destination, a base speed, a current speed, a journey distance to its destination, and a current speed restriction based on the road it's traveling on.
## Initialization:

Nodes: A specified number of nodes are created and connected using preferential attachment to form a linked network with circular paths. The network is then laid out to avoid overlapping links.
Vehicles: A specified number of vehicles are created and assigned to random nodes. Each vehicle is given a random destination node and a base speed.Additionally, the vehicle's initial speed restriction is set based on the road it starts on.

## Behavior:

Vehicle Movement:

Speed Adjustment:
Each vehicle checks for other vehicles ahead on its current path.
If another vehicle is detected within a certain distance, the current vehicle reduces its speed to avoid a collision.
The amount of speed reduction depends on the distance to the vehicle ahead.
The vehicle's speed is also constrained by the current speed restriction of the road it's on.
Overview
--------

This is a NetLogo model that simulates the movement of vehicles on a road network. The model includes two types of agents: nodes and vehicles. Nodes represent intersections in the road network, and vehicles move along the links between nodes. The model includes features such as speed limits, random maximum speeds for vehicles, and collision avoidance.

Design Concepts
---------------

* **Spatial Extent:** The model is defined on a two-dimensional grid, with nodes and links representing intersections and roads, respectively.
* **Temporal Extent:** The model operates in discrete time steps, or ticks. At each tick, vehicles move along the links between nodes and update their speed based on local conditions.
* **Stochasticity:** The model includes randomness in the form of random maximum speeds for vehicles and the selection of destinations.
* **Collectives:** The model simulates the collective behavior of vehicles moving on a road network.
* **Observation:** The model includes a visualization of the road network and the movement of vehicles.

Details
-------

### Entities, States, and Variables

* **Nodes:** Nodes represent intersections in the road network. They have a position on the grid. They also have a list of links connected to them.
* **Links:** Links represent roads between intersections. They have a distance to the destination, a speed limit, a color, and a thickness.
* **Vehicles:** Vehicles represent individual agents moving on the road network. They have a position on the grid, a color, a shape, and a size. They also have a maximum speed, a current speed, a local speed restriction, a journey distance, a remaining journey distance, a path to the ultimate destination, and a flag indicating whether they are moving.

### Process Overview and Scheduling

The model operates in two main procedures: `setup` and `go`. `Setup` initializes the nodes and vehicles, and `go` advances the simulation by one tick.

### Initialization

At the beginning of the simulation, the `setup` procedure initializes the nodes and vehicles. The `nodes-init` procedure generates a random network of nodes and links using the network extension. It then sets the links. The `vehicles-init` procedure creates a specified number of vehicles and assigns them random starting points and destinations. It also calculates the shortest path between the starting point and destination and sets the initial speed and remaining journey distance.

### Input

The user can specify the number of nodes and vehicles in the model by setting the `number_of_nodes` and `number_of_vehicles` sliders in the interface.

### Submodels

The `go` procedure advances the simulation by one tick. It first checks whether any vehicles have reached their destinations and stops them if they have. It then moves the remaining vehicles along the links between nodes and updates their speed based on local conditions.

The `check-ahead` procedure checks whether there are any vehicles ahead of the calling vehicle and adjusts its speed accordingly. The `move-at-correct-speed` procedure checks whether the speed of the vehicle is greater than the speed limit for the road and adjusts it if necessary.

### Output

The model includes a visualization of the road network and the movement of vehicles. The user can observe the behavior of the vehicles and the impact of different parameters on their movement.

### Design Concepts

* **Spatial Extent:** The model is defined on a two-dimensional grid, with nodes and links representing intersections and roads, respectively.
* **Temporal Extent:** The model operates in discrete time steps, or ticks. At each tick, vehicles move along the links between nodes and update their speed based on local conditions.
* **Stochasticity:** The model includes randomness in the form of random maximum speeds for vehicles and the selection of destinations.
* **Collectives:** The model simulates the collective behavior of vehicles moving on a road network.
* **Observation:** The model includes a visualization of the road network and the movement of vehicles.



## Extensions used

Network extention nw
