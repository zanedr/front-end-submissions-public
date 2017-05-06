# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/Mickyfen17/jet-fuel)

#### Link to the Deployed Application
[Your project's production URL](http://jet-fuelled.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Eric Sayler](https://github.com/Mickyfen17/jet-fuel/commits/master?author=esayler)

-[Michael Fenwick](https://github.com/Mickyfen17/jet-fuel/commits/master?author=Mickyfen17)

#### Provide a Screenshot of your Application

![](http://i.imgur.com/184DMfa.png)

## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

- Added ability to delete individual folders and Urls

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[FE query to backend for sort functionality](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/app.js#L65)

- Utilized the backend (knex's `orderBy()`) to sort our URLs based on query params passed through in the GET request.

#### Link to a specific block of your code on Github that you feel not great about
[Giant IIFE for toggling filter](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/app.js#L37)

- Could be cleaned up to seperate the state logic from DOM manipulation. Multiple nested if statements are hard to follow.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![](http://i.imgur.com/Mb2nvaG.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

- [Link to unhappy path example](https://github.com/Mickyfen17/jet-fuel/blob/master/test/routes.spec.js#L232)
-----


# Instructor Feedback

### Specification Adherence

**50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

### User Interface

**15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* Minor bug on page load - the last folder in the list already appears to be open according to the icon, but I can't add a URL to the folder.
* Would like to see the visits increment as soon as I click the shortened link - have to refresh the page in order to see the visits increase.
* Nice job adding some client-side URL validation
* Great UI on the sorting buttons, the arrows are a nice touch

### Data Persistence with SQL Database

**20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

* Can add unique or null validation in the [database schema](https://github.com/Mickyfen17/jet-fuel/blob/master/db/migrations/20170503160714_initial.js#L5) since we always want folder names to be unique

### Testing

**15 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests.

* You want to make sure you call `done()` after the seeding promise is resolved in the `beforeEach` and `afterEach` [here](https://github.com/Mickyfen17/jet-fuel/blob/master/test/routes.spec.js#L35-L51)
* Sad path [here](https://github.com/Mickyfen17/jet-fuel/blob/master/test/routes.spec.js#L133-L141) could be for a folder that doesn't exist
* Good use of a sad path test [here](https://github.com/Mickyfen17/jet-fuel/blob/master/test/routes.spec.js#L176-L185)
* Overall, great happy and sad path testing - great to see a redirect test too.

### JavaScript Style

**15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* Nice job breaking the routes into different router files and [using the prefixes](https://github.com/Mickyfen17/jet-fuel/blob/master/server/index.js#L19-L20) - continue doing this. You'll see it's really beneficial as the number of routes grow.
* Be sure to respond with an explicit response code in [the redirect](https://github.com/Mickyfen17/jet-fuel/blob/master/server/redirect.js#L17). There are a few different response codes you can use depending on if your redirect is permanent or temporary.
* The [body parser middleware](https://github.com/Mickyfen17/jet-fuel/blob/master/server/index.js#L10) is only used for the API routes, so probably best to only use it in the API routers.
* Would be great to have a sad path [here](https://github.com/Mickyfen17/jet-fuel/blob/master/server/router.js#L44-L46) if the folder is not found in the database.
* Good sad path response [here](https://github.com/Mickyfen17/jet-fuel/blob/master/server/router.js#L53) - another sad path to consider is if the record already exists in the database since the folders must be unique.
* Testing for `activeFolder` but not `url` [here](https://github.com/Mickyfen17/jet-fuel/blob/master/server/router.js#L66)?
* If you're not going to include any entity in the [response of a delete](https://github.com/Mickyfen17/jet-fuel/blob/master/server/router.js#L84), typically a 204 status code is used for the response.

* Make sure to add a `catch()` to be able to handle error result in [your fetch call](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/app.js#L64-L72) - there were multiple instances of this
* Can set `$('folders')` to a variable [here](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/folders.js#L14) in order to save calls to the DOM
* Would probably extract [this](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/urls.js#L33-L51) into some kind of URL template
* When appending elements to the DOM, especially in a loop ([like here](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/urls.js#L30-L55)), you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.
* Think about [clearing input field](https://github.com/Mickyfen17/jet-fuel/blob/master/public/lib/urls.js#L88) after you know the fetch call is successful so that the user doesn't lose what they put into the field and they can see why something might have gone wrong
* Good separation of client-side code

### Workflow

**20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

* Good to see a lot of small commits and use of issues - good PR workflow with comments and context in PR

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 135 / 150
