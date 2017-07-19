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
