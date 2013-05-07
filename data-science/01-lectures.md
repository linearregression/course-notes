# Data science in action
* Nate Silver's predictions for Obama/Romney
* Obama's campaign
* Hurricane Sandy; visualizations and data-repurposing
* Analysis of emotional expression in books
* Relative import of scientific papers, web pages, etc.
* Scientific field taxonomy over time (bibliometrics)
* Food pairings
* Musical genre popularity over time
* Disease trends (Google trends; subject to media attention manipulation)
* Unknown drug side effects

# Context
What is data science? 
* intersection of hacking skills, math knowledge, and domain expertise
* skills needed: statistics, data munging, visualization

Three types of tasks:
1. preparing for analysis
2. running it
3. interpreting and communicating results

Data products:
* data-driven apps
* interactive visualizations
* online DBs

# Dimensions
Not data science:
* business intelligence - less flexible structure
* statistics - component of DS; often smaller datasets
* database management - not always relational (or structured!), not always limited to a single DB
* visualization - component of DS; again, often smaller datasets
* machine learning - closest to DS; choosing the algorithms is usually a small part of the process in DS, however (swamped by data cleaning, etc.)

tools <=> abstractions
structures <=> statistics
desktop <=> cloud
hackers <=> analysts

# Course overview
Why focus more on abstractions? Tools change over time
Fundamental abstractions for data science:
* matrices/linear algebra
* relations/relational algebra

Why focus more on the cloud? we have more data than can fit on a desktop

Why focus more on analysts than hackers? You don't need advanced skills to do this work, necessarily

Why focus more on structures than statistics? Data cleaning and analysis are more of the work

How much time do you spend "handling data" vs. "doing science"?
* most common answer: 90%

# eScience
Scientific change:
* Empirical
* Theoretical
* Computational
* eScience

eScience takes the world first, then you check the data to test hypotheses (vs. design experiments to test specific hypotheses)
The cost of data acquisition has dropped immensely; the cost to analyze that data is now the bottleneck

Three Vs
1. Volume: number of rows / objects / bytes
2. Variety: number of columns / dims / sources
3. Velocity: number of rows / bytes per unit time

also: Veracity: can we trust the data?

Business is beginning to look more like science - collect data, hire scientists, make empirical decisions

# Big data
Big data: any data that is expensive to manage and hard to extract value from

Sources:
* data exhaust from customers
* new and pervasive sensors (yay!)
* data hoarding
