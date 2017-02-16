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

## Rubric

### Blog Post (45 Points - 15 points per post)

### JavaScript Style (40 points)

* 37: Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There are a few small instances where an instructor would recommend taking a different approach and refactor.

Tons of tiny, easy to read JS functions with single responsibility. Correct use of importing multiple CSS files to a master file and pulling out the Info box code into it's own files. Honestly would have just liked to have seen more code written.

```js
$quitButton.on('click', () => {
  quitApp()
})

$themeSelector.on('change', () => {
  $chosenTheme = $('#theme-selector option:selected').val()
  editor.setOption('theme', $chosenTheme)
})

$runButton.on('click', () => {
  const code = transpileToES5()

  checkForMaliciousIntent(code)
  eval(code)
})

$uploadButton.on('click', () => {
  setEditorValue(openFile())
})

const setEditorValue = (content) => {
  if(!content) return
  editor.setValue(content)
}
$saveButton.on('click', () => {
  const code = editor.getValue()
  saveFile(code)
})

$toES5Button.on('click', () => {
  const code = transpileToES5()
  editor.setValue(code)
})
```

### User Interface (10 points)

* 7: The application has many strong pages/interactions, but a few holes in lesser-used functionality. 

The overall look and feel of the app is well polished and user friendly. Howevever there is a major UI bug when a user enters code past 28 lines, you can't click the Run button. Simple fix is to move it to the panel with all other icons.

### Risk Taking and Creativity (60 points)

- 55: Developers pushed themselves and their team by taking risks which is demonstrated by an almost delivered feature. Developers explored concepts and technologies outside the scope of the curriculum.

The group took a big risk in taking on this project without know how to accomplish it. Once they figured out how to use CodeMirror and Babel, it was a much simplier problem than they expected. They implemented extra features such as open and save file functionality and keyword shortcuts for console.log().

### Workflow (20 Points)

* 20: The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application. There is visible evidence of code review happening in pull requests and discussion around approaches. Your team uses Waffle effectively to create small, single functionality user stories that are assigned to team members.

The group used great syntax for commit messages [FIX] Fixed render bug... [UPDATE] Finish x feature. Lots of commits and user stories.


### To get a 3, you need to achieve 130 points
### To get a 4, you need to achieve 160 points

## Total Score -  164 / 175
