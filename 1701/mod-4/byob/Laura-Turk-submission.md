# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/lauraturk/lt-byob)

#### Link to the Deployed Application
[Heroku](https://byob-madlib.herokuapp.com/)


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
Yes - with githooks for linting and testing

* Wrote tests for both happy and sad paths for each endpoint?
Yes

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/lauraturk/lt-byob/blob/master/data/data_fetch.js)

* It's likely not the prettiest, but I am proud that I reasoned through webscraping and parsing the return from the API I used to parse the words. It returned the text back as a single string w/ each word suffixed with it's coded part of speech (e.g. cat/NN). I would also like to refactor this further to use directly in the post so that a user could post a title and body or the url of a book on amazon and have it post the parsed and sorted words to the database. I used a class to give it additional flexibility for future use.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/lauraturk/lt-byob/blob/master/server.js#L124-L136)
and 
[code that makes me sad](https://github.com/lauraturk/lt-byob/blob/master/test/routes.spec.js#L361-L377)

* I don't think this is doing what I want it to do. My test passes, but that speaks more to the tiny size of my test seed file rather than to the efficacy of this code. Challenges I faced here were not fully understanding the syntax of what I should do, leaving it to the last minute ;-(, and maybe the overall architecture of my api being too loosy goosy for this to work as it should? I'm not sure.

* The second piece of code makes me very said because I just don't understand why the test won't pass in Circle Ci. They passed locally, and the endpoint works in postman sans problems. What's the deal, Circle CI? I'm sad I had to skip that test.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test suite](http://i.imgur.com/LBzugc0.png)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

![linter output](http://i.imgur.com/FRa5xyW.png)

#### Attach a screenshot of your CircleCI build passing

![circleCI build](http://i.imgur.com/Y64ooEF.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

* This is the first project I really, truly TDD'd and it was great. No last minute stress trying to get tests written and passing, and didn't have to mess around with postman a ton until I was confident things were work. I'd also love to start adding Spanish text samples and words to this dataset! Dave and I might use this as a spring-board to make a madlib game for our capstone. All the ideas... though I'm worried this back end might not up to snuff for what we need.
-----


# Instructor Feedback (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Documentation

* **5 points** -  The README documentation is out-of-date or inaccurate in some places. Instructor can not successfully use every endpoint based on following the documentation. 

- Would like to see one helpful part of API documentation which is showing sample output from an API call
- Try to break up the blocks of text for some of the endpoints
- The key for word types is good

### Feature Completion

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

* **35 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. Error handling is informative and helpful for the end-user. The project has a linting configuration that passes with no errors.

- Good `before` and `beforeEach` in your [tests](https://github.com/lauraturk/lt-byob/blob/master/test/routes.spec.js#L14-L26), but you don't need these functions to run for your client routes, only API routes dealing with the DB
- Be more descriptive in [test names](https://github.com/lauraturk/lt-byob/blob/master/test/routes.spec.js#L379), you can also use `describe` to group similar tests together, which also have their own titles
- Ideally, group similar tests like [this test](https://github.com/lauraturk/lt-byob/blob/master/test/routes.spec.js#L348-L359) and [this test](https://github.com/lauraturk/lt-byob/blob/master/test/routes.spec.js#L379-L390) next to each other for better test readability
- Overall good coverage of happy and sad paths

### JavaScript Style

* **25 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- The relationship between words and text snippets in your implementation is a one-to-many relationship, which is OK for BYOB, but in the future, this relationship should be a many-to-many to reduce data redundancy (since multiple text snippets can share the same word), and this should change if you use this backend in your capstone.
- The order of elements in the [array of Promise.all](https://github.com/lauraturk/lt-byob/blob/master/db/migrations/20170709160029_initial.js#L52-L56) does not guarantee the order of execution - careful with this if the order matters
- Promises are not [pos](https://github.com/lauraturk/lt-byob/blob/master/db/seeds/test/test_seed.js#L38), they are amazing!
- Would want to see more response messages that are descriptive when the user requests something that is incorrect or does not exist
- [This route](https://github.com/lauraturk/lt-byob/blob/master/test/routes.spec.js#L363) is not totally RESTful - all you want to do is POST to `/api/v1/text_samples`
- Were you having any [CORS](https://github.com/lauraturk/lt-byob/blob/master/server.js#L18) issues?...
- You don't want [one specific route](https://github.com/lauraturk/lt-byob/blob/master/server.js#L124) to handle query parameters - the route should look like `/api/v1/:table`, and if the user specifies query params, then handle them
- [This is clever](https://github.com/lauraturk/lt-byob/blob/master/server.js#L138), but dangerous - you're giving access to all table in your database by [not checking the table](https://github.com/lauraturk/lt-byob/blob/master/server.js#L141) and just trusting the user
  - In this app, it's not a big deal, but imagine if you had a users table
- A switch statement might be better [here](https://github.com/lauraturk/lt-byob/blob/master/server.js#L256-L264) because you are checking for a set of discrete values
- Could definitely use some refactoring/extraction in [this route](https://github.com/lauraturk/lt-byob/blob/master/server.js#L271)

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 125 / 150
