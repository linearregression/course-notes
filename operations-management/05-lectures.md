# Reasons for variety
Fit-based variety - each customer has a unique point of maximal utility, distance from that point decreases utility (horizontal differentiation) (t-shirts)
Performance-based variety - each customer prefers high performance, but differ in how they value quality vs. price (computers)
Taste-based variety - customers differ in taste and over time (food, music, art)

Variety because:
* heterogeneous preferences
* price discrimination
* variety-seeking
* avoiding price competition
* channel shelf space
* niche saturation

# Capacity calculations
Setup / switchover costs lower capacity
Ex: custom shirts sold online; infinitely many sizes, many styles and colors, four weeks lead time, minimum order of 5 shirts
Production process: cutting (constant setup time); sewing (sewing + assembly); finishing

Capacity given a batch size = batch size / (setup time + batch size * time per unit (processing time))
Compare to individual capacity: number of workers / processing time

Large batches are a form of economy of scale - minimize impact of setup time; cap as function of batch size asymptotically approaches individual cap

Large batches lead to higher inventory

Batch = collection of flow units produced between two setups

# Mixed model production
Large batches lead to mismatch between supply and demand (e.g., excess inventory)
Need to balance inventory with capacity
Long production runs lead to higher average inventory; frequent changeover lowers the average inventory

mixed model production == heijunka (in Toyota model)

in MMP, batch = all units produced before repeating the pattern of production (e.g., flow units processed between *three* (or types+1) setups)
Calculation: desired cap = batch/(setup time + batch * processing time), solve for batch size, then split total batch size by proportion of types in demand

Adding another product will increase the optimal production run length
More setups == more capacity spent on setup

# Choosing a batch size
Choosing batch size can move the bottleneck
* too-small batches put the bottleneck on the setup step
* too-large batches overwhelm other steps
* optimal: choose batch size to equal the next bottleneck

# Demand fragmentation and pooling
Over-segmenting demand makes prediction *much* harder; aggregation reduces uncertainty
Statistics!
coefficient of variation = STDEV / MEAN
combining demands = lower demand variability == demand pooling

made to stock (vs. made to order) pools demand

# Flexibility
Shortening setup times increases flexibility

SMED (single minute exchange of dies)
1. measure total changeover time
2. determine internal and external activities (external can be done outside of the changeover process, while the step is active)
3. move external activities to before or after the shutdown
4. improve the internal activities
5. improve the external activities
6. standardize procedures

Flexibility can increase setups required and capital required; partial flexibility may be a solution (almost all the benefits of full flexibility with much lower cost)
Software developers - massively polyglot programmers (expensive and rare) vs. mildly polyglot programmers 

# Platforms and modularity
Increase variety through the process for high efficiency = economy of scale (keep things standard as long as possible) = delayed differentiation

Modularity allows differentiation delay - isolate the variable elements (iPhone + case, case is colorful)

# Limits to customer choice
Too much choice can overwhelm customers

