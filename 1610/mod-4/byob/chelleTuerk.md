## Your projects's repo URL
[BYOB repo](https://github.com/chelletuerk/shut-up-and-shake-it)

## Link to the Deployed API
[Heroku link](https://byobackend.herokuapp.com/)

## Completion

### Were you able to complete all 17 endpoints? If not how many did you complete?

Yes
### Were you able to complete all 31 endpoint tests?

Yes--and I changed the number to 31, per Alexxxxx

### Code Quality

### Link to code block in repo
[Link to code block](https://github.com/chelletuerk/shut-up-and-shake-it/blob/master/tests/server-test.js#L17-L22)

### Why were you proud of this piece of code?
Reason you are proud of code

I'm particularly a fan of this code because it eliminates the need to have a 'beforEach' and 'afterEach' block in every test.  
This code runs first every time clearing out the test database.   Wowowowowowow

### Link to a specific block of your code on Github that you feel not great about

[Link to shitty code](https://github.com/chelletuerk/shut-up-and-shake-it/blob/f652e7e82c595cdfb973d70b1c53a1a05507b0f0/tests/server-test.js#L363-L382)

### Why do you feel not awesome about the code? What challenges did you face trying to write/refactor it?
Reason you don't feel awesome about this code.

I continued to get an error concerning the database with the test.  All similar tests were fine.  I tried everything under the sun
to amend the error to no avail.  Sooooo, I deleted it.  5 points gone...I'm aware.  wah wah wah

* Unhandled rejection error: insert into "favorites" ("email", "password") values ($1, $2) - column "email" of relation "favorites" does not exist
    at Connection.parseE (/Users/chelletuerk/4mod_turing/build-a-backend/node_modules/pg/lib/connection.js:569:11)
    at Connection.parseMessage (/Users/chelletuerk/4mod_turing/build-a-backend/node_modules/pg/lib/connection.js:396:17)
    at Socket.<anonymous> (/Users/chelletuerk/4mod_turing/build-a-backend/node_modules/pg/lib/connection.js:132:22)
    at emitOne (events.js:96:13)
    at Socket.emit (events.js:188:7)
    at readableAddChunk (_stream_readable.js:176:18)
    at Socket.Readable.push (_stream_readable.js:134:10)
    at TCP.onread (net.js:543:20)


### Attach a screenshot or paste the output from your terminal of the result of your test-suite running.
![](http://i.imgur.com/DMjKcAT.png)

Instructor Feedback

Points: x / 150
