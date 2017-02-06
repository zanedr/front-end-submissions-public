#Real Time Submission Form

##Project Spec

###Link to the Github Repository for the Project

[Github Repo](https://github.com/gness1804/real-time)

###Link to the Deployed Application

[Check it out live!](https://real-time-gness.herokuapp.com/)

###Link to Your Commits in the Github Repository for the Project

[TeamMate1](https://github.com/gness1804/real-time/commits/master)

###Provide a Screenshot of your Application

[Screenshot](https://github.com/gness1804/real-time/blob/master/public/real-time-screen-shot-1.png)

##Completion

###Were you able to complete the base functionality?

Yes.

###Which extensions, if any, did you complete?

None.

##Code Quality

###Link to a specific block of your code on Github that you are proud of

[Excerpt that I am proud of](https://github.com/gness1804/real-time/blob/master/test/feature-tests.js#L8-L38)

###Why were you proud of this piece of code?

I wrote this code to mock a login to my application and to provide fake user data. I am particularly proud of lines 30-32, as this represents my successful efforts to stub a user login, which is a challenge that proved particularly difficult. I am also proud of the fact that I broke this code out into separate functions rather than keeping it in the tests themselves.

###Link to a specific block of your code on Github that you feel not great about

[Excerpt that could use more work](https://github.com/gness1804/real-time/blob/master/public/core-functionality.js#L64-L79)

###Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

This function is longer than it needs to be. As one can see, it contains three loops, two of which loop through the same array. The main challenges in writing and refactoring were trying to tally all the votes in a way that kept the lines of code to a minimum. Tallying the votes was more difficult than I'd thought, especially since there was no static 'A, B, C, D' choices. I know this code needs refactoring, but I ran out of time in the end.

##Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[Test suite](https://github.com/gness1804/real-time/blob/master/public/real-time-passing-tests.png)

##Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Edge case test](https://github.com/gness1804/real-time/blob/master/test/feature-tests.js#L85-L105)

This tests my data validation that gives the user an error message if they leave one or more input fields blank when entering a question.

##Please feel free to ask any other questions or make any other statements below!

This project was hard, but I am proud of my work and my final project.

## Instructor Feedback (Brittany)

### Concept and Features

* 45 points - The base functionality is all in place, though there's one bug I've noticed when voting on a poll. I can continue to cast multiple votes each time I click on an option, rather than having subsequent votes replace my original votes. This could be resolved by refactoring some of the server-side code [here](https://github.com/gness1804/real-time/blob/master/server.js#L151-L161). Instead of simply doing a `push` to `app.locals.questions.responses`, we'd first want to check if a response for that github user already existed. If so, let's update that vote value, rather than pushing a new one to the array.

### Code Quality (JavaScript)

* 35 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.

Be consistent with/without your use of jQuery. If you're using jQuery in one place, use it all over the place: [line 2 here](https://github.com/gness1804/real-time/blob/master/public/display.js#L2-L5) could be refactored to `$('#notification-logged-in-or-out').text(`Hello ${profile.name}`);

When showing/hiding [elements](https://github.com/gness1804/real-time/blob/master/public/display.js#L18-L21), you could make use of jQuery's [toggle](http://api.jquery.com/toggle/) method instead.

Instead of returning an entire HTML file on your get request for a [question](https://github.com/gness1804/real-time/blob/master/server.js#L86), why don't we just return the question JSON data and incorporate it into the DOM on the client-side, with jQuery.

### Testing

* 25 points - The application has all routes tested and a minimum of five unit tests. No tests are failing on master and any skipped tests have an explanation of why skipped.

Excellent job of getting very difficult tests into the codebase. Mocking out certain interactions can be incredibly difficult, but you've demonstrated a solid understanding of testing small features by faking the surrounding data.

### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Very nice consistently formatted and informative commit messages - it's easy to get a good understanding of the history just at a quick glance. Didn't notice the use of many branches but perhaps you have deleted the ones you've merged in.

### Extensions

* N/A

## Total Score: 130 / 150
