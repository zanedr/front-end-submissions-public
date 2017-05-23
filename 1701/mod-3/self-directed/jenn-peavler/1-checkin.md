### Student:
Jennifer Peavler

### Project Name:
Show Me the Pin  

#### Check In: 1  

#### Collaborators:  
This is a solo project.

#### Project Pitch  
The application name is 'Show me the Pin!'.  Upon page load, the user will see signUp and logIn options.  The user
will also be able to view pinball machines and their locations if the machine is located within a 25 mile radius from the user location.  

Upon signUp/logIn, if the user walks within 500 ft of a pinball machine location, the user will receive a notification.  If after discussion with instructors, this goal seems too lofty for a two-week project, instead, the app will be used for the following purpose:

Upon signUp/logIn, the user may click on a pinball machine card and the user will see displayed:
  1) A picture of pinball machine
  2) Bio info of pinball machine
  3) User high scores of pinball machine
  4) High scores that will be posted will be
    a) Grand Champion
    b) High Score 1
    b) High Score 2
    b) High Score 3
    b) High Score 4
The user may then enter a new high score if his/her score beats one of the existing high scores.  An extension
of this feature would be to add a validation process.  Possibly the user must take a selfie and there will
be in place face and digit recognition that validates the user profile and the digits that he/she entered.

### Deliverables  

#### Stack:
React
??Have access to long-lat data, need to use phone location to know if user is near a pinball location
??How to send notifications through app

#### APIs:  
https://pinballmap.com/api/v1/docs

#### Wireframes
sketch file:  
[sketch]('./images/wireframe.sketch')
screenshots:
[mobile]('./images/mobile-layout.png')
[desktop]('./images/desktop-layout.png')

#### Waffle.io
https://waffle.io/jennPeavler/show-me-the-pin

### Reflection  

#### Order Of Attack  
Above waffle.io shows cards that layout plan of attack, but essentially
1. Become familiar with api data
2. Api data includes long-lat info of pinball location, figure out how to
   get user long-lat data so to match with closest api pinball locations
3. Figure out how to send notifications in app when user is within 500 ft of pinball location
4. Build out components and user interface
5. Test each component/function in app as it is built


#### MVP
MVP was described in the project pitch, but to reiterate:
1.  Upon page load, the user will see signUp and logIn options.  The user
will also be able to view pinball machines and their locations if the machine is located within a 25 mile radius from the user location.
2.  Upon signUp/logIn, if the user walks within 500 ft of a pinball machine location, the user will receive a notification.  If after discussion with instructors, this goal seems too lofty for a two-week project, instead, the app will be used for the following purpose:
3.  Upon signUp/logIn, the user may click on a pinball machine card and the user will see displayed:
  1) A picture of pinball machine
  2) Bio info of pinball machine
  3) User high scores of pinball machine
  4) High scores that will be posted will be
    a) Grand Champion
    b) High Score 1
    b) High Score 2
    b) High Score 3
    b) High Score 4
The user may then enter a new high score if his/her score beats one of the existing high scores.  An extension
of this feature would be to add a validation process.  Possibly the user must take a selfie and there will
be in place face and digit recognition that validates the user profile and the digits that he/she entered.

#### Nice To Haves   
This app has room to grow.  I have already hinted at some extensions.  Other than the previously mentioned extensions, this could potentially become a marketplace to buy and sell pinball machines.  It could become a way for venues that have pin to advertise drink/food/entertainment specials.  It could also be a place for users to share expertise for fixing/restoring pinball machines.  It could be a hub for tournament/competition news.  It could be a place to find all of the pinball podcasts.  There are a number of directions this app could go.

#### Biggest Challenges  
One big challenge is to deal with the coordination of user location with the location of the api pinball location data.  My mentor deals with commercial real estate apps and is well versed in traversing geographical data/databases.  I have also reached out to the moderator of the pinball map api and feel he will be a good resource.

I think another big challenge will be to figure out how to send a notification to the user.  Ideally I want a little notification icon to show up in the notification bar of the user's phone.  Initially the only resource that I have to get this accomplished is the interwebs.
