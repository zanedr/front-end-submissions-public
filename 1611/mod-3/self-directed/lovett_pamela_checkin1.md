### Student: Pamela Lovett

### Project Name: Check your tone at the Door (or the command line)

#### Check In: 1  

#### Collaborators:  

This will be a solo project.

#### Project Pitch  

Sentiment analysis software has typically been used to monitor consumers' opinions of events, products, and services through social media and other digital outlets. In recent years, a number of companies have implemented this same technology in workplace channels in order to gauge employee morale and anticipate such things as fraud, employee turnover, and potential litigation.

Since Slack serves as one the primary forms of communication for the students and staff at Turing, it makes sense (for the betterment of the community as a whole) to utilize the data available in channels to get a regular "pulse" of how the community is doing. The use of emotion analysis software within the Slack environment could not only give us a clearer view of where the community stands as a whole or in different cohorts, but could also give individuals the opportunity to help adjust the tones of certain channels or do a check of their own tone before posting or sending a message.

This is important because of the phenomenon of emotional contagion. Emotional contagion is a type of interpersonal influence (long recognized in the psychological literature) that speaks to how other peoples' feelings influence our own emotions and behavior. Consciously managing one's emotions (or at least being aware of what emotions one is spreading) is an important factor in creating a collaborative, positive school environment at Turing.

The goal of this project is to create a slackbot (specifically utilizing the command slash API) that would allow any Slack user to input text for tone analysis. The five emotions that would be analyzed are as follows: Anger, disgust, fear, joy, and sadness. The slackbot would give the user a breakdown of whether each emotion is likely to be perceived in the content of the submitted message. The extension of this project will utilize the Real-Time-Messaging API through Slack to analyze the tone of entire channels within a set date range.

TLDR:
Building a slackbot that will allow users to input text for tone analysis through IBM Watson's Tone Analyzer. The extension of this project would give a weekly summary of the overall tone of a channel.

### Deliverables


#### APIs:  
Links to any API docs that you have decided to use

[https://www.ibm.com/watson/developercloud/tone-analyzer/api/v3/](Watson Tone Analyzer)
[https://api.slack.com/slash-commands](Slash Commands via Slack)

Extensions:
[https://api.slack.com/rtm](Slack Real-Time-Messaging API)

#### Wireframes  

N/A

Results from the tone analysis will be posted as written summaries via slack.

#### Waffle.io

[https://waffle.io/thatPamIAm/check_your_tone](Waffle)

### Reflection  

#### Order Of Attack  
Given that this project is more "back-end" in nature, I'm going to start my approach with setting up the BE environment - to include express/Node.js/heroku. Watson's API has a Node-sdk that I'll be utilizing for this project as well.

In total, I will have to be sure that the command slash API through slack is working properly with the API from Watson before I can move into styling the tone analysis results in greater detail.

#### Nice To Haves   

- Colored bar graphs posted to slack (as opposed to a written summary of results) to give a visual of the data coming back from the analysis.
- Utilizing Slack's RTM API to get the data from a week's worth of conversation in a particular channel for an overall analysis
- Building a UI in addition to the slackbot. I am hoping that after I build out my server in Node.js and everything is posting as it should in Slack, that I wll be able to utilize that same server to act as my BE environment for a UI interface as well.

#### Biggest Challenges  

- Learning, understanding, and implementing Node.js and Express in such a limited amount of time with no prior exposure.

- Implementing my extension of using the RTM API through slack. I'm not sure how much trouble I might have with rate limits when I'm trying to pull messages over several days from the channel. Also unsure of how difficult this might be to implement, although it does seem possible from what I've read.

3 resources:
1) The internet and the wealth of tutorials/informational videos about these technologies.

2) The docs - both the slack API docs and Watson docs look pretty well written. There's also a fair amount of stuff available on Stack OverFlow and the like about these APIs and building out an HTTP server in Node.js.

3) Prior grads, the students in Mod4, and my teachers. Really - anyone who has had experience with server-side technologies or these particular APIs.
