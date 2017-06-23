---

title: Method for finding optimal paths using a stochastic network model
abstract: A method finds an optimal path from a source to a destination. The possible paths from the source to the destination are represented as a stochastic graph of nodes connected by edges. Each edge has an independent probability distribution over a cost of the edge. A constraint for reaching the destination is defined. The graph is reduced to a relatively small set of deterministic minimum cost problems, which can be solved to determine an optimal path that maximizes a probability of reaching the destination within the constraint.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07573866&OS=07573866&RS=07573866
owner: Mitsubishi Electric Research Laboratories, Inc.
number: 07573866
owner_city: Cambridge
owner_country: US
publication_date: 20060830
---
The work leading to the present invention was supported in part by an NSF Graduate Fellowship NSF grant CCR 0324914 NSF grants ANI 0225660 and ITR 0219018. The government has certain rights in the invention.

The invention relates generally to finding minimum cost paths and more particularly to finding optimal paths modeled with a stochastic network.

Finding minimum cost or shortest paths generally optimal paths or most likely to succeed paths is important in many practical transportation and communication applications. The problem is to find a route from a source to a destination under certain constraints. For example a best geographical route to the airport before a departure time a best route on the drive home before running out of fuel or a best route in a network to send packets with minimum delay.

The invention is concerned with paths that can be modeled as a stochastic network graph . A stochastic network includes nodes connected by edges. The edges represent the individual paths that can form a potential optimal route and the nodes are intermediate points where alternative paths can be selected for a particular route. In a stochastic network a cost of traversing an edge path is drawn randomly according to a probability distribution associated with the edge. Typically the cost distribution represents a length of the edge or the travel time to traverse the edge. This is how the real world works.

Because it is difficult to define the meaning of stochastic shortest paths it is also difficult to formalize the problem. When the edges that model the paths are modeled by probability distributions the shortest paths could determine an average minimize a combination of mean and variance or minimizing some other specified criterion. In addition the shortest paths can be found adaptively or non adaptively. Adaptive methods are most common perhaps because a non adaptive minimization of the expected path length trivially reduces to a deterministic shortest path problem.

Most prior art methods minimize an expected length of paths from the source to the destination or a combination of expected lengths and expected costs such as bicriterion problems J. Mote I. Murthy and D. Olson A parametric approach to solving bicriterion shortest path problems European Journal of Operational Research 53 81 92 1991 and S. Pallottino and M. G. Scutella Shortest path processes in transportation models Classical and innovative aspects Technical Report TR 97 06 Universita di Pisa Dipartimento di Informatica 1997.

Some methods optimize a non linear function of the path length. Other methods define a decision theoretic framework R. P. Loui Optimal paths in graphs with stochastic or multi dimensional weights Communications of the ACM 26 670 676 1983. There the optimal path maximizes an expected utility for a class of monotonically increasing utility functions.

An adaptive method for finding shortest paths that maximizes the probability of arriving before the deadline is described by Y. Fan R. Kalaba and I. J. E. Moore Arriving on time Journal of Optimization Theory and Applications Vol. 127 No. 3 pp. 485 496 December 2005. Formulations of this type with a nonlinear objective function though perhaps most useful in practice are few because the hardness of the problem arises and accumulates from many levels e.g. combinatorial distributional analytic functional to list a few. For example in the absence of randomness the combinatorial nature of the problem may be hard to approximate. In the absence of a graph structure the objective function may be difficult to optimize.

Most prior art methods that operates on stochastic shortest paths use adaptive processes. There the selection of the best next path is based on information about realized edge lengths so far. Most of the adaptive methods focus on minimizing expected length few consider minimizing a non linear function of the length and only give approximate heuristic processes.

The most relative method is that of Loui. Loui considers a general utility function of the path length which is monotone and non decreasing and proves that the expected utility becomes separable into the edge lengths only when the utility function is linear or exponential. In that case the path that maximizes the expected utility can be found via traditional shortest path process. For general utility functions Loui describes a process based on a certain enumeration of paths.

Mirchandani and Soroush give exponential processes and heuristics for quadratic utility functions P. Mirchandani and H. Soroush Optimal paths in probabilistic networks a case with temporary preferences Computers and Operations Research 12 4 365 381 1985. For non monotone utility functions that use penalties Nikolova et al. give hardness results and pseudo polynomial processes E. Nikolova M. Brand and D. R. Karger Optimal route planning under uncertainty Proceedings of International Conference on Automated Planning and Scheduling 2006.

The embodiments of the invention provide a method for finding minimum cost shortest paths from a source to a destination under some predetermined constraint e.g. a deadline. The paths are modeled as a stochastic network graph of nodes and edges. The invention considers the problem of finding the optimal paths in the graph with independent and randomly distributed edge lengths costs .

