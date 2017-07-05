# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/kamos1/jetfuel)

#### Link to the Deployed Application
[heroku](https://fathomless-hamlet-87357.herokuapp.com/)

#### Provide a Screenshot of your Application
![screenshot](<img width="1280" alt="screen shot 2017-06-30 at 12 28 44 pm" src="https://user-images.githubusercontent.com/24981999/27749182-bef142fa-5d8f-11e7-9a07-5ad99c6f9557.png">)

## Completion

#### Were you able to complete the base functionality?

No we were able to complete all functionality on the project except for sorting my number of clicks. We did not finish this
part of the project because we were unable to get the clicks to increment properly until Friday morning.

#### Which extensions, if any, did you complete?

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](<img width="1280" alt="screen shot 2017-06-30 at 12 58 43 pm" src="https://user-images.githubusercontent.com/24981999/27750164-e22c5260-5d93-11e7-8867-082af9496db3.png">)

* cleaned up our code by breaking out queries and endpoints.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](<img width="864" alt="screen shot 2017-06-30 at 12 53 32 pm" src="https://user-images.githubusercontent.com/24981999/27750012-3d7951be-5d93-11e7-91c1-4899fc4e75a0.png">)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
This one block of code seems to be handling a lot by putting the responsibility of updating clicks in 
the same get as the short url. Would have liked to break the clicks into a PUT but was unsuccessful. It also broke two tests.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[test suite](<img width="995" alt="screen shot 2017-06-30 at 12 36 58 pm" src="https://user-images.githubusercontent.com/24981999/27749437-da686508-5d90-11e7-9e43-e249e44b5e5a.png">)

#### Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

-----


# Instructor Feedback (Brittany)

## Specification Adherence

**45 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

* Not sure if this was an error introduced today but the sorting functionality does not work. It removes the URLs from the DOM and doesn't re-add them or maintain them in a sorted order.

## User Interface

**15 points**: The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* I know the background wasn't green earlier but this is a little hard to look at haha.

* More obvious error handling would be nice the text all kind of blends in together so when I submit an invalid URL it's difficult to see the error message right away.

## Data Persistence with SQL Database

**20 points**: The application persists data in a SQL database with correct relationships between folders and URLs.

## Testing

**10 points**: Lorem ipsum dolor set amet

* No client-side tests but good coverage of happy/sad paths on server-side routes.

* You never want to [rollback](https://github.com/kamos1/jetfuel/blob/master/test/routes.spec.js#L36-L40) your database during tests. That would potentially put your schema in an out-of-date state and you'd be testing against the wrong data structure. You're essentially undo-ing the rollback right away by calling `migrate.latest` on line 30, so what good is this doing you anyway?

## JavaScript Style

**12 points:** Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

* If `receiveFolders` is a GET request to the server, it does not need to be wrapped in [document.ready](https://github.com/kamos1/jetfuel/blob/master/public/scripts.js#L1-L3). It is not logic that depends on the DOM being ready.

* An ID of `button` is kind of [vague](https://github.com/kamos1/jetfuel/blob/master/public/scripts.js#L5). What does the button do? I'm assuming there is more than one button on the page.

* These two [functions](https://github.com/kamos1/jetfuel/blob/master/public/scripts.js#L24-L38) are pretty duplicative. I bet they could be refactored to be a little more dynamic ;)

* Why are we using [.ajax](https://github.com/kamos1/jetfuel/blob/master/public/scripts.js#L66-L86) in some places and fetch in others and [.get](https://github.com/kamos1/jetfuel/blob/master/public/scripts.js#L175-L183O in others?

* Looping through folders like [this](https://github.com/kamos1/jetfuel/blob/master/public/scripts.js#L90-L105) and doing a DOM manipulation on each loop is slow. DOM manipulations are expensive and you want to do as few manipulations as possible. A better solution for appending elements like this would be to use Document Fragments.

* [This](https://github.com/kamos1/jetfuel/blob/master/routes/queries.js#L101-L109) would be nice in the ES6 shorthand syntax ;)

* Nice breaking out of routes/queries/server file but it would be nice to contain all of these within their own `server` directory rather than at the root of the application.

## Workflow

**15 points**: The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

* Most commits are small with relevant code; some instances where they handle a bit more than they should but changesets and history are generally readable.


### To get a 3 on this project, you need to score 110 points or higher
### To get a 4 on this project, you need to score 135 points or higher

# Final Score: x / 150
