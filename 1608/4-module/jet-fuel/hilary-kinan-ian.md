# Jet Fuel Submission Form

 [Project Spec](http://frontend.turing.io/projects/jet-fuel.html)
 
 ------

## Basics
#### Link to the Github Repository for the Project

 [Repo](https://github.com/hilarylewis92/jetFuel)
 
#### Link to the Deployed Application

 [Application](https://jetfuelshortener.herokuapp.com/)
 
#### Link to Your Commits in the Github Repository for the Project
 
 -[Commits](https://github.com/hilarylewis92/jetFuel/commits/master)
 
#### Screenshot of your Application

 -[app](https://cloud.githubusercontent.com/assets/18403177/22384375/45e323ba-e48b-11e6-9519-414e2e21833e.png)
 
## Completion
 
#### Were you able to complete the base functionality?
 * Yes except for popularity (very close though)
 
 #### Which extensions, if any, did you complete?
 * No
 
 # Code Quality
 
#### Link to a specific block of your code on Github that you are proud of
 -[code](https://github.com/hilarylewis92/jetFuel/blob/master/server.js#L49-L54)
 
 * We implemented a redirect function for the shorten url to redirect to the long url instead of just putting the long url link as the href in the short url a tag. We are proud of this code because it took more time to implement, it is clean, and it is the right way to create a shorten url application.
 
#### Link to a specific block of your code on Github that you feel not great about
 -[code](https://github.com/hilarylewis92/jetFuel/blob/master/server.js#L49-L54)
 
 * Considering our time crunch for this project, we decided to allow the application to reload on submitting a new folder and url instead of preventing the defualt. We did this so the componentDidMount function would fire again in order to fetch the data from the api to render it to the page. If we did it the right way, we would have preventing the default and make another function to fetch the data on sumbit. This would have added more time which we did not have to meet our deadline.
 
#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
    -[tests](https://files.slack.com/files-tmb/T029P2S9M-F3WTHQUG1-fc78e952dc/screen_shot_2017-01-27_at_12.33.50_pm_1024.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'
 
 -----
 
#### Please feel free to ask any other questions or make any other statements below!
 
 -----
 

# Instructor Feedback

- Points: (base 150)

**110/150**

Notes from Brittany

## Spec Adherance

**40 points**  

Most user stories completed, except for the popularity and sorting. Number of Visits remains '0' even after clicking on several links, and we cannot ascend/descend the order based on creation time/popularity. Otherwise, the rest of the base functionality is in place and working well.

## User Interface

**15 points**  

Clear that there was effort put into the UI and styling, though there are a handful of bizarre displays. For one, I would hide the URL heading text (Url/Shortened URL/Created At/Number of Visits) unless there are actually URLs there. Without URLs in place, all of that text blends in together and doesn't actually reference anything. 'Created At' is also the only text that ends with a colon, making it look like the value of 'Created At:' is 'Number of Visits'

Additionally, the shortened URL ends up not actually being shorter than the full URL. I understand the logic is in place, but as a result the visual representation of this looks inaccurate as the Shortened column is much wider than the URL column.

## Data Persistance with SQL Database

**20 points**  

I see things have been refactored a bit from the last check-in, which looks great. Returning the JSON responses rather than HTML templates was hopefully a bit easier and closer to what you're familiar with. Again, being ambitious is good, but it's best to do something the way you know how before refactoring to try a new pattern or strategy.

## Testing
**7 points**  

Clear effort was made to begin testing some server-side functionality. The `app.address` issue noted [here](https://github.com/hilarylewis92/jetFuel/blob/master/test/routes.spec.js#L11-L12) is likely because you aren't exporting anything from your `server.js` file. It's not enough to simply require the server file, you need to actually export your `app` variable from it so it can be used in tests.

Minimal effort for testing components and adding integration tests for client-side code, but I appreciate that testing files were stubbed in with a basic test in place. One piece of advice I give everyone here is to stub out **everything** you need to test for each component -- write all of your describe blocks and it blocks and what each of them should test, and then in each of them just `assert(2 + 2).equals(4)`. This gives you a roadmap for adding tests in later on and makes it much easier to go back and recall what tests you need to add.


## JavaScript Style

**15 points**

Inconsistent use of single vs double quotes in [various places](https://github.com/hilarylewis92/jetFuel/blob/01af3eed69fa490cf04bf0756345b51cf3de1bfc/server.js#L4-L6). Find a linting configuration you can all agree on at the start of your project and stick to it to avoid style inconsistencies.

No points off for this, but if you are going to choose not to use semi-colons anywhere, be sure you can defend that decision. It is very unlikely you'll work on a team in the future that would allow this, and if I had a candidate writing code without semicolons it's definitely something I would ask about on an interview. Also, if you're choosing not to use them, [be consistent](https://github.com/hilarylewis92/jetFuel/blob/master/src/App.js#L24-L31).


### Code you're proud of: Redirect endpoint
Indeed, this is a nice endpoint to have in place for the redirect. Two notes I'd add here: you might want to explicitly set the response [status code](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html) to `301`. It defaults to `302` here, meaning that the resource has 'temporarily' moved, but in our scenario the redirect is essentially permanent. Also always be sure to handle your promise exceptions with `.catch()`.

### Code you're not proud of: Reloading on submit
The link for this code is the same as your redirect code, so I'm not 100% sure what line numbers you're referring to here, but thank you for writing out the explanation of the correct way to handle that scenario. That sounds like a good plan had you had more time to complete the refactoring.


## Workflow

**10 points**  

Commit messages are mostly informative and consistent. As a group, I would agree on a message style prior to pushing commits into master. e.g. Hilary started each commit message with a capital letter, did not use punctuation, and wrote them in the imperative tense. This matches the default that github uses for things like merge commits, and is the most common convention. Other commits in the codebase were lowercase and less informative or repetitive ([removed a .](https://github.com/hilarylewis92/jetFuel/commit/f468bb3f18b144dc0ead8ccbb23ba6edf99605ee), remove another '.'). Better messages for these commits would be 'Fix relative directory path' and I'd [squash](https://ariejan.net/2011/07/05/git-squash-your-latests-commits-into-one/) them into one before pushing to master.

Based on the number of commits, it also looks like the workload was a bit uneven. It seems as if Ian dominated much of the coding and it's difficult to tell exactly how the work was split up in this group. Because I am not in the classroom with you in person each day, I can't assume this is true, but this is how it appears to someone who only has the git history to go off of. 

Good use of many branches, though it's good to remember to clean those up [after they've been merged](https://github.com/hilarylewis92/jetFuel/branches).

Don't commit [console.logs](https://github.com/hilarylewis92/jetFuel/commit/bf18cf94ffd8d6a2525423ec82fcc71ebfbb5e13#diff-78c12f5adc1848d13b1c6f07055d996eL47) or commented out code. This clutters up the diffs when looking at PRs or history. If you really can't let go of that code because you're afraid it will be lost into the abyss forever, use `git stash create` to temporarily stash these changes before you commit. Then you can `git stash pop` to pull them back in on your local copy! More info [here](https://git-scm.com/docs/git-stash)