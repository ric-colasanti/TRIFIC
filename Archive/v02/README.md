 A Simple Road Network-Based Vehicle Simulation for Tillydrone

## Abstract:
This NetLogo model simulates a simple road network of Tillydrone, nodes (intersections), and vehicles. Vehicles move between nodes along the network's edges, following a random path. The model incorporates traffic-aware speed control and local speed restrictions based on the road network of Tillydrone to provide a more realistic simulation of traffic flow and congestion.

## Model Description:

Agents:

Nodes: Static agents representing intersections (locations) on the Tillydrone road network. They are connected by links to form the network topology.
Vehicles: Mobile agents that move between nodes. Each vehicle has a current location, a destination, a base speed, a current speed, a journey distance to its destination, and a current speed restriction based on the road it's traveling on in Tillydrone's road network.
## Initialization:

Nodes:The nodes form a linked network  based on Tillydrone's road network topology. The network.
Vehicles: A specified number of vehicles are created and assigned to random nodes. Each vehicle is given a random destination node and a base speed. Additionally, the vehicle's initial speed restriction is set based on the road it starts on in Tillydrone's road network.
## Behavior:

Vehicle Movement:

Speed Adjustment:

Each vehicle checks for other vehicles ahead on its current path.
If another vehicle is detected within a certain distance, the current vehicle reduces its speed to avoid a collision.
The amount of speed reduction depends on the distance to the vehicle ahead.
The vehicle's speed is also constrained by the current speed restriction of the road it's on in Tillydrone's road network.

Overview
--------

This is a NetLogo model that simulates the movement of vehicles on Tillydrone's road network. The model includes two types of agents: nodes and vehicles. Nodes represent intersections in the road network, and vehicles move along the links between nodes. The model includes features such as speed limits based on Tillydrone's road network, random maximum speeds for vehicles, and collision avoidance.

Design Concepts
---------------

* **Spatial Extent:** The model is defined on a two-dimensional grid, with nodes and links representing intersections and roads in Tillydrone's road network, respectively.
* **Temporal Extent:** The model operates in discrete time steps, or ticks. At each tick, vehicles move along the links between nodes and update their speed based on local conditions in Tillydrone's road network.
* **Stochasticity:** The model includes randomness in the form of random maximum speeds for vehicles and the selection of destinations.
* **Collectives:** The model simulates the collective behavior of vehicles moving on Tillydrone's road network.
* **Observation:** The model includes a visualization of the road network and the movement of vehicles in Tillydrone's road network.

Details
-------

### Entities, States, and Variables

* **Nodes:** Nodes represent intersections in Tillydrone's road network. They have a position on the grid. They also have a list of links connected to them.
* **Links:** Links represent roads between intersections in Tillydrone's road network. They have a distance to the destination, a speed limit based on Tillydrone's road network, a color, and a thickness.
* **Vehicles:** Vehicles represent individual agents moving on Tillydrone's road network. They have a position on the grid, a color, a shape, and a size. They also have a maximum speed, a current speed, a local speed restriction based on Tillydrone's road network, a journey distance, a remaining journey distance, a path to the ultimate destination, and a flag indicating whether they are moving.

### Process Overview and Scheduling

The model operates in two main procedures: `setup` and `go`. `Setup` initializes the nodes and vehicles based on Tillydrone's road network, and `go` advances the simulation by one tick.

### Initialization

At the beginning of the simulation, the `setup` procedure initializes the nodes and vehicles based on Tillydrone's road network. The `nodes-init` procedure generates a random network of nodes and links using the network extension based on Tillydrone
