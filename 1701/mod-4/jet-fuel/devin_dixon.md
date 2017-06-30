# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

# Basics

#### Link to the Github Repository for the Project
[jetfuel](https://github.com/devthehuman/jet-fuel)

#### Link to the Deployed Application
[heroku](https://dd-sh-jetfuel.herokuapp.com/)

#### Provide a Screenshot of your Application
![screenshot](https://github.com/devthehuman/jet-fuel/blob/master/app/assets/images/screenshot.png)

## Completion

#### Were you able to complete the base functionality?

If not, explain what is missing and why.
  * Everything except sorting by visits/date added was completed. We struggled for a while with getting the visits column for each link to increment, and that functionality still isn't working despite our best efforts. 

#### Which extensions, if any, did you complete?
  * N/A
# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[happy code](https://github.com/devthehuman/jet-fuel/blob/master/server.js#L92-L105)

* Why were you proud of this piece of code?
  * I'm proud of this particular block of code (even though the increment isn't working) because it required me to do a lot of reading/research on how to redirect to a different url using Express/Knex. Even though the entire route isn't behaving the way I'd like, I learned a lot in the process.

#### Link to a specific block of your code on Github that you feel not great about
[sad code](https://github.com/devthehuman/jet-fuel/blob/master/app/index.js#L80-L94)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
  * I don't feel awesome about this code because it made sorting by visits much more challenging than it needed to be, to the point where we didn't have enough time to refactor it to make it work. It was really difficult to write other functions that took the links array and manipulated it before appending to the folder, as well as functions that would clear the folder out and make the call again. Overall, if we had made this piece more modular and functional from the get-go, it would've made our lives a whole lot easier. 

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

![test suite](https://github.com/devthehuman/jet-fuel/blob/master/app/assets/images/test-screenshot.png)

#### Please feel free to ask any other questions or make any other statements below!
  * We gave testing our best shot, but were left confused as to why certain ones weren't passing and required the beforeEach/afterEach to be nested within the describe blocks while others did not. Any comments on why our tests aren't passing or any point to the appropriate docs would be awesome. Overall, I don't feel like this represents my best work because of how much time I spent debugging, but I sure did learn a ton and I'm happy about that.

Anything else you wanna say!

-----


# Instructor Feedback (Brittany)

NEEDS TO BE FIXED BEFORE EVAL

## Specification Adherence

**x points**: Lorem ipsum dolor set amet

## User Interface

**x points**: Lorem ipsum dolor set amet

## Testing

**x points**: Lorem ipsum dolor set amet

## JavaScript Style

**x points**: Lorem ipsum dolor set amet

## Workflow

**x points**: Lorem ipsum dolor set amet


### To get a 3 on this project, you need to score 110 points or higher
### To get a 4 on this project, you need to score 135 points or higher

# Final Score: x / 150
