# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/dhubertus/byob)

#### Link to the Deployed Application
[Heroku](https://byob-dave-hubertus.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
(Yes)

* Seeded a database with at least 2 tables and 1 relationship?
(No) #####


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
[happy code](https://github.com/dhubertus/byob/blob/master/server.js#L164-L186)

* Why were you proud of this piece of code?
Proud of this code because it is easily readable, functions with checkAuth, and handles errors properly.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/dhubertus/byob/blob/master/server.js#L105-L118)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
I realized too late in the game that I can have colliding questions even thought they are in reference to different bets. I would refactor the db query to be more selective based on additional information.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

<img width="793" alt="screen shot 2017-07-14 at 11 49 07 am" src="https://user-images.githubusercontent.com/25044263/28223959-9a18fbac-688a-11e7-8364-75540f9f1268.png">


#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

<img width="529" alt="screen shot 2017-07-14 at 12 09 47 pm" src="https://user-images.githubusercontent.com/25044263/28224733-794bcf28-688d-11e7-9827-cedd49c76660.png">


#### Attach a screenshot of your CircleCI build passing

<img width="904" alt="screen shot 2017-07-14 at 12 45 33 pm" src="https://user-images.githubusercontent.com/25044263/28226175-6b559610-6892-11e7-9be3-23d4e3a765b7.png">

-----

#### Please feel free to ask any other questions or make any other statements below!

I originally planned on scrapping bets from ESPN and betting odds for MLB, NBA, NFL, and NHL as to have a table in which the questions could be tied to the game by foreign key but found it difficult to make dynamic as scrapped data comes in. I decided to use stale data, which I though about adding a hardcoded foreign key for 'MLB' but ultimately moved onto testing and Circle CI/Heroku.

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
