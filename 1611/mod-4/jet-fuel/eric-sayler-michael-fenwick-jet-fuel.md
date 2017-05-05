# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/Mickyfen17/jet-fuel)

#### Link to the Deployed Application
[Your project's production URL](http://jet-fuelled.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Eric Sayler](https://github.com/Mickyfen17/jet-fuel/commits/master?author=esayler)

-[Michael Fenwick](https://github.com/Mickyfen17/jet-fuel/commits/master?author=Mickyfen17)

#### Provide a Screenshot of your Application

![](http://i.imgur.com/184DMfa.png)

## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

- Added ability to delete individual folders and Urls

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[FE query to backend for sort functionality](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/app.js#L65)

- Utilized the backend (knex's `orderBy()`) to sort our URLs based on query params passed through in the GET request.

#### Link to a specific block of your code on Github that you feel not great about
[Giant IIFE for toggling filter](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/app.js#L37)

- Could be cleaned up to seperate the state logic from DOM manipulation. Multiple nested if statements are hard to follow.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![](http://i.imgur.com/Mb2nvaG.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

- [Link to unhappy path example](https://github.com/Mickyfen17/jet-fuel/blob/master/test/routes.spec.js#L232)
-----


# Instructor Feedback

- Points: x / 150
