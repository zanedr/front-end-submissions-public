# Franklin Crosby BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

# Basics

#### Link to the Github Repository for the Project
[project repo](https://github.com/Obleo33/byob.git)

#### Link to the Deployed Application
[production URL](https://fcbyob.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/Obleo33/byob/commits/master)

## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
(Yes)

* Had at least 10 endpoints that returned responses with appropriate status codes?
(Yes)

* Secured at least 4 endpoints with JWTs?
(No)

* Enforced a linter and wrote code that conformed to it?
(Yes)

* Wrote tests for both happy and sad paths for each endpoint?
(Yes)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Happy Code](https://github.com/Obleo33/byob/blob/master/csv_converter.js#L1-L18)

* Why were you proud of this piece of code?

I really like how this works. It opened my understanding of how the different files work together. 

#### Link to a specific block of your code on Github that you feel not great about
[Challenging Code](https://github.com/Obleo33/byob/blob/master/csv_converter.js#L1-L18)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

This code feels pretty hackey. I particularly don't like the nested ifs. The main challenge was checking for 3 different scenarios. 

## Testing

![](http://i.imgur.com/TcCVSdz.png)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running

![](eslint-config-airbnb-base)

-----

#### Please feel free to ask any other questions or make any other statements below!

This project was a major struggle for me. I think the main source of my trouble was that it shined a light on all the gaps in my knowledge. I plan to continue to work toward completion as well as rebuilding for my mod 3 personal site.

-----

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **40 points** - Developer has implemented all 10 endpoints but did not secure 4 of them with JWTs or have a custom endpoint based on query params.

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

* I can't see any data on production, but from your migration, seed files, and tests looks like you are able to get some data in and persisting
* Great use of a joins table [here](https://github.com/Obleo33/byob/blob/master/db/migrations/20170516144611_initial.js#L36-L43) to keep your data normalized with a many-to-many relationship
* Good job including `table.timestamps(true, true);` to your tables, you will often want created-at/updated-at in case you want to sort by these
* It was interesting that you pointed out [separate seed files](https://github.com/Obleo33/byob/tree/master/db/seeds/test) need are loaded alphabetically - good job working with that

### Testing & Linting

* **28 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with some errors.

* The linting image you submitted in this form is not working - show show me the linting, and I will adjust the points
* [This line](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L4) is redundant since you can just get the environment from you environment variable you declared at the top
* This [migration](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L18) is good to do, but just do it once before all of the tests (in a `before` block) instead of before every test - the seed, however, should be before every test like you have it
* It's a good idea to test the type of response in [each test](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L40-L46) too - to test if you expect `html` or `json`
* Since [this route](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L92) is for retrieving a single resource, then you typically do not send the resource within an array, but just send the single object as JSON
* Why the deletion of the user in [this test](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L166-L170)? Your `beforeEach` should delete and re-seed the users for each test
* Ideally, in addition to testing for the [response code](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L203), there would be some text that the user would see to knwo that the email cannot change
* Nice sad path test [here](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L332-L342)
* I'm curious about why you're doing [this](https://github.com/Obleo33/byob/blob/master/test/routes.spec.js#L357-L366)

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* When you have a lot of routes in the server file, it's a good idea to break the routes out into other files know as `routers`. Take a look at the [Express documentation](https://expressjs.com/en/api.html#router) to see how they work.
* Be sure to have a `catch()` for all promises in case they fail like [here](https://github.com/Obleo33/byob/blob/master/server.js#L93) - you did a pretty good job using them everywhere else
* Why [create a variable](https://github.com/Obleo33/byob/blob/master/server.js#L101-L105) if you're not going to use it elsewhere?
* If for some reason there was an error for [this catch](https://github.com/Obleo33/byob/blob/master/server.js#L113), it would most likely be an internal server error (code 500), and not anything to do with something not found in the database or it couldn't update (you should get an empty array back). Good job with `catch()` errors like [these](https://github.com/Obleo33/byob/blob/master/server.js#L158) though
* Are you using [this chunk](https://github.com/Obleo33/byob/blob/master/server.js#L195-L201) still?

- Points: 123 / 150