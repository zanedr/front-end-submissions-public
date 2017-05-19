# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[Beers&Brewery-BYOB](https://github.com/Mickyfen17/build-your-own-backend)

#### Link to the Deployed Application
[Heroku deployed BYOB](https://byod-beers.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

[BYOB-Commits](https://github.com/Mickyfen17/build-your-own-backend/commits/master)

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
(Yes)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/Mickyfen17/build-your-own-backend/blob/master/server/index.js)

* Why were you proud of this piece of code?

Clean server index file utilizing app use and requiring individual routes from else where in the server folder.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/Mickyfen17/build-your-own-backend/blob/master/server/beers.js#L11)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Main GET request for /beers which also handles multiple query params.
It gets the job done but the nested if/else's can be hard to follow.

## Testing

![](http://i.imgur.com/L79duMy.png)

## Linting

![](http://i.imgur.com/9xmNZXA.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Cool project and quite enjoyed the time spent in the terminal and with Postman. TDD was in full flow for this one.

## Note on foreign ID's

The csv files that I decided to use already had ID's which linked to each other. When seeding I found the the ID's weren't being added to the correct row.
I decided to to create a new ID for each table which ended up linking to the correct foreign tables.
This is why in the POST requests I have to find the max value of a column and add a +=1 to pretty much auto increment the ID.
Primary key still auto increments is expected.

-----

# Instructor Feedback

- Points: x / 150
