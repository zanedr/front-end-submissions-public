### Student:
Leta Keane

### Project Name:
emotican

#### Check In: 1  

#### Collaborators:  
Mentor: TBD

#### Project Pitch  
Many children, due to autism, developmental delays, or trauma, have difficulty with both emoting and recognizing facial expressions. Built with React, this app utilizes Microsoft's Cognitive Services Emotion API and the device webcam to help children practice making, and thereby recognizing, facial expressions.

### Deliverables  

#### Stack:
 - React
 - Redux
 - Microsoft Azure: Cognitive Services - Emotion API
 - Enzyme, fetchMock

#### APIs:  
 - [Emotion API](https://westus.dev.cognitive.microsoft.com/docs/services/5639d931ca73072154c1ce89/operations/563b31ea778daf121cc3a5fa)

#### Wireframes  
 - ![instructions view](http://imgur.com/IpLsXzc)
 - ![view after selecting emotion, before enabling camera](http://imgur.com/JI8no14)
 - ![mid-playing view](http://imgur.com/kXKRfGa)
 - ![learning view](http://imgur.com/bTtVJBA)

#### Organization link
 - [Waffle.io link](https://waffle.io/letakeane/emotican)


### Reflection  

#### Order Of Attack  
I'll start by hooking up the webcam and capturing a video frame onto a canvas element. This is necessary to be able to test the API call.

I'll create the components and containers, and hook them up with Redux and Router.

I'll determine the actions and reducers needed for the app.

I'll write unit tests and integration tests.

I'll continue to refine the components.

I'll refactor.

#### MVP
An app in which a user can select an emotion to try to match, using the webcam to capture their expression, which is analyzed by the Emotion API.

#### Nice To Haves   
 - A section where users can learn more about emotions.
 - A second exercise where users can be presented with images of people and asked to identify the pictured emotion.
 - Some sort of backend so users could save and track their progress.
 - A formal progress tracking system.

#### Biggest Challenges  
I foresee the API call being the largest challenge, since it also inherently involves the webcam, video elements, and canvas elements all at once.
