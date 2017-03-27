# Build Your Own Backend Submission Form

[Project Spec](http://frontend.turing.io/projects/build-your-own-backend.html)

* Fork this repo, if you haven't already and check out a branch
* **Use this README as a template to create a file in this folder with your name as the title.**
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[BYOB](https://github.com/gprocell927/BYOB)

#### Link to the Deployed API
[Producción](https://byob-anesthesia.herokuapp.com)

## Completion

#### Were you able to complete all 17 endpoints? If not how many did you complete?
* Yes

#### Were you able to complete all 34 endpoint tests? If not how many did you complete?
* No. There are 24 tests.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[El código](https://github.com/gprocell927/BYOB/blob/master/server.js#L25-L49)

* Why were you proud of this piece of code?

I struggled with building the query/param endpoint. Initially I tried to make it it's own endpoint. Then I realized that making multiple requests to the same endpoint was not making for a fun time. Although the nested if statements bother me, I felt that this piece was easy enough to follow.

#### Link to a specific block of your code on Github that you feel not great about
[Link to code block in repo](https://github.com/gprocell927/BYOB/blob/master/test/server_test.js#L257-L330)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

I had trouble debugging errors involving my database and testing. Tests would pass until a certain unknown point, and then they would begin to fail. Most of the errors revolved around my before and after hooks. I would try to rollback and migrate my databases periodically,but that only got me so far. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![Testing GIF](http://g.recordit.co/XvLZX7QKBT.gif)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Testing that a post request returns a 422 error if provided insufficient info -- does not pass)](https://github.com/gprocell927/BYOB/blob/master/test/server_test.js#L320-L342)

-----

#### Please feel free to ask any other questions or make any other statements below!
I am slowly starting to understand how to pick through more of the layers in referencing items that are linked between tables. 

I do still have some issues with test seed data. Theoretically, I don't feel that I should have had to stub data like I did for my tests. The tests also seemed to make sense to me, and I'm at a loss as to why they are not passing or why they pass intermittently. In conclusion, I don't fully grasp the connection of the seed data in before and after hooks within describe blocks. Shouldn't it be following the methods that were run on it? Ideally, each test within the block should have started with a fresh database, right?

Anything else you wanna say!

-----

# Instructor Feedback

- Points: x / 150
