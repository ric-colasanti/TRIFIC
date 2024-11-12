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
    
Movement:
The vehicle moves forward at its adjusted speed, which is the minimum of its desired speed and the current speed restriction.
    
Destination Reached:
Once a vehicle reaches its destination, it selects a new random destination from its current node's neighbors.
The vehicle then moves towards the new destination, updating its speed restriction based on the new road, repeating the process.

## Model Parameters:

Number of Nodes: Controls the size of the network.
Number of Vehicles: Determines the number of vehicles in the simulation.
Base Vehicle Speed: Sets the maximum speed of vehicles.
Traffic Sensitivity: Controls how strongly vehicles react to traffic conditions.
Road Speed Limits: Determines the maximum speed limit for each road in the network.

Visualizations:

Network Visualization: Visualize the network topology with nodes and links.The color and the thickness of the road indicates the road speed. 
Vehicle Trajectories: Track the movement of vehicles over time.
Traffic Density: Visualize the density of vehicles on different parts of the network.
Speed Variations: Show how vehicle speeds change in response to traffic conditions.

## Extensions used

Network extention nw
