Student:

#### Check In: 3

#### Project Name: Run Spot

#### Client: n/a

### Deliverables:  

##### Now that you have started building your app, what are the frameworks/additional modules/technologies/testing frameworks you are using, list those here (ALL of them).  
- use fetch instead of axios (e.g. `isomorphic-fetch`)

##### Based on the MVP you stated in the second check in template, list what you have accomplished, and what still needs to be done.  
- User can log in and be directed to a list of their tracks
- User can click on a playlist and get a list of their tracks (100 max)
- Added Redux/Thunk with integrated loading bar

##### Based on unexpected challenges and/or unexpected progress adjust your MVP to reflect what you can get done by your next check in.  

##### What is on fire/what are you having trouble with?
- async issues with Redux/Thunk and managing state/getting track BPMs
- user sessions cookies are not utilized nor are user sessions stored in non-volatile memory on server
- spotify-web-api-node is limiting/may need to switch to raw fetch/axios calls in backend

##### TODO:
- Remove `spotify-web-api-node` and do raw isomorphic-fetch or axios calls to Spotify's api
- Change `sematable` (table component)?
- Store entire state of table in Redux
- Add user action to create new Spotify Playlist based on the current state of `TracksTable`
- Need to pull in Audio Features (which include tempo metadata) for each track asynchronously
- Be able to get more Playlists than the first 50
- Be able to get more Tracks than the first 50
- Bring in user saved tracks in addition to user playlists
- Add Error notifications

#### Screen Shots of Current State Of App


