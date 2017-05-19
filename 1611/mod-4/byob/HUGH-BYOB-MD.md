# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[Yung REPO LINK](https://github.com/hmorri32/byo-backend)

#### Link to the Deployed Application
[Secret Depths - HEROKU](https://secure-depths-86331.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Commits](https://github.com/hmorri32/byo-backend/commits/master)

## Completion

#### Were you able to complete the base functionality?

* Seeded a database with at least 2 tables and 1 relationship?
YES
* Had at least 10 endpoints that returned responses with appropriate status codes?
YES
* Secured at least 4 endpoints with JWTs?
YES
* Enforced a linter and wrote code that conformed to it?
YES
* Wrote tests for both happy and sad paths for each endpoint?
YES
* Setup automatic deployments with CircleCI to a production app on Heroku?
YES
# Code Quality
- Super great!

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L122-L150)

* Why were you proud of this piece of code?
This was my first succesful PUT request! It solidified my knowledge of HTTP request as well as restful API basics. 
It also cemented my knowledge surrounding how the database actually interacts with knex/express. Super cool stuff.
I also implemented some ultra robust error handling. Which was neat. 

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L184-L213)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
This is a link to one of my handy PATCH works. I forced the request to include certain params and those params only. 
I would have like for it to be more dynamic. IE, I wish I could have patched up one or many key value pairs as opposed to
only the three I wrote. I would have gotten there, just ran out of time. 

## Testing

Attach a screenshot or paste the output from your terminal of the result of your test-suite running
![yungtests](http://g.recordit.co/ASfqQl3Yuw.gif)

## Linting
Attach a screenshot or paste the output from your terminal of the result of your linter running
-No errors. 
![no errors](http://g.recordit.co/Vd2OTFsOqm.gif)

-----

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

This project was sweet as heck! Seriously. I enjoyed it tremendously. 


--------------------------



# Instructor Feedback [Brittany]

## Feature Completion

### Endpoints
**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.

### Data Persistence with SQL Database
**40 points**: The application contains 2 tables with a proper relationship between data sources.

## Testing and Linting

**30 points**: Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.

* It's more important to have a `seed.run()` in a beforeEach block rather than [afterEach](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L29-L32). If a test fails, it will never actually reach the `afterEach` block. (So there's a chance that the re-seed wouldn't be run and our remaining tests would be working off inconsistent data.) We previously put them in both beforeEach and afterEach, but if you're going to choose one or the other, `beforeEach` is the way to go.

* [This](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L59-L103) test is doing a little too much. In an endpoint like this, I would likely just assert that an array with a length of 2 came back and maybe that each record contained a shark_id. You don't need to test that every single property value exists because you're actually writing those assertions down [here](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L161-L189) when you're getting a shark by ID. It doesn't necessarily hurt to have this duplicate coverage, but it doesn't help either. Think about how many of your tests would fail if you just decided to remove the `tagDate` column from the sharks table. You'd have to update the same code in multiple tests to get them all passing again.

* 44 tests is fabulous, but probably, in general, a little overkill. E.g. is [this](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L105-L114) test asserting the same thing as [this](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L46-L56) one?

* What are all these [blank](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L1037-L1050) lines?

* We didn't go over this in class, but in the future you could add linting to your CircleCI builds by adding the following to your `circle.yml` file:

```json
test:
  override:
    - ./node_modules/.bin/mocha
    - ./node_modules/.bin/eslint
```

### JavaScript Style
**15 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* [You](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L120) [are](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L15) [weird](https://github.com/hmorri32/byo-backend/blob/master/test/server.spec.js#L35)

* [I beg to differ.](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L14-L15)

* 13 endpoints! 🎉

* Very nice organization of your [require statements](https://github.com/hmorri32/byo-backend/blob/master/server.js#L1-L8)

* I like that you split out your server configuration and your routes. We prematurely added `/api/v1/` to the start of all of our routes just for practice/following common conventions. If you were really working with a versioned API, or one that would potentially have future versions, [this](http://stackoverflow.com/questions/26040329/how-do-you-handle-api-version-in-a-node-express-app) is a solid strategy. Just FYI.

* [Here](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L26-L27) you likely want to refactor a little bit. If there are no sharks as a result of your `select` you are likely getting back an empty array. In your `.then()`, I would write a conditional that checks for a length on the sharks returned. If there's a length, respond with the 200, otherwise respond with a 404. In your `.catch()`, you would respond with a 500/503 (generic, internal server error) because it would mean something went wrong with the database - but we don't know exactly what. Any number of things can go wrong, and we can't determine that ahead of time. A 404 on the other hand, we know would be a result of an empty sharks array. So for example:

```js
database('sharks').select()
.then(sharks => {
  if (sharks.length) {
    return response.status(200).json(sharks);
  } else {
    return response.status(404);
  }
})
.catch(error => {
  return response.status(503).({ error });
});
```

(I see you're following that strategy [here](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L31-L33). I would still add a `.catch()` here for an internal server error.)

* Cool that you broke out your different types of errors as well, though I think the naming conventions could use a little work. e.g. `error.arrayLength` might be best named `error.noRecordsFound`. Array length is just a little vague. e.g. what is actually wrong with the array length? Is it too long? Is it too short? If we're using it solely for saying there is no length, we can safely assume we want to return a 404/use a `noRecordFound` error.

* [This](https://github.com/hmorri32/byo-backend/blob/master/helpers/error.js#L19) error message could be even more useful if you actually include the user's query param value. e.g. maybe they had a typo they didn't realize that they would recognize by reading it in the error message. Without that, the `queryArrayLength` error is almost identical to the `arrayLength` error and doesn't offer us much more except the fact that we used a query param.

* [Always include .catchs() for any promises!](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L51-L55)

* Eeep, [this](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L89) is a little long. Might be something that would be good to break out as well so we could specify each array value on a new line.

* There is some duplicated code that could likely be broken out into helpers. Look how similar [this](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L123-L133) is to [this](https://github.com/hmorri32/byo-backend/blob/master/routes/index.js#L153-L163). You could likely make a helper function that takes in the list of required parameters and does the check for them. Also, [tell us what fields we're missing](https://github.com/hmorri32/byo-backend/blob/master/helpers/error.js#L29)

### Misc

* Cool favicon +1


- Points: 146 / 150

You absolutely crushed it. Great work. Keep it up.
