### Student: Devin Dixon

### Project Name: TBD

#### Check In: 1  

#### Collaborators:  
Solo

#### Project Pitch  
An application that shows the user all the music events happening in their area, allowing the user to
add an event to their plans and interact with other users who are also attending the same event

### Deliverables  

#### Stack:
* React
* Redux
* Router
* Express
* Postgres

#### APIs:  
[TicketMaster API](http://developer.ticketmaster.com/products-and-docs/apis/getting-started/)

#### Wireframes  
Used paper/pen to draw out wireframes

#### Trello
[Trello](https://trello.com/b/sSlNNNOu/personal-project)  

### Reflection  

#### Order Of Attack  
* Build out a landing page that checks the backend to see if the user already exists
* Redirect on log in to the home page, which pulls from the ticket master api to render event pictures/flyers, as well as the current user's details
* Build the event details page and address how to dynamically route there from the home page
* Figure out how to display which users have the same plans as the current user, and how to allow the current user to contact them

#### MVP
At the very least, the app should allow users to see the events in their area and the details of those events, allow them to add an event to their plans, and then display other users also attending

#### Nice To Haves   
* Users stay signed in through local storage
* Display directions to an event using Google API
* Allow users to upload/change profile pictures
* Search events by genre, artist name, location, etc

#### Biggest Challenges  
* Data scrubbing, since the json response is so large
* Interaction between users
* Dynamic routing from event picture to event details
* Storing event information under specific user in the backend

Taylor:

MVP: 
React, React-Router, Redux, Jest, Enzyme, Express, Node, KNEX(PSQL)
Testing, UX/UI

Check In 2, Thursday 5/25:
KNEX?
Else {
  Search functionality. 
}

Check In 3, Tuesday: 
- User tables
- User able to sign in and out
- Search functionality
- Tests on actions, reducers, component(maybe just one) —> don’t expect components to be done

