# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/cjorda15/brob)

#### Link to the Deployed Application
[Heroku](https://intense-taiga-19330.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
(Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes?
(Yes)

* Secured at least 4 endpoints with JWTs?
(Yes)

* Enforced a linter and wrote code that conformed to it?
(Yes)

* Wrote tests for both happy and sad paths for each endpoint?
(Yes(if you include sad path as unauthorized, will do proper sad paths for bad validation for last remaining few by tomorrow ))

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/cjorda15/brob/blob/master/server/router.js)
--lines 137-152
* Why were you proud of this piece of code?

Not a whole lot I'm truly proud of really, this once had a loop doing a lame id generator(there's already things for that??). oh boie.  

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/cjorda15/brob/blob/master/server/router.js)

Pretty much the whole thing

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Just want to reflect a true blue RESTful api
#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://github.com/cjorda15/brob/blob/master/sc.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](https://github.com/cjorda15/brob/blob/master/bb.png)
can't output if no errors, but certainly will when there is some..

#### Attach a screenshot of your CircleCI build passing

[circleCI build](https://github.com/cjorda15/brob/blob/master/ss.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say! (Nope!)

-----


# Instructor Feedback (Brittany)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**6 points**: The README includes documentation for all available endpoints and how to use them. Instructor can follow the documentation for using the API but has to do some parsing.

* Formatting is really difficult to read here. Make use of headings and break things out a bit better. Format the write request requirements in code blocks rather than plain text.

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
