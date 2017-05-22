# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/marissa27/trivia-time)

#### Link to the Deployed Application
[Your project's production URL](https://thetriviabackend.herokuapp.com/)
* Migrate still not working *

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/marissa27/trivia-time/commits/master)

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
(No)

* Setup automatic deployments with CircleCI to a production app on Heroku?
(Yes)

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/marissa27/trivia-time/blob/master/server.js#L99-L109)

* http://localhost:3000/dog?breed='Whippet&age=10
* I was proud of taking a snippet of code and being able to reverse engineer it to a working query - very exciting!

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/marissa27/trivia-time/blob/master/test/routes.spec.js#L274-L290)

* Just a bummer to get the checkAuth to work and then not be able to figure out how to test it and set that up to work. 

## Testing

([Imgur](http://i.imgur.com/003BTQx.png)

## Linting

[Imgur](http://i.imgur.com/yDKNidp.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Still having a hard time with testing and would like some extra resources for learning/practicing!

-----

# Instructor Feedback [Brittany]

## Feature Completion

### Endpoints
**50 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

* Your implementation of JWTs is slightly off -- you should not be committing your [.env](https://github.com/marissa27/trivia-time/blob/master/.env) file. The only reason [this line](https://github.com/marissa27/trivia-time/blob/master/server.js#L30) works is because you have pushed up your secret & token in the .env file. The proper way to do this would be to .gitignore the .env file, and swap out any instances of `config.CLIENT_SECRET` with `process.env.CLIENT_SECRET || config.CLIENT_SECRET`. Essentially, CircleCI and Production environments should not be able to read your config because it's generated from a hidden `.env` file. You would need to set CLIENT_SECRET at an environment variable in both CircleCI and Heroku.

### Data Persistence with SQL Database
**40 points**: The application contains at least 2 tables with a proper relationship between data sources.

## Testing and Linting

**20 points**: Project has a running test suite that covers most happy/sad paths but is missing some coverage.

* Your authorized endpoint tests aren't working because you need to give the test suite a token variable to pass in. You are trying to access [process.env.TOKEN](https://github.com/marissa27/trivia-time/blob/master/test/routes.spec.js#L239), but that is likely undefined unless you run your test script like so:

```bash
TOKEN=<yourTokenValue> ./node_modules/.bin/mocha
```

In CircleCI, when they get to the testing portion, you need to have created TOKEN as an environment variable. There is a link for documentation on this in the slack channel posted last week.

* We didn't go over this in class, but in the future you could add linting to your CircleCI builds by adding the following to your `circle.yml` file (pretty common convention):

```json
test:
  override:
    - ./node_modules/.bin/mocha
    - ./node_modules/.bin/eslint
```

### JavaScript Style
**10 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Remember that any number of things can go wrong within a request to a database, and we might not always be able to anticipate the error. In cases like [this](https://github.com/marissa27/trivia-time/blob/master/server.js#L55-L63) a 404 is a predictable error that we can use to respond with when we realize we have no results or an empty array. The `.catch()`, in that case, would have to handle literally every other thing that could have possibly gone wrong. Because we can't anticipate what went wrong, we'd want to respond with a 500 and the error message. Refactored, a proper way to handle this type of request and any errors might look like this:

```js
  database('quizzes').select()
  .then((quizzes) => {
    if (quizzes.length) {
      response.status(200).json(quizzes);
    } else {
      response.status(404);
    }
  })
  .catch((error) => {
    response.status(500).send({ error })
  });
```

* Status code [here](https://github.com/marissa27/trivia-time/blob/master/server.js#L129) should be a 500 rather than a 403 (unauthorized).

* You can shorten [this](https://github.com/marissa27/trivia-time/blob/master/server.js#L142-L149) up a bit by creating an array of required parameters and changing the error messages based on what's missing. Something like this:

```js
const queryObj = {
  question: request.body.question,
  answer: request.body.answer,
  quiz_id: request.params.quiz_id,
};

for (let requiredParameter of ['question', 'answer']) {
  if (!queryObject[requiredParameter]) {
    return response
      .status(422)
      .send({ error: `Expected format: { question: <String>, answer: <String> }. You're missing a "${requiredParameter}" property.` });
  }
}
```

* Again, [here](https://github.com/marissa27/trivia-time/blob/master/server.js#L159) we can't assume the `.catch()` block was caught because of missing data. In fact, it most likely wouldn't be caught here because you're doing all that logic right away before you even try a database transaction. So we already verified that there is no missing data. Make this error handling more generic and return a simple 500 with the error that was actually thrown. (e.g. one of the fields might have been sent in as an incorrect data type!)

* Again, [here](https://github.com/marissa27/trivia-time/blob/master/server.js#L194-L197), you're already checking authentication and returning a 403 when the request enters the `checkAuth` function, so if it made it through that entire function, we know that the authorization has succeeded and there's 0 chance that the error that's ultimately thrown here would be related to invalid credentials.

## Points: 120 / 150
