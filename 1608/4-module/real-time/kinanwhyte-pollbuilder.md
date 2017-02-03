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

# Instructor Feedback

- Points: (base 150)
