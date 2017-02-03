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
[Repo for Lacey and Dale's Jet Fuel](https://github.com/lrknaff/jet-fuel)

#### Link to the Deployed Application
[Lacey and Dale's Jet Fuel](https://jet-fuel-lk.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Lacey Knaff](https://github.com/lrknaff/jet-fuel/commits?author=lrknaff)

-[Dale Hendrickson](http://45.media.tumblr.com/96975bc08e24a9876e62311fdd0c4a34/tumblr_ne4ehpSJ5z1qa747mo1_500.gif)

#### Provide a Screenshot of your Application

![Jet Fuel](https://drive.google.com/open?id=0B9Va2UnLFcUOLXpLT3VpczRBUHc)

## Completion

#### Were you able to complete the base functionality?

All base user stories and functionality has been completed.

#### Which extensions, if any, did you complete?

The ability to search for urls in the url list.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of

* Passing the data between the [DOM and the database](https://github.com/lrknaff/jet-fuel/blob/master/public/index.js#L170-L202)
* Loading seed data with foreign key for [child tables](https://github.com/lrknaff/jet-fuel/blob/master/db/seeds/dev/folders.js#L1-L30)

#### Link to a specific block of your code on Github that you feel not great about

There are two examples of redundant code that could use significant refactoring related to the sorting functionality.
* [jQuery Events](https://github.com/lrknaff/jet-fuel/blob/master/public/index.js#L130-L172)
* [knex Queries](https://github.com/lrknaff/jet-fuel/blob/master/server.js#L52-L70)


#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

* [Jet Fuel Tests](https://drive.google.com/open?id=0B9Va2UnLFcUONFVWS1l6X0hVZ1U)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

No edge cases were tested.

-----

#### Please feel free to ask any other questions or make any other statements below!

-----

# Instructor Feedback

- Points: (base 150)

**129/150** - so entire project is a 3

Notes from Brittany

## Spec Adherance

**50 points** - No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

All of the base functionality is implemented, however there is a single bug when adding a new URL. As a user, if I enter a url such as `http://github.com`, then click on the shortened URL it generated, it tries to redirect me to `http://http//github.com` which can't be found. I would suggest putting a check in the code [here](https://github.com/lrknaff/jet-fuel/blob/master/public/index.js#L62) to ensure the original URL wasn't entered with `http://` by the user. (Subtracting 5 points here)

Adding 5 points for implementation of the search field in the URLs, which evens you back out to the full 50 points.

## User Interface

**15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

It could use a little more love around the list of folders and urls. At an initial glance, I have a hard time parsing the grouping/heirarchy of all the information on the page. Better use of margins, paddings and headings could alleviate this a bit.

Also, form elements look so much friendlier when they've been styled. They are notoriously difficult to style, so I admit it didn't need to be a top priority, but it makes a huge difference when trying to indicate/denote the available interactions on the page.

## Data Persistance with SQL Database

**20 points** - The application persists data in a SQL database with correct relationships between folders and URLs.

Great job reworking the database seeding to handle your dependent folder/url relationships!


## Testing

**12 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

We're skipping some important integration tests on the server-side, and lacking client-side tests.


## JavaScript Style

**15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

Some duplicitous code that could use refactoring, but overall well-thought out and structured codebase that was easy to follow and read through.

Some inconsistencies with the use of double vs. single quotes throughout the codebase and other minor stylistic things, such as spacing. Create and agree on a linting configuration ahead of time to clean these things up a bit.

When appending elements to the DOM, especially in a loop ([like here](https://github.com/lrknaff/jet-fuel/blob/master/public/index.js#L108-L120)), you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.

No points off for this, but I noticed the use of ES5 and lack of semi-colons. These are fine decisions as long as you are consistent with them, but make sure you are still comfortable writing ES6 and make sure you can defend your decision to not use semi-colons. (If I had seen code like this in a technical interview, I would ask the candidate about both of those choices. It is very rare that you'll join a team that would be ok with not using semi-colons.)

### Dom to Database Code
* Remember we discussed not needing to [preventDefault](https://github.com/lrknaff/jet-fuel/blob/master/public/index.js#L175) if you were no longer using the form element directly.

### Database Seeding
* Good work refactoring this from our last check-in! Just styling nit-pick, be consistent with your use of [single quotes](https://github.com/lrknaff/jet-fuel/blob/master/db/seeds/dev/folders.js#L9) vs. [double quotes](https://github.com/lrknaff/jet-fuel/blob/master/db/seeds/dev/folders.js#L16)


### jQuery Events
Besides duplication already noted, some additional ways to clean this up:

* Use jQuery's [.hasClass()](https://api.jquery.com/hasclass/) method to check if the `ascend` class exists rather than doing a strict equal check against the entire class attribute [here](https://github.com/lrknaff/jet-fuel/blob/master/public/index.js#L135). This will allow you to add other classes in the future to that element without having your JavaScript break.
* Move that conditional logic to the place where the code is actually differing: `returnDescendingList()` vs. `returnAscendingList()`. We are making that get request no matter what, the conditional has no effect on whether or not we do that, so let's move it down to the single line that actually differs.

### knex Queries
Agreed this could be refactored for less duplication. Other notes I'd suggest:

* Actually log the error message that is given to you in your `.catch(error)`. 'something wrong with db' is not super informative
* You can likely store the urls table as a variable to break this [line](https://github.com/lrknaff/jet-fuel/blob/master/server.js#L63) up a bit. 


## Workflow

**17 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Lots of nice tiny, readable commits, and consistent commit message formatting -- though not synchronized! (Lacey uses all lowercase, Dale starts with an uppercase). Very much a nitpick, but it's something a lot of teams try to standardize on.

Be sure not to commit commented out code or `console.logs()`. This clutters up the diffs when looking at PRs or history. Instead, use `git stash create` to temporarily stash these changes before you commit. Then you can `git stash pop` to pull them back in on your local copy! More info [here](https://git-scm.com/docs/git-stash)

Made use of many branches, it's a good idea to [delete them after they've been merged](https://github.com/lrknaff/jet-fuel/).

Good use of PRs and easy to review the diffs.