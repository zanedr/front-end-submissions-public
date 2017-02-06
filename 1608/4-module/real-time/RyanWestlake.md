# Real Time Submission Form

[Project Spec](http://frontend.turing.io/projects/real-time.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your Repo](https://github.com/rcwestlake/pollr)

#### Link to the Deployed Application
[Your Application](http://pollr-al.herokuapp.com/)

#### Link to Your Commits in the Github Repository for the Project

-[Ryan's commits](https://github.com/rcwestlake/pollr/commits/master)

#### Provide a Screenshot of your Application
![myapp](http://g.recordit.co/P5b4sBG513.gif)

## Completion

#### Were you able to complete the base functionality?
[Ohhhhh yeaaaa](https://www.youtube.com/watch?v=OG_6CopW9GQ) 

#### Which extensions, if any, did you complete?

Only possible extension is a nicely designed 404 page for errors. 

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Code I can pat on the back](https://github.com/rcwestlake/pollr/blob/master/public/js/poll.js#L107-L113)

* Why were you proud of this piece of code?

Very clean, also uses the data to easily identify which choice is made later.

#### Link to a specific block of your code on Github that you feel not great about
[Code I would say 'better luck next time kid' to](https://github.com/rcwestlake/pollr/blob/master/public/js/poll.js#L67-L92)

* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

While it is simply chaining 3 promises together, it seems there could be a better, more efficient way.

#### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.

[Ma' tests](http://g.recordit.co/X5UmtYIb3h.gif)

#### Provide a link to an example, if you have one, of a test that covers an 'edge case' or 'unhappy path'

[Tests for paths that are not as happy as they could have been if they were dating a 200 status](https://github.com/rcwestlake/pollr/blob/master/test/test.js#L80-L92)

-----

#### Please feel free to ask any other questions or make any other statements below!

Look forward to learning how I can improve my code/structure/thought process!

-----

# Instructor Feedback (Brittany)

### Concept and Features

* 45 points - The base functionality is all in place, though there's one bug I've noticed when navigating to a specific poll page. If I'm not logged in, I immediately get a 401 Unauthorized error the first time around on page load. This appears to be a timing thing -- we only really want to 'unauthorize' a request if they are trying to actually submit an answer to the poll.

### Code Quality (JavaScript)

* 35 points - Developer solves problems with a balance between conciseness and clarity and often extracts logical components. Developer can speak to choices made in the code and knows what every line of code is doing.

#### Pat Yourself on the Back Code
[This](https://github.com/rcwestlake/pollr/blob/master/public/js/poll.js#L107-L113) looks nice but can still be further improved. When looping through an array to append something to the DOM, you'll want to make use of [Document Fragments](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment) to build up all the HTML you need before actually manipulating the DOM. Currently, your code manipulates the DOM on each loop. This is a slow and expensive process. Using a document fragment, you could "build up" all the HTML you'll need and then append it to the DOM once at the end of the loop. Also let's not bother with `<br/>` tags. Use CSS for spacing/`p` tags for wrapping text content.

#### Refactorable Code
Yes, there is a better way for this. The code as it exists now is still readable and easy to follow, but what I'd like to see is these requests broken out into named functions. You don't necessarily need to wait for the question data to return in order to start fetching the option data, because you've set up your API in a nice manner that allows you to access your option values by the same ID. A refactored version of this code would kick off all 3 API requests at the same time, so they don't have to wait on eachother:

```javascript
const fetchPollData = (id) => {
  if (id) {
    fetchQuestion(id)
    .then(question => $('#question').text(question.text);
    catch(error => console.log('Error fetching question'));

    fetchOptions(id)
    .then(options => appendOptions(options));

    fetchVotes()
    .then(votes => appendVotes(votes));
  }
}
```

### Testing

* 25 points - The application has all routes tested and a minimum of five unit tests. No tests are failing on master and any skipped tests have an explanation of why skipped.

Good work getting a significant amount of tests in. The `$/io` undefined issues are because the tests are running outside the context of the browser (they're running in the terminal, making certain variables inaccessible). You could leverage a tool like [Selenium Webdriver](http://www.seleniumhq.org/docs/03_webdriver.jsp) to help mimic that environment. (`npm install selenium-webdriver`) 

### Workflow

* 25 points - The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application.

Very nice consistently formatted and informative commit messages - I dig the 'category' name of each commit. Though I wouldn't officially merge any WIPs to master -- you should create issues and pull requests for code that is a WIP (stored on a separate branch) and label them as WIP. When all the code is complete, make sure your commit messages simply say what's being done and merge to master, trash the feature branch, close the PR/issue.


### Extensions

* N/A

## Total Score: 130 / 150
