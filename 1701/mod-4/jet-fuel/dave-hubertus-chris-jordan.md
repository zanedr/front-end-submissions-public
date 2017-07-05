# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/dhubertus/jet-fuel)

#### Link to the Deployed Application
[heroku](https://dave-chris-jet-fuel.herokuapp.com/)

#### Provide a Screenshot of your Application
<img width="1246" alt="screen shot 2017-06-30 at 12 30 33 pm" src="https://user-images.githubusercontent.com/25044263/27749248-082f13e8-5d90-11e7-8fcb-cbe17881d476.png">

## Completion

#### Were you able to complete the base functionality?

Yes. We completed base functionality.

#### Which extensions, if any, did you complete?

We did not do any extensions.

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/dhubertus/jet-fuel/blob/master/public/src/radio-btn.js#L1-L20)

* Why were you proud of this piece of code?
We are proud of the work we put into JetFuel. 
For JetFuel using the first backend we have ever built, we are proud of the ways we found to solve issues as they came along.
This project also forced us to dive into the relationship between front end and backend as well as understaand config files and environments. 

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/dhubertus/jet-fuel/blob/master/public/src/helper.js#L34-L66)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
Testing - We struggled to include full testing as we had issues with utilizing berfore each to roll back tables between tests.
We have a branch that has the 'proper' configuration including a test seed and test db utilizing our migration however we are still experienceing issues.
We also have some code sanitiation we wish we could have handled.
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
<img width="647" alt="screen shot 2017-06-30 at 4 05 17 pm" src="https://user-images.githubusercontent.com/25044263/27755649-300545ea-5dae-11e7-982b-5c04b32cdd82.png">

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----


## Instructor Evaluation Points (Robbie)

### Specification Adherence

* **50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

### User Interface

* **15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

- A button labeled `Dropdown`?...I have no idea what this does before I click it
- The scrolling of links and folders in the middle of the page is kind of painful to use, why not expand the list down the page? I can only see one thing at a time.
- Should clear input after new folder is created
- Why is half the page dark and the bottom light?...

### Data Persistence with SQL Database

* **20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

- Good migration and schema
- Good seed data, but you should have a separate test seed directory/file - this could be a reason your tests are failing

### Testing

* **10 points** - Project has a running test suite that tests and multiple levels but fails to cover some features.
*Tests are commented out/failing currently (CircleCI)* - need these to be passing

- Should have tests for cases when there are no folders or urls (for a folder) in the DB
- [These functions](https://github.com/dhubertus/jet-fuel/blob/master/test/routes.spec.js#L105-L133) should run for every test interacting with the database, at least running the migrations and seed for GET routes and then re-seeding for POST routes
- Should have a sad path for folder name that already exists, if possible

### JavaScript Style

* **12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing. Need more RESTful routes

- Use the semantic form element for [these forms](https://github.com/dhubertus/jet-fuel/blob/master/public/index.html#L11-L21)
- Don't ship [commented-out code](https://github.com/dhubertus/jet-fuel/blob/master/public/index.css#L6-L8) unless you need it in the future, in that case make a note by the commented code
- Where were you having [CORS issues](https://github.com/dhubertus/jet-fuel/blob/master/server/server.js#L10) to need this?
- [This route](https://github.com/dhubertus/jet-fuel/blob/master/server/server.js#L35-L49) with query params is not quite what we're looking for - not the RESTful convention. You want to query for a folder/category or URL using the primary key
- Should have the `jetfuel` prefix [here](https://github.com/dhubertus/jet-fuel/blob/master/server/server.js#L76) since this is not an actual domain, the path should just be relative to localhost or your production URL
- For the most part you are using `catch()` in your queries, but make sure you are [consistent](https://github.com/dhubertus/jet-fuel/blob/master/server/server.js#L82) and always use `catch()` for any promise
- [This route](https://github.com/dhubertus/jet-fuel/blob/master/server/server.js#L63) should probably be `api/v1/categories/:id/urls`, not passing in the ID through query parameters
- When appending elements to the DOM, especially in a loop, you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.
- [Doing this](https://github.com/dhubertus/jet-fuel/blob/master/public/src/card-input.js#L19-L20) client side can have some risks because you want this URL to be unique, no two users should have the same shortened URL for two separate links, so you have to check the database from the client side each time you make a shortened URL
- Be sure to have `catch()` functions for every fetch call in case something goes wrong. Note that a 404 response from a fetch call will NOT result in an error, it is technically a successful response according to the fetch API
- The separation of files is nice, seems to be refactored

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

- *Do not* commit your node module to GitHub - always have this directory listed in a `.gitignore` file. Add the gitignore right away, as soon as you `git init`.

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 135 points or higher

# Final Score: x / 150 Need passing test suite.