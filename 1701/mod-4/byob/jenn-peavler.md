# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/jennPeavler/build-your-own-backend)

#### Link to the Deployed Application
[Heroku](https://build-a-backend-jenn-peavler.herokuapp.com/api/v1/countries)


## Completion

#### Were you able to complete the base functionality?

* Documented all available endpoints and their usage in the README?
Yes.  I was able to write the functionality to hit all required endpoints and they are documented in the README.

* Seeded a database with at least 2 tables and 1 relationship?
Yes.  I seeded a table that has a list of countries.  The another table was seeded with a list of malnutrition data points.
Each data point in the second table is related to/refers to a country entry.  Each country entry may be associated with one or
several malnutrition data points.  So the tables are a one to many relationship.  One country to many malnutrition data points.

* Had at least 10 endpoints that returned responses with appropriate status codes?
Yes.  10 endpoints were implemented and return appropriate status codes.

* Secured at least 4 endpoints with JWTs?
Yes.  All of my POST/PATCH/DELETE requests are secured with a JWT.  That is 6 endpoints.

* Enforced a linter and wrote code that conformed to it?
Yes, I enforced a linter and a pre-commit git hook to that linter as one of the first steps in the project.

* Wrote tests for both happy and sad paths for each endpoint?
Yes.  Happy and sad path tests are written for each endpoint as well as some other functionality tests.

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes, automatic deployments with CircleCI to a production app on Heroku are implemented.  I am still having the odd occurence happen
where my CircleCI branch succeeds, but when I push that branch to github and merge that to master, the master branch fails.
We discussed this in class and over slack.  Solution is pending.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code]('https://github.com/jennPeavler/build-your-own-backend/blob/master/Server/getRequests.js#L5-L23')

* Why were you proud of this piece of code?
I like that I combined the to GET endpoints for all of one resource (i.e. ‘/api/v1/merchants’) into one modular file.  This
will allow me to easily add enpoints in the future.  Within this block of code, I could further enhance by making the filter
variable dynamic so that iso_code is not hardcoded.

#### Link to a specific block of your code on Github that you feel not great about
[sad code]('https://github.com/jennPeavler/build-your-own-backend/blob/master/Server/patchRequests.js#L38-L103')

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
While this code is functional, the if, else if, else block of code is very long.  I will be happier about it when I go back
to refactor it.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://i.imgur.com/pqRqGz8.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter git hook](http://i.imgur.com/YnXXuGp.png)
[linter running in atom](http://i.imgur.com/kc0LwNJ.png)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](http://i.imgur.com/vNUaetl.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say

Thank you.  I really enjoyed this project!  I look forward to putting a forward face on it!  The remaining question is just
the one that I discussed earlier about my circleCI branch passing in circleCI however when it is pushed to GH and merged
to master, master branch is failing in circleCI with the error message that I slacked to you.  Thanks!


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **7 points** -  The README includes documentation for all available endpoints and how to use them. Instructor can easily follow the documentation for using the API.

- Use some markdown formatting to help styling of formatted code or bulleted lists because there are big blocks of text that can be difficult to read
- Would like to see one helpful part of API documentation which is showing sample output from an API call

### Feature Completion

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

* **30 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. Error handling is informative and helpful for the end-user. The project has a linting configuration that passes with no errors.

- [This](https://github.com/jennPeavler/build-your-own-backend/blob/master/tests/routes.spec.js#L13-L19) is interesting, I like the idea of it, but you are calling the function every time you want to check contents of the array. One other way you could do this is sort the array by the ID value, then you know the order that the elements should be in
- Don't forget to check for the type of response, in [this case](https://github.com/jennPeavler/build-your-own-backend/blob/master/tests/routes.spec.js#L38) JSON
- [For this case](https://github.com/jennPeavler/build-your-own-backend/blob/master/tests/routes.spec.js#L131), we might have said you should respond with a 404 if a table is empty, but you should just return a successful response with an empty array
- [Name your tests](https://github.com/jennPeavler/build-your-own-backend/blob/master/tests/routes.spec.js#L153) with the API route, not the function name since the function name could change and it could be only one part of that endpoint
- Watch spelling in test file ("insesnsitive" and "enpoint")
- You should not be sending the [primary key in a POST](https://github.com/jennPeavler/build-your-own-backend/blob/master/tests/routes.spec.js#L341) - the primary key value should be left up to the database to decide
  - The place where you can hard code primary keys is your test seed file, but that is it - any subsequent requests made to the test database should be up to the DB to determine the primary key
- Overall, good happy and sad path test coverage

### JavaScript Style

* **30 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- Using the country name as [the foreign key](https://github.com/jennPeavler/build-your-own-backend/blob/master/db/migrations/20170708090528_initial.js#L14-L15) can be dangerous because what happens if the country name changes? You would have to find all instances of that country and change them in the DB. Usually, you will always use the primary key ID as the foreign key in another table.
- Great job refactoring your server file and putting routes into a router file, I can see the VERB-related files getting large and confusing to read in a large application, but this is a good attempt at organization
- One place where you refactored that could be weird with more endpoints is the `getOneResource`, the `iso_code` query parameter is very specific to certain endpoints, and the `getOneResource` could be used for many endpoints
- The nesting of your resources is  little backwards. For instance `/api/v1/countries/malnutrition_data/:name` gets the malnutrition data for a given country with a name specified
  - What you want to do is nest the resources like: `/api/v1/countries/:name/malnutrition_data`, the `:name` in this route is known as a "slug" since it's not using the primary key ID, and then for that specific country, we get the malnutrition data
- For the route `/malnutrition_data/:country_name/:year`, this works but is not a common practice at all. Usually, you will submit a POST to `/malnutrition_data` with the country_name and year in the body of the request
- Careful with overriding variables after you have changed the data, [like here](https://github.com/jennPeavler/build-your-own-backend/blob/master/Server/postRequests.js#L12-L13), debugging this can be difficult because the state of the variable is changing
- [These multi-line ternaries](https://github.com/jennPeavler/build-your-own-backend/blob/master/Server/postRequests.js#L16-L17) are notoriously hard to read for other developers and yourself down the line, get away from them after they extend beyond one line. After one line, readability drops drastically.
- Be sure to include `catch` on [promises](https://github.com/jennPeavler/build-your-own-backend/blob/master/Server/patchRequests.js#L81) to be able to handle the error

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 127 / 150
