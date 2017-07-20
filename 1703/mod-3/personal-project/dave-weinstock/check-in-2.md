## Project Name: WhosPlaying

#### Check In: 2

#### Project Pitch

WhosPlaying: an app to quickly see which artists are playing shows in your current location, and provides information about those artists with resources to learn more about them or listen to their most popular songs

#### Stack:

React, Redux, Router

#### APIs:
- SeatGeek API
- Spotify API
- Google Maps API
- Google Images API (?)

#### Wireframes

[Sketch Mockup](https://www.dropbox.com/s/cgvuuk5bxy3bmq9/Screen%20Shot%202017-07-17%20at%209.46.19%20PM.png?dl=0)

#### Order Of Attack

- Get API calls working
- build first iteration of UI
- finish all major features
- polish UI

#### MVP

App that displays a list of artist names and info about event for concerts in your current location, plus ability to search other locations.

#### Biggest Challenges

- The SeatGeek API only accepts Lat/Long and postal codes as search queries. I may need to find a way to convert a city/state string into the corresponding postal code.
- Many events that the API returns do not include ticket price info, so I cannot filter out all expensive concernts

#### Instructor Notes

  
  
#### Deliverables for next checkin:
  Search location
  Map and plotting of points.
  Tests
