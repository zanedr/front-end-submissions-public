# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/hilvitzs/byob)

#### Link to the Deployed Application
[Heroku](https://sh-byob.herokuapp.com/)


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
Yes

* Seeded a database with at least 2 tables and 1 relationship?
Yes

* Had at least 10 endpoints that returned responses with appropriate status codes?
Yes

* Secured at least 4 endpoints with JWTs?
Yes

* Enforced a linter and wrote code that conformed to it?
Yes

* Wrote tests for both happy and sad paths for each endpoint?
No - I tested most happy and sad paths but for some I wasn't entirely sure how to get an error.

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code]()

* Why were you proud of this piece of code?

I'm actually really proud of the entire project. I really wasn't understanding the concepts we've covered and although this project was a struggle, especially with CircleCI and Heroku (since this was the first time I did that), I am very happy that I got most things to work and have a pretty thorough understanding of what's going on.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/hilvitzs/byob/blob/master/server.js#L104-L116)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

While I think that this will work for one query, I was confused as to how to extend that to multiple query parameters. I was happy that I thought of the object.keys and checking to see if they're there and using that for the select(), but I know that it's not completely functional and could be written better.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://i.imgur.com/SdCER8Q.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](http://i.imgur.com/MZulgYY.png)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](http://i.imgur.com/9xdBlIA.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

I am feeling a lot better about everything with this project, as well as with the extra Jet Fuel practice. I know that I could have done a little bit more testing but just understanding the basics of everything that I'm doing is a great, new feeling.

My token for this project is: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImpvaG4iLCJwYXNzd29yZCI6InNtaXRoIiwiaWF0IjoxNTAwMDE1MzY0LCJleHAiOjE1MDA2MjAxNjR9.dtGXeHB_1AxqPBByPDgJEYxgenurmgH7TQLceB_qWAI';
-----


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **5 points** -  The README documentation is out-of-date or inaccurate in some places. Instructor can not successfully use every endpoint based on following the documentation. 

- Would like to see one helpful part of API documentation which is showing sample output from an API call
- I don't see any documentation about the endpoint that uses a query parameter

### Feature Completion

* **55 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

- The relationship between wines and attributes seems to be a many-to-many relationship, but your schema uses a one-to-many relationship. It works here, but there is a lot of data redundancy in the attributes table. Ideally, you would have a wines, attributes, and wines_attributes table to join the many-to-many relationship.

### Testing & Linting & Error Handling

* **25 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Error handling has been implemented but does not cover all possible scenarios or is unhelpful for the end-user. Linter has some errors that need fixing.

- I don't see a test for the wines query parameter
- Your `before` function does not need to [seed data](https://github.com/hilvitzs/byob/blob/master/test/routes.spec.js#L19) because your `beforeEach` will take care of the seeding
- Even if you can't test for exact content (values in the array) in the test, for instance [here](https://github.com/hilvitzs/byob/blob/master/test/routes.spec.js#L47-L50), you can at least test for properties of the objects in the array
- Good sad path test [here](https://github.com/hilvitzs/byob/blob/master/test/routes.spec.js#L124)
- Overall, good happy path tests, but like you said, some sad path tests are missing - always make sure you're testing for structure of data if you can't test for exact content

### JavaScript Style

* **30 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- Were you actually having CORS issues with your own API to need [this code](https://github.com/hilvitzs/byob/blob/master/server.js#L7)?
- In the future, when your server file contains a lot endpoints, you can extract these endpoints to their own router file, [see the docs](https://expressjs.com/en/guide/routing.html#express-router)
- Missing a couple `.catch()` for handling errors if promises are not resolved
- You want to make sure you check the properties that are being passed in [here](https://github.com/hilvitzs/byob/blob/master/server.js#L189) just in case there isn't anything malicious in the body if someone was changing a property that was not supposed to change

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 115 / 150
