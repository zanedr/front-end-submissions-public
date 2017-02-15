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
  
---

# Instructor Feedback

- Points: (base 150)