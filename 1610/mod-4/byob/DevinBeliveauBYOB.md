## TripPlanner: Build Your Own Backend

![BYOB](http://g.recordit.co/avaxlIqDFr.gif)

#### GitHub: [Repo](https://github.com/devinmarieb/trip-planner)

#### Deployed: [Heroku App ](https://tripplannerprjct.herokuapp.com/)

### Completion

I have eighteen endpoints for TripPlanner:

9 `GET` requests

3 `POST` requests

3 `PATCH` requests

3 `DELETE` requests

I have 53 passing tests for TripPlanner. All endpoints have a test that checks for `status 200` and `status 404`. Where applicable, endpoints are tested for `status 422`.

### JSON: notes after reading the JSON docs (or as much of it as I could actually understand).

`GET /articles HTTP/1.1 Accept: application/vnd.api+json` : This project was my first experience using Postman for actual development / deployment. I'm not sure what do do with headers on the server side, so I did not include anything like this in my code. I do not understand what `self` and `related` links are.

`HTTP/1.1 200 OKContent-Type: application/vnd.api+json` : I guess I'm not sure how exactly how to structure success status codes. Mine are structured `res.status(200)` because it is similar to examples I have seen.

`406 Not Acceptable` : As with above, I did not include any `406 status` codes as I do not quite understand headers.

For all status codes I did not include things like `OK`, `Not Acceptable` and `Not Found`. As mentioned above, my status codes are structures more like `res.status(422).send(error)`.

### [Code I am proud of](https://github.com/devinmarieb/trip-planner/blob/master/server.js#L235-L254)

This is the code for deting a user. I am proud of this code because it was a slightly harder piece of logic to work out. It was the first delete request I wrote and I had to first search trips to make sure that trips associated with the users were deleted before the user was deleted.

### [Code I am not so proud of](https://github.com/devinmarieb/trip-planner/blob/master/server.js#L21-L40)

This is the code for checking if there is a request query. I wouldn't say I'm not proud of this code, but since I didn't know what requests queries were before this project, I'm not sure I went about checking for one the right way. I feel like there is probably a cleaner way to write this piece of code.

![Passing Tests](http://g.recordit.co/SvSnkOcsP9.gif)

### [Sad path test for getting a specific user](https://github.com/devinmarieb/trip-planner/blob/master/tests/server-test.js#L173-L191)

This is an example of a test that checks a sad path.

#### Other notes:

I'm still a little confused about headers. After reading the JSON docs, I'm not sure when/how I'm supposed to declare header types or know when/how I'm supposed to use them.

Instructor Feedback

Points: 150 / 150

Notes: Great job on this project. Super friendly interface for accessing the API - that was a great touch to add.

Re: the headers: [This](http://expressjs.com/en/4x/api.html#setHeaders) is how you would set custom headers. You can use [req.accepts](http://expressjs.com/en/4x/api.html#req.accepts) to lock down accepting only certain types of content types - or [req.is](http://expressjs.com/en/4x/api.html#req.is) to respond different to certain content types.

`res.status(200)` is going to give you a lot of what you need without having to go deep in the weeds. 

## Endpoints

Note: All endpoints (and then some) present

60 points - The application has all 17 endpoints (6 GETs, 3 POSTs, 3 PUTs/PATCHs, 3 DELETEs, 2 CUSTOM) with responses for happy and sad paths for each endpoint.

## Data Persistence with SQL Database

1 relationship present - data seeded at minimum amounts

40 points - The application persists data in a SQL database but with correct relationships between folders and URLs.

## Testing

All tests present!!!

Note: The 404 tests like [this one](https://github.com/devinmarieb/trip-planner/blob/master/tests/server-test.js#L45-L46) don't actually test the specific endpoint. If you add some console.log statements in different endpoints, you'll probably find that it doesn't hit the ones you expect (like, `usres` won't hit `app.get('api/users')`

I believe that actually, an api endpoint to a collection of items (the get trips, countries, etc) would actually never return a 404 - since if the table didn't exist, you would get a `500` and if it did. 

30 points - Project has a running test suite that has 34 passing tests (a sad path and a happy path test for each endpoint)

## JavaScript Style

20 points - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There zero instances where an instructor would recommend taking a different approach.
