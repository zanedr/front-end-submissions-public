# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/esayler/byob)

#### Link to the Deployed Application
[Your project's production URL](https://zelda-recipes.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/esayler/byob/commits/master)

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
(No)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(No)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/esayler/byob/blob/master/server/router.js#L254)

* Why were you proud of this piece of code?
- Used a transaction to make sure mutiple inserts of data are committed and if any fail then all changes to the DB are rolled back.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/esayler/byob/blob/master/server/router.js#L302)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

- Lots of repetive code. Hard to refactor unless split out into different endpoints. Body of patch for recipe has same nested shape
as returned recipe data, making it hard to process a patch when some things are optional. 

## Testing

Attach a screenshot or paste the output from your terminal of the result of your test-suite running

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running

![](http://i.imgur.com/wLHR6bb.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Spent lots of time scraping data during the first part of the week. Will finish testing, CircleCI and JWT and update with a PR.

-----

# Instructor Feedback

- Points: x / 150
