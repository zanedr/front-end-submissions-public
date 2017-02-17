# Imposter Syndrome Submission Form

[Project Spec](http://frontend.turing.io/projects/imposter-syndrome.html)

------

# Basics

#### Link to the Github Repository for the Project
[Your Repo](https://github.com/gness1804/fired-up)

#### Link to Blog Posts
TBD

#### Link to Your Commits in the Github Repository for the Project

-[Graham](https://github.com/gness1804/fired-up/commits/master?author=gness1804)

-[Alex](https://github.com/gness1804/fired-up/commits/master?author=pilewski)

-[Ian](https://github.com/gness1804/fired-up/commits/master?author=ianlancaster)

#### Provide a Screenshot of your Application
![Screenshot](https://github.com/gness1804/fired-up/blob/master/images/fired-up-screenshot.png)
![Gif of app usage](http://g.recordit.co/3jKZHw8gEv.gif)

## Completion

#### Were you able to complete the base functionality of your planned MVP?
Yes

#### Did you take risks and creatively utilized Electron's many different abilities?
* What were your biggest risks?
  * Handling time features
  * Using Chart.js, menubar npm package, and active-window package  
* What is one feature that you think is really creative?
  * We were able to chart our session times using Chart.js
  * We also really like our fire icon!

#### Which extensions, if any, did you complete?

None.

# Code Quality

#### Link to a specific block of your code on Github that you are proud of
[Chart code](https://github.com/gness1804/fired-up/blob/master/lib/render.js#L239-L259)
* Why were you proud of this piece of code?

This code succeeds in implementing a difficult functionality: charting session data. It functions with a variable number of sessions and session data, so it is flexible and efficient.

#### Link to a specific block of your code on Github that you feel not great about
[Code from render](https://github.com/gness1804/fired-up/blob/master/lib/render.js#L1-L25)
* Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?

This beginning part of the render file has a ton of global variables. It also illustrates that much of the code on this page could have been broken into separate files.

-----

#### Please feel free to ask any other questions or make any other statements below!

-----

# Instructor Feedback

## Rubric

### Blog Post (45 Points - 15 points per post)

### JavaScript Style (40 points)

* 35: Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing. 

The group could have broken render.js file into three seperate files (renderer, button-events and graph) to keep the code more readable. Overall the JS is very well written with lots of small, single responsibility functions throughout the code base.

### User Interface (10 points)

* 7: The application has many strong pages/interactions, but a few holes in lesser-used functionality.

Improvements: Fix icon to show in dark menubar, clean up labels in graph, different colors for each line in graph, overall more polish to look of app. 


### Risk Taking and Creativity (60 points)

- 55: Developers pushed themselves and their team by taking risks which is demonstrated by a delivered feature. Developers explored concepts and technologies outside the scope of the curriculum.

The group tackled a lot of unique challenges using Active Window to track the time spent in each application, Chart.js to graph those times, and different OS specific scripts to make Active Window not throw errors when they should be ignored. The graph was particularly creative in showing the history of each session.

### Workflow (20 Points)

* 20: The developer effectively uses Git branches and many small, atomic commits that document the evolution of their application. There is visible evidence of code review happening in pull requests and discussion around approaches. Your team uses Waffle effectively to create small, single functionality user stories that are assigned to team members.

The group had a ton of very small and well written commit messages and lots of PRs. They also had 50+ Waffle issues, with each assigned to a group member.

### To get a 3, you need to achieve 130 points
### To get a 4, you need to achieve 160 points

## Total Score -  117 + (blog score) / 175
