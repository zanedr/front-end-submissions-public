##Real Time - Lacey Knaff
>A real-time polling app that uses WebSockets

####Link to Github Repository
[Github Rep](https://github.com/lrknaff/real-time)

####Link to Deployed Application
[Application](https://real-time-laceyk.herokuapp.com/)

####Link to Commits
[Commits](https://github.com/lrknaff/real-time/commits/master)

####Screenshot of Application
![Take Poll](https://github.com/lrknaff/real-time/blob/master/screenshots/Screen%20Shot%202017-02-03%20at%2010.02.26%20AM.png)
![Create Poll](https://github.com/lrknaff/real-time/blob/master/screenshots/Screen%20Shot%202017-02-03%20at%2010.01.52%20AM.png)

###Completion
####Were you able to complete the base functionality?
* I did complete the base functionality, however there are a few bugs. For example, on initial login I could not figure out how to reroute the user to the poll. As of now, the user must visit the link, log in, and then revisit the link to view the poll. If the user is already logged in he or she can go straight to the link and it will display the results.

####Extensions
I was not able to complete and extensions on this project

###Code Quality
####Link a specific block of code on Github you are proud of
[view](https://github.com/lrknaff/real-time/blob/master/public/authO/poll.js#L20-L34)

* I was proud of this specific piece of code because I was able to get through my complicated way of saving users to local storage and matching them with their specific votes and displaying them on the page. As I say below, I don't think it was the best approach, but I was proud that I could figure out a way to make it work regardless.

####Link to a specific block of your code on Github that you feel not great about
[view](https://github.com/lrknaff/real-time/blob/master/server.js#L67-L81)

* I don't feel great about this code because I feel as though I could have somehow connected the votes to be stored and send with the users in WebSockets as opposed to having to save to local storage and then having to parse through the votes and users to know votes went with what user. I'm also not sure that I needed to store an individual user along with a user list. I was trying to get the votes and users to have the same id, and I really struggled with that portion of this project.

####Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![Test Suite](https://github.com/lrknaff/real-time/blob/master/screenshots/Screen%20Shot%202017-02-03%20at%2011.36.40%20AM.png)


####Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'
I did have time to write enough tests to cover any edge cases.



## Instructor Feedback (Brittany)

### Concept and Features

* 35 points - The base functionality is all in place, but as mentioned there are a couple of bugs around redirects/routing. There are a couple of options for redirecting a user to a URL after they've created a new poll. One option would have been to do a simple `window.location.replace(pollUrl)` in the success handler of your API request. Instead of [hiding the poll and displaying the links](https://github.com/lrknaff/real-time/blob/master/public/createPoll.js#L23-L25) Just call `window.location.replace()` with the new poll URL. You could also do the redirect on the server-side. Instead of just returning the poll data in the response [here](https://github.com/lrknaff/real-time/blob/master/server.js#L38-L58), you can call `res.redirect` and send them to the new poll URL.

Unfortunately these routing bugs make the app pretty difficult to use. I must log-in (where the authentication validation is firing immediately upon page load, rather than just when clicking 'Sign In' or just when trying to vote). I do see the app in it's most working state when I refresh or hit the back button after already being authenticated, so it's clear the core requirements are there -- just a little tough to find!

### Code Quality (JavaScript)

* 35 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.

A couple of notes on the data structure [here](https://github.com/lrknaff/real-time/blob/master/server.js#L49). I think a more semantic approach would have been to store all of the possible responses under the same key as an array:

```javascript
{
  questionText: 'foo',
  options: [ response1, response2, response3 ]
}
```

This would provide a little more flexibility in scenarios like [this](https://github.com/lrknaff/real-time/blob/master/public/authO/poll.js#L7-L18) where you want to fill in DOM values in similar elements for each option value.

I'm also a little unsure of the structure of your application directories. There appears to be an entire Auth0 folder, though it also contains general poll logic. I would use the module pattern to help group all poll logic together and all authentication logic together.

I'm not sure what this [conditional](https://github.com/lrknaff/real-time/blob/master/public/authO/poll.js#L11) is doing/why it's needed. If you are getting poll data back from the server based on the poll you requested through the URL, it should be assumed that `id === pollId`. A test on that server-side route would confirm.

### Testing

* 15 points - The application has a small number of routes tested and no unit tests. No tests are failing on master.


### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.


### Extensions

* N/A

## Total Score: 110 / 150
