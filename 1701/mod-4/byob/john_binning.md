# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/JohnBinning/BYOB)

#### Link to the Deployed Application
[Heroku](https://byobaseball.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
(Yes)

* Seeded a database with at least 2 tables and 1 relationship?
(Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes?
(Yes)

* Secured at least 4 endpoints with JWTs?
(Yes)

* Enforced a linter and wrote code that conformed to it?
(Yes)

* Wrote tests for both happy and sad paths for each endpoint?
(Yes)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/JohnBinning/BYOB/blob/master/test/routes.spec.js#L455-L472)

* Why were you proud of this piece of code?

I feel that this is a good test.  I test to make sure we get the correct status code on delete, and then further validate that the response code was accurately returned by making sure we have on less person in the db than we previously did.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/JohnBinning/BYOB/blob/master/server/server.js#L180-L185)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I wanted to send back the name the deleted franchise, but had difficulty figuring out how.  I feel like it would be nice to have better confirmation that we deleted the correct franchise.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://i.imgur.com/GM3CY51.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](https://i.imgur.com/tZ3hx3a.png)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](https://i.imgur.com/uZnUnU1.png)

-----

#### Please feel free to ask any other questions or make any other statements below!


-----


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
