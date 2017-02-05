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

# Instructor Feedback

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
* 35 points - Some features were sacrificed to meet the deadline. At best, this is a prototype. Major features covered by the learning goals listed above were not written by the developer.
* 10 points - Major features are missing, there are major bugs that make it impossible to use, and/or the application is not deployed to production.
* 0 - There is no application.

### Code Quality (JavaScript)

* 50 points - Developer writes code that is exceptionally clear and well-factored. Application is expertly divided into logical components each with a clear, single responsibility.
* 35 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.
* 25 points - Developer writes effective code, but does not breakout logical components. Application shows some effort to break logic into components, but the divisions are inconsistent or unclear. There are many large methods or functions and it is not clear to the evaluator what a given section of code does.
* 10 points - Developer writes code with unnecessary variables, operations, or steps which do not increase clarity.
* 0 points - Developer writes code that is difficult to understand. Application logic shows poor decomposition with too much logic mashed together.

### Testing

* 25 points - The application has all routes tested and a minimum of five unit tests. No tests are failing on master and any skipped tests have an explanation of why skipped.
* 17 points - The application has most routes tested and some unit tests. There are no tests failing testing on master.
* 12 points - The application has a small number of routes tested and no unit tests. No tests are failing on master.
* 0 points - The application is has no testing.

### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.
* 17 points - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.
* 12 points - The developer makes large commits covering multiple features that make it difficult for the evaluator to determine the evolution of the application.
* 0 points - The application was not checked into version control.

### Extensions

* 20 points - The application persists all poll questions and responses to a database.
* 20 points - When creating a new poll, you have the ability to set an end date and time to automatically close the poll (you can visit the poll to see results but no one can vote).

## Total Score:  / 150
