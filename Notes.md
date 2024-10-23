#Supervised Learning
## Classifcation
map some input to a discrete value (a category such as T or F, Boy/girl)

**Important Terminology**

* Instances = Inputs
* Concept = Function
* Target Concept = Answer
* Hypothesis Class = All Functions
* Sample = Training Set
* Canidate = Is the cencept = Target concept
* Testing set (self explanitory)


**Decision Trees**

- Classification Problem





## Regression
Map some input to some real number (continous quantity)

## Neural Networks
Artifical NN works like a real nueron with activation levels and firing thresholds

perceptron = nueron

backpropagation -> calculating the loss by travelling backwards through the network

Optimizing weights:

* gradient descent
* momnetum terms
* higher order derivitives
* random optimization
* penalty for "complexity"

Restriction Bias:
what we are able to represent

* boolean - betwork of threshold like units
* continous - connected no jumps - 1 hidden layer
* arbitrary - stitch together - two hidden layers

Preference Bias: Selection of one representation over another

* what algorithim
* initial weights - small random values

## Instance Based Learning
KNN
more dimensions/features means an exponetially larger amount of data needed

## Ensemble Learning: Boosting
building up a bunch of simple rules for a pattern and combine them into a single more complex rule

This is done over iterating through subsets of data to find rules 

## Suport Vector Machines
Still dont know what these are
finds a linear seperator of data whike maximizing the margins between it 

## Computational Learning Theory
**Important Definitions**

* Computational Complexity 
	*	How much computational effort is needed for a leanrer to converge?
* Sample Complexity (batch)
	*	How many teaching examples are needed for a earner to create a successful hypothesis
* Mistake Bounds
	* How manny musclassifcations can a learner make over an infinite run
* Training error
	* Fraction of training examples miscalssifed by h
* True error
	* Fraction of examples that wold be miscalssified on samoel drawn from the distribution over inputs
* Version Space
	* All of the hypotheses that are consistent with the data seen

**3 ypes of learning:**

* Teacher ask the larner for C(x)
* Teacher gives X, asks for C(x)
* X is determinered by nature and C(x) is then told by the learner

**Learner with Mistake Bands:**

* Assume its possible each variable is positive and negated
* Given input, compute output
* If wrong, set all positive variables that were 0 to absent, and all negavtive varivales that were 1 to absent. Repeat

**PAC Learning**

Probably approximatley correct
Shoots for a success rate that has low error and a certainity that is acceptable given the error and time taken to compute (perfection is not possible but allows for a more realistic goal )

**ε - exhausted Version Space**

Reminder ε = error goal

A version space of some sample data is ε-exhuasted if and only if every hypothesis in the version space has low error

Charles explanation - If eveything you may choose has a error less than ε

## VC Spaces
**Infinite Hypothesis Spaces**

Some hypthesis spaces are not infinite like a discrete decision tree and are reffered to as agnostic.

VC dimension - largest set of inputs tha the hypothesis class can shatter (label in all possible ways) often is the # of parameters 
for d-dimensional hyperplane the VC dimension  is d+1

H PAC Learnable if and only if VC dimension is finite
## Bayesian Leanring
`argmax Pr(h|D)`
apply bayes rule to get
`(Pr(D|h)Pr(h))/Pr(D)`
Pr(h) - prior h
Pr(D) - prior on the data
argmax- arguments of the maxima

## Bayesian Inference
**Joint Distribution**

probability distribution of all possible pairs of outputs

**Conditional Independence**

P(X|Y,Z) = P(X|Z)

**Belief Networks aka Bayesian Networks**
Not necessarily cause and effect but there are statistical depencies among nodes

**Why Sampling**

* two things disbtributions are good for: 
	* proability of value 
	* generate valies
* Simulation of a complex prociess
* apporximate inferences - In a machine sense
* visualization - in a human sense(get a feel of the data)

**Why Naive Bayes**

* Pros

	* Inference is cheap
	* Few parameter
	* Estimate parameters with labeled data
	* Connecrs inference and clasifcation
	* empirically successful
* Con
	* It doesnt model interrelationship between attributes (hence the naive)

# Unsupervised Learning
##Random Optimization
input spaxe X
objective function (fitness function) f: X->R
Goal: find x<-X such that f(x)=maxf(x)

ramdomized optimization
**hill climbing** 
traverse hills to find local optima
**random restart hill climbing**
Multiple restarts of the hill climbing process at different starting points to ensure a global maxima is found

**simulated annealing**
Don't always improve so sometimes you need to explore

When T->: like hill climbing
WHen T->inf: random walk

**Genetic Algorithims**
introduces crossover of populations
replaces least fit individuals via crossover and keeps most fit individuals

Crossovers indicates a mix of the two points to create a new unique individual

how does this not effect the integrity of data?

## Clustering
**single linkage clustering**

define intercluster distance as the distance between 2 points in two clusters
merge two closet cluster
repeat to make n clusters

**k-means clustering**
pick k centers at random
each center claims its closests points
recomputer centers by avg the clustered points
repeat

**clustering properties**
no clustering can acheive all 3

* Richness: for any assignment of objects to clusters there is some distacne matrix D such that the clustering scheme returns that clustering
* scale-invariance: Sclaing distances by a positive value does not change the clustering (changing units/scales doesnt change clustering)
* consistency: Shrinking intracluster distances and expandigng intercluster distances does not change the clustering

## Feature Selection
**filtering** 
features are deef into a search and then fewer features are filtered to input to the learner
faster approach but ignores the larning problem 
**wrapping**
features are fed into the search and learner which are wrapping around each other
Here criteria is built in conjuction with the learner while the filtering apporach has no conjucntion with the learner.
Slow and takes into account model bias
