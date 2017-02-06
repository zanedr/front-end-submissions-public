# Real Time Submission Form

[Project Spec](http://frontend.turing.io/projects/real-time.html)

# Basics

#### Link to the Github Repository for the Project
[Repo](https://github.com/ChelseaSkovgaard/realtime)

#### Link to the Deployed Application
[Application](https://realtimez.herokuapp.com)

#### Link to Your Commits in the Github Repository for the Project

-[Nick Chambers](https://github.com/ChelseaSkovgaard/realtime/commits/master?author=nnchambs)

-[Chelsea Skovgaard](https://github.com/ChelseaSkovgaard/realtime/commits/master?author=ChelseaSkovgaard)

#### Provide a Screenshot of your Application
<img width="504" alt="screen shot 2017-02-03 at 11 32 49 am" src="https://cloud.githubusercontent.com/assets/18074889/22603610/553f05a2-ea05-11e6-8209-302a4a432b6f.png">

<img width="530" alt="screen shot 2017-02-03 at 11 37 56 am" src="https://cloud.githubusercontent.com/assets/18074889/22603624/6142faca-ea05-11e6-996c-5c3f5482e964.png">


## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

* No

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
* Why were you proud of this piece of code?
We're proud of this piece of code because we used web sockets and figured out
how to pass the picture.
https://github.com/ChelseaSkovgaard/realtime/blob/master/server.js#L52-L73

#### Link to a specific block of your code on Github that you feel not great about
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
We think we could refactor this.
https://github.com/ChelseaSkovgaard/realtime/blob/master/public/poll.js#L24-L38

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

<img width="351" alt="screen shot 2017-02-03 at 11 43 49 am" src="https://cloud.githubusercontent.com/assets/18074889/22603812/2c7cc798-ea06-11e6-85dd-a3f4fb89858f.png">

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

-----

#### Please feel free to ask any other questions or make any other statements below!

We initially tried building this project by building a database. We wanted the number of answers you could input to be dynamic so we built two tables - one for questions and one for answers linked by the question id. We ran into a lot of complications using this method, so we ended up starting over with a new repo. Our old repo was (https://github.com/ChelseaSkovgaard/RealTalk).

# Instructor Feedback (Brittany)

### Concept and Features

Does it have the expected features?

* 35 points - The base functionality is all in place, though slightly buggy. Regardless of how many polls I create, I can only really access the latest one. This is because you have a single URL (https://realtimez.herokuapp.com/poll.html#) for voting on polls. One solution for this would be to use query params to create unique URLs for each poll created. For example, you'd reference each URL by the ID of the newly created poll:

```html
https://realtimez.herokuapp.com/poll?pollId=947260523746034597
```

From here, when the page loads, you would detect the `pollId` value from the URL, and make a request specific to that poll:

```js
fetch(`/api/v1/polls?pollId=${pollId`)
  .then(res => res.json())
  .then(pollData => console.log(pollData));
```

### Code Quality (JavaScript)

* 35 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.

#### Code That You Like:
Agreed, this is some nice code. 

#### Code that could be refactored:

Things I'd like to see in this piece of [code](https://github.com/ChelseaSkovgaard/realtime/blob/master/public/poll.js#L24-L38):

* Make the looping count dynamic rather than set to '4' in case we want to support more or less options in the future. This is easily accomplished with `poll.answers.length`
* Leverage document fragments to build up all the HTML you need to append before adding it to the DOM. Currently you're manipulating the DOM on every loop which is a slow, expensive process.

#### Other Code
Don't get into the habit of committing console logs and be consistent with your use of semi-colons: [https://github.com/ChelseaSkovgaard/realtime/blob/master/public/poll.js#L12-L14](https://github.com/ChelseaSkovgaard/realtime/blob/master/public/poll.js#L12-L14)

Be consistent with/without your use of jQuery. If you're using jQuery in one place, use it all over the place: [this](https://github.com/ChelseaSkovgaard/realtime/blob/master/public/poll.js#L50) could be refactored to $(connectionCount).text(`Connected Users: ${count}`)


### Testing

* 17 points - The application has all routes tested but NO unit tests. There are no tests failing testing on master. 

All backend routes are tested but some unit tests would have been great! Even if you don't get around to writing them, spec them out/stub them in so that it's easier to go back to later. It's useful to know what needs to be tested, and also demonstrates you have an understanding of the code that could be tested.

### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

### Extensions

* N/A

## Total Score: 112 / 150