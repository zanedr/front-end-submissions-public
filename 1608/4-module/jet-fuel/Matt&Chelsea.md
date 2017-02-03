# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

------

# Basics

#### Link to the Github Repository for the Project
[Repo](https://github.com/MilkMan90/JetFuel)

#### Link to the Deployed Application
[Application](https://jetfuelz.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Matt Kauffman](https://github.com/MilkMan90/JetFuel/commits/master?author=MilkMan90)

-[Chelsea Skovgaard](https://github.com/MilkMan90/JetFuel/commits/master?author=ChelseaSkovgaard)

#### Screenshot of your Application
<img width="716" alt="screen shot 2017-01-26 at 9 07 47 pm" src="https://cloud.githubusercontent.com/assets/18074889/22360299/c88bccc0-e40b-11e6-8859-2d0dd7fb5c7f.png">

## Completion

#### Were you able to complete the base functionality?

* Yes

#### Which extensions, if any, did you complete?

* No

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
* Why were you proud of this piece of code?
This was our own extension of generating a random string for the shorturl of our application.
```
function generateRandomString() {
  let characterArray = []
  for(var i = 0; i < 6; i++){
    characterArray.push(String.fromCharCode(97 + Math.floor(Math.random()*25) +1 ))
  }
  return characterArray.join('')
}

app.post('/api/urls', (request, response) => {
  const { actualurl, clickCount, folder_id} = request.body;
  let string = generateRandomString();

  database('urls').select('shorturl').then(function(res){
    console.log(res);
    let array = res.map((item)=>{
      return item.shorturl
    })
    while(array.includes(string)){
        string = generateRandomString();
        console.log(string);
    }
```

#### Link to a specific block of your code on Github that you feel not great about
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

  We feel good about most of our code. One of our challenges was when we had to change how the ids of our urls were being created and had to drop and replace a column using migrations.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
  GET /api/folders
    ✓ should return all folders (48ms)

  POST /api/folders
    ✓ should create a new folder (38ms)

  GET /api/urls/:folder_id
    ✓ should return urls associated with a folder

  POST /api/urls
  [ anonymous { shorturl: '2' },
  anonymous { shorturl: '3' },
  anonymous { shorturl: '1' },
  anonymous { shorturl: 'lbisbm' },
  anonymous { shorturl: 'zxfhvv' },
  anonymous { shorturl: 'hwlboe' } ]
    ✓ should add a url

  DELETE /api/urls/:id
    ✓ should return urls associated with a folder

  GET /api/urls
    ✓ should return all the urls


  6 passing (146ms)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!

-----

# Instructor Feedback

- Points: (base 150)

**129/150** - so entire project is a 3!

Notes from Alex & Meeka

## Base Expectations

Everything is present except that sort by popularity and date is unclear, we're not certain through the UI if that is implemented. 

In looking at the code, looks like sort does not take date into account.

So for that reason, **42/50**

If you add this functionality, deploy it and link it in this PR - we can bump that score.

### Bugs and UI nitpicks

These are nitpicks and we're sure you know some of them - this what we would suggest you fix before you put this in a portfolio.

1. Is `https://` hardcoded? This is already a problem for sites that aren't using `https://`
  - if you had espn.com, for example, the redirect fails
  - Safer to just use `http` most likely - just delete the `s`
  - [Problem Code Is Here](https://github.com/MilkMan90/JetFuel/blob/master/server/server.js#L69)

2. Make sure the form field clears itself after submit
  - No indication in the UI when the submit works in general
    - For example, if you have a bunch of folders, and then you add a new folder - the folder appears below the fold so the user has no idea that things worked

3. When adding a URL, doesn't automatically show in the UI that it belongs to a folder. Have to do a hard refresh.
- Is related to [this piece of code](https://github.com/MilkMan90/JetFuel/blob/master/src/components/App.js#L65)

4. Confusing: When you hover over a folder, suggestion to highlight per URL and not the entire folder.

5. Sort: It's unclear what the sort is actually sorting on. Folder, or Url - is it sorting by popularity or date?

6. User should be able to see all folders (within reason) without scrolling. Consider if logo taking up half of the screen is a good use of space. 

7. Think about pagination when user builds up a ton of folders. Have an answer to how that would work for interviews, you don't have to fix it for this project though given the use case.

## User Interface

**15 points** - The application has many strong pages/interactions, but a few holes in lesser-used functionality.

## Data Persistance with SQL Database

**20 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.

It's clear you looked in the docs to figure out best practices in [things like this](https://github.com/MilkMan90/JetFuel/blob/master/server/server.js#L60)

## Testing

**20 points** - Project has a running test suite that exercises the application at multiple levels including server and client tests.

Good job of hitting every end point and every method - impressive without the lesson and with only a week AND with adding the DB. 

[This Delete Test](https://github.com/MilkMan90/JetFuel/blob/master/test/routes.spec.js#L70-L81) doesn't actually test that anything was deleted. You should consider checking the test database that whatever you just deleted isn't there. If you want to avoid hitting the DB in the test, make another get request and make sure that the deleted folder is not present.

We would really like to see code broken out of the server, so you could unit test it, but will not deduct points for this.

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


## JavaScript Style

**12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

There were two major bugs - `https` hard coding and no sorting by created date.

We would really, really, really like to see more fundamental refactoring. See notes below. Given the time limit, we're impressed you got the thing done - but the level of code living in one file that could be broken out will not be acceptable, most likely, where you work next. For example, in Form.js, the return statement should only have:

```
  <div className="Form">
        {createNewFolder()}
        {createNewURL()}
   </div>
```

In App.js - any time there is a fetch call, all those fetches should be in their own folder. 

[These lines of code](https://github.com/MilkMan90/JetFuel/blob/master/src/components/App.js#L28-L49) are the right idea - but should not live in this file. [These lines of code](https://github.com/MilkMan90/JetFuel/blob/master/src/components/App.js#L16-L25) should be in their own function, named GetAllFolders (to match your style) and should also not live in this file.

## Server Side Code

[Route route](https://github.com/MilkMan90/JetFuel/blob/master/server/server.js#L117-L119) should be the first route. If you have a get route that is /{param} you would never get to your route route. Basically, route order matters. So if you do, for instance, a wildcard route that would need to be below specific routes. Let us know if that is unclear.

Consistency with api route naming is important. For example, [this route](https://github.com/MilkMan90/JetFuel/blob/master/server/server.js#L93) should match your other api route style and be `api` and not `a`

This style of [helper function](https://github.com/MilkMan90/JetFuel/blob/master/server/server.js#L49-L55) should not live in your main server file. The server file should only contain the server, routes and you should try to pull anything else out into additional files that are required in. Reason is that this file is essentially your skeleton and it both gets big quick and should be easy to scan and understand.

We love you you require MD5 and then write your own random string generator function (you should probably use MD5 tho)

## Client Side Code

index.js is clean, good work

Good work separating components

Do ya'll really [hate spaces](https://github.com/MilkMan90/JetFuel/blob/master/src/components/LinkList.js#L33)? 

Would strongly suggest you have an .eslintrc or .jshintrc that defines these types of preferences that you pull into your future projects. Can give you more detail on that if you need it. But basically, the more you can make your preferences known for style, the easier it is not just assume it's a lazy choice. We're probably going to put together a lesson on this - but thing back to Tae's lesson from Mod 2 - Meeka

## Workflow

**20 points** - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Lots of commits - 12 PRs - good PR naming - sounds like team dynamic was great. Screenshot in the readme! 
