# Introduction
Machine learning is becoming ubiquitous
Grew out of AI; couldn't program complex tasks, so program the machine to learn how to program itself

Current uses:
* data mining (clickstream, medical records, etc.)
* highly-complex/difficult programs (NLP, handwriting, vision, etc.)
* self-customizing programs (recommendations, etc.)
* research on human learning

# What is machine learning?
Samuel (1959): field of study that gives computers the ability to learn without being explicitly programmed
- checkers
Mitchell (1998) - formal def'n of Well-posed learning problem: computer learns from experience E for some task T and some performance measure P if performance on T improves according to P after experience E

ML algos:
* supervised learning (main 1)
* unsupervised learning (main 2)
* reinforcement learning
* recommender systems

# Supervised learning
Ex: housing price prediction
Give a dataset that includes the right answers, extrapolate to a new point within the range -- a regression problem (predict continuous valued output)

Ex: breast cancer - tumor size / malignancy
predict prob of malignancy based on new tumor size -- classification problem (predict discrete valued output)
can classify on more than one factor (e.g., size + age), up to infinite number of features

To store infinite features in finite space: use an algorithm
