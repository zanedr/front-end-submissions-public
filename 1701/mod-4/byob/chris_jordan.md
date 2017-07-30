# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/cjorda15/brob)

#### Link to the Deployed Application
[Heroku](https://intense-taiga-19330.herokuapp.com/)


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
(Yes(if you include sad path as unauthorized, will do proper sad paths for bad validation for last remaining few by tomorrow ))

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/cjorda15/brob/blob/master/server/router.js)
--lines 137-152
* Why were you proud of this piece of code?

Not a whole lot I'm truly proud of really, this once had a loop doing a lame id generator(there's already things for that??). oh boie.  

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/cjorda15/brob/blob/master/server/router.js)

Pretty much the whole thing

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Just want to reflect a true blue RESTful api
#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://github.com/cjorda15/brob/blob/master/sc.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](https://github.com/cjorda15/brob/blob/master/bb.png)
can't output if no errors, but certainly will when there is some..

#### Attach a screenshot of your CircleCI build passing

[circleCI build](https://github.com/cjorda15/brob/blob/master/ss.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say! (Nope!)

-----


# Instructor Feedback (Brittany)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**6 points**: The README includes documentation for all available endpoints and how to use them. Instructor can follow the documentation for using the API but has to do some parsing.

* Formatting is really difficult to read here. Make use of headings and break things out a bit better. Format the write request requirements in code blocks rather than plain text.

### Feature Completion

**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

**20 points**: Project has a running test suite that covers most happy and sad paths for each endpoint. Error handling has been implemented but does not cover all possible scenarios or is unhelpful for the end-user. Linter has some errors that need fixing.

* I know this is just in your description, but [402](https://github.com/cjorda15/brob/blob/master/test/routes.spec.js#L22O) is not accurate here. Make sure test descriptions accurately reflect the functionality.

* Not sure why [this](https://github.com/cjorda15/brob/blob/master/test/routes.spec.js#L35-L43) commented out code is here. You are doing those exact lines directly beneath where you commented them out.

* I wouldn't actually [sort](https://github.com/cjorda15/brob/blob/master/test/routes.spec.js#L61-L62) the data you're getting back in your tests because it gives it another layer of being further away from the "truthy" data. It makes it slightly different in ways that you won't be able to reproduce in development/production. Don't sort, and instead only make assertions that don't depend on your data being in a particular order. (You can do a find on the entire array to check the value of a particular record)

* 402 is not the correct [status code](https://github.com/cjorda15/brob/blob/master/test/routes.spec.js#L176)

* If [these tests](https://github.com/cjorda15/brob/blob/master/test/routes.spec.js#L354-L376) aren't passing you should skip them rather than just commenting out the code.


### JavaScript Style

**25 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* You don't need this entire [authentication](https://github.com/cjorda15/brob/blob/master/test/routes.spec.js#L157-L169) endpoint, and you definitely wouldn't hardcode the username and password data into your test file. You could have just signed a JWT and logged its value on the first run of the server and held onto it for the duration of the project.

* Nice touch putting your [readme at the root](https://github.com/cjorda15/brob/blob/master/server/index.js#L20)

* Always have [catches](https://github.com/cjorda15/brob/blob/master/server/router.js#L71) with your promises.

* Not sure what's happening in [this endpoint](https://github.com/cjorda15/brob/blob/master/server/router.js#L123-L125) What is the purpose of the 'query' part of the URL? It looks like you're grabbing column and type from the actual query string, rather than from a dynamic part of the URL.

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 111 / 150