The goal is to maximize a probability that the path lengths do not exceed a given threshold value constraint such as the deadline time. The invention provides a surprising exact process for the case of normally distributed edge lengths which is based on a quasi convex maximization.

We provide a method for finding an optimal path from the source to the destination subject to some constraint. As used herein optimal can have various meanings depending on the particular application. Optimal can mean least cost least time a maximized probability of reaching the destination within the constraint or a most likely to succeed path etc.

Each edge E has an associated independent random variable cost expressed as a probability distribution e.g. length or travel time X. The exact meaning of the cost depends on a particular application. The probability of the cost can be distributed normally additively exponentially or distributed according to a Bernoulli function. The normal probability distribution of the cost can be expressed in terms of its mean and its variance .

We have a constraint t. The constraint can be expressed as a time interval t from a start time t to a deadline time t i.e. t t t. It should be understood that constraints other than time can be used for other applications. For example the constraint can be an actual total budget for achieving some goal.

We would like to find the optimal paths from S to T that maximizes the probability that we reach the destination within the constraint e.g. time interval t.

We find the optimal path by constructing and solving an equivalent parametric shortest path problem on the same graph. The graph G distinguishes the source S and destination T . Each path is given a cost parameter dependent weight u w where uand ware nonnegative weights and the parameter varies in a range 0 . The parametric shortest paths problem finds parameter values breakpoints at which the shortest path changes.

We refer to the number of breakpoints as the parametric shortest path complexity and note that the complexity is equal to the number of paths which are shortest for the non empty open interval 0 counting paths of identical parametric weight as one. We call these the optimal paths.

We establish a connection between the stochastic shortest paths with normal distributions and the parametric shortest paths problem. This enables us to apply our average and smoothed results for the former to the parametric shortest path setting as well.

By relatively small we mean that the number of problems is constant or at most linear with respect to the number of edges. The prior art solutions at best are exponential or worse. Typically the prior art methods use approximate heuristics with no known bounds on error and processing times. Whereas our method provides provable bounds and computable process times. The relatively small number of deterministic problems are solved to determine an optimal path that maximizes a probability of reaching the destination within the constraint. The evaluation of a relative small number of candidate paths can be done using deterministic minimum cost processes.

We define convex functions and their generalization to quasi convex functions and state the main property of their global maxima. Let C be a convex set.

Definition 2.1 A function C is convex if for all x y in the set C and 0 1 x 1 y x 1 y . The functions is quasi convex if all its lower level sets are convex.

Definition 2.2 We say that x is an extreme point of the set C if x cannot be represented as a convex combination of two other points in the set C 

Theorem 2.3 Let C be a compact convex set. A quasi convex function C that attains a maximum over the set C attains the maximum at some extreme point of C.

We provide a few more definitions. The shadow of the convex set in onto the two dimensional plane is the orthogonal projection of the convex set onto the plane. The dominant of the set C in is defined as the set of all points that are greater than a point in C x X y for some y in the set C.

Therefore as shown in we first project the graph which is geometrically a hypercube of nodes and has a hypercube hull onto a mean variance plane including path vertices and a path hull which is a polygon. The path vertices in the projection correspond to the costs of path e.g. length or time.

The projection is performed as follows. For any path through the graph construct a vector of 0 s and 1 s indicating which edges are used by the path. This vector points at a corner of a hypercube in R where E is the number of edges. The convex hull of all corners corresponding to valid paths is called the path polytope. Each vertex of the polytope corresponds to a valid path.

We also construct a vector of all mean parameters and associated with each edge and another vector of all variance parameters associated with each edge. These two vectors span a plane in R. We project the polytope onto that plane to obtain a shadow the convex path hull . Vertices of the shadow path hull correspond to paths in the original graph that extremize a parametric cost function that is related to our original cost function above. The optimal path is identified by only inspecting a small subset of vertices on the lower left side of the polygon i.e. the vertices with small variances and small means. The edges in the polygon have no meaning.

We apply a quasi convex maximization to the graph with normally distributed edge lengths. We select the best route to reach the destination from the source by or before given deadline time t. The problem has natural applications to transportation networks with uncertain traffic conditions such as reaching the airport on time.

Assume each edge i has independent normally distributed length X N where is a mean and a variance. Our goal is to maximize

The objective in Equation 3 cannot be separated into edges costs and does not satisfy suboptimality. Therefore a dynamic programming approach based on substructure fails. To better understand the properties of the objective function we formulate the objective function as a continuous optimization problem over the path polytope in where m is the number of edges.

We index all edges by 1 2 . . . m and represent each edge subset by its incidence vector x with x 1 if edge i is in the subset and x 0 otherwise. All 2subsets of edges correspond to the vertices of a unit hypercube in . The ST path polytope or the path polytope for short is the convex hull of incidence vectors of simple ST paths. The polytope is a subset of the unit hypercube in and the vertices of the polytope are a subset of the vertices of the hypercube. Thus the optimal ST path is a solution to maximize

