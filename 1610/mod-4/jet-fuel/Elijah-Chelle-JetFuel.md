Jet Fuel Submission Form

Project Spec

Fork this repo, if you haven't already and check out a branch
Use this README as a template to create a file in this folder with your name as the title.
Submit a pull request
Pro Tip: You can use recordit.co to record interaction gifs.
Secondary Pro Tip: Here's how to link to specific line number(s) in Github
Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume
Basics

Link to the Github Repository for the Project

Your projects's repo URL

[GitHub repo](https://github.com/chelletuerk/jet-fuel)

Link to the Deployed Application

[Deployed Site](https://jetfuel2.herokuapp.com/)

Provide a Screenshot of your Application

![Screenshot of application](http://i.imgur.com/fVWER0z.png)

Completion

Were you able to complete the base functionality?

Yes

Which extensions, if any, did you complete?
None

Code Quality

Link to a specific block of your code on Github that you are proud of

[shortURL Get and Post](https://github.com/chelletuerk/jet-fuel/blob/master/server.js#L88-L130)

Why were you proud of this piece of code?

It was a fun challenge to think about how to redirect the user to the appropriate site while also updating the visit counter.

Link to a specific block of your code on Github that you feel not great about

[Rendering the URLs](https://github.com/chelletuerk/jet-fuel/blob/master/public/index.js#L149-L162)

Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
Reason you don't feel awesome about this code.

We spoke with Brittany about optimizing this funciton when rerendering.  We never got around to updating it, though.

Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![Test suite](http://i.imgur.com/Vecce7T.png)

Please feel free to ask any other questions or make any other statements below!

Anything else you wanna say!

# Instructor Feedback - Brittany

## Specification Adherence

* 50 points: No approach was taken that is counter to the spirit of the project and its learning goals. There are no features missing from above that make the application feel incomplete or hard to use.

Good job handling the URL formatting issues with an alert. Would be even nicer if we could actually parse the URL and format it as necessary to support all the different ways people might type in a URL ;)

User Interface
* 20 points - The application is pleasant, logical, and easy to use. There no holes in functionality and the application stands on it own to be used by the instructor without guidance from the developer.

## Data Persistence with SQL Database

* 20 points - The application persists data in a SQL database but with correct relationships between folders and URLs.


## Testing

* 7 points - Project has sporadic use of tests and multiple levels. Not all controller actions are tested. There are little or no attempts at integration testing.

Some server tests, no client-side tests.


## JavaScript Style

* 13 points - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.

It's often a good idea to save selectors that you're using in [multiple places](https://github.com/chelletuerk/jet-fuel/blob/master/public/index.js#L10-L12) to a variable at the top of your file. This saves jQuery from having to search for that element again. It can find it once and you can re-use that reference to the element anywhere you need it.

I'd use a selected class [here](https://github.com/chelletuerk/jet-fuel/blob/master/public/index.js#L32) with the `addClass` method that contains the appropriate styling rather than adding an inline-style with `.css()`.

A better [name for sorting](https://github.com/chelletuerk/jet-fuel/blob/master/public/index.js#L49-L52) rather than up/down would be ascending/descending (or asc/desc). Up down is more of a directional/geographical discriptor while asc/desc is an ordering descriptor.

Is [this](https://github.com/chelletuerk/jet-fuel/blob/master/server.js#L109-L126) PUT method actually being used? It looks like it was intended to handle updating the counter number for a particular URL, but it looks like you're also doing that in the [GET](https://github.com/chelletuerk/jet-fuel/blob/master/server.js#L99) request. The GET request is a nice place for this functionality. If you had wanted to do it outside of that request, you'd probably want to use a PATCH rather than a PUT. A PUT requires that you replace the entire data object and have all of the data associated with it at all times. A PATCH allows you to change just a single property on the object you want to update.

When doing a `POST` to [create a new record](https://github.com/chelletuerk/jet-fuel/blob/master/server.js#L70), the status code should be 201 rather than 200 if things were successful. Take a look at all the status codes that exist [here](http://www.restapitutorial.com/httpstatuscodes.html). But yayyy, good job using the correct status code [here](https://github.com/chelletuerk/jet-fuel/blob/master/server.js#L101)!

Some toggling between [ES5](https://github.com/chelletuerk/jet-fuel/blob/master/server.js#L67-L740) and [ES6](https://github.com/chelletuerk/jet-fuel/blob/master/server.js#L98) syntax throughout the codebase. Let's be consistent.

## Workflow

* 15 points - The developer makes a series of small, atomic commits that document the evolution of their application. There are no formatting issues in the code base.

No committing commented out [code](https://github.com/chelletuerk/jet-fuel/blob/master/public/index.js#L1-L30) or [console.logs](https://github.com/chelletuerk/jet-fuel/blob/master/public/index.js#L105)!

You don't want to commit [WIPS](https://github.com/chelletuerk/jet-fuel/commit/5a2bc0e12f6da99b2a3b9622929bcd8547b78ff1) to master. Put a commit like this in a pull request but rename the message before merging to master with `git commit --amend`

Points: 125 / 150
