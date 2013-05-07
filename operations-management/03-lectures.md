# Module 1: Performance analysis
Three basic measures for any operation
1. Flow rate / throughput
2. Inventory
3. Flow time
4. Flow unit (customer, sandwich, etc.)

Cumulative inflow of customers (based on time of arrival)
Cumulative outflow (based on time of departure)
Inventory = inflow - outflow (number of units in process at a given time)
Flow time = time from inflow to outflow (time spent in process)
Flow rate = # of flow units in the process per unit of time

[ software dev: big question is flow unit. feature? LOC (no)? project? ]

# Drivers of these measures
Multiple steps in the process
Processing/activity time = time/flow unit for a given step/station
Process flow diagram
* triangle == flow units waiting (delay)
* box == step

Process mgmt = managing the doing of things repeatedly
Project mgmt = managing a single event

Capacity = 1/processing time (flow units made by a worker in a single unit of time); parallel (mult workers) => num workers / processing time
Process capacity / bottleneck = lowest-capacity process step
Flow rate = min(demand rate, process capacity)
Utilitzation = flow rate / capacity

# Productivity
Measuring labor productivity

Cycle time = 1/flow rate (how much time passes between completion of units)
Direct labor content = sum of processing times across process
Direct idle time = sum(cycle time - processing time for each step)
Average labor utilization = labor content / (labor content + idle time)
Cost of direct labor = wages per unit of time / flow rate (money per flow unit)

no delays between processing steps == machine-based process

labor cost importance:
* compare to value-added
* roll up costs across the value chain (including supplier costs, etc.)

# Little's law
average inventory = average flow rate * average flow time

Consequences:
* you can choose two of I, FR, and FT (fix FR, reduced inventory == reduced flow time)
* given two of the measures, you can calculate the third (e.g., flow time is often hard to discern)

# Inventory turns
Amount of time a unit spends in the process
Inventory turns = cost of goods sold / inventory = 1 / flow time

COGS, not revenue (margins don't matter here)
Inventory cost calculation = annual inventory costs / inventory turns per year = per-unit inventory costs

# Drivers of inventory
buffer or suffer: in a system with no buffering (inventory), flow rate suffers (McDonald's vs. Subway)

made-to-stock pros: 
* scale economies in production
* rapid fulfillment

made-to-order pros:
* fresh preperation
* allows for customization
* produce exactly to demand

5 reasons for inventory
1. pipeline (minimum to deal with >0 flow time)
2. seasonal (driven by seasonal demand and constant cap)
3. cycle (economies of scale in production)
4. safety (buffer against demand)
5. decoupling inventory/buffers (buffers between internal steps)

Inventory shields from variability in demand or processing time

# More complex operations
Multiple flow types == different processing times for each path

To determine bottleneck: look at each resource/step individually for cap, and look at flow rate for each path for demand
Implied utilization = demand / capacity (can be > 100%)
highest implied utilization == bottleneck

alternative
* look at available work for each step (e.g., 60 min/hour/worker)
* compare to processing time * demand for each step
* divide total time per step / available work per step

Processes with attrition - similar process

Interesting: tweak the mix to optimize metrics

# Review


