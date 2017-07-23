# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](http://github.com/devthehuman/build-your-own-backend)

#### Link to the Deployed Application
[Heroku](https://byob-dd-lol.herokuapp.com/)


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
[happy code](https://github.com/devthehuman/build-your-own-backend/blob/master/scraper.js#L1-L42)

* Why were you proud of this piece of code?
  * This was my first time implementing a web scraper in a project and I really enjoyed how simple it was to learn and 
  the ability to scrape a site for specific data I wanted. The recursive calls took some fiddling with to get the scraper
  to run all the way through, but I got it. 

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/devthehuman/build-your-own-backend/blob/master/test/routes.spec.js#L111-L125)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
  * This code is a bummer because the test itself works in the terminal and the endpoint is fine in Postman, but for some 
  reason it doesn't like it in CircleCI. I've tried a bunch of different ways to refactor it and I'm honestly stumped as to 
  why it doesn't pass the build.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://github.com/devthehuman/build-your-own-backend/blob/master/screenshots/test-suite-ss.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](https://github.com/devthehuman/build-your-own-backend/blob/master/screenshots/linter-ss.png)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](https://github.com/devthehuman/build-your-own-backend/blob/master/screenshots/circle-ci-ss.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say
* After completing this project and looking back on it, I would definitely make a more complex database with many-to-many 
  relationships implemented. 

-----


# Instructor Feedback (Brittany)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**8 points**: The README includes documentation for all available endpoints and how to use them. Instructor can follow the documentation for using the API but has to do some parsing.

* I'd like a formatted example of what kind of JSON object I need to pass through for POST requests. The list of properties is nice but let's make it a little more readable.

### Feature Completion

**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

**30 points**: Project has a running test suite that covers all happy and sad paths for the appropriate endpoints, works locally but not in CircleCI - linter passes but is pretty weak and still allows for a lot of inconsistencies in style.

* I would use `it.skip` rather than [commenting out](https://github.com/devthehuman/build-your-own-backend/blob/master/test/routes.spec.js#L111-L125) an entire test for the sake of CircleCI.

* [These two lines](https://github.com/devthehuman/build-your-own-backend/blob/master/test/routes.spec.js#L71-L72) shouldn't pass a linter. Your jshintrc file is pretty weak and allows a lot of inconsistencies in your code style.

### JavaScript Style

**20 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Endpoint URLs don't need to have words like 'new' or 'delete' or [all](https://github.com/devthehuman/build-your-own-backend/blob/master/test/routes.spec.js#L34) in [them](https://github.com/devthehuman/build-your-own-backend/blob/master/test/routes.spec.js#L129). You can overload a single URL with multiple HTTP methods (e.g. use `/api/v1/roles` for GET and POST, `api/v1/roles/2` for DELETE, PATCH, PUT). Usually those types of words are put in client-side routes as an indicator to the user about what they should be doing on that page.

* You shouldn't commit your `.env` file and [this](https://github.com/devthehuman/build-your-own-backend/blob/master/server.js#L18-L20) should not work. You need to set these values as environment variables in CircleCI and Heroku and fallback to the `config` values if you are in development.

* It's difficult to tell that [this endpoint](https://github.com/devthehuman/build-your-own-backend/blob/master/server.js#L104-L105) is for getting a **specific** champion. I see you're using it for when people pass in a name as a query param. This is something I would build into your get request for all champions -- Loop through the `Object.keys(request.query)` and chain any found query parameters as where conditions in knex. You could do this chaining with [whereIn](http://knexjs.org/#Builder-whereIn).

* Generally you wouldn't return the entire array of roles from a [post request](https://github.com/devthehuman/build-your-own-backend/blob/master/server.js#L144). Either return the single newly created role, or return nothing with just a successful 204.

* When deleting a record, you should use the primary key id in the URL of the endpoint rather than making a user [pass in a name property](https://github.com/devthehuman/build-your-own-backend/blob/master/server.js#L294-L315). e.g. this should be rewritten `app.delete('api/v1/champions/:id')` and make your where condition based on `req.params.id` rather than a value in the body.

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 118 / 150
