### JetFuel Submission

[JetFuel GitHub](https://github.com/zkc/JetFuel)

[JetFuel Production](http://zucknastyjetfuel.herokuapp.com/)

[JetFuel Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

[Julian Kyer Commit History](https://github.com/zkc/JetFuel/commits/master?author=juliankyer)

[Kyle Zucker Commit History](https://github.com/zkc/JetFuel/commits/master?author=zkc)

#### Completion
We were able to complete the base functionality but no extensions.

#### Code Quality
[Happy Code A](https://github.com/zkc/JetFuel/blob/cecbad64cd4d2f92e07e6b60c86e62f840be9205/server.js#L18-L28)

I just like this piece of code. It's basically from one of the lessons, but it puts something visual on the page right away, and shifted my perspective on how the app is structured.

[Happy Code B](https://github.com/zkc/JetFuel/blob/cecbad64cd4d2f92e07e6b60c86e62f840be9205/public/index.js#L45-L48)

I'm throwing this in there too, because I'd always wondered how URL-shortening services worked, and where those seemingly random strings came from. Didn't realize it was this easy.

[Sad Code](https://github.com/zkc/JetFuel/blob/cecbad64cd4d2f92e07e6b60c86e62f840be9205/server.js#L52-L61)

I think kinda put error-handling on the back-burner as we were trying to figure things out, and that bums me out.

[Unhappy Path Test](https://github.com/zkc/JetFuel/blob/913840563cb96e2d497fd62a1f176149a22f0348/test/routes.spec.js#L131-L144)

#### Tests
![image](https://cloud.githubusercontent.com/assets/5368526/25758992/e969666c-318d-11e7-993e-b5328065aa64.png

#### App Screenshot
![image](https://cloud.githubusercontent.com/assets/5368526/25758539/2267a78c-318c-11e7-9d7b-e41caec7d5c4.png

I enjoyed this project, learning how to hook everything up to build a real app was cool. The backend stuff hurt my brain a little bit, but I like the possibilities it unlocked.

## Instructor Evaluation Points (Robbie)

The following set of points are distributed at the discretion of the instructor.

### Specification Adherence

**50 points**: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

### User Interface

**15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

* A little confusion in the user flow since the URL shortener and the folder to add the URL to appear to be in two separately colored elements - seems like two different form groups that could be unrelated to each other.
* Would expect fields to clear when the URL is successfully submitted (same with folder submit)
* Would like to see an arrow or some kind of indicator on the `Date` and `Clicks` buttons to show what the order is
* You have to refresh the page in order to see the visits count increase (or you have to switch between folders) - would be nice to alter the visits client-side too
* Minor bug: some kind of validation on the url - you can put in `jdhfksjhdfkjhs` and it will try to redirect you unsuccessfully
* Not sure which category this will go in for this rubric, but [so many divs](https://github.com/zkc/JetFuel/blob/master/public/index.html) - consider some more semantic HTML tags to use

### Data Persistence with SQL Database

**20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

* Since the [folder names](https://github.com/zkc/JetFuel/blob/master/db/migrations/20170504081852_initial.js#L6) must be unique, you can add some database validation for uniqueness and null values

### Testing

**10 points** - Project has sporadic use of tests and multiple levels. Not all controller actions are tested. There are little or no attempts at integration testing.

* [For this test](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L17-L19), could test for some kind of content specific to that page
* [Here](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L39-L42), you should either need a `.then()` or `return` and not both to fulfill the promise.
* Not testing for any content [here](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L61-L63)...would expect to see something about the folders in the database (properties and values), almost testing for content in [this test](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L88-L90)...you know what should be in the database according to your seed file or POST request.
* Want to see a sad path for folders POST too [here](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L68), possibly empty or missing content in the body, also folders must be unique
* Why the need for the timeout [here](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L98)?
* [This](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L100) is a good test, can also add type of response you expect to get in [here](https://github.com/zkc/JetFuel/blob/master/test/routes.spec.js#L111) (like JSON)
* It would be great to see a test for a server-side redirect in your test suite

### JavaScript Style

**12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

* I see now that you're doing some client-side validation of folder name uniqueness [here](https://github.com/zkc/JetFuel/blob/master/public/index.js#L7) - that's good
* Good practice to have `catch()` for errors when [using fetch](https://github.com/zkc/JetFuel/blob/master/public/index.js#L37)
* Using a library like [moment](https://www.npmjs.com/package/moment) will make your life a lot easier especially when [dealing with dates](https://github.com/zkc/JetFuel/blob/master/public/index.js#L44-L52)
* When appending elements to the DOM, especially in a loop ([like here](https://github.com/zkc/JetFuel/blob/master/public/index.js#L59-L69)), you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need before adding it to directly to the DOM.
* Can probably just prepend an array of elements [here](https://github.com/zkc/JetFuel/blob/master/public/index.js#L133-L135) instead of using a `forEach` according to the jQuery docs for [prepend](http://api.jquery.com/prepend/).

* In general, it's a good practice to bring your API routes into a separate router file to make your [server file](https://github.com/zkc/JetFuel/blob/master/server.js) more readable - see [express.Router](https://expressjs.com/en/guide/routing.html#express-router)
* Good status code response [here](https://github.com/zkc/JetFuel/blob/master/server.js#L48) - 201!
* The `api/v1/folders/:folderID` [resource](https://github.com/zkc/JetFuel/blob/master/server.js#L58-L67) should only send back information about the folder with primary key `folderID`, not links contained within that folder. You should use a GET to `api/v1/folders/:folderID/links` to respond with the links for a particular folder.
* Express has some [middleware](https://expressjs.com/en/starter/faq.html) already available to you to handle [if a page is not found](https://github.com/zkc/JetFuel/blob/master/server.js#L19-L22) (404) or if you have a server error (500)
* Good error handling [here](https://github.com/zkc/JetFuel/blob/master/server.js#L96) if the resource isn't found - would like to see more of this sad path style.
* Be sure to specify a response code for [the redirect](https://github.com/zkc/JetFuel/blob/master/server.js#L86) - there are a few different kinds of redirects depending on if the redirect is permanent, temporary, or if you want the browser to cache it.

### Workflow

**15 points** - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

* Good, small commits but would like to see more conversation in the PR workflow - adding context to your PRs for the reviewer (in the description).

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 135 points or higher

# Final Score: 122 / 150
