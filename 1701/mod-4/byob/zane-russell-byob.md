# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[byob](https://github.com/zanedr/build-your-own-backend)

#### Link to the Deployed Application
[heroku](https://guarded-temple-79046.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
(Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes?
(Yes)

* Secured at least 4 endpoints with JWTs?
(Yes)

* Enforced a linter and wrote code that conformed to it?
(Kind of, used airbnb's and didn't have time to complete the linting)

* Wrote tests for both happy and sad paths for each endpoint?
(For all except the delete points)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/zanedr/build-your-own-backend/blob/master/server.js#L290)

* Most intricate server request I've ever made

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/zanedr/build-your-own-backend/blob/master/server.js#L290)

* The same code.  There must surely be a better and more concise way to do this.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://imgur.com/a/8diD1)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](https://imgur.com/a/MOcTi)
got a hook up for the linter at least.  I'll try to resolve this

#### Attach a screenshot of your CircleCI build passing

[circleCI](https://imgur.com/a/fEvi8)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----


# Instructor Feedback (Brittany)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**8 points**: The README includes documentation for all available endpoints and how to use them. Instructor can follow the documentation for using the API but has to do some parsing.

* I'd like a formatted example of what kind of JSON object I need to pass through for POST requests. The list of properties is nice but let's make it a little more readable and tell me what data types each property requires. (e.g. what should be passed in as a string, what should be an integer, etc).

### Feature Completion

**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

**x points**: Lorem ipsum dolor set amet

### JavaScript Style

**x points**: Lorem ipsum dolor set amet


## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: x / 150
