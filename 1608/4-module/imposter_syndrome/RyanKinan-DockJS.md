# Imposter Syndrome Submission Form

[Project Spec](http://frontend.turing.io/projects/imposter-syndrome.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your Repo](https://github.com/rcwestlake/dockjs)

#### Link to Blog Posts
[Kinan's](https://medium.com/@iamkinansw/an-intro-to-electron-97fad3973951#.ef6rpcv4j)

#### Link to Zip File of Application (if you did that, not required)


#### Link to Your Commits in the Github Repository for the Project

- [Kinan](https://github.com/rcwestlake/dockjs/commits?author=kswhyte)

- [Ryan](https://github.com/rcwestlake/dockjs/commits?author=rcwestlake)

#### Provide a Screenshot of your Application
<img width="1280" alt="screen shot 2017-02-12 at 10 14 15 pm" src="https://cloud.githubusercontent.com/assets/13802107/22871720/c9dac67c-f170-11e6-8efb-a83a0620580f.png">

## Completion

#### Were you able to complete the base functionality of your planned MVP?
* Yes, we actually exceeded it by adding the transpile functionality and console.log "shortnames".

#### Did you take risks and creatively utilized Electron's many different abilities?
* Yes, we use several features that Electron blesses us with. We used the menubar package and filesystem to upload and save files. A user can simply click our menubar icon and write code right away, seeing the output. We split our app in half, using the console on the right and text editor on the right.

* **What were your biggest risks?** We had no idea how to accomplish the app at the beginning. Creating a desktop REPL with a text editor with a new framework like Electron seemed risky to us. We went after it anyways. We had to figure out how to create a text editor, take the editor's value, evaluate it, and show the output in the console. We used Electron which is new, and the menubar app. 
* **What is one feature that you think is really creative?** Allowing a user to upload/save code and have vanillaJS transpiled into ES6 and ES6 into vanillaJS by simply clicking a button. Create shortnames for console.log, including 'l', 'log', 'serve', 'brew'.

#### Which extensions, if any, did you complete?

We were very close to getting it distributed, but alas, not quite there. We plan to work on it after the evaluation so we can share it.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
* [Kinan](https://github.com/rcwestlake/dockjs/blob/master/app/renderer.js#L67-L81): Proud of how we broke out the functions and were able to transpile both ways.
* [Ryan](https://github.com/rcwestlake/dockjs/blob/master/app/renderer.js#L47-L52): This was a big moment for us. After researching for awhile, we realized we could evaluate our code in one line. It made our day. Also very clean.

#### Link to a specific block of your code on Github that you feel not great about
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
	- [Code](https://github.com/rcwestlake/dockjs/blob/master/app/renderer.js#L31-L36)
	- We weren't sure how to implement this with CodeMirror (texteditor), so obviously not proud that it doesn't work.

-----

#### Please feel free to ask any other questions or make any other statements below!

-----

# Instructor Feedback

- Points: (base 150)
