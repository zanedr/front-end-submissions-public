### Student: Anders

### Project Name: Stash Tracker  

#### Check In: 1  

#### Collaborators: none

#### Project Pitch
I hope to create a platform that Winter Wildlands Alliance could potentially use to collect information about where backcountry skiers spend their time.

The [WWA](https://winterwildlands.org/) works to ensure public land management recognizes the needs and desires of backcountry skiers, snowboarders, snowshoers, Nordic skiers and other winter enthusiasts. One important aspect of this advocacy work is knowing what specific outdoor spaces are important to winter enthusiasts. This can be challenging as these folks don't always like to share this information publicly. To that end, the WWA is in need of an effective, simple and discrete way to collect this information from outdoor enthusiasts.

I hope to create a map portal where users can:
* Draw and save polygon shapes on a google terrain map
* Save the specific shapes and activities and submit them to an 'admin'
* Login into a personal Strava account and pull activities in from backcountry skis and hikes
* Admin has ability to aggregate all the activities onto one map   

### Deliverables  

#### Stack:
* React/Redux
* Google Maps API
* Strava API

#### APIs:  
Links to any API docs that you have decided to use
* [Google Maps](https://developers.google.com/maps/documentation/javascript/)
* [Strava](http://strava.github.io/api/)

#### Wireframes  
Include screenshots to wireframes or comps of **EVERY PAGE** of the MVP of your app. You can include these by adding additional files to your submissions directory, or linking to an imgur account. You're asked to use Sketch, or Balsamiq, or a different digital wireframe/comp application but if you choose to use pen/paper please let your instructors know and bring those to class Monday.  

Desktop Start Page
![Desktop Start Page](https://github.com/anderswood/front-end-submissions-public/blob/master/1701/mod-3/self-directed/anders-wood/images/Desktop%20Start%20Page.png 'optional title')

Desktop Tracks Added Page
![Desktop Track Added Page](https://github.com/anderswood/front-end-submissions-public/blob/master/1701/mod-3/self-directed/anders-wood/images/Desktop%20Tracks%20Page.png 'optional title')


#### Waffle.io
Link to your waffle.io account with at least 10 cards indicating baby steps to how you want to structure your attack.
* [Waffle](https://waffle.io/anderswood/stash-tracker)  

### Reflection  

#### Order Of Attack  
Based on your wireframes, in what order are you going to approach building out this application?

1. Identify frameworks and libraries needed, achieve basic, initial functionality with each
  * React/Redux
  * Leaflet
  * Google maps APIs
  * Strava API
  * Back-end
2. Setup leaflet with google maps
3. Pull in google maps drawing capability? polygons?
4. Authenticate user info with Strava
5. Pull in Strava information
6. User interaction with google maps and strava data
7. Persistence
8. Admin view
9. Data aggregation on one map


#### MVP
* App that users can create shapes/polygons on google map and submit to an Admin

#### Nice To Haves
What are your reach features? Ie: "Web Sockets & 3D Animations!"
* Backend
* Aggregate data for Admin
* Strava API display and save activities

#### Biggest Challenges
What do you forsee being the biggest challenges of this project? List at least 3 resources you've thought of to help overcome these challenges.

##### Biggest Challenges:
* The new pieces: backend, leaflet, google maps API
* Strava API

##### 3 Resources to Overcome Challenges
* Taylor and Meeka
* Kyle, alum from backend that used Strava API
* Other folks in class using google maps (John, Bucket, Dave)

Taylor:

MVP:
Google Maps API, React, Jest, Enzyme
Create, delete a collection of routes
UI/UX
Test

Extension:
Edit, Route

Check In 2, Thursday 5/25:
Are you using React-Router & Redux?
Be able to display map on page, and draw on it?

Check In 3, Tuesday:
Grab all information from one route.

