---
title: "Projects, Ideas and Tutorials"
coverImage: /img/pages/projects/projects_cover.jpg
coverMeta: in
coverSize: partial
coverHeight: 40
draft:          false
comments:       false
showTags:       false
showPagination: false
showSocial:     false
showDate:       false
---

## Technology Focuses
- Conversation as a Platform & Artificial Intelligence
- Internet of Things (hardware in general)
- ASP.NET Core
- Open Source

I am actively engaged with with community, startups and enterprises projects on different scales.. When I get the time, passion projects are a fun way to upskill, explore/deepen knowledge and create content for blog/tutorial/talk content. Below are a few projects.
___

#### Terminology
Caap: Conversation as a Platform  
NLP: Natural Language Processing  
LUIS: Microsoft's Language Understanding Intelligence Service (NLP)  
AI: Artificial Intelligence  
ML: Machine Learning
IoT: Internet of Things (Connected hardware and devices)
___
<!-- Project Template

**Project** | [[GitHub](https://github.com/)]  
_[ technologies ]_  
Description

-->

<!--- Current Projects --->
{{< alert warning >}} Coding & Hacking in progress - Look out for blog posts!{{< /alert >}}

**IoT Nerf Turret with Voice and Computer Vision** | [[GitHub](https://github.com/KSLHacks/intelligentNerfTurret)]  
_[ IoT, Ardunio, Servos, RaspberryPi, Cognitive Services, AI, ML, NLP, Image Recognition]_  
Building a Nerf gun turret which has the ability to turn (swivel) using arduio and servo motors. A camera and microphone will provide two input mechanisms to control the device. Audio will be converted from speech to text using Microsoft Cognitive Services Bing APIs, and sent to LUIS for NLP. Based on the command, the device will use the camera and computer vision tools to determine the target, aim and fire!

___
<!--- Ideas and Interest Areas --->
{{< alert info >}} Ideas and Interest Areas {{< /alert >}}

**Conected Smart Mirror**  
_[ IoT, CaaP, NLP, Cognitive Services, AI ]_  
I've always wanted to create a smart mirror (one way mirror overlaying a LCD screen). The mirror will be powered by a RaspberryPi and house a personal assistant chatbot. You can have a conversation with the chatbot which will tell you news, weather, personal schedule, etc. The mirror will know who it is talking to by a camera powered by facial recognition to retain user state and history. We can possible make the chatbot proactive, displaying news alerts and messages.

___
<!--- Completed Projects --->
{{< alert success >}} Completed Projects {{< /alert >}}

**JabbR-Core** | [[GitHub](https://github.com/MachUpskillingFY17/JabbR-Core)]  
_[ ASP.NET Core, SignalR, Authentication, Entity Framework, Open Source, Cross Platform ]_  
Open source project porting JabbR, a chat application built with ASP.NET and SignalR, to the ASP.NET Core framework. Working with Microsoft's ASP.NET Core engineering team.

**IoT 2-Factor-Auth Door Lock (Facial + Voice Recognition)** with [ItsJamesIRL](https://twitter.com/ItsJamesIRL) | [[GitHub](https://github.com/KSLHacks/2FA_DoorLock)]  
_[ IoT, RaspberryPi3, Python, Microsoft Cognitive Services, AI ]_  
2FA physical locking system using Raspberry Pi3 with RP Camera V2.1 and microphone. photo and audio is sent to the Microsoft Cognitive Services APIs to do identity detection based on facial and voice recognition.

**Fridge ChatBot** | [[GitHub](https://github.com/KSLHacks/FridgeChatBot)] [[Demo](http://aka.ms/fridgechatbot)]  
_[ CaaP, MSFT Bot Framework, NLP:LUIS, Azure Web App ]_  
ChatBot that helps you make decisions on what to cook for your next meal. The bot takes ingredients that you have at home, or would like to cook with and offers recipes with ratings, links and pictures. Once you decide on a recipe, it can send you a grocery list so you know exactly what to buy! This bot can even retain the state of your grocery list.

**Schedule Bot** with [NoWaySheCodes](https://twitter.com/NoWaySheCodes) | [[GitHub Tutorial](https://github.com/KSLHacks/BotScheduleDemo)]  
_[ CaaP, MSFT Bot Framework, NLP:LUIS, Azure Storage, Azure Web App ]_  
Chatbot that allows you to search, find and display results for sessions and activities at an event. Create a database of sessions and activities using azure table storage which the bot will query. The results are formatted and displayed through media rich cards for better viewing and UX.
