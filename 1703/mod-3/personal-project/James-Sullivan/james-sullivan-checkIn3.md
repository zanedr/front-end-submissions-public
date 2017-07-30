## Project Name:  txtSMART

#### Check In: 3  

#### Project Pitch  

   Create an app that hooks up a text message line with Twilio and analyzes the text message content with the Watson API

### Deliverables  

  Over the weekend, I completed the deliverables of linking the message UI to the Watson API, displaying tone data on click.
  I also wrote unit tests for my components.  Additionally, I created a send component the sends messages from the application
  and displays the info to the message console.
  
  Next check in, I would like to hook up my receive messages to the console and do more work on the UI.

#### Stack:

   React
   Express
   Express-Session
   Body Parser
   Twilio Node.js SDK
   Watson Node.js SDK
   ngrok

#### APIs:  

  Twilio (SMS Service)
  Watson (IBM)

#### Wireframes  

  [wireframe](https://imgur.com/a/ban1j)

#### Waffle & Github

[github repo](https://github.com/jsullivan5/txtSMART) 
[join Waffle](https://waffle.io/jsullivan5/txtSMART/join)

#### Order Of Attack  
  
  Connect the receive messages to the message console.
  Get conversations working as threads.
  Create analyse conversation feature
  Get graph to display tone over time.
  User Sign in and New account feature.

#### MVP

  An App that sends and receives SMS messages that can be analyzed for tone by the Watson API.

#### Nice To Haves   

  Sign up/Create new number functionality.
  A graph that shows tone over the course of a conversation.

#### Biggest Challenges  

  Creating a back end.
  Storing data.
  Using cookies or a database to store conversations as threads.
  Creating a meaningful graph.
  Figuring out the APIs

#### Instructor Notes
  
  

#### Deliverables for next checkin:
   - Messages displayed
   - Tone for single message 
   - somes tests
