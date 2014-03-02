# Problem 3 

1. Which graph-related tasks does an ideal GitHub Network Graph need to address?

	*The Github Network Graph addresses many low level and topology-based tasks. On the low-level taks, it most importantly covers cluster and sort. These are most important of the low-level task because it seperates the commits out by branch and by contributor, and sorts via data so that one can visualize the progress, and time it took to create and modify a repository. In the topology-based task, adjacency and common connection are covered. Adjaceny is very visible as we subdivide by branch and contributor. By y-value, we can see that the adjacent nodes are by the same user and on the same branch. The common connection is also needed because the commits are all on the same repository and fork. Thus, each of the commits must have a psth to connect from one node to the other. 

2. Get back to the GitHub network visualization you implemented and test it with the following projects on GitHub: D3, jQuery and Bootstrap. There's a lot more data, but the interaction patterns of users are also very different. What do you notice about the three repositories?

	* The amount of data in the d3, jQuery, and Bootstrap repository far outnumber the repositories I used and tested in problem 2. As a result, much of the data is outside of the bounds of the svg, and the viewer does not see all the commits. Interestingly though, the distribution of user interaction is very different than in Problem 2. Mike Bostock seems to have made the vast majority of commits for d3, jQuery is similarly dominated by only 3 or 4 main contributors, and Bootstrap is a little more diverse when it comes to contributors. In the case of Bootstrap, it seems that small teams worked on seperate branches. 

3. How does this impact your graph?

	* The graph is hard to read in this scenario because there are so many commits and users. The links have paths that are hard to follow as the they overlap. We would need to make changes that fit most of the relevant information in the SVG

4. How would you improve your visualization to address issues with the larger and more complex data?

	* Depending on who the viewer of the visualization, we might need to summarize data to draw larger conclusions. For example, we might need to add a third dimension, that being time, and show a visual to animate how the progression of the repository. This visualization could use size to show the importance of key contributors, while not wasting visual energy on repetitive data (generalizing the fact that the main contributor had made the vast majority of commits, rather than enumerating these commits). 