# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)


------

# Basics

#### Link to the Github Repository for the Project
[JetFuel](https://github.com/DanGrund/jetFuel/issues/25)

#### Link to the Deployed Application
[heroku deployment calm-temple-36519](https://calm-temple-36519.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Limbo](https://github.com/DanGrund/jetFuel/commits?author=mlimberg)

-[Dan](https://github.com/DanGrund/jetFuel/commits?author=DanGrund)

#### Provide a Screenshot of your Application

![screenshot](http://i.imgur.com/Snyupgi.png)

## Completion

#### Were you able to complete the base functionality?
* Yes 

#### Which extensions, if any, did you complete?

- N/A

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code block in repo](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/server.js#L98-L119)

* Why were you proud of this piece of code?

This is the end point for shortened URLs, that handles redirects and visit counter. it's fancy. 

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/db/migrations/20170316143038_initial.js#L14)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

this is the single line in our db that handles the time created for the shortened url. we tried every single knex method for timestamping and couldn't get any of them to work, and Date.now is too big to be an integer in postgres so we ended up just stringifying date.now and storing as a string  ¯\_(ツ)_/¯

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![tests](http://i.imgur.com/9uo3GG7.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!
Testing the server proved to be difficult because we used a test db in heroku. The beforeEach and AfterEach seemed to be updating the seed records appropriately but then the test to get all folders would say it has a length of 0 instead of 2. Then, when post was added it would successfully push to DB and throw off the get test because it now had length 3 instead of 2. Didn't get it working 100% but we are able to pass tests when we control the # of records in the test DB. 

-----

# Instructor Feedback - Brittany

## Specification Adherence

* 50 points: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

Good job handling all different URL formats :party-popper:


User Interface
* 20 points - The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor without guidance from the developer.

Cool drippy bloody logo and I like that you played around with CSS transitions for your folder buttons. Was able to use the app without any hassle.

Nitpicks:

* I'd style your add folder button and shorten URL button with the same CSS. Often times I'll make a single class named `call-to-action` or `cta` to style elements like buttons that are clickable. 'Call to action' is the jargony, product manager term for elements that should call a user's attention because they can interact with them. 
* An ascending/descending arrow in the table headers for visits/dates would be nice so we have a quick and persistent visual indicator of what sort order we're currently in. Less important here but more important when you have large datasets and there may be multiple sort conditions being met simultaneously.
* Better placeholder text for the URL input field might be `http://www.example.com` or an indication of how a user should actually format and enter their url. Also less important here because you are gracefully handling all URL formats for the user.

## Data Persistence with SQL Database

* 20 points - The application persists data in a SQL database but with correct relationships between folders and URLs.


## Testing

* 15 points - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

[Just stub some it blocks in here even if you dont have time to actually write the assertions](https://github.com/DanGrund/jetFuel/blob/master/test/app-test.js)


## JavaScript Style

* 13 points - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

Is this [put](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/server.js#L121-L136) actually being used? It looks like it's just handling updating the visit count but it also seems you're doing that in your [get](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/server.js#L109) request as well. Either way, if you are just trying to update a single property on a data object, you'd want to use a `PATCH` instead of a `PUT`. A `PUT` replaces the entire data object (therefore requiring you to have all the data points associated with it), whereas a `PATCH` allows you to just pass in and update a single property.

Hell yeah for using the correct [status codes here](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/server.js#L87)

[Ya'll are weird. +1 point for legitimate JavaScript Style](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/server.js#L140)

Some day, we will teach you all about proper error handling. But for now, just know that [this is not proper](https://github.com/DanGrund/jetFuel/blob/e77c1e9398192824d4a07c9f20cbd4881a5988be/server.js#L116).

Make sure you're handling any Promise errors with your [fetch requests](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L5-L9) with `.catch()` blocks.

Making an API request does not require that the document be ready. [Your loadFolders request](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L12) can be kicked off right away. Only functions that rely on the DOM right away (e.g. click handlers/element selectors) need to be wrapped in `document.ready()`. In this app (because it's so teensy), it's pretty safe to assume that the document will be ready by the time you receive your data response of folders and you can successfully render your folders to the DOM. If you were hesitant to make that assumption, you could do a check within your `.then()` block before trying to render them to the DOM. 

Whenever we have a [loop](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L16-L20) that does DOM manipulations, we should consider using a [Document Fragment](https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment) to build up the HTML first. DOM Manipulations are the slow part of the front-end and if we were making 1,000 `.append()` calls to update the DOM our browser would eventually lock up. Doc Frags allow you to build up a bunch of 'virtual' HTML first within your loop, then append it all at once at the very end.

[This](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L30) is kind of a weird place to kick off this function. Generally, I put all the function calls that are happening immediately on page load at the bottom of my file so I can interpret what's happening as soon as I load the page all in one place. It's a little hidden when it's here in the middle of the file and I wouldn't recognize that it was being called if I hadn't looked at things line-by-line.

Hmmm, [this](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L33) looks a little odd to me. Using a template string for an input variable? What is the type of this `input` value that we're passing in? A jQuery element? A string selector? 

Better names for the [sorting functionality](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L36-L44) would be ascending/descending (or asc/desc) rather than up/down. Up/down is a more directionaly/geographical/spatial? descriptor rather than an ordering descriptor.

You can have access to the [element](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L47) that's been clicked on with `$(this)`, rather than continuing to access `$('#visits')`. As your code is now, jQuery has to continue to search the DOM for that visits selector every time you reference it rather than just re-using the clicked element with `$(this)`. 

Move [this](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L52) out of your conditionals. You're toggling the class no matter what, so just end that entire function with the toggle.

Both of these [functions](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L46-L64) could probably be refactored into one, lots of repeat code here. Add a data attribute or an extra class to determine if they clicked on date or visits and conditionally sort based on that value.

[No](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L70)

You are using the `toggle` method earlier in this file, and then using add/remove class [here](https://github.com/DanGrund/jetFuel/blob/master/src/index.js#L99-L103)

## Workflow

* 20 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Nice commit history, easy to read and follow along. Could use a little additional consistency in your messages (advice I give to everyone). A lot of teams will typically follow [these rules](https://www.google.com/search?q=writing+good+commit+messages&oq=writing+good+commit+messages&aqs=chrome..69i57j0l2.2566j0j7&sourceid=chrome&ie=UTF-8). Commits are nice and tiny with mostly relevant code. Good use of issues PRs and branches.

Points: 137 / 150
