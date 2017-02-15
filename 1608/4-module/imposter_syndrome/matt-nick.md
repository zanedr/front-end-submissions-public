# Imposter Syndrome Submission Form

[Project Spec](http://frontend.turing.io/projects/imposter-syndrome.html)

* Fork this repo, if you haven't already and check out a branch
* Use this README as a template to create a file in this folder with your name as the title.
* Submit a pull request
* Pro Tip: You can use [recordit.co](http://recordit.co/) to record interaction gifs.
* Secondary Pro Tip: [Here's how to link to specific line number(s) in Github](http://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github)
* Tertiary Pro Tip: You can re-use some of these things in your portfolio/resume

------

##Basics

#### Link to the Github Repository for the Project
[CK5](https://github.com/MilkMan90/ck5)

#### Link to Blog Posts
[Coming soon...](http://burymewithmymoney.com/)

#### Link to Zip File of Application (if you did that, not required)
[CK5 via Dropbox](https://www.dropbox.com/s/rg6acobashvvwri/ElectronReact-1.0.0-mac.zip?dl=0)

#### Link to Your Commits in the Github Repository for the Project

-[Matt](https://github.com/MilkMan90/ck5/commits?author=MilkMan90)

-[Nick](https://github.com/MilkMan90/ck5/commits?author=nnchambs)

#### Provide a Screenshot of your Application
![ck5](http://g.recordit.co/4rlX5j9W3y.gif)

## Completion

#### Were you able to complete the base functionality of your planned MVP?
  Yes. 

#### Did you take risks and creatively utilized Electron's many different abilities?
* What were your biggest risks?
    
    Using the webAudio API, a NPM package created by Turing students, Redux 
* What is one feature that you think is really creative?
  
    The crossfader. 

#### Which extensions, if any, did you complete?

  Building a zip file of the application. 


##Code Quality

#### [We like this action.](https://github.com/MilkMan90/ck5/blob/master/app/actions/loadsong.js#L56-L85)
* Why were you proud of this piece of code?

  Because aSync, promises, Promise.all, and we refactored this from within a  component and put it into this beautiful action. 

#### [This component renders too much too often.](https://github.com/MilkMan90/ck5/blob/master/app/components/PlayBox.js#L80-L103)
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it? 

  How we re-render the entire Playbox component on each second "tick" of the  song, so that we can keep the progressbar and time updated. Given a bit more  time, we could have broken this out into smaller components that managed  themselves  
  
-----

#### Please feel free to ask any other questions or make any other statements below!

-----

# Instructor Feedback

## Rubric

### Blog Post (45 Points - 15 points per post)

### JavaScript Style (40 points)

* 37: Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There are a few small instances where an instructor would recommend taking a different approach and refactor.

#### Async Action
As mentioned over screenhero, the only thing I'd add here is making sure we actually do something with that `.catch()`. Otherwise I'm most happy about how you were able to leverage another student's module from 1606 heh :)

#### Component Re-rendering
Also as mentioned over screenhero, I think the solution here is to break this out into smaller components so that only what needs to be re-rendered on progress is updated. As is, without that refactoring, I'd say to make sure you split [line 83](https://github.com/MilkMan90/ck5/blob/master/app/components/PlayBox.js#L83) into multiple lines -- that nowrap is hard to read with such a long line. And [lines 90-93](https://github.com/MilkMan90/ck5/blob/master/app/components/PlayBox.js#L90-L93) look awfully similar to me. Could we perhaps have an array of these buttons and iterate over them to generate the control buttons instead?


### User Interface (10 points)

* 9: The application has many strong pages/interactions, but a few holes in lesser-used functionality. 

UI is polished and easy to understand and use. The only thing I'd add in is a loader icon/indicator for when you select a directory and it builds the playlist from the audio files. That takes a bit of time.


### Risk Taking and Creativity (60 points)

- 55: Developers pushed themselves and their team by taking risks which is demonstrated by an almost delivered feature. Developers explored concepts and technologies outside the scope of the curriculum.

Great job working with the WebAudio API (not something a ton of people have become experts with just yet). Despite not be able to finish the Analyzer portion, the app was pared down to a solid MVP to deliver a complete experience. A+ prioritizing.


### Workflow (20 Points)

* 20: The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application. There is visible evidence of code review happening in pull requests and discussion around approaches. Your team uses Waffle effectively to create small, single functionality user stories that are assigned to team members.


### To get a 3, you need to achieve 130 points
### To get a 4, you need to achieve 160 points

## Total Score -  127 + (blog score) / 175
