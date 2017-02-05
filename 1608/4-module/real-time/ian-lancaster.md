# Real Time Submission Form

[Project Spec](http://frontend.turing.io/projects/real-time.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project`
[Project Repo](https://github.com/ianlancaster/real-time-polling)

#### Link to the Deployed Application
[Live Deployment](https://real-time-polling-il.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[TeamMate1](https://github.com/ianlancaster/real-time-polling/commits/master)

#### Provide a Screenshot of your Application
![pollApp](https://github.com/ianlancaster/real-time-polling/blob/master/application-screenshot.png?raw=true)

## Completion

#### Were you able to complete the base functionality?
* Yes this application covers all base functionality

#### Which extensions, if any, did you complete?
* I did not complete either of the extensions

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
- [Express POST Testing](https://github.com/ianlancaster/real-time-polling/blob/master/test/index.js#L111-L127)
* I am proud of this code because I was able to figure out how to use supertest and chai together to write a very robust test for the post route with minimal lines.

#### Link to a specific block of your code on Github that you feel not great about
* I wrote and refactored the code as best I can. There is nothing that I can find that I would want to change. I wish I had done the extensions.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![Testing Screenshot](https://github.com/ianlancaster/real-time-polling/blob/master/test-screenshot.png?raw=true)

Unit testing the script files proved impossible without incorporating webpack. jquery is currently loaded via cdn and without loading that script first jquery is undefined in tests. I tried imports, requires, binding, etc.. could not make it work. The server is thoroughly tested though.

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing an unhappy path](https://github.com/ianlancaster/real-time-polling/blob/master/test/index.js#L147-L162)

This tests that express returns an error if a user has an incomplete profile. This functionality makes it a little bit harder to bypass the authentication.

-----

#### Please feel free to ask any other questions or make any other statements below!

It was really hard to get the authentication to work without using query parameters. I could not whitelist wildcard callback URLs, so I had to set up a detour redirect to the login route in order to authenticate. I would love some feedback on in this area. Is this a good way of handling auth?

-----

# Instructor Feedback (from Alex)

## Evaluation Criteria

Alex is an instructor at a seven month developer training program in Colorado. In the middle of a long rant about the merits of CoffeeScript, he wants to check for student understanding. He could pause for a moment and ask the room if they have any idea what he's talking about, but he suspects they'll just smile and nod like they always do. He knows that some students may not want to admit in front of the whole group that they neither understand what Alex is talking about, nor do they particularly care.

- Alex decides to use Crowdsource to poll the room.
- He goes to the site to generate a new poll and adds three potential responses: "This is old hat to me", "I have an okay understanding of this", "I have no idea what you're babbling about".
- He gets back a link to share with others that contains a voting page that shows the options for the poll.
- He drops the link into Slack and his students vote.
- His students need to authenticate themselves before they can vote.
- Alex can see in real time the poll results and a picture of each student next to their response.
- Alex feels pleased when he sees that 100% of his students are absolute masters of everything he has ever taught.


### Concept and Features

Does it have the expected features?

* 50 points - Met expectations as outlined by the user personas, the application is a solid first version. All planned features were delivered and the application is easy to use.

Awesome job on this project Ian. You have all the functionality working properly, your app is very easy to use and has a clean design, plus you list all of the active polls and have the ability to add as many options as you want per poll.

### Code Quality (JavaScript)

* 45 points - Developer writes code that is exceptionally clear and well-factored. Application is expertly divided into logical components each with a clear, single responsibility.

Things I liked:

```js
// Loved how you separated the server.js file with comments. Every endpoint is super simple and clean.


// ------------------------------------
// REST API
// ------------------------------------

app.use(bodyParser.json())
app.use(bodyParser.urlencoded({ extended: true }))
app.use(express.static('public'))
app.use((req, res, next) => {
  res.header('Access-Control-Allow-Origin', '*')
  res.header('Access-Control-Allow-Headers', 'Origin, X-Requested-With, Content-Type, Accept')
  next()
})

app.set('port', process.env.PORT || 3000)

app.locals.polls = {}

app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, '/public/index.html'))
})

app.get('/login', (req, res) => {
  res.sendFile(path.join(__dirname, '/public/login.html'))
})

app.get('/polls/:poll_id', (req, res) => {
  res.sendFile(path.join(__dirname, '/public/polls.html'))
})

app.get('/api/polls', (req, res) => {
  res.json(app.locals.polls)
})

app.post('/api/polls', (req, res) => {
  app.locals.polls[shortid()] = req.body
  res.json(app.locals.polls)
})
```

Also your client-side JS has single-responsibility functions that are well named.

Things I would improve:

I would have liked to seen multiple flat data structures instead of one large object that stored all votes like so:

```js
// Place new vote
app.locals.polls[pollId].options[vote].profiles[uid] = profile
```

That's a lot of chaining and can get difficult to maintain as data requirements get more complex. I would have stored 3 different objects in 3 arrays and used relationships. This way it's much easier to transition to a database and store them with Knex:

```js
 const { polls, options, votes } = app.locals

 const poll = { id, question }
 const option = { id, text, pollId }
 const vote = { id, user, optionId }

// Add poll
polls.push(poll)

// Add option
option.push(option)

// Add vote
votes.push(vote)
```

You should never expose API client ids. You have them in your auth0-variables.js file and it's not in your .gitignore file. Just be careful of this in future projects. Check out the npm package dotenv to keep confidential info in your .env file and then call them with process.env.ENV_VARIABLE.

I'm not exactly sure where you are redirecting to the login route, I couldn't find it but come grab me and walk me through your auth process sometime.

### Testing

* 20 points - The application has all routes tested and tested websocket data. No tests are failing on master and any skipped tests have an explanation of why skipped.

Great test suite for the backend, I liked that you have tests using dummy data sent with web sockets.

To test your client-side code with jQuery, you should download the minified jQuery js file instead of CDN'ing it. Then you can require it like a normal file and you don't have to rely on someone else's server.

### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

It's apparent you know how to a lot of small, focused commits and PR's with clear comments to keep your progress organized and well documented. Great job.

### Extensions

* N/A

## Total Score: 140 / 150

Excellent project Ian, great work.
