# Real Time Submission Form

[Project Spec](http://frontend.turing.io/projects/real-time.html)

------

# Basics

#### Link to the Github Repository for the Project
[My Repo](https://github.com/hilarylewis92/polling-app)

#### Link to the Deployed Application
[My Application](https://real-time-polling-app.herokuapp.com/form/)

#### Link to Your Commits in the Github Repository for the Project

-[My Commits](https://github.com/hilarylewis92/polling-app/commits/master)

#### Provide a Screenshot of your Application
![Screenshot](https://cloud.githubusercontent.com/assets/18403177/22602856/3693519c-ea02-11e6-99b9-7f8a1ecd3ca3.png)

## Completion

#### Were you able to complete the base functionality?
* I have all functionality working except an image linking to each vote.

#### Which extensions, if any, did you complete?


# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Link to code](https://github.com/hilarylewis92/polling-app/blob/master/server.js#L80-L99)

* Why were you proud of this piece of code?
I am proud of this code because I took the time to read the docs and figure out how to grab information from the object and display it on the screen.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code](https://github.com/hilarylewis92/polling-app/blob/master/server.js#L80-L99)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
As you can see, this is the same code I am proud of because I tried really hard to implement the image of each voted within this code but I failed because of the deadline. I also think I can refactor this function to be more simple but I did not have time do do that.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![Screenshot](https://cloud.githubusercontent.com/assets/18403177/22603106/477a671a-ea03-11e6-8761-328f1f1f838e.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!

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

* 35 points - One major feature was sacrificed to meet the deadline but the spirit of the application and baseline functionality was meet.

Great job on getting a working, real-time polling app with authentication. We discussed this already but the major feature missing is having the user picture display when a user votes instead of the vote count. Another bug I encountered is that when I create a second or third poll it redirects me to the first poll I created so that's the only poll I can vote on.

One thing that isn't in the spec but you should be aware of is that when I vote for one poll, it actually would cast a vote for all polls. This is something that I'm seeing in a lot of projects and I need to do a better job of teaching, but basically what you want to do is emit a vote on a poll-specific channel instead of a general voteCast channel. For example:

```js
// Current client-side code
for (let i = 0; i < buttons.length; i++) {
  buttons[i].addEventListener('click', function() {
    socket.send('voteCast', this.innerText)
  })
}

// Could be this instead ...
for (let i = 0; i < buttons.length; i++) {
  buttons[i].addEventListener('click', function(e) {
    const pollId = e.target.id // Grab id of poll from button or some html attribute
    socket.send('voteCast:${id}', this.innerText)
  })
}
```

### Code Quality (JavaScript)

* 35 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.

Things I liked:

```js
// Very concise, clean functions that only do one thing and you have a single event listener for all buttons to vote instead of an event listener for each button. Also your app.js file code for authenticating users is very clean and easy to read.

on('usersConnected', (count) => {
  connectionCount.innerText = 'Connected Users: ' + count
})

socket.on('statusMessage', (message) => {
  statusMessage.innerText = message
})

for (let i = 0; i < buttons.length; i++) {
  buttons[i].addEventListener('click', function() {
    socket.send('voteCast', this.innerText)
  })
}

socket.on('voteCount', (votes, user) => {
  let votedFor = Object.keys(votes).map(vote => {
    return vote + ':' + votes[vote]
  })
  voteCount.innerText = votedFor
})
```
Things I would like to see improved:

```js
// Because you were trying to count the vote totals instead of returning the user image, it made your code more complicated than it needed to. I like how you used reduce in this countVotes function but I would have moved the reduce code into it's own function called callVotes.

const countVotes = (votes) => {
  let voteArr = []
  for (key in votes) {
    if(votes.hasOwnProperty(key)) {
      var value = votes[key]
      voteArr.push(value)
    }
  }

  let voteCount = voteArr.reduce((allVotes, vote) => {
  	if(vote in allVotes) {
  		allVotes[vote]++
      }
  	else {
  		allVotes[vote] = 1
      }
  	return allVotes
  }, {})
  return voteCount
}

// You should never expose API client ids. You have them in your auth0-variables.js file and it's not in your .gitignore file. Just be careful of this in future projects. Check out the npm package dotenv to keep confidential info in your .env file and then call them with process.env.ENV_VARIABLE.

// I think the bigger issue in this app is thinking about how you want to structure your data. You would want to have an app.locals.polls array to store all polls, an app.locals.choices array to store all choices and include the pollId in each choice, and an app.locals.votes array to store all votes that include a choiceId and user image.
```


### Testing

* 17 points - The application has all routes tested but NO unit tests. There are no tests failing testing on master.

Great job testing all of the backend routes with checks on the request body properties but I would love to see unit tests. You should test functions like the one below that do a lot of string manipulation and could have a lot of potential inputs:

```js
function getParameterByName(name, url) {
  if (!url) {
    url = window.location.href
  }
  name = name.replace(/[\[\]]/g, "\\$&")
  var regex = new RegExp("[?&]" + name + "(=([^&#]*)|&|#|$)"),
  results = regex.exec(url)
  if (!results) return null
  if (!results[2]) return ''
  return decodeURIComponent(results[2].replace(/\+/g, " "))
}
```

### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

It's apparent you know how to use small, focused commits and PR's with comments to keep your progress organized. Great job.

### Extensions

* N/A

## Total Score: 112 / 150

Great job on getting a working polling app that authenticates users. Just be sure to think about how to best store and organize information and pass it between client and server and to test your app to make sure you can create multiple polls and vote on them.
