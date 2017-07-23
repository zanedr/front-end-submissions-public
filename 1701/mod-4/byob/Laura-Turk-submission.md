# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/lauraturk/lt-byob)

#### Link to the Deployed Application
[Heroku](https://byob-madlib.herokuapp.com/)


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
(Yes) - with githooks for linting and testing

* Wrote tests for both happy and sad paths for each endpoint?
(Yes)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/lauraturk/lt-byob/blob/master/data/data_fetch.js)

* It's likely not the prettiest, but I am proud that I reasoned through webscraping and parsing the return from the API I used to parse the words. It returned the text back as a single string w/ each word suffixed with it's coded part of speech (e.g. cat/NN). I would also like to refactor this further to use directly in the post so that a user could post a title and body or the url of a book on amazon and have it post the parsed and sorted words to the database. I used a class to give it additional flexibility for future use.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/lauraturk/lt-byob/blob/master/server.js#L124-L136)
and 
[code that makes me sad](https://github.com/lauraturk/lt-byob/blob/master/test/routes.spec.js#L361-L377)

* I don't think this is doing what I want it to do. My test passes, but that speaks more to the tiny size of my test seed file rather than to the efficacy of this code. Challenges I faced here were not fully understanding the syntax of what I should do, leaving it to the last minute ;-(, and maybe the overall architecture of my api being too loosy goosy for this to work as it should? I'm not sure.

* The second piece of code makes me very said because I just don't understand why the test won't pass in Circle Ci. They passed locally, and the endpoint works in postman sans problems. What's the deal, Circle CI? I'm sad I had to skip that test.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test suite](http://i.imgur.com/LBzugc0.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

![linter output](http://i.imgur.com/FRa5xyW.png)

#### Attach a screenshot of your CircleCI build passing

![circleCI build](http://i.imgur.com/Y64ooEF.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

* This is the first project I really, truly TDD'd and it was great. No last minute stress trying to get tests written and passing, and didn't have to mess around with postman a ton until I was confident things were work. I'd also love to start adding Spanish text samples and words to this dataset! Dave and I might use this as a spring-board to make a madlib game for our capstone. All the ideas... though I'm worried this back end might not up to snuff for what we need.
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
