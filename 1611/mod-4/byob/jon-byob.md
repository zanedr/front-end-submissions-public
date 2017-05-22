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
[Your projects's repo URL](https://github.com/ActionJonny/BYOB)

#### Link to the Deployed Application
[Your project's production URL](https://fantasy-baseball-backend.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/ActionJonny/BYOB/commits/master)

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
[Link to code block in repo](https://github.com/ActionJonny/BYOB/blob/master/server.js#L127-L143)

* I found it very difficult removing a row with a foreign key pointing to it. The part that tripped me up the most was not realizing it was not deleting the player from the database, it was moving them after I changed the team_id to null.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/ActionJonny/BYOB/blob/master/server.js#L74-L143)

* It is weird that this block includes the code I am most proud of, but pretty bummed I wasn't able to including my JWT's in these methods.

## Testing
![test](http://recordit.co/rHQWyvcA87/gif/notify)
Attach a screenshot or paste the output from your terminal of the result of your test-suite running

## Linting

![linting](http://g.recordit.co/mBu1eMZmr7.gif)

* Not sure why I am not getting a response with no errors, but there are not linting issues.

-----

#### Please feel free to ask any other questions or make any other statements below!

* I need to get lunch before gear-up! 

-----

# Instructor Feedback [Brittany]

* [Ahhhhhhhh what is this??](https://github.com/ActionJonny/BYOB/commit/851378b05d8650b26de542ef7ff763a50d33039f). Your first commit should happen as soon as you make the repo. No commit should ever add 8k lines of code. You are very, very lucky your laptop didn't get run over by a bus before pushing up this commit.

## Feature Completion

### Endpoints
**40 points**: Developer has implemented all 10 endpoints but did not secure 4 of them with JWTs or have a custom endpoint based on query params.

* Error handling is a bit off/pretty weak with some of the endpoints. No JWTs.

### Data Persistence with SQL Database
**40 points**: The application contains at least 2 tables with a proper relationship between data sources.

## Testing and Linting

**30 points**: Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.

* You're likely getting different results for your linting errors because when you run `npm run lint`, it uses the configuration you've specified locally in your project. Running `eslint ./` will use a global installation of eslint, that might not be using the same set of rules and configurations.

* I know the blog post we shared during jetFuel suggested [this](https://github.com/ActionJonny/BYOB/blob/master/test/routes.spec.js#L15-L30) to be the way to set up these blocks, but you actually don't want to do any migration rollbacks in your tests. A rollback in this project would essentially drop your beers and breweries table. If we weren't doing a `migrate.latest` in the beforeEach block, this would have caused many of your tests to fail as the beers and breweries tables would no longer be there. Think about the fact that you always want to be testing against the most up-to-date version of your schema. For future reference, it would be best to do a single `migrate.latest()` in a `before` block, and do a `seed.run()` in a `beforeEach`. (It's fine to run seeds in multiple blocks just for extra assurance, but probably unecessary.) This should work fine:

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

* We didn't go over this in class, but in the future you could add linting to your CircleCI builds by adding the following to your `circle.yml` file (pretty common convention):

```json
test:
  override:
    - ./node_modules/.bin/mocha
    - ./node_modules/.bin/eslint
```

### JavaScript Style
**10 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Remember that any number of things can go wrong within a request to a database, and we might not always be able to anticipate the error. In cases like [this](https://github.com/ActionJonny/BYOB/blob/master/server.js#L14-L22) a 404 is a predictable error that we can use to respond with when we realize we have no results or an empty array. The `.catch()`, in that case, would have to handle literally every other thing that could have possibly gone wrong. Because we can't anticipate what went wrong, we'd want to respond with a 500 and the error message. Refactored, a proper way to handle this type of request and any errors might look like this:

```js
  database('players').select()
  .then((players) => {
    if (players.length) {
      response.status(200).json(players);
    } else {
      response.status(404);
    }
  })
  .catch((error) => {
    response.status(500).send({ error })
  });
```

* The conditional query param in [this endpoint](https://github.com/ActionJonny/BYOB/blob/master/server.js#L24-L42) is essentially the same functionality as exists in your `/api/v1/teams/:id` [endpoint](https://github.com/ActionJonny/BYOB/blob/master/server.js#L54-L62). It's not necessarily a bad thing to have multiple endpoints to retrieve the same data, but this example feels a little contrived and has created duplicate code as a result.

* This [endpoint](https://github.com/ActionJonny/BYOB/blob/master/server.js#L74-L82) is assuming that the only thing that could go wrong with the database transaction is that a user is missing data. I would move the 422 error up to the very beginning of the handler for this endpoint, before you even make a database transaction, because you already have all the data you need in order to surface this message. You have all the data that comes from the request itself, so why not check it right away before even trying to do the insertion? I'd also like to see the error message tell me exactly what fields I'm missing. If your README doesn't specify exactly what data is needed to do a POST request, you'll want to have more detailed error messages.

* You don't want to just be returning the [request.body](https://github.com/ActionJonny/BYOB/blob/master/server.js#L87) here. Even if all the data is the same (e.g. you've hardcoded IDs that you pass in yourself), you still want to send back the record from the database. More often than not, the database will be autogenerating IDs that you'll need access to later.

* Make sure you always always always use `catch` blocks after any `.thens()` that you're [using](https://github.com/ActionJonny/BYOB/blob/master/server.js#L138-L140)

## Points: 120 / 150
