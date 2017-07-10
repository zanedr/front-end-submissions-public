# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/JohnBinning/jetFuel)

#### Link to the Deployed Application
[heroku](https://steelbirdfood.herokuapp.com/)

#### Provide a Screenshot of your Application
[screenshot gif](http://g.recordit.co/TN3o9rg0Zx.gif)

## Completion

#### Were you able to complete the base functionality?

We did not complete sorting by number of link clicks, or sorting by date added. We also did not get to showing the date the link was created. (I don't even want to talk about the awful box-shadow on hover; it fell lower and lower on the priority list as time wore on.)

This was mostly due to a lack of time (as was the messy code). The demo competition on Thursday night, though great, severely cut into our project work time. It was also due to the plain old fact that we didn't check in on the spec details once we got into the feverish frenzy of racing the clock; that's totally on us.

#### Which extensions, if any, did you complete?
None, as far as we can tell.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/JohnBinning/jetFuel/blob/master/public/scripts/index.js#L93-L98)

* Why were you proud of this piece of code?

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/JohnBinning/jetFuel/blob/master/public/scripts/index.js#L63-L71)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
```window.location``` is disgusting and I am ashamed. We literally wrestled with the redirect functionality of the app for over 8 hours (including taking the time to ask for help). Along the way I got things partly working (the app did not redirect but the generated short url, when manually copied into the browser, successfully redirected), but when I used an anchor tag, everything stopped working and it took another hour to untangle it.

Ultimately there's a LOT of DRYing up and refactoring we'd like to do.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](http://i.imgur.com/VqZ6ppf.png)

#### Please feel free to ask any other questions or make any other statements below!

Looking forward to cleaning this up for our portfolios!

-----


## Instructor Evaluation Points (Robbie)

### Specification Adherence

* **50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

### User Interface

* **15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

- Once I click on a folder, I see the links in that folder, but I can't get back to the list of folders unless I refresh the page, which should not be required.
- Validation on form and URL is good, but URL validation could be more robust (not just looking for `.`)

### Data Persistence with SQL Database

* **15 points** - The application persists data in a SQL database but with correct relationships between folders and URLs, but hard-coded dev and prod environment foreign keys.

- Schema looks good with folders and links with folder_id foreign key link
- Not sure what the test migration files are doing...
- [This block](https://github.com/JohnBinning/jetFuel/blob/master/db/seeds/production/folders.js#L29-L31) is not necessary for folders because you can give `insert()` an array of data directly, not needing to iterate over each folder
- [This loop](https://github.com/JohnBinning/jetFuel/blob/master/db/seeds/dev/links.js#L61-L63) is good because you want to give the link the correct folder_id foreign key, but you don't want to hard code foreign keys in development or production, only the test environment if necessary

### Testing

* **15 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

- [This file](https://github.com/JohnBinning/jetFuel/blob/master/test/index_test.js) should be removed - serves no purpose. Same with [this](https://github.com/JohnBinning/jetFuel/blob/master/test/testfolders.js) and [this](https://github.com/JohnBinning/jetFuel/blob/master/test/testlinks.js) now that you have a database hooked up.
- [Test file](https://github.com/JohnBinning/jetFuel/blob/master/test/routes.spec.js) from the lesson...shouldn't be left in the repo
- [The before and beforeEach blocks](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L26-L37) should not be in the client routes `describe` block because these routes do not interact with the database
- Migration is only needed once before all of the tests, not before each test. You can put [this](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L63-L66) in a `before` section
- Good [sad path](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L87-L94)
- If you are grouping tests together with [describe](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L96), then make sure the [related tests](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L75-L94) go inside that `describe()`
- Good [response code](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L120)
- Be consistent with testing for [json response](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L128) in other tests
- Did you mean to test for a link ID within a folder [here](https://github.com/JohnBinning/jetFuel/blob/master/test/server_test.js#L202-L210)? This test doesn't make sense in its current state.

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- The root level of the project is pretty messy - multiple server files, migrations...
- When appending elements to the DOM, especially in a loop, you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.
- [This GET request](https://github.com/JohnBinning/jetFuel/blob/master/public/scripts/index.js#L31) seems unnecessary - why not just append the new folder?
- Don't forget error handling with `catch()` on every [fetch call](https://github.com/JohnBinning/jetFuel/blob/master/public/scripts/index.js#L239)
- The fetch API considers a 404 response successful, which won't be handled through a `catch()`, so make sure you account for this when using fetch

- I'd be interested to know when you ran into [CORS issues](https://github.com/JohnBinning/jetFuel/blob/master/server.js#L15-L20) in this app
- [These](https://github.com/JohnBinning/jetFuel/blob/master/server.js#L24-L25) should be removed after using DB
- You only need to send the HTML file [here](https://github.com/JohnBinning/jetFuel/blob/master/server.js#L29-L30), and then assets will be requested via the link/script tags in the HTML
- Good edge case handling [here](https://github.com/JohnBinning/jetFuel/blob/master/server.js#L36-L41)
- Since you are using a primary key to get a folder [here](https://github.com/JohnBinning/jetFuel/blob/master/server.js#L67), then the variable `folders` should be singular because you only expect a single folder to be returned based on a primary key
- [These routes](https://github.com/JohnBinning/jetFuel/blob/master/server.js#L145-L165) are not the most RESTful because they are not dealing with specific resources in the database, [this](https://github.com/JohnBinning/jetFuel/blob/master/server.js#L153) route is OK, but you wouldn't nest it under your API
- Good job using `catch()` in your database query promises for error handling

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

- *Do not* commit your node module to GitHub - always have this directory listed in a `.gitignore` file (which you do have, but they are still in the repo). Add the gitignore right away, as soon as you `git init`.

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 130 / 150