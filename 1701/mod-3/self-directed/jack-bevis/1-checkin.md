### Student: Jack Bevis

### Project Name: Get Out There

#### Check In: 1  

#### Project Pitch  
Get Out There will be a web application for people who what to find amazing places to climb, hike, bike, camp, etc. and who are looking for people to join them. The app will allow users to create their own account in order to search for trailheads, campgrounds, or crags, as well as let them indicate where they plan on heading on a given day. I hope to eventually incorporate some features to map areas and times that are most popular so users can view that data in order to help them plan their next adventure. The application will be built using React and React-Router, with the potential for Redux depending on final scale of the project. The intent is to incorporate mapbox/leaflet for the mapping aspect, as well as Victory for data visualization of most popular areas over time. I would like to incorporate a backend database for users, as well as a potential slackbot feature in future iterations, that would help people meet up and plan trips utilizing the front-end site.

### Deliverables  

#### Stack: React, Redux, React-Router, Victory or React-D3 for visualization, mapbox/leaflet,

#### APIs:
Primary API for iteration 0:
[Mountain Project API](https://www.mountainproject.com/data)

Pending or others for future iterations:
[The Crag API](https://www.thecrag.com/article/API)
[Campground API](http://developer.active.com/docs/read/Campground_APIs)
[National Park Service API](https://www.nps.gov/subjects/digital/nps-data-api.htm)
[Google Maps API](https://developers.google.com/maps/documentation/javascript/)

#### Wireframes  
[Wireframes](https://drive.google.com/open?id=0BwVmMWZvRBbXWmtaQkIxT2FXd3M)

#### Waffle.io
[Get Out There Waffle](https://waffle.io/jbevis/Get-Out-There)

### Reflection  

#### Order Of Attack  
My plan of attack is to spend at least another full day planning out the layout/architecture of the app while I hammer down the MVP and research some technologies to use related to mapping and visualization. I then plan on building out the basic skeleton of the app from a mobile first stand point. Iteration 0 of this app may only focus on one type of location, either trailheads or crags, and then work towards have many different options. I plan on incorporating TDD to keep myself accountable on the project while also working on fine tuning some best practices. Depending on whether the app is going to built using only React or React with Redux will shape how I approach building out either components, or actions/reducers/containers early on.

#### MVP
My MVP will be an app with well done CSS and well thought out UI/UX. The MVP will focus on having full functionality for one of the activity types. This will include rendering all locations as pins on a map, with corresponding info when pin is clicked. user will be allowed to save locations and mark themselves are either seeking people to go with or not. There will also be a route on the app that indicates which locations receive the most traffic and a heat map indicating use over time.  

#### Nice To Haves   
Data visualization of area use over time using Victory or React-D3, this will be in chart form as well as heat map.
Backend database for users.

#### Biggest Challenges  
I believe the most challenging part of this project will be sourcing all of the necessary data I want to use, and making sure all the different api calls work well with each other. Incorporating the maps, both location and heat I also imagine will present a unique challenge. I plane on reviewing quite a few tutorials on how to accomplish these things as well as leverage other members of my cohort who are trying to accomplish similar things in their projects. Ultimately, I hope to incorporate a slack bot feature that will allow people to pair up via slack based on activity interest parameters e.g. distance from current location, time to finish trail, difficulty, etc etc.
