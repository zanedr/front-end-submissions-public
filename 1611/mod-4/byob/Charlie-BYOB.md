# Charlie Dunn - BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/dunncl15/BYOB)

#### Link to the Deployed Application
[Your project's production URL](https://byob-prod.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/dunncl15/BYOB/commits/master)

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
[Link to code block in repo](https://github.com/dunncl15/BYOB/blob/master/server.js#L48-L63)

* Why were you proud of this piece of code?
I thought using .some was a good way to approach validating that a PATCH request has at least one of the required park properties. If someone tries a PATCH with an arbitrary property that is not listed in parkProps then it will throw an error.

However, it still fails when you submit a PATCH with multiple properties and at least one property is included in the parkProps array. Ex/

{ name: 'New Park',
  mumbo_jumbo: 'adfadf' }

This error isn't caught because the .some recognizes the name property so the condition is met.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/dunncl15/BYOB/blob/master/db/seeds/dev/locations.js#L21-L28)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

Promises are still a bit confusing to me. I have a hard time following when a Promise is resolved and this particular code block is confusing from that stand point.

## Testing

Attach a screenshot or paste the output from your terminal of the result of your test-suite running
![](http://i.imgur.com/wbLfUQ0.png)

## Linting

Attach a screenshot or paste the output from your terminal of the result of your linter running
![](http://i.imgur.com/PnnHnBt.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Thanks for your help this week!

-----


# Instructor Feedback [Brittany]

* Thank you for having a README with your available endpoints.

## Feature Completion

### Endpoints
**60 points**: Developer has implemented 11 of 10 endpoints and secured 4 of them with JWTs or have a custom endpoint based on query params.

* Error handling is a bit off, but a solid effort nonetheless.

### Data Persistence with SQL Database
**40 points**: The application contains at least 2 tables with a proper relationship between data sources.

## Testing and Linting

**25 points**: Project has a running test suite that covers happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with few errors.

* Nice [before blocks](https://github.com/dunncl15/BYOB/blob/master/test/routes.spec.js#L14-L22)

* We didn't go over this in class, but in the future you could add linting to your CircleCI builds by adding the following to your `circle.yml` file (pretty common convention):

```json
test:
  override:
    - ./node_modules/.bin/mocha
    - ./node_modules/.bin/eslint
```
* The few remaining errors in your linter could be quickly and easily cleaned up to get the entire thing passing.

### JavaScript Style
**15 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* A better [conditional](https://github.com/dunncl15/BYOB/blob/master/server.js#L17-L19) here would check for `process.env.CLIENT_SECRET` rather than checking if the environment is `development`. This would help you recognize if you were getting errors because you forgot to specify an environment variable in CircleCI or Heroku. e.g. I would refactor to something like this:

```js
let CLIENT_SECRET = process.env.CLIENT_SECRET || config.CLIENT_SECRET
// same thing for username and password


if (!CLIENT_SECRET) {
  throw { error: 'Make sure you have a CLIENT_SECRET, USERNAME and PASSWORD' }
}
```

* You could return plain text [here](https://github.com/dunncl15/BYOB/blob/master/server.js#L24), or better yet your README file that documents all the data endpoints that you **can** hit.

* [Nice error handling here](https://github.com/dunncl15/BYOB/blob/master/server.js#L38-L45)

* You don't have to send back the park deleted message [here](https://github.com/dunncl15/BYOB/blob/master/server.js#L139). Sending a 204 without any type of data or message is perfectly fine, as a 204 implies success **and** no response body.

* Nice job breaking out errors and authentication [logic](https://github.com/dunncl15/BYOB/blob/master/server.js#L6-L7).

* [403](https://github.com/dunncl15/BYOB/blob/master/server.js#L211) status code doesn't make sense here. That one is reserved for authentication issues, this looks like it would be handling a generic user error which would return a 422 instead.

* Some [duplicate](https://github.com/dunncl15/BYOB/blob/master/server.js#L169-L175) code [here](https://github.com/dunncl15/BYOB/blob/master/server.js#L192-L198) that could probably be cleaned up by breaking the logic out into a helper function.

## Points: 140 / 150

Great job!