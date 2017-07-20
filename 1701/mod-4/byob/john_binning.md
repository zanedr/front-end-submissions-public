# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/JohnBinning/BYOB)

#### Link to the Deployed Application
[Heroku](https://byobaseball.herokuapp.com/)


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
[happy code](https://github.com/JohnBinning/BYOB/blob/master/test/routes.spec.js#L455-L472)

* Why were you proud of this piece of code?

I feel that this is a good test.  I test to make sure we get the correct status code on delete, and then further validate that the response code was accurately returned by making sure we have on less person in the db than we previously did.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/JohnBinning/BYOB/blob/master/server/server.js#L180-L185)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I wanted to send back the name the deleted franchise, but had difficulty figuring out how.  I feel like it would be nice to have better confirmation that we deleted the correct franchise.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](https://i.imgur.com/GM3CY51.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](https://i.imgur.com/tZ3hx3a.png)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](https://i.imgur.com/uZnUnU1.png)

-----

#### Please feel free to ask any other questions or make any other statements below!


-----


# Instructor Feedback (Instructor Name)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**10 points**: The README includes documentation for all available endpoints and how to use them. Instructor can easily follow the documentation for using the API.

* Under "put", for updating franchises, you mention "Only put the data fields you would like to update, not all fields will be necessary for every put request". This is actually slightly unrestful, as a put should generally require all fields to be passed in for a complete update. If you want to allow partial updates, use a patch instead.

### Feature Completion

**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

**35 points**: Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. Error handling is informative and helpful for the end-user. The project has a linting configuration that passes with no errors.

* [Eep](https://github.com/JohnBinning/BYOB/blob/master/test/routes.spec.js#L18). Instead of hardcoding your JWT here, you can set it as an environment variable in CircleCI like [this](https://circleci.com/docs/1.0/environment-variables/#setting-environment-variables-for-all-commands-without-adding-them-to-git) So you would do a check for `process.env.AUTH_TOKEN` but then fall back to whatever is in your `.env` file for local development with `process.env.AUTH_TOKEN || config.AUTH_TOKEN`. Not something to legitimately worry about in this project, but just for future reference.

* [These two tests](https://github.com/JohnBinning/BYOB/blob/master/test/routes.spec.js#L39-L56) are essentially asserting the same thing...that a route that doesn't exist will 404. The heirarchy of the URL doesn't necessarily matter in this case.

* I know we discussed this, but you could put a high-level describe block to handle the [before/beforeEach](https://github.com/JohnBinning/BYOB/blob/master/test/routes.spec.js#L60-L75) blocks so that you don't have to repeat yourself so frequently. It doesn't hurt anything to have multiple of these block statements, but they aren't really giving you much. (Once the database is migrated once, it's already at the latest, so at the very least, you could take out the repeat calls to migrate).

* Error handling [here](https://github.com/JohnBinning/BYOB/blob/master/server/server.js#L150) could be a little more robust. What exactly went wrong with the edit? What did the user pass in with the request? Were all the property names accurate? Were all the data types for their values appropriate?

* No points off for this, but in the future run your linter in the terminal rather than using it as a plugin in your text editor. It's a pain in the ass to get yelled at while you're coding because of a linter and it's nicer and easier to see the overall output in the terminal rather than line-by-line indicators in the text editor.

### JavaScript Style

**25 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* You don't actually need [this](https://github.com/JohnBinning/BYOB/blob/master/server/server.js#L26-L45) endpoint. I would have just signed a token right away anywhere in your server file, `console.logged` it, and held onto that value for the remainder of the project.

* Your URLs are a litttttleeeee too specific in places like [here](https://github.com/JohnBinning/BYOB/blob/master/server/server.js#L109) and [here](https://github.com/JohnBinning/BYOB/blob/master/server/server.js#L125). Remember the `/` separators in URLs most often denote some sort of heirarchal structure of data. `name` and `id` aren't nested resources, but rather properties on the resource type you're already querying. These get requests are also doing very similar things - almost all of the code is repeated except for the name of the property you're filtering by. This is a scenario where you could instead make use of query params and make a custom URL like `/api/v1/franchises?name=Foo` and `/api/v1/franchises?id=12`. Then you can do a check for:

* are there any query params? 
* if so, take each of them and filter the request by the query name (stored in a variable like `filterName` so that it can be dynamic)

**Knex syntax for chaining where [conditions](http://knexjs.org/#Builder-whereIn)**

* You can overload a url like `/api/v1/pitcher_data/:id` with GET, PUT, PATCH and DELETE without having to get more specific than that. e.g. you have `api/v1/pitcher_data/delete/:id` but putting that http method in the URL isn't standard convention.

* Let's make sure we delete directories that we're not using. Like [old](https://github.com/JohnBinning/BYOB/tree/master/db/seeds).

* Nice job seeding your data with multiple files, not easy to get that right.

* What's [this](https://github.com/JohnBinning/BYOB/blob/master/check.js)? Any utils/scraping/reference code can be saved under a directory called something like `scraping` or `data-utils`. If it's just a stray file, I'd put it in a gist and leave a link to it somewhere in your repo so you can go back to it if you ever need.


## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 130 / 150