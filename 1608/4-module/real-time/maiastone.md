##Real Time Submission Form

[Link to the Github Repository for the Project](https://github.com/maiastone/real-time)

###Your Repo

[Link to the Deployed Application](https://real-time-response.herokuapp.com/)

###Your Application

[Link to Your Commits in the Github Repository for the Project](https://github.com/maiastone/real-time/commits/master)


###Provide a Screenshot of your Application

![real-time-response herokuapp com--surveyid 3449c9e5e332f1dbb81505cd739fbf3f iphone 6](https://cloud.githubusercontent.com/assets/18236434/22602895/5aed8134-ea02-11e6-9567-d417d331e492.png)

##Completion

Were you able to complete the base functionality?   
Yes

If not, list what functionality is missing.
Which extensions, if any, did you complete?

##Code Quality

[Link to a specific block of your code on Github that you are proud of](https://github.com/maiastone/real-time/blob/master/public/form.js#L59-L72)

Why were you proud of this piece of code?   
The way solved the routing and the conditional rendering might not have been the best approach, but I really had to think 
about the UI, and in the end, this did the trick.   
#### Notes   
There is some weird bug - probably related to this code, but in some cases the path doesn't go where it should, or render the page as
it should, or show signed in.  However, if you press refresh, and you might need to enter a survey again, it works.   

[Link to a specific block of your code on Github that you feel not great about](https://github.com/maiastone/real-time/blob/master/server/index.js#L63)

Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?   
This isn't a piece of logic that needed refactoring, but a good example of a concept I'm not comfortable with yet.
I did a tiny bit of research, but didn't have time to really get the differences between using use and get and resolve and the paths.
Definitely not comfortable with express, routing, and paths.   

Attach a screenshot or paste the output from your terminal of the result of your test-suite running.   
 GET /api/survey/:surveyID
    ✓ should return a 200 status (38ms)
    ✓ should return the user survey
    ✓ should add a survey when post is executed


  3 passing (90ms)


Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'