Projecting the path polytope onto the span of vectors . . . and . . . defines the convex path hull which we call the path polytope shadow.

The objective in Equation 4 is not separable far from linear or quadratic and not even convex. This places the objective in a category of programming and combinatorial optimization problems for which there are no general efficient solutions. Although the integer constraints usually cause the main difficulty in this case it is not clear how to solve this problem even in the fractional version.

It turns out that our objective has a special structure which forces its maximum to lie on the boundary of the feasible set. In particular the structure is quasi convex on a subset of the path polytope and monotone in .x and .x on the remaining subset of the polytope. This can be unfortunate because we do not have a polynomial description of the boundary of the path polytope or even its shadow.

For example computing the rightmost and uppermost vertices of the path polytope shadow corresponds to the finding the longest path in terms of the edge means and the edge variances respectively. Therefore the computation of the path convex hull is in general strongly NP hard. On the other hand we can efficiently find the extreme points on the dominant of the shadow hull because the extreme points optimize a linear objective 1 for 0 1 .

Our main Theorem 3.3 below shows that for sufficiently early departure time which eliminating the incidence of a longest path problem our objective is quasi convex. We first state a lemma about the correspondence of the stochastic and parametric shortest paths problems.

Lemma 3.1 There is a one to one correspondence between the extreme points on the shadow of the path polytope dominant on the plane spanned by vectors u u . . . u w w . . . w and the breakpoints of the parametric shortest path problem with edge weights u w.

By Lemma 3.1 the results for the complexity of the parametric shortest paths problem imply equivalent bounds for the number of extreme points on the shadow dominant.

Theorem 3.3. When the deadline t is no less than the mean of the smallest mean path the solution to Equation 4 is an extreme point of the dominant of the path polytope shadow.

We first consider the relaxed version of Equation 4 . Denoting x and x .x. This system becomes equivalent to

Now any extreme point of the shadow is the projection of an extreme point of the original path polytope m which has integer coordinates. Hence the optimal solution of the relaxed program of Equation 4 is also a solution to the integer program of Equation 5 . Each extreme point on the shadow dominant is the solution to a linear program min min c.x 6 

Equivalently each extreme point corresponds to a path minimizing cx cx where xis the total mean of the path and xis the total variance so for c c 0 it can be found via any shortest path process.

To find all extreme points on the shadow dominant we start with its two endpoints the leftmost point which corresponds to the path with smallest mean and the bottom most point which is the path of smallest variance.

Having found them we denote them m s m s where mis the mean and sthe variance of path . We then solve Equation 6 with c c s s m m if m 0 otherwise c c 1 0 . Suppose the new solution is m s . If different from both and we repeat the procedure for finding a vertex between paths and between etc. Clearly in this way we find all vertices on the shadow.

When the departure time is closer to the deadline so that any shortest path has a mean greater than t the optimal value of the program is be negative and the objective function is decreasing in the mean of the path and increasing in the variance. In this case the solution to the relaxed program is on the upper left boundary of the shadow between the left most extreme point of lowest mean and the uppermost extreme point of highest variance. Because finding the simple path with highest variance is strongly NP hard.

We do not expect to find a good polynomial time approximation. In addition the objective function in Equation 5 is no longer quasi convex on the feasible set intersected with x x t. Even if we could find the fractional solution it is not guaranteed to coincide with the integer solution to Equation 4 .

We described a pseudo polynomial process that may possibly include non simple paths which is polynomial in the number of nodes n and the maximum edge variance . This process constructs a dynamic programming table as follows.

For each possible value s 0 1 . . . of a path variance and for each node v determine the predecessor of node v on a path from the source S to node v of variance s and smallest mean. At the end we have paths from the source to the destination one for each possible variance s and smallest mean for that variance value.

Then we find the optimal ST path by computing the objective function value t path mean square root over pathvariance for each partially optimized path of variance s and select the path with smallest objective value.

If the edge weight vectors u w are uniformly random unit vectors or fixed vectors which are slightly perturbed then the expected number of extreme points on the path polytope shadow is linear and consequently our process described above has a small expected polynomial running time. The techniques described here are motivated by techniques for the polynomial simplex process for linear programming.

Note that the vertices of the path polytope P are a subset of the vertices of the unit hypercube in particular 

Fact 2. The polytope P is contained in the unit hypercube which in turn is contained in a ball with radius square root over m 2.

Theorem 4.1 Let u w 2 be uniformly random unit vectors and let V be their span. Then the expectation of the number of edges of the projection of P onto V is at most 2 square root over 2 m.

