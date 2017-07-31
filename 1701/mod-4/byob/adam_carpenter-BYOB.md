# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[GitHub -BYOB](https://github.com/Adamj1232/Build-Your-Own-Backend)

#### Link to the Deployed Application
[heroku-BYOB](https://b-y-o-b.herokuapp.com/api/v1/venues/all)


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
**?**

* Seeded a database with at least 2 tables and 1 relationship?
Yes

* Had at least 10 endpoints that returned responses with appropriate status codes?
No - I had a ton of trouble getting my put and patches work

* Secured at least 4 endpoints with JWTs?
Yes

* Enforced a linter and wrote code that conformed to it?
No

* Wrote tests for both happy and sad paths for each endpoint?
Yes

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/Adamj1232/Build-Your-Own-Backend/blob/master/db/migrations/20170710180907_initial.js#L1)

* Why were you proud of this piece of code? Only one migration needed!

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/Adamj1232/Build-Your-Own-Backend/blob/master/server.js#L286)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it? I couldn't get insert to work inside my put method, I rewrote multiple times and looked through the docs

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://imgur.com/KhtXibI)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output]() Wasn't able to implement this in time

#### Attach a screenshot of your CircleCI build passing

[circleCI build](http://imgur.com/a/sSZt0) 

-----

#### Please feel free to ask any other questions or make any other statements below!

I received my first interview this week, it was on Tuesday so I spent a lot of time preparing for that as well as my portfolio. Crushed the interview and the tech challenge but it put me way behind on this project and the pattrn party. I have been struggling since to get back on track in class.

-----


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **10 points** -  The README includes documentation for all available endpoints and how to use them. Instructor can easily follow the documentation for using the API.
* **5 points** -  The README documentation is out-of-date or inaccurate in some places. Instructor can not successfully use every endpoint based on following the documentation. 
* **0 points** - The README documentation is too sparse or inaccurate to be helpful.

### Feature Completion

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.
* **40 points** - Developer has implemented all 10 endpoints but did not secure 4 of them with JWTs or have a custom endpoint based on query params. The database is seeded with at least two tables but without an appropriate relationship.
* **20 points** - Developer is missing endpoints and has not secured or customized any of the ones that have been implemented. The database is not seeded with two tables and one relationship.

### Testing & Linting & Error Handling

* **40 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. Error handling is informative and helpful for the end-user. The project has a linting configuration that passes with no errors.
* **20 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Error handling has been implemented but does not cover all possible scenarios or is unhelpful for the end-user. Linter has some errors that need fixing.
* **10 points** - Project has significant lack of testing for happy and sad paths of endpoints. Error handling is non-existent or missing status codes and helpful messages. Linter is failing on multiple lines.

### JavaScript Style

* **40 points** - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There _zero_ instances where an instructor would recommend taking a different approach.
* **20 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.
* **15 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.
* **10 points** - Your application has a significant amount of duplication and one or more major bugs. Developer cannot speak to most choices and does not know what every line of code is doing.


### To get a 3 on this project, you need to score 115 points or higher
### To get a 4 on this project, you need to score 140 points or higher

# Final Score: x / 150
