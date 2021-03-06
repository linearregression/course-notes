# Reasons for defects
Quality: performance and conformance (meeting customer needs and meeting expected standards)

Probability of defects compound over # of steps
yield = % of good units produced; can be measured at a single step or for the whole process

Redundancy (Swiss cheese model) decreases defect rates, but can't eliminate it entirely -- ALL things have to go wrong to end with a faulty unit (compared to assembly line, where ANY step can go wrong and spoil the output)

# Quality and flow
Defect rates can change locations of bottlenecks (e.g., high defect rate means that you'll get less correct production out of a step); changes demand for later in the flow (50% rate at step 2 means you need 2D input to get D input for step 3)

Scrap vs. rework -- scrap means all prior steps suffer from defects; rework means only the current step is affected
* Calculate correct expected processing time
* or calculate implied utilization by dividing demand by capacity

Cost of defects:
* before bottleneck = driven by the input costs 
* after bottleneck = opportunity costs of missing the sale

resource starving vs. resource blocking - buffer or suffer!
Inventory protects from variability regardless of variability source (demand or quality)
Toyota system: reduce inventory to expose problems (so they can be fixed)

Kanban: work is authorized by demand, so inventory is controllable

# Six Sigma
What about non-binary quality issues?
LSL = lower specification limit
USL = upper specification limit

Capability score (Cp score) = (USL - LSL) / (6 * stdev)
Improve Cp score == higher quality
parts per million = defect rate * 1M units, standard expression for quality targets
with this, you can calculate the allowable stdev for any desired quality goal

# Control charts
common cause variation - variance between outputs of the same process/tool
* can be low or high
assignable cause variation - variance between outputs of different processes/tools

Minimize CCV 
Identify ACV as quickly as possible

1. track process parameter over time with control limits (not the same as the specification limits)
2. variation outside the limits (say, 3sigma above and beyond) may be ACV

Control limits aren't about defects -- they're just about identifying causes of variation

Statistical process control
* Capability analysis - what is the current inherent capability of the process?
* Conformance analysis - control charts to identify loss of control
* Investigate for assignable cause - root cause analysis
* Eliminate or replicate assignable cause - corrective action 

# Jidoka
Information turnaround time (ITAT) - feedback/learning - time after defects start til they're detected?
* buffer/inventory increases ITAT

Test flow units maximally before the bottleneck
Jidoka - detect-alert-stop, the machine alerts and shuts itself down
Andon Board / Cord - make defects stand out visibly, upon detection yank the cord (stops the line) and the problem shows up on the board

DAS => root-cause problem solving => avoid future problems => loop

# Problem solving
Root cause analysis

Ishikawa diagram / fish-bone diagram
* brainstorming potential causes
* looks like a fish skeleton
\ \ \   \
-------------- defect
/   / /   /

Five whys for root causing

Pareto chart
* graph # of defects by cause
* 80-20 logic (80% of defects from 20% of causes)

Iterative problem solving: interaction between models and reality
* idea => production => jidoka => ishikawa chart => pareto chart => alternatives => experiments => etc.

# Toyota production system
Ford production system
* optimization of work
* focus on utilitization
* low variety (huge batches)
* built around economies of scale

Toyota production system
* lack of scale meant failure
* systematic elimination of waste
* built around serving demand

Components:
1. Muda (zero-non-value-added activities)
2. Production flow synchronized with demand
  1. Mixed model production (heijunka)
  2. match demand based on Takt time
3. Quality methods to reduce defects
  1. Fool-proofing (poka-yoke)
  2. Detect-stop-alert (jidonka)
4. Flexibility
5. Standardization of work
6. Worker involvement

Enemies of operations
1. Waste - use of resources beyond what is needed to meet customer requirements
2. Variability - longer wait times and/or customer loss; buffer or suffer
3. Inflexibility - supply and demand mismatch problems