# BYOB Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/letakeane/faceEmotionAPI)

#### Link to the Deployed Application
[Heroku](http://faceemotionapi.herokuapp.com/api/v1/faces)


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
Yes

* Wrote tests for both happy and sad paths for each endpoint?
Yes

* Setup automatic deployments with CircleCI to a production app on Heroku?
Yes

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L253-L265)

* Why were you proud of this piece of code?
I had a lot of fun writing (hopefully) helpful error messages.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L110-L168)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
This code works well, but is not modular. I also want to be able to implement chainable queries (like `api/v1/emotions/3?gender=2+?race=2`).

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://i.imgur.com/tYK468U.jpg)

#### Attach a screenshot or paste the output from your terminal of the result of your linter running.

[linter output](http://g.recordit.co/dpginiUk6a.gif)

#### Attach a screenshot of your CircleCI build passing

[circleCI build](http://g.recordit.co/e0UMtyRLf3.gif)

-----

#### Please feel free to ask any other questions or make any other statements below!

It might just be the adrenaline backwash after staying up very late last night, but I'm feeling very positively about this project. It was a nice mix of challenging and achievable. There were moments when I felt frustrated, but I never felt completely at sea. It was also just really nice to get to pair with you guys (even on solving my very dumb syntax errors).

-----


# Instructor Feedback (Brittany)

The following set of points are distributed at the discretion of the instructor.

### Documentation

**8 points**: The README includes documentation for all available endpoints and how to use them. Instructor can follow the documentation for using the API but has to do some parsing.

* I'd like a formatted example of what kind of JSON object I need to pass through for POST requests. The list of properties is nice but let's make it a little more readable. You can make a block of code by doing a line of 3 grave marks before and after the code block.

### Feature Completion

**60 points**: Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params. The database is seeded with at least two tables and one relationship.

### Testing & Linting & Error Handling

**35 points**: Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. Error handling is informative and helpful for the end-user. The project has a linting configuration that passes with no errors.

* [This](https://github.com/letakeane/faceEmotionAPI/blob/master/test/routes.spec.js#L51) is a scenario where we would also use environment variables rather than hard-coding the accurate values in. Not a huge deal in this case since the credentials aren't actually  sensitive data but just for future reference.

* [Clever](https://github.com/letakeane/faceEmotionAPI/blob/master/test/routes.spec.js#L81) though I'm a little weary of adding that line for the sake of making additional assertions that depend on order. It's just one extra step that makes your testing responses just slightly different than the responses you'll be getting in development and production, and we want to keep them as similar as possible.

* Your recordit for linting shows you linting your server.js file but in the future I'd also include your test files in that linting process ;)

* Not sure which linter configuration you're using as your repo seems to have eslintrc and jshintrc files, I'd go remove whichever one you're not using.

### JavaScript Style

**25 points**: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* [Nooooo :(](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L7)

* We don't want to fallback to [production](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L4) here, development is better. I'm assuming you're doing that so you could shorten [this](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L21-L23) conditional and not have it complain about not having a `config`. This is another instance where you would set environment variables for secret, username and password and fallback to the config values in your `.env` file.

* I'd take [this](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L56-L76) endpoint out all together, as it was only needed for getting the JWT in the first place. Doing `jwt.sign()` and console logging the value the first run of your server would have done the same trick.

* [Ahhhh](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L108)

* [This](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L111-L167) is a big, gnarly conditional. This could be refactored to loop through all the `Object.keys()` of `request.query` and just chain any of those keys that exist as where conditions. You could do that chaining with [whereIn](http://knexjs.org/#Builder-whereIn)

* I wouldn't include the races/genders/ages words in the URLs for [these endpoints](https://github.com/letakeane/faceEmotionAPI/blob/master/server.js#L170-L216). If you're returning faces, end the URL at faces and use query params for the genders/ages/races.

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 130 points or higher

# Final Score: 128 / 150
