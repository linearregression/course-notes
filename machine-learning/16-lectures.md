# Recommender systems
One example of automatically-learned features

Ongoing example: movie ratings

* `nu` = number of users
* `nm` = number of movies
* `r(i, j)` = 1 if movie i has been rated by user j
* `y(i, j)` = rating given to movie i by user j

# Content-based recommendations
* `x1` = romance
* `x2` = action

Represent movies as feature vectors based on content; treat ratings as linear regression problem

* for each user, learn parameter THETA; predict user j as rating movie i with `(THETAj^T) * x^i` stars

