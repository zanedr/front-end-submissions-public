# Real Time Submission Form
### For Kinan Whyte

[Project Spec](http://frontend.turing.io/projects/real-time.html)

------

# Basics

#### Link to the Github Repository for the Project
[My Repo](https://github.com/kswhyte/real-time)

#### Link to the Deployed Application
[My Application](https://poll-bui1der.herokuapp.com/)

#### Link to My Commits in the Github Repository for the Project

-[My Commits](https://github.com/kswhyte/real-time/commits/master)

#### Provide a Screenshot of your Application
<img width="719" alt="screen shot 2017-02-03 at 2 59 49 am" src="https://cloud.githubusercontent.com/assets/13802107/22587142/a90112d6-e9bd-11e6-9811-68d4449f3c6f.png">

<img width="718" alt="screen shot 2017-02-03 at 2 59 31 am" src="https://cloud.githubusercontent.com/assets/13802107/22587115/83337454-e9bd-11e6-8938-71214e31df44.png">

## Completion

#### Were you able to complete the base functionality?
Yes

#### Which extensions, if any, did you complete?

Extension attempt: When creating a new poll, you have the ability to set an end date and time to automatically close the poll (you can visit the poll to see results but no one can vote).

I made an attempt at this, not wanting to delete the progress that I made. I honestly just ran out of juice at the end and could not muster up brain power to finish tackling what I feel won't be too hard to implement.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[proud](https://github.com/kswhyte/real-time/blob/master/public/vote-page/scripts/vote.js#L12)

* Why were you proud of this piece of code?

I was quite proud of all the lines of code that came together in synchronicity, not so much any in particular, but if I have to pick, I was happy about pulling out responsibilities in 3 separate functions here upon document.ready in which 2 api calls are made, rendering respective html that includes pulling out data into the html to make it dynamic. the getParameterByName is something that we can trace to a stack overflow post, shared with much of the class, that is pretty handy too.

#### Link to a specific block of your code on Github that you feel not great about
[not so proud](https://github.com/kswhyte/real-time/blob/master/public/vote-page/scripts/vote.js#L79)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I am not happy about having to set up event listeners on all of these options. I feel like there is a more dynamic means of accomplishing this. I'm sure some thinking ouside of a burned out state may lender some refactoring-super powers.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

<img width="619" alt="screen shot 2017-02-03 at 3 21 55 am" src="https://cloud.githubusercontent.com/assets/13802107/22587721/15dfba68-e9c0-11e6-83c0-2ac7c2d4c86b.png">

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'
[testing an edge case](https://github.com/kswhyte/real-time/blob/master/test/test.js#L6)
-----

#### Please feel free to ask any other questions or make any other statements below!
Wooohoo! First time to sleep at Turing tonight! should be wakign up with a nice hat-head, unclean teeth, the same clothes as i wore for potentially 48 hours, and high-spirits for actually finishing this difficult project and turning in something I believe is worthy and I am proud of!
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

Awesome job Kinan for completing all of the features, I can tell you put a lot of effort into this project. It's a simple, clean, easy to use app that works. I especially like that you can see all of the active polls on the home screen to easily navigate to each of them.

One thing that isn't in the spec but you should be aware of is that when I vote for one poll, it actually casts that vote for all polls. So if I vote 'A' for one poll, and other vote I visit will have the 'A' option voted for.

This is something that I'm seeing in a lot of projects and I need to do a better job of teaching, but basically what you want to do is emit a vote on a poll-specific channel instead of a general voteCast channel. For instance:

```js
// Current client-side code
$('#option3').on('click', (e) => {
  let optionID = e.target.classList[1]
  let profileImg = localStorage.getItem('profileImg')
  socket.emit('voteCast', optionID, profileImg)
})

// What you could do instead ...
$('#option3').on('click', (e) => {
  let pollId = //Grab the poll id from the url or a html tag
  let optionID = e.target.classList[1]
  let profileImg = localStorage.getItem('profileImg')
  // Emit on a poll-specific channel.
  socket.emit('voteCast:${pollId}', optionID, profileImg, pollId)
})

// Current server-side code
socket.on('voteCast', (optionID, profileImg) => {
  updateVoteResults(profileImg)
  app.locals.voteResults.push({
    optionID,
    profileImg
  })
  io.sockets.emit('voteCount', app.locals.voteResults)
})

// What you could do instead ...
socket.on('voteCast:${pollId}', (optionID, profileImg, pollId) => {
  updateVoteResults(profileImg)
  app.locals.voteResults.push({
    optionID,
    profileImg
  })
  // Emit back out to a poll specific voteCount channel
  io.sockets.emit('voteCount:${pollId}', app.locals.voteResults)
})
```

### Code Quality (JavaScript)

* 40 points - Developer writes code that is exceptionally clear and well-factored. Application is expertly divided into logical components each with a clear, single responsibility. There are a few instances of duplication, unused code and exposed sensitive user information.

Overall I thought your code was very well refactored, in clean small functions broken into specific files. You handled authenticating correctly using localStorage and you had error messaging on sad paths. Things that really liked:

```js
// In server.js file, your endpoints are very simple (not much code which makes it easy to read quickly) and respond with the correct files or data.

app.get('/polls', (req, res) => {
  res.sendFile(__dirname + '/public/create-poll.html')
})

app.post('/polls', (req, res) => {
  const poll = req.body
  poll['id'] = md5(poll.id)

  app.locals.pollForms.push(poll)
  res.send(app.locals.pollForms)
})

app.get('/vote/*', (req, res) => {
  res.sendFile(__dirname + '/public/vote-page/vote-page.html')
})

app.get('/api/v1/polls', (req, res) => {
  let polls = app.locals.pollForms
  res.send(polls)
})

// In vote.js, I like how you break your code into single-responsibility functions that are well named.

const getCurrentPoll = (pollID) => {
  $.get(`/api/v1/polls/${pollID}`)
    .then(poll => {
      renderCurrentPoll(poll)
    })
}

const renderProfileImgs = () => {
  $.get('/api/v1/vote_results')
    .then(results => {
      console.log('results', results)
      results.forEach((userSelection) => {
        $(`#option${userSelection.optionID}`).append(
          `<img class='user-profile-img' src='${userSelection.profileImg}'>`
        )
      })
    })
}
```

Things I would like to see improved:

```js
// In vote.js, this could be one click listener on '.poll-option-button' and you grab the optionId as a data-attribute in the button html. When you see the same function four times with the exact same code except for the id name, it's highly likely you can refactor into one function.

