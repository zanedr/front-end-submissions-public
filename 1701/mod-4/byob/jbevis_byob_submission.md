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


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **5 points** -  The README documentation is out-of-date or inaccurate in some places. Instructor can not successfully use every endpoint based on following the documentation.

- I wanted to see more about possible values that you could send in the body for say earthquake `DEPTH` (what units is the depth in)
- Would like to see one helpful part of API documentation which is showing sample output from an API call

### Feature Completion

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

* **30 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Error handling has been implemented but does not cover all possible scenarios or is unhelpful for the end-user. Linter has some errors that need fixing.

- Stick to the convention of naming your test environment `test` instead of [testing](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L2)
- You're doing a lot of extra work [here](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L39-L50) with the `beforeEach`. In your implementation, you are rolling back your schema, migrating, and then seeding data for every test. This is overkill since all you want to do is delete the records from your tables and reseed, not run a migration.
  - Instead, have a `before`, which only runs once before all the tests which runs the migrations, and then a `beforeEach` that clears records and reseeds the tables
- [This](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L58) is good so you can actually test content
- [Good](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L155) sad path here
- I would expect [this response](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L397) to be related to the `badDepth`, but the error talks about not being authorized
- Good sad-path test [here](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L459)
- Why do you need [this](https://github.com/jbevis/build-your-own-backend/blob/master/server.js#L330-L333)?

### JavaScript Style

* **20 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- For the earthquakes, you want to keep the auto incrementing primary key, and then if you have another ID associated with an earthquake, use another column
- [This route](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L195) is not nested in a RESTful way
  - It should be something like `'/api/v1/region/5/earthquakes'`or `/api/v1/earthquakes?region=5` using a query param
- Same idea with [this route's](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L211) nesting
  - You have the query param structure right, but you don't need the additional `filterMag` in the URL (`/api/v1/earthquakes/filterMag?magLow=4.5&magHi=8.0`) - you can just use `/api/v1/earthquakes?magLow=4.5&magHi=8.0`
- I see most endpoints for POST and PUT/PATCH using non-RESTful formats like described above
- [This endpoint](https://github.com/jbevis/build-your-own-backend/blob/master/test/routes.spec.js#L466) lists the region ID in reverse order. Instead of `/api/v1/:id/regions`, it should be `/api/v1/regions/:id`.
- You're not serving any static files, so you don't need this [line](https://github.com/jbevis/build-your-own-backend/blob/master/server.js#L11) other than for your `/` route, which is not needed for this project
- Were you having CORS issues? I doubt you need [this](https://github.com/jbevis/build-your-own-backend/blob/master/server.js#L14) either?
- [Here](https://github.com/jbevis/build-your-own-backend/blob/master/server.js#L292-L328) you are sending two sets of responses, which will probably not happen successfully because the connection to the client will close after the first response is successful (this is why you're seeing the errors in your test suite)

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 115 / 150
