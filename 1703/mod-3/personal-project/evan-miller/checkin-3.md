## Project Magic Mirror:  

#### Check In: 3  

#### Project Pitch
A Magic Mirror, is a reflective monitor that will show data to the participant on top of a mirror. Positioned to be a unit the user would see during their daily routine, it can include the current date, daily weather outside, travel information, music currently playing, and daily schedule.

On top of that, if set goals were to be made, adding Alexa for voice interaction would make the unit hands free and customisable.

### Deliverables  

#### Stack:
- React
- Redux
- Electron

#### APIs:
- Weather Underground
- Newsapi
- Alexa

#### Hardware:
- 27" LED Monitor
- 2 Way Mirror
- Raspberry Pi 3
- Microphone
- Speaker

#### Wireframes

![Main](https://www.dropbox.com/s/s1ob3b07ej1n2vf/magic_mirror_mock.png?dl=1)

#### Waffle & Github
[github repo](https://github.com/EvanSays/magic-mirror)

[waffle](https://waffle.io/EvanSays/magic-mirror)

#### Order Of Attack

##### iteration 0 : Initial Discovery and Research
- ~~Create wireframes in Sketch~~
- ~~Research APIs~~
- ~~Create BOM for physical materials~~
- ~~Understand requirements~~

##### iteration 1 : Order BOM / Build Boilerplate / Harness Data
- ~~Order BOM~~
- ~~Create React/Redux boilerplate~~
- ~~Wireframe and position data/mock content, which includes routing content, and some CSS styling~~ 
- ~~Connect to Weather Underground and NewsAPI, create cleaner functions to harness data needed~~ 
- Add Youtube playlist to play
- ~~Show APIs information~~

##### iteration 2 : Initial App Tests / Build Hardware & Test
- Write tests for first stage **In Progress**
- ~~Install Rasp Pi software~~
- Test all hardware together, make sure it works
- **Test project on Raspberry, bundle with electron**

##### iteration 3 : Connect Alexa
- ~~Create API key, test Alexa on local computer~~
- Connect Alexa with project, injecting JS to do so, find tutorials, ask for help **In Progress**
- Test, can Alexa turn features/information on/off? Can Alexa toggle a container on/off by voice command?

##### iteration 4 : App Test on Raspberry Pi
- Will app run on Raspberry Pi?
- Get Raspberry pi to start project on startup/reboot.
- Strip monitor, build out frame

##### iteration 5 : Put Together
- Put all together, including speakers.
- Test, test, and more tests.

#### MVP

A working smart mirror that displays the weather and daily news.

#### Nice To Haves   
- Alexa
- Calender
- More APIs
- Music

#### Biggest Challenges
- Testing the app with mock functions.
- Understanding and incorporating Alexa.  
- How to put app on Raspberry Pi, electron?

#### Instructor Notes

#### Deliverables for next checkin:
- Get app working with Electron
- Find an Alexa Mentor
- Start the build process

