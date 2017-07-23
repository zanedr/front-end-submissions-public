# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/kellymiller6/byob)

#### Link to the Deployed Application
[Heroku](https://km-build-your-own-backend.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
Yes

* Seeded a database with at least 2 tables and 1 relationship?
Yes

* Had at least 10 endpoints that returned responses with appropriate status codes?
Yes

* Secured at least 4 endpoints with JWTs?
Yes

* Enforced a linter and wrote code that conformed to it?
Yes

* Wrote tests for both happy and sad paths for each endpoint?
Yes

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L433-L451)

* Why were you proud of this piece of code?

Honestly not that proud of any of my code, it's all super repetitive and needs to be
refactored. This test was perhaps my favorite problem I solved.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L288-L299)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
All my sad path tests need to be more thorough and my error messages that go along with them.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://i.imgur.com/yyvJTsc.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](http://i.imgur.com/EPKXMje.png)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](http://i.imgur.com/V2vyvj4.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say

-----


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **5 points** -  The README documentation is out-of-date or inaccurate in some places. Instructor can not successfully use every endpoint based on following the documentation. 

- I wouldn't recommend linking to code since some developers aren't familiar with Node, and certainly everyone using your API might not necessarily have backend experience
- Would like to see common helpful parts of API documentation which is showing sample output from an API call and the possible data you can pass in to a POST or PATCH/PUT request

### Feature Completion

* **55 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

- Taking off 5 points because the query parameter implementation was not correct, looking for something like `/api/v1/covers?date=08092017` instead of `/api/v1/covers/date/08092017`

### Testing & Linting & Error Handling

* **30 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Error handling has been implemented but does not cover all possible scenarios or is unhelpful for the end-user. Linter has some errors that need fixing.

- What do you need [this line](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L12) in your test file?
- You're doing a lot of extra work [here](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L43-L54) with the `beforeEach`. In your implementation, you are rolling back your schema, migrating, and then seeding data for every test. This is overkill since all you want to do is delete the records from your tables and reseed, not run a migration.
  - Instead, have a `before`, which only runs once before all the tests which runs the migrations, and then a `beforeEach` that clears records and reseeds the tables
- Even if you can't test for exact content [here](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L61-L64) because of ambiguity in the order of records, you can still test for structure (properties) of the data in the array
- Do not see a test for a GET request with a custom query parameter
- Good sad path and error response [here](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L94), [this is good too](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L474-L487)
- Should not be submitting ID values, like [here](https://github.com/kellymiller6/byob/blob/master/test/routes.spec.js#L313), even in testing. It is OK to specify the ID in a seed file, but for any requests, you should let the database handle the auto incrementing ID value

### JavaScript Style

* **30 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- Put your data files in some data directory just to clean up your project file structure
- Multiple routes are not following the RESTful API convention, for instance `/api/v1/covers/id/4` should just be `/api/v1/covers/4`, the ID is implied following the resource, no need to specify `/id/4`
- Were you actually having CORS issues to [need this](https://github.com/kellymiller6/byob/blob/master/server.js#L13)?
- In the future, when your server file contains a lot endpoints, you can extract these endpoints to their own router file, [see the docs](https://expressjs.com/en/guide/routing.html#express-router)
- Why the inconsistency between the error [here](https://github.com/kellymiller6/byob/blob/master/server.js#L109) and [here](https://github.com/kellymiller6/byob/blob/master/server.js#L123)

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 120 / 150
