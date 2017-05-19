# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/ActionJonny/BYOB)

#### Link to the Deployed Application
[Your project's production URL](https://dashboard.heroku.com/apps/fantasy-baseball-backend)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/ActionJonny/BYOB/commits/master)

## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
(Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes?
(Yes)

* Secured at least 4 endpoints with JWTs?
(No)

* Enforced a linter and wrote code that conformed to it?
(Yes)

* Wrote tests for both happy and sad paths for each endpoint?
(Yes)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/ActionJonny/BYOB/blob/master/server.js#L127-L143)

* I found it very difficult removing a row with a foreign key pointing to it. The part that tripped me up the most was not realizing it was not deleting the player from the database, it was moving them after I changed the team_id to null.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/ActionJonny/BYOB/blob/master/server.js#L74-L143)

* It is weird that this block includes the code I am most proud of, but pretty bummed I wasn't able to including my JWT's in these methods.

## Testing
![test](http://recordit.co/rHQWyvcA87/gif/notify)
Attach a screenshot or paste the output from your terminal of the result of your test-suite running

## Linting

![linting](http://g.recordit.co/mBu1eMZmr7.gif)

* Not sure why I am not getting a response with no errors, but there are not linting issues.

-----

#### Please feel free to ask any other questions or make any other statements below!

* I need to get lunch before gear-up! 

-----

# Instructor Feedback

- Points: x / 150
