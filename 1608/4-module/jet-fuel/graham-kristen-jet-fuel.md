#Jet Fuel (Kristen Burgess and Graham Nessler)

##Link to the Github Repository for the Project

[Github Repo](https://github.com/gness1804/jet-fuel)

##Link to the Deployed Application

[Check it Out!](https://kbgn-jetfuel.herokuapp.com/)

##Your Application

###Link to Your Commits in the Github Repository for the Project:

[Graham's commits](https://github.com/gness1804/jet-fuel/commits/master?author=gness1804)
[Kristen's commits](https://github.com/gness1804/jet-fuel/commits/master?author=kristenburgess25)

##Our Application: 

![Screenshot](jet-fuel-screenshot.png)

##Completion

###Were you able to complete the base functionality?

Yes.

###Which extensions, if any, did you complete?

None.

##Code Quality

###Link to a specific block of your code on Github that you are proud of

[Our sort function!](https://github.com/gness1804/jet-fuel/blob/master/public/index.js#L152-L188)

####Why were you proud of this piece of code?

This piece of code sorts the URLs by popularity. We are proud of this code because it performs a complex function effectively and we both work together to solve the problems in it. It also involved a vanilla JS XMLHttpRequest(), which allows use to dive more deeply into the http request logic than a wrapper from a library would have.

###Link to a specific block of your code on Github that you feel not great about

[Our showOneFolder and showURL functions](https://github.com/gness1804/jet-fuel/blob/c8003c6bd530afb3cff659749bf0e883d1bcdc63/public/index.js#L42-L122)

####Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

This code is overly long and repetitive. We did not have time to refactor, and there is a lot of repetition. We could combine functions like  this into a single function, and also break out functions into smaller functions and separate files. We did not get around to doing a lot of this type of refactoring that would have helped the code be more readable and maintainable.

Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'
Pending

Please feel free to ask any other questions or make any other statements below!
Pending

# Instructor Feedback

Points: (base 150)

** 118/150** - Which translates to a passing 3

## Base Expectations

**42 points**

If the bug below is fixed, and you document the fix and deploy it, we will bump this score to a 50.

The app isn't totally usable as an MVP due to this bug

1. All of the hard coded data redirects correctly. When we try to visit links we added, we get the url appended to the end of the heroku url instead. If you don't have `http://` in the user input, the redirect doesn't work properly. There is no UI to support the user understanding this.

```
Given that I am an anonymous user of the system
When I follow a service shortened URL
Then I expect to be redirected to the original URL
```

### User Interface

**12 points** The application has many strong pages/interactions, but a few holes in lesser functionality

We suggest you fix before adding to the portfolio.

1. When you create a url, the UI doesn't show you the long url in any way so it's hard to check what got added.

2. Clicking sort popularity traps you where you can't go anywhere or go backwards in the sort process (although it does work)
  - same with selecting a folder - no way to travel back

### Data Persistance with SQL Database

**20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

### Testing

**20 points** - Project has a running test suite that exercises the application at multiple levels including server and client tests.

Really appreciate having sad path tests like [this one](https://github.com/gness1804/jet-fuel/blob/master/test/test.js#L74-L79). Best testing we've seen so far.

[No commented out code](https://github.com/gness1804/jet-fuel/blob/master/test/routes.spec.js) on master please

[This Post Test](https://github.com/gness1804/jet-fuel/blob/master/test/test.js#L96-L109) doesn't actually test that anything was created in the db. You should consider checking the test database that whatever you just posted is there. If you want to avoid hitting the DB in the test, make another get request and make sure that the added folder is present.

Make sure the README for the project has the test command in it - as well as the migration to create the test database command.

You should perhaps consider making an npm script that runs all the setup migrations. And an npm script to run your test command - and list those both.

You would want to document that someone pulling down the repo needs to create the db

```
$ psql
psql (9.4.5)
Type "help" for help.

# CREATE DATABASE mocha_chai_tv_shows;
CREATE DATABASE
# CREATE DATABASE mocha_chai_tv_shows_test;
CREATE DATABASE
```

And how they might run migrations:

```
$ knex migrate:latest --env development
$ knex migrate:latest --env test
```

To migrate per database

### JavaScript Style

**12 points** - This is a very soft 12. See notes below.

Holy Guacamole [the length of this sort function](https://github.com/gness1804/jet-fuel/blob/master/public/index.js#L7-L40)

#### Refactor, Refactor, Refactor.

You need to have very small single responsibility functions. There is so much going on in this sort function, that I would never allow a PR with this in it to be merged into a project I was running. 

`sortByPopularity` should be 5 different functions

1. Displaying the photo titles
2. Making an API call to grab the URLs
3. Sorting the results of the API call
4. Rendering the results to the dom
5. Handling the error response to the original api call

And further more, these functions should not all live in this file once they are broken out.

`showOneFolder` - each DOM element should be its own variable or its own function. 

1. showSortAscendingButtons, showDateAscendingButtons, etc, etc

You have the right idea with this [shorten-url](https://github.com/gness1804/jet-fuel/blob/master/shorten-url.js) - that's what we want to see.

#### Consistency

You need consistency on how you call APIs in the code base - for example - [this code](https://github.com/gness1804/jet-fuel/blob/master/public/index.js#L99) does not match [this code](https://github.com/gness1804/jet-fuel/blob/master/public/index.js#L155). We know you want to get the thing done, but you should always review your code to make you match style and technology before you merge.

In one function, you have DOM code [here](https://github.com/gness1804/jet-fuel/blob/master/public/index.js#L162)

The next line, you [switch to jQuery](https://github.com/gness1804/jet-fuel/blob/master/public/index.js#L163)

### Workflow

**12 points** - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

We can tell that you are making a solid effort to do this well - with small commits - but small commits don't actually help unless you make them with purpose.

You have lots of PRs but no inline code comments. Which makes us think, based on the things discussed below, that you need to work on reviewing code more critically before merging. 

You have a lot of mismatching JS style. You have a lot of files that you aren't using. Delete these files. Your PR process should not allow you to accidentally commit unused files. You should be pushing a PR up every day and maybe every few hours in a week long project. And you should be reviewing like a hawk, your own PRs as well as your partners.
