# Jet Fuel Submission Form

[Project Spec](http://frontend.turing.io/projects/jet-fuel.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

# Basics

#### Link to the Github Repository for the Project
[Nick and Andrew's Repo](https://github.com/nnchambs/jet-fuel/)

#### Link to the Deployed Application
[Shor.ty](https://sh-orty.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Nick](https://github.com/nnchambs/jet-fuel/commits?author=nnchambs)

-[Andrew](hhttps://github.com/nnchambs/jet-fuel/commits?author=andrewLcrist)

#### Provide a Screenshot of your Application
![😍Shor.ty😍](jet-fuel/Screen Shot 2017-01-27 at 1.08.20 PM.png)

## Completion

#### Were you able to complete the base functionality?
* Yes

#### Which extensions, if any, did you complete?

- None

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[this code is sweet](https://github.com/nnchambs/jet-fuel/blob/master/helperfriends.js#L53-L61)
* Why were you proud of this piece of code?

It's dynamic and sorts based on both created_at and popularity. Quite nice.

#### Link to a specific block of your code on Github that you feel not great about
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
[this code is lame/weak sauce](https://github.com/nnchambs/jet-fuel/blob/master/public/index.js#L47-L97)
Repetition with how we're rendering the URLs. It could be cleaned up. jQuery sux.
#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
[WIP](jet-fuel/Screen Shot 2017-01-27 at 1.13.46 PM.png)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

n/a

-----

#### Please feel free to ask any other questions or make any other statements below!

mercy, please.

This project was SWEET! It was awesome to use node/Express and get to use knex and postgres. Knex is really, really cool. 
-----


# Instructor Feedback

- Points: (base 150)

**97/150**

Notes from Brittany

## Spec Adherance

**50 points**

Succeeded in implementing the evaluation criteria, though some of the more granular user stories were missing. (i.e. being able to sort in an ascending **and** descending order)

## User Interface

**7 points**

Seems to have run out of time for styling. One particularly weird thing I noticed is when you enter a new folder, the font size of the folder names changes from large to small. The smaller font makes it difficult to differentiate grouping and heirarchy.

Difficult to tell where you've added a new link, as you're only displaying the shortened hash rather than the original URL entered and the full shortened URL.

I would expect to be able to 'toggle' the sorting buttons for an ascending and descending list, but it appears both buttons are only a one-time deal.

## Data Persistance with SQL Database

**20 points**

The server-side logic looks very nicely organized; I like the strategy of breaking out the database queries into a different file, but perhaps 'helperfriends' isn't the best name for this file. Additionally, I think it would be best to leave the actual response-specific code in the server logic. It mentally makes more sense to see that 'when I do a get request for folders, this is what I'm sending back'. That also eliminates the need to pass around that response object to make it available in your helpers file. Something along these lines:

```javascript
app.get('/urls/:id', (request, response) => {
  const { id } = request.params;
  helpers.getUrlsById(id)
    .then(urls => {
      response.status(200).send(retrievedUrls);
    })
    .catch(error => {
      response.status(500).send(error);
    });
});
```

## Testing

**0 points**

Though a test file is present with the appropriate vendor imports, there are no tests.

## JavaScript Style

**15 points** - There is definitely room for improvement with refactoring duplicitous code, but it is clear there is a demonstrated understanding of how to work with the given technologies in an appropriate manner. 

### Sweet dynamic sorting code
Agreed, this is a nice function that does a good job of handling multiple situations and reduces potential repeat code. One thing I would suggest is fixing up your `catch()` method to actually log something useful like the error message. Otherwise good job on this piece!

### Lame/Weak Sauce Code
Agreed, this is lame/weak sauce. For starters, you don't necessarily need to wait for `document.ready()` to make API calls. That check could be moved down to an area where you actually need the document object (e.g. when you are appending elements to the DOM.)

Additionally, when appending elements to the DOM, especially in a loop, you'll want to take advantage of [DocumentFragments](https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment). DOM Manipulation is the most expensive part of client-side code, and document fragments allow you to build up all the HTML you need first so that you can just make one call to append to the DOM.

## Workflow

**5 points**

It looks like Nick did the majority of the work on this project based on the commit history. Whether or not that's true, I would have liked to see equal commits from both members so that I could more easily track who was responsible for which portions of the application.

The commit messages are uninformative: "trying again", "please please please", "Great", "this will work". It's important to clean these up before pushing to master so that you have an accurate and useful history to reference later on when you need to look back to previous versions of your application.

There are instances of commented out code pushed into master. This clutters up the diffs when looking at PRs or history. If you really can't let go of that code because you're afraid it will be lost into the abyss forever, use `git stash create` to temporarily stash these changes before you commit. Then you can `git stash pop` to pull them back in on your local copy! More info [here](https://git-scm.com/docs/git-stash)