$('#option1').on('click', (e) => {
  let optionID = e.target.classList[1]
  let profileImg = localStorage.getItem('profileImg')
  socket.emit('voteCast', optionID, profileImg)
})

$('#option2').on('click', (e) => {
  let optionID = e.target.classList[1]
  let profileImg = localStorage.getItem('profileImg')
  socket.emit('voteCast', optionID, profileImg)
})

$('#option3').on('click', (e) => {
  let optionID = e.target.classList[1]
  let profileImg = localStorage.getItem('profileImg')
  socket.emit('voteCast', optionID, profileImg)
})

$('#option4').on('click', (e) => {
  let optionID = e.target.classList[1]
  let profileImg = localStorage.getItem('profileImg')
  socket.emit('voteCast', optionID, profileImg)
})

// You should delete files like routes.js that are completed commented out or unused and you should never expose API client ids. You have them in both .env.example and auth0-variables.js files and either are in your .gitignore file. Just be careful of this in future projects. Check out the npm package dotenv to keep confidential info in your .env file and then call them with process.env.ENV_VARIABLE
```

### Testing

* 17 points - The application has all routes tested with sad path tests but NO unit tests. There are no tests failing testing on master.

Great job testing all of the backend routes but I would love to see unit tests. You should test functions like the one below that do a lot of string manipulation and could have a lot of potential inputs:

```js
const getParameterByName = (name, url) => {
  if (!url) {
    url = window.location.href
  }
  name = name.replace(/[\[\]]/g, '\\$&')
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url)
  if (!results) return null
  if (!results[2]) return ''
  return decodeURIComponent(results[2].replace(/\+/g, ' '))
}
```

### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Looking at your commit history and PR's, it's clear you know how to keep your progress organized and well documented.

### Extensions

* 0 points (but great attempt) - When creating a new poll, you have the ability to set an end date and time to automatically close the poll (you can visit the poll to see results but no one can vote).

I'm really glad you attempted to implement this feature. If you ever have extra time, you should finish it and think about how you would handle people voting in different time zones.

## Total Score:  132 / 150

Great job on this project Kinan!
