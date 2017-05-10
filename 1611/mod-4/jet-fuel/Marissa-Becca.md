# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your projects's repo URL](https://github.com/becs919/jet-fuel)

#### Link to the Deployed Application
[Your project's production URL](https://jetfuelshorturl.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Becca](https://github.com/becs919/jet-fuel/commits?author=becs919)

-[Marissa](https://github.com/becs919/jet-fuel/commits?author=marissa27)

#### Provide a Screenshot of your Application
![recordit](http://recordit.co/kYu7VC2Rea.gif)

## Completion

#### Were you able to complete the base functionality?
* Yes - Brittany said that we could focus on testing and not complete date/visited and sorting. We have the date created and visits displaying but no sorting. The visited increments but does not instantly update on page. 

#### Which extensions, if any, did you complete?

- N/A

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo - Testing for server-side](https://github.com/becs919/jet-fuel/blob/37aeda6718b027f94f5a93ba408cd0a5cf7b5f0b/server.js)

* Why were you proud of this piece of code?

We're really proud that we set up our testing environment and wrote sad/happy tests for all endpoints - especially with how new all of this is.  

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo - 2nd migration](https://github.com/becs919/jet-fuel/tree/master/db/migrations)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

We felt great that Brittany had us make a new migration even though it scared us, but now we know how to do it. We weren't proud that we named our columns with dashes at first resulting in us having to make a new migration. We learned to never use dashes in column names. We also made 2 more migrations to drop timestamps and add it back in with the arguments of true,true.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![Testing](http://g.recordit.co/oeDYGy0Yrl.gif)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'
[Unhappy](https://github.com/becs919/jet-fuel/blob/master/test/routes.spec.js#L184-L223)

-----

#### Please feel free to ask any other questions or make any other statements below!

We strayed a lot from our wireframes. We were focusing too much at the beginning of our project on UX/UI and not focusing on the database itself. When we started putting our energy into our database, the UX/UI was left behind. We aren't very proud of our front-end but our database is doing the thing and we have tested it! Also, our visited increments but doesn't automatically load on page when you redirect. That is something we would have liked to finish. 

Questions: How do we practice/learn how to test better? 

-----


# Instructor Feedback (Brittany)

## Specification Adherence

**45 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

* Minor Missing Feature: Sorting functionality was left behind, as we discussed. This is a more minor feature and I'm glad you focused on testing instead. I would encourage you to go back and try to implement this as sorting can be an interesting challenge on the front-end.

## User Interface

**18 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* B-e-a-utiful!

* Shrink me button should be disabled until a valid URL has been entered and a folder has been selected.

## Data Persistence with SQL Database

**20 points** - The application persists data in a SQL database with correct relationships between folders and URLs.

## Testing

**15 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

* [Ahhhhh](https://github.com/becs919/jet-fuel/blob/master/test/routes.spec.js#L14-L25). Let's make sure not to leave commented out code in the repo. If you're afraid you might need that code in place again, you can instead 'stash' it with `git stash` and it will temporarily hide those changes so they don't get committed to the codebase. When you need them again you can pull them back into your working directory with `git stash pop`.

* We probably don't need or want to do migration [rollbacks](https://github.com/becs919/jet-fuel/blob/master/test/routes.spec.js#L36-L41) in our test file because it will manipulate the status of our database schema, and we always want to be testing against the latest most up-to-date schema. I understand the blog post we linked you all to probably led you in this direction, and that's something we'll fix for the next cohort. No points off for this, just wanted to point it out.

## JavaScript Style

**15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

* You could make this [error](https://github.com/becs919/jet-fuel/blob/master/server.js#L37) message more helpful by telling the user exactly what data they're missing - the title!

* Recall how we set that `useNullasDefault` variable in our knex configuration file? If we have a value that we **would** like to use as a default, (such as [visits](https://github.com/becs919/jet-fuel/blob/master/server.js#L81) we could remove that and set an initial value of 0 for the visits field.

* I think the url records would need more than just a required [title](https://github.com/becs919/jet-fuel/blob/master/server.js#L84-L87). Instead of requiring just the title, I would make an array of all the required fields (longUrl, folderId, title) and map through it to make sure your url object contains each of those.

* Make sure you always include a `.catch()` block whenever you're working with [promises](https://github.com/becs919/jet-fuel/blob/master/server.js#L101-L109).

* The functionality within your [document.ready](https://github.com/becs919/jet-fuel/blob/master/public/index.js#L1-L3) doesn't actually need to be wrapped in `document.ready`. A fetch request doesn't depend on the DOM existing, so you could actually kick off that GET request immediately. Only functions that are intended to be executed right away **and** depend on a DOM element should be wrapped in `document.ready`.

* I like that you are immediately grabbing this DOM element and storing it in a [variable](https://github.com/becs919/jet-fuel/blob/master/public/index.js#L5) so that jQuery only has to traverse the DOM for it once, but let's do that for **all** the jQuery selectors we're using multiple times throughout the file. Additionally, the convention of prefixing your variable names with a dollar sign is intended for when the variable represents an actual jQuery element, not a value derived from that element, like in [these lines](https://github.com/becs919/jet-fuel/blob/master/public/index.js#L79-L81). Because these variables represent values or data IDs, and not the actual element selected, I would not prefix them with the dollar sign.

* When appending elements to the DOM, especially in a loop ([like here](https://github.com/becs919/jet-fuel/blob/master/public/index.js#L101-L110)), you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.


## Workflow

**13 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

* Some of the commits are a bit long with large diffs that make them a little difficult to read. In this [commit](https://github.com/becs919/jet-fuel/commit/0a03cea9181be479b4259c61fd0f30efc1c95d01) It should only be adding a POST request or fixing a pre-existing one. Instead it's adding a new migration file (should be it's own separate commit), removing commented out code (should be in a 'Cleanup' commit, or better yet, not have been committed in the first place) and makes many manipulations to the front-end code. Try to commit early and often after every change made so that you can keep the history readable.

* I would also try not to have too many of the same commit. (e.g. there are about 5 [Update Readme](https://github.com/becs919/jet-fuel/commits?author=becs919) commits here). If you want to add more or update a commit, you can continue adding changes to it with `git commit --amend` so that we only get a single update readme commit instead of 5.

* Good use of filing issues, you can link these up directly to your commits and pull requests by adding the issue number in the commit message or PR description. e.g. if issue #20 is 'Add ability to create new URLs', when you complete the work to resolve that issue, make your commit message 'Add Post Request for URLS Fixes #20' and it will automatically close the issue when that code gets merged into master.

### To get a 3 on this project, you need to score 110 points or higher
### To get a 4 on this project, you need to score 135 points or higher

# Final Score: 126 / 150
