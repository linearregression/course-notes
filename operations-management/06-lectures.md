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
time in queue = activity time * (utilization / (1 - utilization)) * ((CVa^2 + CVp^2)/2)
flow time = time in queue (Tq) + processing time

# Waiting time with multiple servers
Previous formula = 1 resource

time in queue = (activity time / m) * ((utiltization^(sqrt(2(m+1))-1)) / (1 - utilization)) * ((CVa^2 + CVp^2)/2)
utilization for multiple resources = p / (a * m) (where a is avg intake time)
inventory in queue  = 1/a * time in queue

Seasonality
* slice the data into regular intervals
* assume demand is constant within each interval

# Pooling
Pooling doesn't change overall utilization, but lowers queue time
Tradeoff: responsiveness vs. efficiency
Pooling shifts the efficient frontier

Cons:
* assumes flexibility
* increases complexity of work-flow
* increases variability of service time
* interrupts the customer relationship

# Sequencing
Triage - prioritize incoming units
first-come first-served = easy to implement; perceived fairness; lower variance of waiting time

Alternative: shortest processing time rule
* minimizes average waiting time
* hard to know true processing times (e.g., physician's office - it'll only take a minute)

Appointments problems
* no-shows
* solves the wrong problem (shifts waiting inventory out of waiting room to home, etc.)

# Process design
Deal with waiting by changing processes (e.g., Hertz pickup)

flow time efficiency = total value add time of a unit (flow time) / total time a unit is in the process

Two types of waste:
* auxiliary activities to get to value add (e.g., driving to doctor's office)
* wait time

Optimize by reducing wait time OR by reducing auxiliary activities

Process mapping
* customer actions
* onstage actions (direct interaction with customer)
* backstage actions (without customer effort)
* support processes

Options:
* move work offstage
* reduce customer action / rely on support processes
* eliminate steps (instead od optimizing capacity)
* avoid fragmentation of work by specialization
* prevent abandoment by moving waiting later in the process
* have the waiting occur outside a line
* set waiting expectations

# Loss models
Loss problems
* demand can be bigger than capacity

r = p / a
compare r to m in erlang loss table
== probability that unit will not be able to be served (all servers are utilized)
