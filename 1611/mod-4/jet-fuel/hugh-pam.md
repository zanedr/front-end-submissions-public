# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[jet-fuel](https://github.com/thatPamIAm/jet-fuel/)

#### Link to the Deployed Application
[AERONAUTICAL FUEL!](aeronautical-fuel.herokuapp.com)

#### Link to Your Commits in the Github Repository for the Project

-[Pam](https://github.com/thatPamIAm/jet-fuel/commits/master?author=thatPamIAm)

-[Hugh](https://github.com/thatPamIAm/jet-fuel/commits/master?author=hmorri32)

#### Provide a Screenshot of your Application

![Imgur](http://i.imgur.com/Dbgtp9q.png)

![Imgur](http://i.imgur.com/tODZQQy.png)

![recordit](http://g.recordit.co/2xKX5de4bP.gif)

## Completion

#### Were you able to complete the base functionality?
* Yes - everything but the sort functionality by date

#### Which extensions, if any, did you complete?

- N/A

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Core Redirect Code Block](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L81-L91)

* Why were you proud of this piece of code?

Writing this block of code represented a monumental paradigm shift in my thought process surrounding the functionality in the backend. Client side javascript, for me, seems inordinately complex. Actually shortening the urls, then redirecting to their respective longer URLs seemed to be the crux of this project. It was, however, not. Implementing the shortening and redirecting action helped solidify what it was that we were actually meant to be doing. It also made me less apprehensive when approaching certain problems in our server side code.

#### Link to a specific block of your code on Github that you feel not great about
[Code block that handles clicking sort by date btn](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L134-L148github.com)

[Corresponding sorting function](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L178-L182)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

As evidenced by the code, this is a complete work in progress. I have yet to figure out how to sort our URLs by the date/time at which they were created. We used an npm package called moment.js in order to restructure the ISO timestamp and convert it to something more readable. And so, the created_at data comes back as, for example, "today at 1:50pm". The data is actually stored in the database as originally described though. We tried to sort by date in the index.js file, which interacts with the dom. And so, it would be a matter of parsing the necessary numbers out and consequently sorting them. Or, figuring out a way to sort them on the backend side. Still have not figured out how to implement either approach. I am displeased with this code as sorting by date is a requirement on this project and I'm generally not cool with leaving things unfinished.

Also I am generally displeased with the format and length of our index.js file. It is in desperate need of refactoring/reformatting. JQuery and vanilla javascript don't seem to do well with importing and exporting files/functions. I'm sure there is a workaround that does not involve using several script tags in the index.html, though I haven't figured out what it is.

Testing on this codebase was problematic as well. The before and afterEach hooks in our routes test suite seemed erratic and unpredictable. I would have liked to test the DOM interaction more and also would have liked to test the helper URL validation regex functions we used.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Imgur](http://i.imgur.com/0ChELQu.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

![Imgur](http://i.imgur.com/ylGOGm6.png)

-----

#### Please feel free to ask any other questions or make any other statements below!

Cool project. Quite enjoyable. Back end code isn't so scary after all.

-----

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Specification Adherence

**45 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

* Didn't quite get to date being sorted, but saw number of visits able to sort
* Folder names should be unique, but currently I can submit two folders with the same name - can do this client side and/or server side

### User Interface

**15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* The UI leaves some things to be desired design wise...but not bad. Not sure about the background color and title color selection (hence the white background on "folders"). Would be nice to have an indication on the right blank section to select a folder before I try to add a new shortened URL.
* Would like to see the number of visits incremented on the client side
* Good job adding some URL validation!
* Errors just keep getting prepended to the page until a refresh - just replace errors with the most recent error

### Data Persistence with SQL Database

**20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

* Can add uniqueness to folder name in the [schema setup](https://github.com/thatPamIAm/jet-fuel/blob/master/db/migrations/20170503160117_initial.js#L9)
* Try to get away from hard-coding in primary keys in [your seed files](https://github.com/thatPamIAm/jet-fuel/blob/master/db/seeds/test/folders.js#L10), hence the value of returning the `'id'` as a second argument for `insert()`
* [Jhun would be proud](https://github.com/thatPamIAm/jet-fuel/blob/master/db/seeds/test/folders.js#L44)

### Testing

**12 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

* Need to resolve the [seed promise](https://github.com/thatPamIAm/jet-fuel/blob/master/test/routes.spec.js#L14-L22) with a `.then()` or `return`.
* Why all the spaces before the `done()`?
* For [this route's sad path](https://github.com/thatPamIAm/jet-fuel/blob/master/test/routes.spec.js#L101-L110), would be great to see a test for a folder id that doesn't exist in the database.
* Would be great to test for a foreign key [here](https://github.com/thatPamIAm/jet-fuel/blob/master/test/routes.spec.js#L124) to make sure the database got the correct set of URLs
* Good status code [response](https://github.com/thatPamIAm/jet-fuel/blob/master/test/routes.spec.js#L150).
* Can also test, in many/all of these API routes the type of response body you expect (JSON)
* Good sad path [here](https://github.com/thatPamIAm/jet-fuel/blob/master/test/routes.spec.js#L168), should probably respond with a different status code - probably 400 since the POST body needs to be modified.
* Great to see a [redirect server-side test](https://github.com/thatPamIAm/jet-fuel/blob/master/test/routes.spec.js#L229) - sad path is always good too!
* Would like to see a sad path for [this route](https://github.com/thatPamIAm/jet-fuel/blob/master/test/routes.spec.js#L207) similar to what you have in above tests

### JavaScript Style

**15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Haha:
> Actually shortening the urls, then redirecting to their respective longer URLs seemed to be the crux of this project. It was, however, not.

* Awesome:
> Back end code isn't so scary after all.

* In general, it's a good practice to bring your API routes into a separate router file to make your [server file](https://github.com/zkc/JetFuel/blob/master/server.js) more readable - see [express.Router](https://expressjs.com/en/guide/routing.html#express-router)
* Not sure that you need [this here](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L19) since you're not sending data directly through forms, only with `fetch`
* Keep in mind to handle the occurrence where there is a request for an `id` that doesn't exist in the database, like in [this route](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L33-L39)
* [Using `moment` is good](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L104-L105) - time is difficult...
* Be sure to specify a response code for [the redirect](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L89) - there are a few different kinds of redirects depending on if the redirect is permanent, temporary, or if you want the browser to cache it.
* Always have a `catch` in [a promise](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L53-L59) to catch errors - there are other instances of this in your server file
* Good use of status code 201 for [creating a URL](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L77)
* Not sure why you want to pass in another `id` [here](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L74) to create a URL, you have the `folder_id` and you want the URL's primary key (id) to auto increment
* Cool use of `increment()` [here](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L83)
* [This line](https://github.com/thatPamIAm/jet-fuel/blob/master/server.js#L95) seems redundant, why not just use `app.get('port')` again? Then you don't have to save the server to a variable

* Like above in server code, your [client-side](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L33) `fetch` code should always have a catch for errors
* When appending elements to the DOM, especially in a loop ([like here](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L47)), you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.
* Make sure you remove [`console.log`](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L28) from your production code
* Can also use the `input` event [here](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L99) instead of `keyup` to reduce the number of times this check runs
* Seems like you're trying to avoid a nested `if/else` [here](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L113-L114), but a ternary really is just that and much less readable in this case. However, [this](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L223-L228) ould be a good place for a ternary
* Good refactoring for the helper functions
* Good use of `sort()` for the number of visits
* If the argument, `input`, is a string [here](https://github.com/thatPamIAm/jet-fuel/blob/master/public/index.js#L213), then you shouldn't have to interpolate it in the jQuery selector


### Workflow

**15 points** - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

* Good, small commits but would like to see more conversation in the PR workflow - adding context to your PRs for the reviewer (in the description).

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 122 / 150
