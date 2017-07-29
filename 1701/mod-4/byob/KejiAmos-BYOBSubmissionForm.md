# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/kamos1/byob)

#### Link to the Deployed Application
[Heroku](https://sensationnel-croissant-26998.herokuapp.com/)


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
Yes

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/kamos1/byob/blob/master/server/queries.js#L67-L86)

* Why were you proud of this piece of code? Had to figure out how to delete a record that had it's ID as a foreign key

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/kamos1/byob/blob/master/server/queries.js#L89-L103)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it? Would have liked to make this filtering more module

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite]([Imgur](http://i.imgur.com/7MBfedm.png))

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output]([Imgur](http://i.imgur.com/7MBfedm.png))

#### Attach a screenshot of your CircleCI build passing

[circleCI build]([Imgur](http://i.imgur.com/46OId2A.png))

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say

I feel like the data returned by some of my endpoints could have been more useful.
Here's a json web token for you to use ```eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImZvbyIsInBhc3N3b3JkIjoiYmFyIiwiaWF0IjoxNTAwMDU0MDA2LCJleHAiOjE1MDEyNjQwMDZ9.HPH9BJhuHHdyQakmlwxYcuO-wz28MulivnWz1batCwk```

-----


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **7 points** -  The README includes documentation for all available endpoints and how to use them. Instructor can easily follow the documentation for using the API.

- I wanted to see more about possible values/data types that you could send in the body of a POST and there are quotes around items like `'fullname'`, which I'm guessing is to denote the data type, but used inconsistently
- Overall, good organization of endpoints

### Feature Completion

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

* **25 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Error handling has been implemented but does not cover all possible scenarios or is unhelpful for the end-user. Linter has some errors that need fixing.

- You're doing a lot of extra work [here](https://github.com/kamos1/byob/blob/master/test/routes.spec.js#L16-L27) with the `beforeEach`. In your implementation, you are rolling back your schema, migrating, and then seeding data for every test. This is overkill since all you want to do is delete the records from your tables and reseed, not run a migration.
  - Instead, have a `before`, which only runs once before all the tests which runs the migrations, and then a `beforeEach` that clears records and reseeds the tables
- Even if you can't guarantee the order of records being returned [here](https://github.com/kamos1/byob/blob/master/test/routes.spec.js#L35-L38), which makes testing for exact content difficult, you can at least test the _structure_ of the data, like properties of the objects. You've done this in some tests, but inconsistently.
- [This](https://github.com/kamos1/byob/blob/master/test/routes.spec.js#L58) is not super realistic, someone would put an ID integer that doesn't exist in the DB, not a random string
- Looking for testing more content of the response [here](https://github.com/kamos1/byob/blob/master/test/routes.spec.js#L109)
- Be more descriptive in your [test titles](https://github.com/kamos1/byob/blob/master/test/routes.spec.js#L356) - it should not delete something, but why? For what case?

### JavaScript Style

* **30 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- Project Name: BYOD?
- Throw your JSON data files into their own directory just to clean up your file tree
- Why the crazy [indentation](https://github.com/kamos1/byob/blob/master/db/migrations/20170709084726_initial.js#L1-L21)?
- Good use of the router to extract API routes [here](https://github.com/kamos1/byob/blob/master/server/server.js#L17), you can additionally prefix all of the routes with `/api/v1` like: `app.use('/api/v1', routes);` to give every route in `routes` that route "prefix"
- I like the intent of separating [routes and queries](https://github.com/kamos1/byob/tree/master/server), it's a great refactor, but [these](https://github.com/kamos1/byob/blob/master/server/queries.js) are more than just database queries - they also include the server response
  - You can separate queries only, for instance like having a queries file with a function called `getAllJobs` that has `database('jobs').select()` in that function
- In most of your [routes](https://github.com/kamos1/byob/blob/master/server/endpoints.js), you end the URL with a `/`, which is not typical. For authenticate, you leave it out, which is what you want to do normally
- Since you have not enforced uniqueness of jobs or employees, be careful with only expecting [one record to be returned](https://github.com/kamos1/byob/blob/master/server/queries.js#L164), there could be multiple records deleted
- Good sequence [here](https://github.com/kamos1/byob/blob/master/server/queries.js#L96-L99) using the foreign key

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 122 / 150
