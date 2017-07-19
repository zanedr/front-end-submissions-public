# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/cbandrow/byob)

#### Link to the Deployed Application
[heroku](https://cb-cardata.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
(Yes, 4 tables, each with a one to many relationship.)

* Had at least 10 endpoints that returned responses with appropriate status codes?
(Yes)

* Secured at least 4 endpoints with JWTs?
(Yes)

* Enforced a linter and wrote code that conformed to it?
(Yes)

* Wrote tests for both happy and sad paths for each endpoint?
(Yes, to an extent. Tests are working locally, but are failing on CircleCI. Most get Happy/Sad paths are covered, there are issues with sad paths for authentication measures.)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Successfully deployed, issues with some tests. Tests pass locally, but fail in the Circle CI)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/cbandrow/byob/blob/master/db/seed/dev/makes-models.js#L25-L91)
Oh man, this was the win for me during this project. Seeding the data. Sounds easy? Well, it required a lot of data manipulation to get it to a usable product.
Each make has references to a set of models. Each model has references to a set of years. Each year has references to a set of Trims. 
It worked and I loved figuring out this technical challenge with Promise.all's nested around. It just felt like a big enough technical challenge for me that I have some pride in nesting the calls and resolving them when needed. 

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/cbandrow/byob/blob/master/server.js#L249-L296)
Not necessarily feeling super sad about these lines, but I'm more concerned about them than anything. I feel like these nested promises look like a callback hell situation. Am I doing the right thing here? Are these queries considered a best practice or acceptable? I want to get better at writing the queries for these routes, but I'm worried if I'm doing them in the right way. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
✓ should GET all makes.
✓ should GET all models by a specific make_name
✓ (sad path) should GET a status code 404 model is not found
✓ should GET all models by a specific make_name 
✓ (sad path) should return a 500 if no the make is invalid  
✓ (sad path) should return a 404 if no models found
✓ should make a GET query to get models by a specific query
✓ (sadpath) should make return a 500 if the query is not valid
✓ (sadpath) should make return a 404 if the query doesnt return an array
✓ should make a GET request to get year data by model
✓ (sad path) should return a 404 if no model is found
✓ should make a GET query to get years by a specific query  
✓ should make a GET request to get Trim data by year  
✓ should make a GET request to get Trim data
✓ should POST a new trim_id.
✓ should POST a new model based on make.
✓ should PUT a new trim by trim id.
✓ should PUT a cars year data.
✓ should DELETE a model
✓ should DELETE a trim

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

![linter output](http://imgur.com/LniRdry)

#### Attach a screenshot of your CircleCI build passing

![circleCI build](http://imgur.com/J7c9V1G)

-----

#### Please feel free to ask any other questions or make any other statements below!

I didn't get much sleep last night. I'm more pleased with how this project turned out compared to Jet-Fuel. I'm mostly concerned about my code quality, especially after being super sleepy. I'm not doing to well when it comes to feeling confident about my work, despite the numbers of hours logged. I don't feel I'm creating code on the same field with my peers, I feel like I'm stuck behind. I'm not feeling good about the code or its output. 

-----


# Instructor Feedback (Instructor Name)

The following set of points are distributed at the discretion of the instructor.

### Endpoints

**x points**: Lorem ipsum dolor set amet

### Data Persistence with SQL Database

**x points**: Lorem ipsum dolor set amet

### Testing & Linting

**x points**: Lorem ipsum dolor set amet

### JavaScript Style

**x points**: Lorem ipsum dolor set amet

### To get a 3 on this project, you need to score 115 points or higher
### To get a 4 on this project, you need to score 140 points or higher

# Final Score: x / 150
