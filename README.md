## Exploring  Wikipedia's hyperlinks network
In this assignment we analyze the Wikipedia's articles network by applying graph algorithms.




Data and setting

There are many options to collect and build the Wikipedia's underlying network, we rely on the dataset provided here, https://snap.stanford.edu/data/wiki-topcats.html. For the purpose of our exploration, we do not consider the entire dataset. Instead, we focus on the articles belonging to a subset of categories.

We Download the reduced version of the graph Wikicat hyperlink graph. Every row indicates an edge. In particular, the two elements are the source and the target, respectively.

From this page we download:

1) wiki-topcats-categories.txt.gz: list of pages per category
2) wiki-topcats-page-names.txt.gz: page names


General notes
We will notice that one article might belong to a single category or multiple ones. In the case of multiple appearance, we break the ties uniformly at random. 

We assume that all edges in the graphs we will consider have weight equal to 1. 

Basically, we have to answer to these research questions: 


RQ1

We Build the graph G=(V, E), where V is the set of articles and E the hyperlinks among them. Then, we have to answer to this basic information:

Is the graph directed?

How many articles are we considering?

How many hyperlinks between pages exist?

Compute the average number of links in an arbitrary page. What is the graph density? Do we believe that the graph is dense or sparse? Is the graph dense?

Visualize the nodes' degree distribution
RQ2
Define a function that takes in input:

A page v
A number of clicks d
and returns the set of all pages that a user can reach within d clicks.

RQ3
Define a function that takes in input:

A category C

A set of pages in C, p = {p1, ..., pn}
and returns the minimum number of clicks required to reach all pages in p, starting from the page v, corresponding to the most central article, according to the in-degree centrality, in C.

Considering that:

The algorithm needs to handle the case that the graph is not connected, thus not all the pages in p are reachable from v. In such scenario, it is enough to let the program give in output the string "Not possible".

Since we are dealing with graph exploration, we can pass more than once on the same page pi.

Since the problem’s complexity is high, we provide just an approximation/heuristic solution for the problem.

RQ4

Given in input two categories: C1 and C2, we get the subgraph induced by all the articles in the two categories.

Let v and u two arbitrary pages in the subgraph. What is the minimum set of hyperlinks one can remove to disconnect u and v?

RQ5

Write a function that, given an arbitrary category C0 as input, returns the list of remaning categories sorted by their distance from C0. In particular, the distance between two categories is defined as

distance(C0, Ci) = median(ShortestPath(C0, Ci))

where ShortestPath(C0, Ci) is the set of shortest paths from each pair of nodes in the two categories.

RQ6

Write a function that sorts the categories in the graph according to their PageRank (PR). For this task you need to model the network of categories such that you can apply the PR algorithm.
