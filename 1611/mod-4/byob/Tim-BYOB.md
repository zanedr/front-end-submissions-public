# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[BYOB Mountains](https://github.com/tbrandle/mountains_backend_BYOB)

#### Link to the Deployed Application

[BYOB Mountains](https://mountains-api.herokuapp.com/)

Still having issues with this. It passes circleCI, but when you go to the heroku site, you get an error for all of the routes.

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/tbrandle/mountains_backend/commits/master)
This is pointing to a different repo. I had to remake a repo for the one on heroku due to some mistakes I made in the beginning. The old repo has all my commits.

## Completion

#### Were you able to complete the base functionality?

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
[Link to code block in repo](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/db/seeds/dev/mountains.js#L19)

* Why were you proud of this piece of code?

The file seeding took forever to solve, but I think this solution is a clever one. I paired with Brittany to solve it, but walking away, I feel I have a much better understanding of how knex works with promises.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L142)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Inside the post mountains end point, I was trying to verify if the range existed in the database.  If it did, send back the id and post the mountain with the foreign id. This part works fine. If the mountain range doesn't exist, I was trying to create the new range, send back the id, then create the new mountain.

For some reason I couldn't get it to work.  I have a feeling it was async issues or just being too nested. Either way, to solve the problem, I simply threw an error.

## Testing

Attach a screenshot or paste the output from your terminal of the result of your test-suite running
[Passing tests](http://recordit.co/3vTFH4bn4B)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running
[Linting image](http://recordit.co/IBJ5kD5fyE)



-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

The only issue with the app currently is that I can't actualy get data back in the deloped heroku URL. Everything is passing, so I'm not sure what is going on there.

-----

# Instructor Feedback [Brittany]

## Feature Completion

### Endpoints
**60 points**: Developer has implemented 11 of 10 endpoints and secured 4 of them with JWTs or have a custom endpoint based on query params.

* Error handling is a bit off, but a solid effort nonetheless.

### Data Persistence with SQL Database
**40 points**: The application contains at least 2 tables with a proper relationship between data sources.

## Testing and Linting

**20 points**: Project has a running test suite that covers most happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.

* Missing some tests for patch and delete endpoints.

* Nice job [testing your helpers](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/test/routes.spec.js#L24-L32)

* The [migrate.latest](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/test/routes.spec.js#L39) can be moved to a `before` block so that it's just done once instead of before every single test. E.g.:

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

* One of [these](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/.eslintrc.js) two [files](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/.eslintrc.json) is unecessary.

* We didn't go over this in class, but in the future you could add linting to your CircleCI builds by adding the following to your `circle.yml` file (pretty common convention):

```json
test:
  override:
    - ./node_modules/.bin/mocha
    - ./node_modules/.bin/eslint
```

* [Roar](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/test/routes.spec.js#L131)

### JavaScript Style
**12 points**: Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

* A better [conditional](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L18-L20) here would check for `process.env.CLIENT_SECRET` rather than checking if the environment is `development`. This would help you recognize if you were getting errors because you forgot to specify an environment variable in CircleCI or Heroku. e.g. I would refactor to something like this:

```js
let CLIENT_SECRET = process.env.CLIENT_SECRET || config.CLIENT_SECRET
// same thing for username and password


if (!CLIENT_SECRET) {
  throw { error: 'Make sure you have a CLIENT_SECRET, USERNAME and PASSWORD' }
}
```

* [403](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L52) is the wrong status code here. That's reserved for authentication errors. A 422 would be better for missing data.

* [422](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L60-L62) is the wrong status code here. That should be reserved for any type of user error from the client-side/with the request. The `.catch()` blocks here are actually going to catch any problems that occur as a result of the database transaction. Because these types of errors are unpredictable, we can only return a 500 status code (internal server error) and send back whatever error message we actually received.

* Probably don't want this [generic endpoint](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L66-L73) for returning all mountains. You could return plain text here, or better yet a README file that documents all the data endpoints that you **can** hit. It also creates [duplicate code](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L85-L90).

* Remember that any number of things can go wrong within a request to a database, and we might not always be able to anticipate the error. In cases like [this](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L112-L119) a 404 is a predictable error that we can use to respond with when we realize we have no results or an empty array. e.g. what if a mountain range with that ID didn't exist and no results came back from your select query? The `.catch()`, in that case, would have to handle literally every other thing that could have possibly gone wrong. Because we can't anticipate what went wrong, we'd want to respond with a 500 and the error message. Refactored, a proper way to handle this type of request and any errors might look like this:

```js
  database('mountains').where('range_id', req.params.id).select()
  .then((mountains) => {
    if (mountains.length) {
      response.status(200).json(mountains);
    } else {
      response.status(404);
    }
  })
  .catch((error) => {
    response.status(500).send({ error })
  });
```

* You shouldn't need this [authentication](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L121-L140) endpoint. If you're not using it, take it out. If you are, you shouldn't be. I would just generate the token once on your server and save it in your `.env` file for reference.

* [mountain.mountain](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L144) is confusing, as is [range.range](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L163). I would try to rename these.

* Instead of throwing [here](https://github.com/tbrandle/mountains_backend_BYOB/blob/master/server.js#L150) this is a perfect opportunity to respond with a 422 and a helpful error message.

## Points: 132 / 150

