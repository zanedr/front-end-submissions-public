### Student: Eric Syaler

#### Check In: 1

#### Project Name: Run Spot

### Deliverables:

#### Project Pitch
An app to organize/sort your Spotify 🎵 tracks into a running playlist based on track BPMs.

Users will be able to authenticate using their Spotify user name/password,
pull down their personal private playlists into the app, select playlist(s) and
sort/organize tracks by BPM and then create a new playlist based on the
sorted/organized tracks and add it to their spotify account.


### Wireframes

![](http://i.imgur.com/SSEhsII.jpg)

#### Frameworks
- React/Redux
- Express
- [spotify-web-api-node](https://github.com/thelinmichael/spotify-web-api-node)

#### APIs
- [Spotify Web API](https://developer.spotify.com/web-api/)
  - Uses Implicit Grant/Client Credentials to access public data
  - Requires OAuth 2.0 Authorization tokens to access private user data
  - Mock data can be built  using Client Credentials and hitting the public data API using `cURL`, Postman, or [Spotify's Interactive Web API Console](https://developer.spotify.com/web-api/console/)

#### MVP
  - Allow user to sign in with their Spotify Credentials and pull in saved tracks/playlists.
  - Allow user to sort the first `x` amount of tracks in their Playlist/Saved-Tracks
  - User can create a new private Spotify playlist based on this new sorted playlist
  - a loading bar if API calls take a while

#### RVP
- Reach Viable Product:
  - User can grab entire playlist tracks with track data sort them into specific BPM ranges as separate Playlists
  - User can sort based on other metadata
- What are the dream extensions you want to build?
  - App uses a back-end caching such as Redis to save User data and making fetching data less expensive
  - or App utilizes a back-end DB to keep track of state, front end caching uses Relay/Apollo to get data from store graphQL server
  - graphQL server interacts with SQL/noSQL DB to hold user data and prevent unnecessary re-fetching API data

#### Collaborators
    - Just me
