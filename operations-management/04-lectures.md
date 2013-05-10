# Intro to productivity
Teddy Roosevelt FTW

Productivity = units of output / input used
Multifactor productivity = output / (capital $ + labor $ + materials $ + service $ + energy $)
Waste and inefficiencies reduce productivity (beyond natural limits == e.g., no more than 60 minutes of work in an hour for a worker)
* distance from the efficient frontier

Tradeoff between responsiveness and productivity

# The seven sources of waste
Lean operations and waste
Sources of waste:

Resource-focused
1. Overproduction (wasted food after buying in bulk) => improve supply-demand match
2. Transportation (moving product around) => relocate processes, standardize transport
3. Rework (readmissions to ICU) => analyze and solve causes of rework
4. Over-processing (staying in the hospital after you're better) => provide clear, customer-driven standards for processes
5. Motion (ergonomics) => arrange people and parts to minimize unneeded motion

Flow-unit-focused
6. Inventory (loan applications backlog) => improve production control system and reduce unnecessary buffer
7. Waiting (ER waiting rooms) => understand the drivers of waiting

Minimizing waste can dramatically affect a business (Totota methods vs. GM methods in 1986)

"Moving is not necessarily working"

*8.* Intellectual waste - not taking full advantage of workers' minds

# Financial value of productivity
Finance / operations disconnect
Always be thinking of the end result (e.g., profit) and the impact of operational changes on it -- don't just optimize productivity for the sake of optimizing it

# KPI
Key performance indicators are meant to draw attention to places where op changes can have the most effect on the bottom line

KPI tree:
Profit = Revenue - Cost
Revenue = Flow rate * $/flow unit
Flow rate = min(demand, capacity)
Capacity = min cap(all resources)
...
Cost = Fixed + variable costs
Variable costs = Flow rate * cost/flow unit
...

Sensitivity analysis - evaluating changes in these components and their effect on profits
= partial derivative of profits wrt an operational variable
(or just use Excel)

Graph revenue and costs per flow rate to see the break-even point

[ holy crap. mind == blown. ]

# Overall equipment effectiveness
OEE framework = all the time available on a resource, identifies all waste, leaves you with the time that the resource is actually adding value
Ex: a machine (100 hrs) - breakdown, changeover (downtime losses) = available time - idling, reduced speed (speed losses) = net operating time - defects, startup (quality losses) = OEE
Ex: airplane (365 days * 24 hours) - at gate, maintenance = block time - taxi/landing = in the air - unbooked = value add (~30%)
Ex: doctor (total paid time) - vacation, sick = in practice - unbooked = time booked for appointments - cancellations = time with patients - visits that don't need an actual doctor, activities that non-doctors could do = value add time

Exercise:
3d printing
12 hours (720 minutes) available/day
70 minutes to model a design *actual value-add work*
30 minutes to set up the computer for a print
30 minutes as a standup (planning)
1/3 models are scrapped on completion
1 day a week maintenance

720 min/day - 30 min (standup) = 690 min / 100 min/model = 6 models (can't start a job unless it'll finish before the end of the day) - 33% (scrap) = 4 models
4 models * 70 min/day = 280 min/day * 6 days = 1680 min / 5040 min = 33% OEE

calculate available time and value-add time first, then fill in the pretty graph
having actual data (esp on knowledge workers) on behavior is very difficult
[ probably wouldn't work on devs at all ]

# Takt time
Every non-bottleneck resource has to have idle time
If you're demand-constrained, even the bottleneck will have idle time

Line-balancing = share work across the resources

Takt time = seconds in time / flow rate => sec/unit
Target manpower = processing time / Takt time 

Assign tasks to resourecs so that total processing times < Takt time
Assign all tasks, minimize work force (maximize labor utilization)

Static vs. dynamic line balancing

Staffing to demand
* level the demand (hold it constant for ... an hour, etc.)
* calculate the Takt time
* plan resources accordingly

# Quartile analysis
Individual variation across resources
Call center example

Process:
* sample processing times per task across individuals
* compare top and bottom quartiles; sometimes up to *300% differences*
* transfer best practices from top performers to bottom performers

# Productivity ratios
Problems with measuring productivity:
* it's hard to measure output => fall back on revenue
* multiple input factors => limit analysis to one category (e.g., labor)

Revenue/cost = revenue/output (operational yield) * output/capacity (transformation efficiency) * capacity / cost (1/unit cost of capacity)
Ex: Airline
Revenue/cost = revenue / revenue-per-mile * revenue-per-mile / airline-seat-mile * airline-seat-mile / employees * employees / labor costs

Analyzing each component allows you to see what contributes to differing productivity across companies
Aggregate data can be misleading

General process:
* Start top-down with the financial statements and productivity ratios
* Supplement with data from the front lines

