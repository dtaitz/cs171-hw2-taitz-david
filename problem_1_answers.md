# Problem 1 

* For each of the 5 visualizations listed above plus the calendar map, answer the following questions:
	* Who is the audience (e.g. project manager, contributor, project user, visitor, etc.)
	* What data have been used? How can you get the data using the GitHub API? (Note that it can be the combination of multiple queries and their processing).
	* Those visualizations are updated over time. What happens if suddenly a contributor pushes many commits in a short time interval? How would you address this particular issue?

1. Contributors to a repository
	* Product Manager because a product manager needs to be able to know how much and when each of the team members are contributing. This would also be very helpful for the contributors so they know how much they are individually adding. 
	* The data consists of number of commits, dates, and users. Using the Github API, we can get that data through the generalized query: /repos/:owner/:repo/stats/contributors
	* In this case, many pushes in a short interval would distort the y-scale as there would be a peak in the graph around the date(s) of those commits. You could cap the y-scale at some arbitrary value, so that the viewer of the visualization understands that the activity was far higher than average and still the detail of the other activity.

2. Commits Activity
	* The audience is the project manger so that he can keep track of progress over time. 
	* The data consists of number of commits per week and dates of commits. Using the Github API, we can get that data through the generalized query: https://api.github.com/repos/:owner/:repo/stats/commit_activity. In this case, you would have to query per branch, as this might include more than master branch than last time.
	* In this case, many pushes in a short interval would have less of a distortion on the y-scale because the bar items are aggregated by week. It would distort the y-scale if the high number of activities in that day was greater than a whole week of activity. The bottom graph would be distorted however when you look at the individual week of those commits and not for the case of any other week. Similar to the first visualization, I would cap the y-scale value for the bottom graph. 

3. Code Frequency

	* The audience is the project user so that they whether the version of the project that they are using has been changed. 

	* The data consists of the weekly aggregate of the number of additions and deletions pushed to a repository. Using the Github API, we can get that data through the generalized query: https://api.github.com/repos/:owner/:repo/stats/code_frequency. In this case, you would also be given access to a - Number of additions, d - Number of deletions in the JSON file.

	* For this visualization, the result of high activity will be similar to the previous answer as the data is aggregated by week. The high number of commits would have to outnumber that of a high activity week to change the y-scale. Though if those commits were largely additions or subtractions, it could change the y-scale if the other weeks had largely the opposite. 

4. Punch card

	* The audience is the project manager to understand when his team is most productive during the day. This shows the total number of commits per hour and day.

	* The data consists of the day number, hour number, and number of commits: Using the Github API, we can get that data through the generalized query: https://api.github.com/repos/:owner/:repo/stats/punch_card. 

	* For this visualization, the result of high activity will be similar to the previous answer as the data is aggregated by week. The high number of commits would have to outnumber that of a high activity week to change the y-scale. Though if those commits were largely additions or subtractions, it could change the y-scale if the other weeks had largely the opposite. 

5. Pulse of a repository


	* The audience is the project manager to understand issues facing the team. Also could be helpful to the project user who ahve questions about the conversations surrounding this data. 
	* The data consists of the issues, pull requests, and comments: Using the Github API, we would need to access the data through multiple queries: https://api.github.com/repos/:owner/:repo/issues/:number/comments and https://api.github.com/repos/:owner/:repo/issues and https://api.github.com/repos/:owner/:repo/pulls/:number/merge
	* For this visualization, the result of high activity will likely not affect the visualization unless those activities had issues, or there were many pull requests (vs. commits).

6. Calendar

	* The audience is the project manager and the project users to understand if the repository is active. 
	* This visualization consists of how many commits (level of activity) of a user. This can be accessed on an individual's Github account. 
	* High activity would unlikely change the scheme of this visualization, as the colors are likely bucketed with ranges. If the color scale is relative, than setting a max for the range would also help maintain relative scaling for lower activity. 

* Looking at the network graph, answer the same questions as above, plus:
	* What is the role of interaction for this visualization? Would a static graph have been sufficient?
	* What happens if many new developers suddenly join the project and push commits for the first time? How would you preserve the graph's readability in such a situation?


7. Network Graph Visualizer

	* The audience is the project manager and the contributors to the repository. This is so they can keep track of what branches the commits of his team are affecting in case of deleterious changes. 
	* The data consists of commits, date of commits, branch, and user: Using the Github API, we would need to access the data through multiple queries: https://api.github.com/repos/:owner/:repo/branches and https://api.github.com/repos/:owner/:repo/commits 
	* For this visualization, the result of high activity will likely skew the graph since the x-axis is scaled by time and there is equal distance between commits. Thus in that single day, there would be many circles and small distances attaching those circles. To fix this, I would make an extra feature that would allow the user to zoom in and out based on time. 
	* The role of interactions, lets the viewer of the visualization see the commit comment, who made the commit, and a link to the actual commit. The visualization also allows the user to scroll over time.
	* This would not be an issue since the visualization is divided vertically by forks. Thus joining a project would only affect the visualization if they were commiting to a branch of one of these forks. 


