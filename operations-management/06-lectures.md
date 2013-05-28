# Responsiveness: intro to waiting models
Implied utilization = flow rate (min of demand, capacity) / capacity
Even when implied utilization < 100%, you can get queue times (i.e., if there's statistical flux in incoming flow and/or process time)

# Waiting time formula
Variability of demand:
a = average inter-arrival time
CVa = stdev(inter-arrival time) / avg(inter-arrival time)
CVa (coefficient of variation of a)

Variability of processing time:
p = average processing time
CVp = stdev(processing time) / avg(processing time)
CVp depends on standardization

Waiting time:
time in queue = activity time * (utilization / (1 - utilization)) * 1/2 * (CVa^2 + CVp^2)
flow time = time in queue (Tq) + processing time

# Waiting time with multiple servers
Previous formula = 1 resource

time in queue = (activity time / m) * ((utiltization^(sqrt(2(m+1))-1)) / (1 - utilization)) * 1/2 * (CVa^2 + CVp^2)
utilization for multiple resources = p / (a * m) (where a is avg intake time)
inventory in queue  = 1/a * time in queue

Seasonality
* slice the data into regular intervals
* assume demand is constant within each interval

