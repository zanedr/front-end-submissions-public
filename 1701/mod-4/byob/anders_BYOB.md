# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/anderswood/byob)

#### Link to the Deployed Application
[Heroku](https://byob-notbeer.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
**Yes**

* Seeded a database with at least 2 tables and 1 relationship?
**Yes**

* Had at least 10 endpoints that returned responses with appropriate status codes?
**Yes**

* Secured at least 4 endpoints with JWTs?
**Yes**

* Enforced a linter and wrote code that conformed to it?
**Yes**

* Wrote tests for both happy and sad paths for each endpoint?
**Yes**

* Setup automatic deployments with CircleCI to a production app on Heroku?
**Yes**

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/anderswood/byob/blob/master/server.js#L118-L144)

* Why were you proud of this piece of code?
###### This code adds a lot of functionality with minimal lines of code- the user can query any of the column heading because the code dynamically pulls in their query

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/anderswood/byob/blob/master/server.js#L227-L248)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
##### I think these parameters are a little confusing for the user to input, could be easier, maybe with a custom search

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test suite](http://i.imgur.com/gFCtIi9.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

![linter output](http://i.imgur.com/pa0GhiK.png)

#### Attach a screenshot of your CircleCI build passing

![circleCI build](http://i.imgur.com/mBOaUeI.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say
-Not my favorite project... don't enjoy hanging out in the backend so much, but very satisfying when the endpoints do work in Postman

-----


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **10 points** -  The README includes documentation for all available endpoints and how to use them. Instructor can easily follow the documentation for using the API.

- Great overall documentation, I like the sample output you would get from queries

### Feature Completion

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

* **35 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. Error handling is informative and helpful for the end-user. The project has a linting configuration that passes with no errors.

- As a convention, [this](https://github.com/anderswood/byob/blob/master/tests/routes.spec.js#L1) should be `test`, not `testing`
- [Here](https://github.com/anderswood/byob/blob/master/tests/routes.spec.js#L8), you would not default to the development environment, you want the testing environment for your knex test configuration
- [Here](https://github.com/anderswood/byob/blob/master/tests/routes.spec.js#L117) you can test for the number of fuel stations you expect to be in the database too
- Good [sad path test](https://github.com/anderswood/byob/blob/master/tests/routes.spec.js#L255)
- Overall great coverage of happy and sad paths

### JavaScript Style

* **30 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- Not sure about `GET /api/v1/stations/fuels/:fuel_type_code` route. The resource nesting here is a little strange because if you are getting `fuels`, then I would expect to get fuel data back. I think `GET /api/v1/stations` with the fuel code as a query param would be more appropriate.
- You aren't serving any static assets, why have [this line](https://github.com/anderswood/byob/blob/master/server.js#L13) in your server file?
- Status code response for a PATCH is usually 200 or 204. [You used a 201](https://github.com/anderswood/byob/blob/master/tests/routes.spec.js#L314-L316), which is for when a resources is created
- The properties you want to change for a resource [via a PATCH](https://github.com/anderswood/byob/blob/master/tests/routes.spec.js#L311) should be passed in the body (like a POST), not as nested URL params
- In the future, when your server file contains a lot endpoints, you can extract these endpoints to their own router file, [see the docs](https://expressjs.com/en/guide/routing.html#express-router)
- You can also extract your helper functions (middleware for JWTs) into their own files
- Good error handling in the server file routes, but there is a good amount of duplication. You can bring some of these checks into their own functions/middleware
- Also look at queries that are nearly duplicated and see if you can extract these to their own functions so you can reuse the queries


## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 135 / 150
