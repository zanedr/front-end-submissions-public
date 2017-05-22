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
[Diversity Tracker](https://github.com/kfarias/BYOB)

#### Link to the Deployed Application
[Your project's production URL](https://diversity-tracker.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/kfarias/BYOB/commits/master)

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
  [Still some warning but no errors](http://i.imgur.com/S4d8Lmd.png)

* Wrote tests for both happy and sad paths for each endpoint?
  No (Not all endpoint tested)

* Setup automatic deployments with CircleCI to a production app on Heroku?
  Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/kfarias/BYOB/blob/master/db/seeds/dev/people.js)

* I think this was a really cool learning experience. I was trying to seed 4 files and was having issues with them seeding at weird times so the forEach helped to condense everything and kept my seed in the right order. I am also really proud that I was able to do three migrations.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/kfarias/BYOB/blob/master/test/routes.spec.js)

* I was not super happy with my tests so I think i will make sure that all of the endpoint are tested before I feel 100%.

## Testing

[Testing](http://i.imgur.com/8G3fLn4.png)

## Linting

[Linting](http://i.imgur.com/S4d8Lmd.png)


-----

#### Please feel free to ask any other questions or make any other statements below!

I learned so much during this project. I would have liked to have more work time, but overall it was a really cool project and I feel much more comfortable using Postgres and making data tables.

-----

# Instructor Feedback [Brittany]

## Feature Completion

### Endpoints
**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

* Error handling is pretty weak, but had a total of 11 endpoints and secured them with JWTs.

### Data Persistence with SQL Database
**40 points**: The application contains at least 2 tables with a proper relationship between data sources.

* Good job getting in two tables and a relationship that made sense. I recall your `peopleInfo` and `allPeople` table days. I'm glad you were able to pull off a more practical implementation.

## Testing and Linting

**20 points**: Project has a running test suite that covers most happy and sad paths for each endpoint.

* Missing some happy/sad path endpoint testing and skipping some others, likely due to errors.

* You have an explicit error message hardcoded for [this](https://github.com/kfarias/BYOB/blob/master/test/routes.spec.js#L107) scenario in your server file. Why not check that the error message is actually what you expect it to be, rather than just testing that the response is an object?

* We didn't go over this in class, but in the future you could add linting to your CircleCI builds by adding the following to your `circle.yml` file (pretty common convention):

```json
test:
  override:
    - ./node_modules/.bin/mocha
    - ./node_modules/.bin/eslint
```

### JavaScript Style
**10 points**: Your application has some duplication and minor bugs. Error handling is weak and there are still console.logs in the codebase.

* The spacing [here](https://github.com/kfarias/BYOB/blob/master/server.js#L1-L11) is a little weird. Convention is to do all imports for 3rd-party libraries/packages line-by-line, have a single space, then do imports for anything that you wrote specifically yourself.

* I would make the error message [here](https://github.com/kfarias/BYOB/blob/master/server.js#L36) different than the one that exists [here](https://github.com/kfarias/BYOB/blob/master/server.js#L46). The first error is actually because they've passed in an invalid token. The token can be invalid for any number of reasons, let's tell them that 'hey, we got your token, but it doesnt work'.

* We want to be doing more than simply [logging](https://github.com/kfarias/BYOB/blob/master/server.js#L53-L55) our errors. Proper error handling means returning the correct status code (in this case, likely a 500), and an informative error message.

* What if there are no people in a particular [mod](https://github.com/kfarias/BYOB/blob/master/server.js#L65-L71) and the array comes back completely empty? Empty results should return a 404 or at least a message that says 'No results'

* Also remember that any number of things can go wrong within a request to a database, and we might not always be able to anticipate the error. In cases like [this](https://github.com/kfarias/BYOB/blob/master/server.js#L86-L91) a 404 is a predictable error that we can use to respond with when we realize we have no results or an empty array. The `.catch()`, in that case, would have to handle literally every other thing that could have possibly gone wrong. Because we can't anticipate what went wrong, we'd want to respond with a 500 and the error message. Refactored, a proper way to handle the errors here might look like this:

```js
  database('mods').where('id', request.params.id).select()
  .then((mods) => {
    if (mods.length) {
      response.status(200).json(mods);
    } else {
      response.status(404);
    }
  })
  .catch((error) => {
    response.status(500).send({ error })
  });
```

* [Roar](https://github.com/kfarias/BYOB/blob/master/server.js#L87)

* 204 [status codes](https://github.com/kfarias/BYOB/blob/master/server.js#L206) are usually reserved for when something was successful but you're not returning any data to the user. In this case, you are still returning some sort of json to the user. Either don't do that or change the status code.


## Points: 130 / 150