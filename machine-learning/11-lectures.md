# ML system design
How do you decide what to work on?
Example: spam classifier
Deciding on features
* try some set of spammy / non-spammy words and build feature vectors based on their presence/absence
  * in practice, you generally don't want to pick words a priori - pick the most frequent words from the training set

How to spend your time?
* collect lots of data (honeypots)
* pick more sophisticated features (e.g., email headers for routing)
* pick sophisticated features for the message body (word stemming, capitalization, punctuation)
* finding misspellings
* etc

# Error analysis
Process:
* start with a simple, fast-to-build algo and test it for Jcv
* plot learning curves
* manually examine the errors in CV that were classified inappropriately; look for systematic trends
* brainstorm features specifically for the systematic errors and evaluate them based on the misclassified examples for frequency

Use Jcv for these evaluations

