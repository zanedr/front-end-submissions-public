# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/devthehuman/jet-fuel)

#### Link to the Deployed Application
[heroku](https://dd-sh-jetfuel.herokuapp.com/)

#### Provide a Screenshot of your Application
![screenshot](https://github.com/devthehuman/jet-fuel/blob/master/app/assets/images/screenshot.png)

## Completion

#### Were you able to complete the base functionality?

If not, explain what is missing and why.
  * Everything except sorting by visits/date added was completed. We struggled for a while with getting the visits column for each link to increment, and that functionality still isn't working despite our best efforts. 

#### Which extensions, if any, did you complete?
  * N/A
# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/devthehuman/jet-fuel/blob/master/server.js#L92-L105)

* Why were you proud of this piece of code?
  * I'm proud of this particular block of code (even though the increment isn't working) because it required me to do a lot of reading/research on how to redirect to a different url using Express/Knex. Even though the entire route isn't behaving the way I'd like, I learned a lot in the process.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/devthehuman/jet-fuel/blob/master/app/index.js#L80-L94)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
  * I don't feel awesome about this code because it made sorting by visits much more challenging than it needed to be, to the point where we didn't have enough time to refactor it to make it work. It was really difficult to write other functions that took the links array and manipulated it before appending to the folder, as well as functions that would clear the folder out and make the call again. Overall, if we had made this piece more modular and functional from the get-go, it would've made our lives a whole lot easier. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test suite](https://github.com/devthehuman/jet-fuel/blob/master/app/assets/images/test-screenshot.png)

#### Please feel free to ask any other questions or make any other statements below!
  * We gave testing our best shot, but were left confused as to why certain ones weren't passing and required the beforeEach/afterEach to be nested within the describe blocks while others did not. Any comments on why our tests aren't passing or any point to the appropriate docs would be awesome. Overall, I don't feel like this represents my best work because of how much time I spent debugging, but I sure did learn a ton and I'm happy about that.

Anything else you wanna say!

-----


## Instructor Evaluation Points (Robbie)

### Specification Adherence

<!-- * **50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use. -->

*Bugs need to be fixed*
- _Redirect does not work on production (redirecting to localhost...)_
- I can submit a link to a folder that doesn't exist, and there is no error or feedback
- If I add a folder, it doesn't appear until refresh...shouldn't have to refresh the page at any point - same with links added to folders
- Sorting links hides some of the links being sorted (and changes styling of shortened URL)

### User Interface

<!-- * **15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.
* **7 points** - The application shows effort in the interface, but the result is not effective. The evaluator has some difficulty using the application when reviewing the features in the user stories.
* **0 points** - The application is confusing or difficult to use. -->

- The links rendering in front of the folder is...not ideal. Hard to read.
- As a new user, not sure where to start and what section of the form does what exactly
- Entering an invalid URL in the form clears the form, which can be annoying to type everything in again instead of just editing characters
- [These are forms](https://github.com/devthehuman/jet-fuel/blob/master/app/index.html#L13-L21), use the form element

### Data Persistence with SQL Database

* **20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

- Good schema in the migration
- Would be nice to see more than one folder and link in the seeds, better for testing too

### Testing

* **15 points** - Project has a running test suite that tests and multiple levels but fails to cover some features. All controller actions are covered by tests. The application makes some use of integration testing.

- [This](https://github.com/devthehuman/jet-fuel/blob/master/test/routes.spec.js#L33-L48) testing `beforeEach` and `afterEach` is not what you're looking for. You want to run migrations once when you run the test suite and then re-seed before each test. I'm guessing you got guidance from [this blog post](http://mherman.org/blog/2016/04/28/test-driven-development-with-node/#.WVxKZdPyusx), which is not a good approach.
- Good sad path [here](https://github.com/devthehuman/jet-fuel/blob/master/test/routes.spec.js#L73)
- Why is [this](https://github.com/devthehuman/jet-fuel/blob/master/test/routes.spec.js#L129-L134) here?
- Be more descriptive [here](https://github.com/devthehuman/jet-fuel/blob/master/test/routes.spec.js#L181) about what the test is doing
- [This](https://github.com/devthehuman/jet-fuel/blob/master/test/routes.spec.js#L203) should probably be a 404 response because the resource is not found even though the request is well-formed

### JavaScript Style

* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.

- The risk of using [this particular hash](https://github.com/devthehuman/jet-fuel/blob/master/app/index.js#L63) is that you could end up with duplicate shortened URLs
- Always use a `catch()` with fetch for error handling, like [here](https://github.com/devthehuman/jet-fuel/blob/master/app/index.js#L15-L19) and other fetch calls
- The fetch API considers a 404 response successful, which won't be handled through a `catch()`, so make sure you account for this when using fetch
- When appending elements to the DOM, especially in a loop, you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.
- Good edge case [here](https://github.com/devthehuman/jet-fuel/blob/master/server.js#L44-L46)
- [This](https://github.com/devthehuman/jet-fuel/blob/master/server.js#L67) is not typical to only send an ID back, usually it is the whole object unless you are hiding sensitive info
- [This console.log](https://github.com/devthehuman/jet-fuel/blob/master/server.js#L111) should go within the `app.listen` because that is actually the point that the app is ready on that port

### Workflow

* **20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.


- *Do not* commit your node module to GitHub - always have this directory listed in a `.gitignore` file. Add the gitignore right away, as soon as you `git init`.
- A little worried about the lopsided commits, but I know Spencer was gone for some on the project

## To get a 3 on this project, you need to score 110 points or higher
## To get a 4 on this project, you need to score 135 points or higher

# Final Score: x / 150 Need to fix bugs in production.