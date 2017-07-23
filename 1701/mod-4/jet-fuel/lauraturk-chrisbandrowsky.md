# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/lauraturk/jet_fuel)

#### Link to the Deployed Application
[heroku](http://lt-cb-jet.herokuapp.com/)

#### Provide a Screenshot of your Application
![Jet Fuel UI](http://i.imgur.com/q80R7ou.png)

## Completion

#### Were you able to complete the base functionality?

At the current state, base functionality is complete. A user can log on to the website, create a folder, take a url, and shorten it. 
Urls redirect to their original website. They are displayed on the DOM and can be copied and for redirecting shortened URLs. 
Multiple urls can be added to created folders.
Folders are default sorted by created date. The can be sorted by created date and popularity. 

#### Which extensions, if any, did you complete?
All of them?

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/lauraturk/jet_fuel/blob/master/db/migrations/20170627214757_initial.js#L2-L28)

* Why were you proud of this piece of code?

We found that making migrations and adding data to a database was a lot of fun. It was enjoyable to get it to work. 

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/lauraturk/jet_fuel/blob/master/server.js#L127-L163)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

In the last few minutes, as we pushed to production, we ran into a serious bug trying to implement a suggestion from Brittany that disabled us from redirecting our links. It worked. And then it didn't. After struggling with it for a good while, we've fixed the bug, but lost valuable time on doing additional tests to our suite. 
#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test suite](http://i.imgur.com/p4Xyz4x.png)

#### Please feel free to ask any other questions or make any other statements below!

We felt the time crunch was awful on this project. We got a lot done, but it feels like there is a lot more to go. Morale is low. 

Chris did a great job doing a lot of last minute heavy lifting as I was busy/preoccupied with demo night. Shout out to Chris!

Laura killed it with the UI reformatting and refactoring the ridiculousness that was Chris's jQuery (it wasn't that bad, Chris just doesn't like jQuery. She also crushed the popularity sort. 

-----


## Instructor Evaluation Points (Robbie)

### Specification Adherence

* **50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

### User Interface

* **15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

- The folder buttons UX is frustrating - clicking on multiple folders one after the other keeps the underline under previously clicked folders
- Radio buttons are not the tool you would use here since radio buttons are mutually exclusive - a user would not click a radio button twice an expect a different action
- Since the date added is not shown for each link, it's hard to tell which way the links are being sorted (either show the date or show which way you're sorting)
- I like that you hide the sort functionality if there is only one link in a folder

### Data Persistence with SQL Database

* **20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

- Why have `seed` and `seeds` directory?
- Good [seed file](https://github.com/lauraturk/jet_fuel/blob/master/db/seeds/test/test_seeds.js), practice putting in multiple folders with links associated to all folders
- Good migrations

### Testing

* **20 points** - Project has a running test suite that exercises the application at multiple levels including server and client tests.

- Good [sad path](https://github.com/lauraturk/jet_fuel/blob/master/test/routes.spec.js#L75-L82)
- Overall, good, clean tests for happy and sad paths
- You only want to run [the migration(s)](https://github.com/lauraturk/jet_fuel/blob/master/test/routes.spec.js#L35-L36) once before the whole test suite, not in the `beforeEach()` - consider doing this in a `before()`, and then you can seed the DB before each test as you are doing

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- Why the [spaces](https://github.com/lauraturk/jet_fuel/blob/master/public/index.html#L5) between the element attributes and values?
- Remove [empty lines](https://github.com/lauraturk/jet_fuel/blob/master/public/style.css#L61) in CSS before committing code
- Good job having a `catch()` with all of your [fetch calls](https://github.com/lauraturk/jet_fuel/blob/master/public/index.js#L15), this is always important for better error handling
- When appending elements to the DOM, especially in a loop, you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.
- Be sure to remove [console.log](https://github.com/lauraturk/jet_fuel/blob/master/public/index.js#L24) before you commit code
- Why the [space](https://github.com/lauraturk/jet_fuel/blob/master/public/index.js#L185) around `this`? I've seen this pattern, but be consistent in your JS files
- Good job handling [this case](https://github.com/lauraturk/jet_fuel/blob/master/server.js#L29-L31) of no folders in DB
- [This query](https://github.com/lauraturk/jet_fuel/blob/master/server.js#L43) should return a single folder if using the primary key, so folder variable should be singular
- I can't see where [this endpoint](https://github.com/lauraturk/jet_fuel/blob/master/server.js#L77-L93) is used...
- Since [this](https://github.com/lauraturk/jet_fuel/blob/master/server.js#L116-L118) case is not part of the API, then the user would probably want to see an actual 404 page and not a JSON response
- [This query/logic](https://github.com/lauraturk/jet_fuel/blob/master/server.js#L169-L173) could be simplified to look for the folder if it exists in the DB, which would simplify the logic that follows

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

- *Do not* commit your node module to GitHub - always have this directory listed in a `.gitignore` file. Add the gitignore right away, as soon as you `git init`.

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 140 / 150