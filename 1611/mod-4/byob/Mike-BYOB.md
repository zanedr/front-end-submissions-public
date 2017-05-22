# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[Beers&Brewery-BYOB](https://github.com/Mickyfen17/build-your-own-backend)

#### Link to the Deployed Application
[Heroku deployed BYOB](https://byod-beers.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

[BYOB-Commits](https://github.com/Mickyfen17/build-your-own-backend/commits/master)

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
(Yes)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/Mickyfen17/build-your-own-backend/blob/master/server/index.js)

* Why were you proud of this piece of code?

Clean server index file utilizing app use and requiring individual routes from else where in the server folder.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/Mickyfen17/build-your-own-backend/blob/master/server/beers.js#L11)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Main GET request for /beers which also handles multiple query params.
It gets the job done but the nested if/else's can be hard to follow.

## Testing

![](http://i.imgur.com/L79duMy.png)

## Linting

![](http://i.imgur.com/9xmNZXA.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Cool project and quite enjoyed the time spent in the terminal and with Postman. TDD was in full flow for this one.

##### Note on foreign ID's

The csv files that I decided to use already had ID's which linked to each other. When seeding I found the the ID's weren't being added to the correct row.
I decided to to create a new ID for each table which ended up linking to the correct foreign tables.
This is why in the POST requests I have to find the max value of a column and add a +=1 to pretty much auto increment the ID.
Primary key still auto increments is expected.

-----

# Instructor Feedback [Brittany]

## Feature Completion

### Endpoints
**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

### Data Persistence with SQL Database
**40 points**: The application contains at least 2 tables with a proper relationship between data sources.

## Testing and Linting

**30 points**: Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.

* I'm a bit surprised that your beforeEach/afterEach [blocks](https://github.com/Mickyfen17/build-your-own-backend/blob/master/test/routes.spec.js#L13-L27) aren't causing intermittent failures. I know the blog post we shared during jetFuel suggested this to be the way to set up these blocks, but you actually don't want to do any migration rollbacks in your tests. A rollback in this project would essentially drop your beers and breweries table. If we weren't doing a `migrate.latest` in the beforeEach block, this would have caused many of your tests to fail as the beers and breweries tables would no longer be there. Think about the fact that you always want to be testing against the most up-to-date version of your schema. For future reference, it would be best to do a single `migrate.latest()` in a `before` block, and do a `seed.run()` in a `beforeEach`. (It's fine to run seeds in multiple blocks just for extra assurance, but probably unecessary.) This should work fine:

```js
before((done) => {
  database.migrate.latest()
    .then(() => {
      done();
    })
});

beforeEach((done) => {
  database.seed.run()
    .then(() => {
      done();
    })
});
```

* You did a great job thoroughly testing every happy and sad path for each endpoint, though some of your 404 tests are a little redundant. For example, [this](https://github.com/Mickyfen17/build-your-own-backend/blob/master/test/routes.spec.js#L71-L81) test is essentially asserting the same thing as [this](https://github.com/Mickyfen17/build-your-own-backend/blob/master/test/routes.spec.js#L44-L54) test. You're simply asserting that if an incorrect URL is entered, you return a 404 error. They don't really differ between tables as your `it` statement might suggest. The 404s like [this](https://github.com/Mickyfen17/build-your-own-backend/blob/master/test/routes.spec.js#L96-L106) and [this](https://github.com/Mickyfen17/build-your-own-backend/blob/master/test/routes.spec.js#L121-L131) are still good to test because we know it's technically a correct api endpoint path, there's just nothing returned from the database. So these endpoints have different logic than ones that simply do not match any endpoints at all.

* We didn't go over this in class, but in the future you could add linting to your CircleCI builds by adding the following to your `circle.yml` file (pretty common convention):

```json
test:
  override:
    - ./node_modules/.bin/mocha
    - ./node_modules/.bin/eslint
```

### JavaScript Style
**15 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Nice organization and breaking out of routes and endpoints/configuration. Solid file structure.

* So we talked a bit about why APIs are usually prefixed with something like `/api/v1` (to version our API based on any breaking changes introduced by new migrations). Your implementation of using `api/v1` and `api/v2` is a little contrived. (Perhaps you were just doing it for practice.) But really we'd want all endpoints to start at `api/v1` (beers and breweries included, even though those tables came in a secondary migration). Then, when we make a migration that creates a "breaking" or "backwards-incompatible" change, that's when we start upping the version in our endpoints. e.g. if we wanted to delete the city/state/code/country columns from the breweries table and replace them with latitude and longitude columns instead, we would create `api/v2` endpoints that worked with these new values, and slowly decommission the `api/v1` endpoints that we no longer want to support. [This](http://stackoverflow.com/questions/26040329/how-do-you-handle-api-version-in-a-node-express-app) stackoverflow thread has a solid explainer of versioning APIs in node/express applications.

* The [GET request](https://github.com/Mickyfen17/build-your-own-backend/blob/master/server/beers.js#L11-L54) for beers is a little gnarly. Also, as written, it seems like it would prioritize selecting by category over selecting by style? What if we had specified both? e.g. `/api/v1/beers?category=foo&style=bar`. Would it stop as soon as it saw category and not filter by both category & style? (Conventionally, you should be able to add as many query params as you'd like to filter by.) I'd break this logic out a bit and try to "build up" a single `where` condition that filters based on any and all query params you've passed through.

* There is some duplicated code that could likely be broken out into helpers. Look how similar [this](https://github.com/Mickyfen17/build-your-own-backend/blob/master/server/breweries.js#L52-L56) is to [this](https://github.com/Mickyfen17/build-your-own-backend/blob/master/server/beers.js#L72-L76). You could likely make a helper function that takes in the list of required parameters and does the check against them. This way we could also be more specific with exactly what fields were missing from the POST requests.


## Points: 145 / 150

Awesome job! Keep it up.