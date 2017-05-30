### Student: Laura Turk

### Project Name: Flash-Card Me!

#### Check In: 1  

#### Project Pitch  
Using Google Vision API and Google Translate create a web app ideal for language learners looking to keep track of all those new words they're learning! The app will allow them to take a picture of text, extract a word/sentence they don't understand for translation/definition and create a flash card with the word/phrase and translation to be saved for future review.

### Deliverables  

#### Stack:
express (node?) backend to keep user's card decks
react-redux


#### APIs:  
* [Google Cloud Vision API](https://cloud.google.com/vision/)
* [Google Translate](https://cloud.google.com/translate/docs/)
* [Google Vision in javascript tutorial](http://terrenceryan.com/blog/index.php/working-with-cloud-vision-api-from-javascript/)

#### Wireframes  
* ![Create Account](./wire-frames/Create-Account.png)
* ![LogIn](./wire-frames/Login.png)
* ![Homepage and Flash Card Decks](./wire-frames/Flash-Card-Deck.png)
* ![Settings Menu](./wire-frames/Settings.png)
* ![Translation Options](./wire-frames/Translation-Options.png)
* ![Flash Cards](./wire-frames/Flash-Cards.png)

#### Waffle.io
[waffle.io](https://waffle.io/lauraturk/flash-cards)

### Reflection  

#### Order Of Attack  
1. build out translation PAGE
2. create card based on translation
3. save card in card Decks
4. mutate card decks
5. user sign in
6. advanced language settings

#### MVP
functioning react-redux app that allows text input, translates it and creates a flashcard that can be used in a flashcard 'deck'. User's cards are saved. google translate API is used.

#### Nice To Haves   
google vision API
advanced language options (separate API?) that offer monolingual definitions in place of translations

#### Biggest Challenges  
I believe my biggest challenges will be:
- learning/building express/backend
- not falling down rabbit holes
- google vision API

1. My mentor
2. Express docs/tutorials
3. google cloud platform documentation


## Instructor Notes: Meeka

#### Goals for next checkins 

- Hit API and create dummy data structure

## Instructor Notes: Nathaniel

UI Design of showing deck and cards
-- change decks to list, click deck to go to deck view and show cards
-- card functionality
-- add router

add some instructions
split image words into clickable buttons
only show definition button if spanish is selected
modify css of uploaded image, max-width, max-height (media-query - responsive second)



