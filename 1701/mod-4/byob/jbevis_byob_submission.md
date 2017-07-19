# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/jbevis/build-your-own-backend)

#### Link to the Deployed Application
[Heroku](https://jb-byob.herokuapp.com/api/v1/regions)


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
[happy code](https://github.com/jbevis/build-your-own-backend/blob/master/server.js#L127-L145)

* Why were you proud of this piece of code?

I struggled with the concept of query parameters for a few days, so I was particulary happy once it finally clicked, and was able to return the earthquakes within a given range. 

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L435-L463)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I think I could have tested this end point more thoroughly, I admit it might have not received as much attention due to me finishing this part of the project very early in the morning.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://recordit.co/lCzgydddgU)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](http://imgur.com/a/cRFgR)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](http://imgur.com/a/dBmyv)

-----

#### Please feel free to ask any other questions or make any other statements below!

*** JWT Token = eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImVhcnRocXVha2UiLCJwYXNzd29yZCI6InNoYWtlIiwiaWF0IjoxNTAwMDE5NzI4LCJleHAiOjE1MDAzNjUzMjh9.C_pmCkBSYI8vNFrc2Dvx11fWlTDKEwEXyIV2OwT6ySk

This project was much harder that I was expecting. The types of bugs encountered and the TIME spent debugging was trying. That being said, I learned a ton, especially being able to think critically about database schema and how table relations work. I wasn't able to implement the type of endpoints I originally envisioned, but that had more to do with the Data. I do feel much better about implementing JWTs now. Yay backend stuffs. That is all.

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
