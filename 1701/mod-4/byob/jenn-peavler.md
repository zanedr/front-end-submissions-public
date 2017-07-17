# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB]('https://github.com/jennPeavler/build-your-own-backend')

#### Link to the Deployed Application
[Heroku]('https://build-a-backend-jenn-peavler.herokuapp.com/api/v1/countries')


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
Yes.  I was able to write the functionality to hit all required enpoints and they are documented in the README.

* Seeded a database with at least 2 tables and 1 relationship?
Yes.  I seeded a table that has a list of countries.  The another table was seeded with a list of malnutrition data points.
Each data point in the second table is related to/refers to a country entry.  Each country entry may be associated with one or
several malnutrition data points.  So the tables are a one to many relationship.  One country to many malnutrition data points.

* Had at least 10 endpoints that returned responses with appropriate status codes?
Yes.  10 enpoints were implemented and return appropriate status codes.

* Secured at least 4 endpoints with JWTs?
Yes.  All of my POST/PATCH/DELETE requests are secured with a JWT.  That is 6 endpoints.

* Enforced a linter and wrote code that conformed to it?
Yes, I enforced a linter and a pre-commit git hook to that linter as one of the first steps in the project.

* Wrote tests for both happy and sad paths for each endpoint?
Yes.  Happy and sad path tests are written for each endpoint as well as some other functionality tests.

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes, automatic deployments with CircleCI to a production app on Heroku are implemented.  I am still having the odd occurence happen
where my CircleCI branch succeeds, but when I push that branch to github and merge that to master, the master branch fails.
We discussed this in class and over slack.  Solution is pending.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code]('https://github.com/jennPeavler/build-your-own-backend/blob/master/Server/getRequests.js#L5-L23')

* Why were you proud of this piece of code?
I like that I combined the to GET endpoints for all of one resource (i.e. ‘/api/v1/merchants’) into one modular file.  This
will allow me to easily add enpoints in the future.  Within this block of code, I could further enhance by making the filter
variable dynamic so that iso_code is not hardcoded.

#### Link to a specific block of your code on Github that you feel not great about
[sad code]('https://github.com/jennPeavler/build-your-own-backend/blob/master/Server/patchRequests.js#L38-L103')

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
While this code is functional, the if, else if, else block of code is very long.  I will be happier about it when I go back
to refactor it.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://i.imgur.com/pqRqGz8.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter git hook](http://i.imgur.com/YnXXuGp.png)
[linter running in atom](http://i.imgur.com/kc0LwNJ.png)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](http://i.imgur.com/vNUaetl.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say

Thank you.  I really enjoyed this project!  I look forward to putting a foward face on it!  The remaining question is just
the one that I discussed earlier about my circleCI branch passing in circleCI however when it is pushed to GH and merged
to master, master branch is failing in circleCI with the error message that I slacked to you.  Thanks!


# Instructor Feedback (Instructor Name)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**x points**: Lorem ipsum dolor set amet

### Feature Completion

**x points**: Lorem ipsum dolor set amet

### Testing & Linting & Error Handling

**x points**: Lorem ipsum dolor set amet

### JavaScript Style

**x points**: Lorem ipsum dolor set amet


## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: x / 150
