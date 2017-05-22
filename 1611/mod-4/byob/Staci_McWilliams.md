# BYOB Submission Form
[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.htm)

# Basics

#### Link to the Github Repo for the Project
[Your projects repo URL](https://github.com/stacimcwilliams/build_your_own_backend)

#### Link to the Deployed Application
[Project Production URL](https://go-global-byob.herokuapp.com/)

#### Link to your commits in the github repo for the project
[Staci McWilliams commits](https://github.com/stacimcwilliams/build_your_own_backend/commits/master)

## Completion

* Were you able to complete the base functionality? Yes but would like to write more tests for this project.

* Seeded a database with at least 2 tables and 1 relationship? (Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes? (Yes)

* Secured at least 4 endpoints with JWTs? (Yes)

* Enforced a linter and wrote code that conformed to it? (Yes)

* Wrote tests for both happy and sad paths for each endpoint? (Some)

* Setup automatic deployments with CircleCI to a production app on Heroku? (Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/stacimcwilliams/build_your_own_backend/blob/24aab76e0ce6686bca5656ff71e29db100bb6042/server.js#L172-L183)

* Why were you proud of this piece of code?

I have never completed a patch request before and I was stoked to get this working and implemented in this project.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/stacimcwilliams/build_your_own_backend/blob/24aab76e0ce6686bca5656ff71e29db100bb6042/server.js#L121-L154)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Would like to refactor and dry up this code but did not have the time to do that.

## Testing

![Attach a screenshot or paste the output from your terminal of the result of your test-suite running](http://g.recordit.co/ZUJ5JKM1ib.gif)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running

![Screenshot of terminal output for linting](http://i.imgur.com/0BwJXaB.png)

Please feel free to ask any other questions or make any other statements below!

Thank you for all the help this and understanding my insane allergic reaction on Wednesday night! I feel like I got experience with all the things I didn't work on alone on the last project and it was really beneficial.

Anything else you wanna say!

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

* Great job on this section

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

* That `.DS_Store`...make sure you don't commit [these](https://github.com/stacimcwilliams/build_your_own_backend/tree/master/db)
* In the [migration file](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/db/migrations/20170516085603_initial.js), the `table.timestamps();` can take the arguments `table.timestamps(true, true);` so that when our data is inserted, it will fill in the created-at and updated-at columns for you - see [the docs](http://knexjs.org/#Schema-timestamps)
* Good use of a foreign in your locations table

### Testing & Linting

* **25 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.

* Don't forget to test the status code for each response - missing it [here](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/tests/routes.spec.js#L72) and some others
* Good job with the [status code](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/tests/routes.spec.js#L107)!
* Would like to see a sad path with [this route](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/tests/routes.spec.js#L132-L148) where you pass in an integer that is "parsable" for an ID that doesn't exist in the database - so some sad paths missing for these situations

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Why bring in `cors` [here](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L3)? Are you using it?
* When you have a lot of routes in the server file, it's a good idea to break the routes out into other files know as `routers`. Take a look at the [Express documentation](https://expressjs.com/en/api.html#router) to see how they work.
* If an ID is requested [here](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L52-L58), such as `12567`, that is not in the database, the 404 will not be hit because the database will not error out - instead, then database query will come back with an empty array. So you'll have to test if the query comes back with an empty array. If so, send a 404, if there is an actual error, it will be a server error for which you would respond with a 500 status code. Same [here](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L76) too.
* Watch out for [extra spaces](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L91) or [no spaces](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L64-L65) for consistency
* For [this](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L155) and [this](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L170) route, you wouldn't want to add `replace` or `edit` to the URL. For instance, you would only need a PATCH to `/api/v1/organizations/:id`, and your server knows you are sending a PATCH request for this particular organization resource.
* Would be nice to bring [`checkAuth`](https://github.com/stacimcwilliams/build_your_own_backend/blob/master/server.js#L27) outside of the server file into some kind of helper


To get a 3 on this project, you need to score 110 points or higher.

- Points: 140 / 150