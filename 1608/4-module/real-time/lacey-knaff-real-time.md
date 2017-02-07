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
