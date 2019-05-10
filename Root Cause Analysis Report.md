# Root Cause Analysis Report
## Project Name: Issue First
## Project Owner: Hannah Ingham
## Date: May 10, 2019 
## Team: Erin Trainor, Vanessa Wei, and Cory Henderson
## Summary:
This report describes five issues we identified in the “Issue First” project by Hannah Ingham [GitHub - issue-first/github-graphql](https://github.com/issue-first/github-graphql).  We were able to submit pull requests to fix four of the five identified issues. These were all issues we identified after being users of the [Issue First](https://issue-first.netlify.com/) site.

## List of Identified Issues
	* Pagination buttons needed at bottom of search results
	* Selecting an Issue does not open a new tab
	* Typo in form 
	* URLs overflow container when page is re-sized
	* Sort results by data updated (both GraphQL and REST)

## Issue Resolution Details
###  Pagination buttons needed at bottom of search results
#### Description:
#### Solution:
###### Pull Request Made?
	- [x] Yes
	- [ ] No
[Link to Pull Request](https://github.com/issue-first/github-graphql/pull/19)

### Selecting an Issue does not open a new tab

#### Description:
We noticed that when using the application, if you selected an issue, rather than the click event opening a new tab the existing page changed to the requested url. This was a problem because you would subsequently loose your place in the search results that had already been reviewed.

#### Solution:
We added a `“target=“` to the `<a>` tag. Originally we had this as `_blank` but VSCode warned us that this may result in a security vulnerability	so we changed the target to match the URL from the `href` on the adjacent line `{props.issue_url}`. The change that was made is found on git-issue.js line 11.

###### Pull Request Made?
	- [x] Yes
	- [ ] No
	- [ ] [Link to Pull Request](https://github.com/issue-first/github-graphql/pull/22)

### Typo in form 
#### Description: There was a spelling typo in the form heading `Please Select Lanugage and Issue Type` on `form.js` line 27.

#### Solution:
Corrected the spelling of `Lanugage`  to `Language`

###### Pull Request Made?
	- [x] Yes
	- [ ] No
[Link to Pull Request](https://github.com/issue-first/github-graphql/pull/20)

### URLs overflow container when page is re-sized

#### Description:
When resizing the window, URLs present in the rendered content overflow their container. 

#### Solution:
In `index.sass` added `word-wrap:break-word` to `.card-content` on line 38. This forces all content to wrap regardless of whether there is a natural word break.

###### Pull Request Made?
	- [x] Yes
	- [ ] No
[Link to Pull Request](https://github.com/issue-first/github-graphql/pull/21)

### Sort results by data updated (both GraphQL and REST)

#### Description: 
It would be great to be able to have the results be returned to the page after being sorted by date updated. This may reduce time spent looking for a project that is actively being monitored.

#### Solution: 
We were not able to solve this for a variety of different reasons. Documentation for graphQL and ApolloQL showed (apparently simple) way of accomplishing this but all of the solutions were done by modifying the resolver structure in the backend. Since first-issue is a front end application different means would need to be used to sort the results after they are sent to the page.

###### Pull Request Made?
	- [ ] Yes
	- [x] No


