# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/DBULL7/VoterData)

#### Link to the Deployed Application
[Heroku](https://gentle-shelf-31018.herokuapp.com/api/v1/voters)


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
(Sad Paths, Happy paths couldn't be tested with MongoDB)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/DBULL7/VoterData/blob/master/server/router.js)

* Why were you proud of this piece of code?

I was able to use multiple controllers and make each controller file responsible only for it's corresponding routes.
It's something that's been bugging me for weeks and to finally do it felt great. 

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/DBULL7/VoterData/blob/master/server/controllers/districtController.js#L66-L79)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

It had to be dynamic to set/update or delete a key value pair on a mongodb record. 
I got it to work but it just looks awful to me.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![Imgur](http://i.imgur.com/ZeG71Lk.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

![Imgur](http://i.imgur.com/yPMEmdG.png)

#### Attach a screenshot of your CircleCI build passing

![Imgur](http://i.imgur.com/jsdLCRr.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say

MongoDB almost proved to be more than I can handle but I made it. Older, with more battle scars, not sure about wiser. 
Definitely made me appreciate the simplicity of SQL databases. Thanks for letting me run with it, I've been 
dreaming about taking huge amounts raw data and sculpting it into something useful for a couple of years now. 
Feels great to have finally done it. 

-----


# Instructor Feedback (Brittany)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**8 points**: The README includes documentation for all available endpoints and how to use them. Instructor can follow the documentation for using the API but has to do some parsing.

* It would be nice to format the write requests with the data they require in a JSON object rather than just listing the property names. This would allow you to also specify the data type for each property which can sometimes be difficult to guess.

### Feature Completion

**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

**x points**: Lorem ipsum dolor set amet

### JavaScript Style

**x points**: Lorem ipsum dolor set amet


## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: x / 150

