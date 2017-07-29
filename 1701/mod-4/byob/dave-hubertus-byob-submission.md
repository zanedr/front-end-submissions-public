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


# Instructor Feedback (Brittany)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**9 points**: The README includes documentation for all available endpoints and how to use them. Instructor can follow the documentation for using the API but has to do some parsing.

* I'd like a formatted example of what kind of JSON object I need to pass through for write requests (POST/PATCH/PUTs). You can make a block of code by doing a line of 3 grave marks before and after the code block. This would also give you more room to tell me what data types each property requires. (e.g. what should be passed in as a string, what should be an integer, etc).

* I like that you added layouts for the data tables as images as well. Gives nice insight into what the data structure looks like.


### Feature Completion

**50 points**: Completed almost all features, but lacking a relationship between the two data tables.

* The relationship is a pretty big part of the challenge for this project, would have been nice to find a way to join these tables in some way or create another one that linked up to either of them.

### Testing & Linting & Error Handling

**30 points**: Project has a running test suite that covers happy and sad paths for each endpoint. Error handling has been implemented and linter is passing.

* We want to use an environment variable [here](https://github.com/dhubertus/byob/blob/master/test/routes.spec.js#L12) rather than hard-coding the JWT.
'
* Error handling in places like [this](https://github.com/dhubertus/byob/blob/master/server.js#L218) [this](https://github.com/dhubertus/byob/blob/master/server.js#L180) and [this](https://github.com/dhubertus/byob/blob/master/server.js#L198) could be more specific. Are they missing the required selection parameter? Tell them so and show them how to format their request appropriately or point them to the documentation that makes sense here.

### JavaScript Style

**20 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* You shouldn't be accessing questions based on their question value, use the primary key (an ID) [here](https://github.com/dhubertus/byob/blob/master/test/routes.spec.js#L76) instead. You can't guarantee that these long question strings are formatted in a URL-friendly way and also unique. (The spaces in these questions is alone enough to be too sloppy to use as an endpoint parameter)

* You don't actually need this authenticate [endpoint](https://github.com/dhubertus/byob/blob/master/test/routes.spec.js#L94-L125) it was there for new users getting their own API tokens. You could have just done a `jwt.sign()` and logged the value once, then remove all of this code.

* Having a `newQuestion` [endpoint](https://github.com/dhubertus/byob/blob/master/test/routes.spec.js#L129) isn't generally how you would structure your URLs. Instead you would overload the `api/v1/questions` endpoint with GET and POST requests. There's no need to denote in the URL what it is you're doing with it, as that will get passed in as the method from the fetch request itself. Adding things like 'new' to the URL are generally preserved for client-side routes so that an end user knows what they should actually be doing on a particular page.


## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 109 / 150