Proof By Fact 2 the perimeter of the shadow of P onto V is bounded by square root over m . Next for each edge I of the polytope P denote by S V the event that edge I appears in the shadow and let l I be the length of the edge in the shadow. The sum of expected edge lengths in the shadow is at most equal to the biggest possible perimeter 

Proof If an edge I of the polytope appears in the shadow the edge makes a small angle with the projection plane V 

Because any edge in the polytope P has length at least 1 by Fact 1 above the length of the edge in the shadow is at least cos V and the expectation the edge appears in the shadow as

We tighten our average case bounds to obtain a smoothed analysis. That is rather than projecting onto a uniformly random 2 plane we start with an arbitrary and possibly worst case a 2D plane and perturb the plane slightly. Then we show that the expected number of edges of the projection of P onto our 2D plane is polynomial in m and inversely polynomial in the size of the perturbation.

Our distribution on 2D planes involves exponential random variables. We recall that a variable x that is exponentially distributed with expectation has cumulative density function 1 and a probability density

Definition 4.3 For any 0 and any unit vector u we define a perturbation of u to be a random unit vector v selected as follows 

Theorem 4.4 Let U span u u be an arbitrary 2D plane. Let vand vbe perturbations of uand u respectively and let V span v v . The expected number of edges of the projection of P onto V is at most 4 square root over 2m for 

This lemma allows both vand vto be drawn from perturbed distributions as opposed to requiring one of them to be uniformly random.

Naturally the smaller the perturbation the weaker the bound in the theorem. Note that by Lemma 3.1 these bounds imply linear in the number of graph edges average and smoothed bounds for the number of optimal paths in the parametric shortest paths problem as well.

We extend our model to distributions other than the normal. For edge lengths coming from a Poisson or a gamma distribution with a fixed second parameter or more generally distributions which are additive and satisfy stochastic dominance we show that the problem reduces to the deterministic shortest path problem with edge weights equal to the parameter of the corresponding distribution. For the case of exponential and Bernoulli random variables whose sums are hard to compute exactly we have polynomial and quasi polynomial time approximation schemes respectively PTAS and QPTAS.

The sum of two independent Poisson random variables with rates means and is another Poisson random variable with a mean equal to the sum. In addition the Poisson distribution satisfies stochastic dominance. Namely its cumulative distribution function for a lower rate is entirely above the cumulative distribution function for a higher rate .

Specifically let D be any single parameter additive distribution namely the sum of two independent random variables with distributions D and D is another random variable with the same distribution and parameter equal to the sum D .

We also use D to denote the random variable with this distribution. Assume in addition that the distribution D satisfies stochastic dominance that is Pr D t Pr D t whenever .

Another realistic example of such a distribution is the gamma distribution gamma a b with a fixed shape parameter b. This defines a family of random variables with arbitrary means variances but with a fixed mean to variance ratio.

Suppose the random length of edge i is X D . Now despite the non separable objective function the additivity of the distribution together with stochastic dominance makes the problem separable 

Unlike the Poisson distribution the exponential and Bernoulli distribution are not additive. Therefore it is not possible to write a simple closed form expression for the objective probability function. We describe a polynomial time approximation scheme based on dynamic programming over a quantization of the probability distribution.

More precisely we give a bicriterion approximation which is given a lateness tolerance p and for 0 it finds a path satisfying

A similar quantization yields a quasi polynomial time approximation scheme for the case of Bernoulli distributions.

The invention provides a method for finding stochastic shortest paths with independent random edge lengths. The method can be used to find the shortest least cost path from a source to a destination under some cost constraint. The path can be a route to the airport on or before a deadline a path for routing a message through a network having quality of service or cost control guarantees a shipping relay for merchandise via boat truck and plane. The method can also be used to identify most reliable route circuit or relay for monitoring protection applications. The method can also be applied to a transaction processing pipeline where a latency guarantee is desired e.g. Internet based sales.

It should be noted that the method is unusual in that it is not based on dynamic programming. Although the problem is inherently discrete in its core are properties from a continuous optimization.

Remarkably changing the edge length distributions alters the problem nature significantly. Embodiments of the invention are provided for additive stochastically dominant distributions exponential distributions and Bernoulli distributions.

Although the specific embodiments of the invention have been described using a minimum cost path application it should be understood that the same basic techniques can be used for other applications. For example the graph can represent possible ways of achieving a goal destination from an initial condition source . In this case the probability distributions represent uncertain costs associated with each step of achieving the goal and the constraint is staying within a budgeted total cost.

Alternatively the source can be an initial state of some process or machine and the destination a final states. In this case the edges represent state transitions and their associated costs. The method now finds an optimal set of transitions to reach the final state.

Although the invention has been described by way of examples of preferred embodiments it is to be understood that various other adaptations and modifications may be made within the spirit and scope of the invention. Therefore it is the object of the appended claims to cover all such variations and modifications as come within the true spirit and scope of the invention.

