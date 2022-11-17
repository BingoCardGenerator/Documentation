# Portfolio Reading guide

## Table of contents
- [Intro](#Intro)
- [Web Application](#Web-application)
- [Software Quality](#Software-quality)
- [Agile Methodology](#Agile-methodology)
- [CI/CD](#CI/CD)
- [Cultural Differences and Ethics](#Cultural-differences-and-ethics)
- [Requirements and Design](#Requirements-and-design)
- [Business Processes](#Business-processes)
- [Professional](#Professional)

## Intro
### What is this document?

This document outlines what I did to achieve each learning outcome.
You can find a detailed explanation of each learning outcome [here](https://github.com/BingoCardGenerator/Documentation/blob/main/dict/Learning%20Outcomes.md).

### What is the bingo card generator?
The bingo card generator is a C# (ASP.NET Core & Entity framework) and JavaScript (React JS) webapplication where you can make a list of challenges for a video game (or other). And then you can generate a random bingo card with those challenges.

### What is the group project?
The [group project](https://github.com/Modus-1) is a project provided by [Mediaan conclusion](https://www.conclusion.nl/mediaan). We were tasked with creating an online white label Menu and Order application for restaurants. 
Customers can scan a qr code on their table to enter the restaurant menu. Here they can select the items they want to order after wich they can place their order and pay for it. The order then gets send to the kichten who will prepare the food and bring it to the customers. 
Additionally the managers of the restaurant can manage the look of the application the menu and the stock of ingredients.

## Web Application (IP)
For the learning outcome web application I have created a [React Js frontend](https://github.com/BingoCardGenerator/CardGenFrontend) and two .NET core API's. [The challenge API](https://github.com/BingoCardGenerator/ChallengeAPI) and [the card API](https://github.com/BingoCardGenerator/CardAPI).

The Challenge API is resposible for creating and managing the challenges that appear on the bingo cards. 
The BingoCard API is responsible for creating and managing the BingoCards that appear on a users profile. Additionally it randomly assigns challenges to the bingo cards based on a list of selected challenges.

The API's are writen in C# using the ASP.NET core and Entity framework core (Add Research paper) because I already had expierience using these frameworks and because I think they work well given the scope of my project. Entity Framework makes it easy to create and mange a code first database. while ASP.NET makes it easy to create and manage API endpoints.     

For the frontend I have chosen to work with Javascript as it is a requirement for school. I am using the React Js framework because this is currently (one of) the most popular frameworks with the most demand in the workfield. As such I wanted to learn how to better use it. 

## Software quality (IP)
To ensure the quality of my software I did the followitng:

- I wrote unit test for my API's (Wich are automatically run by the CI tooling)
- I documented all my code so that other people working on the project can easily work out what my code does and how to use it.
- I made sure my naming conventions stayed consistent within each project.

## Agile methodology (GP)
For the group project we used the Scum methodology as this is one of the most popular ways of working in the work field.
Every day we before we began working we held a 'daily standup' in wich we recap what everybody is going to be working on for the day. if someone finished their task they get assigned a new one. 
The tasks are listed on a Scrum board in Jira. here you can find all tasks and their status in the ongoing 'Sprint' and all user stories in the backlog.

We work in 2-3 week 'Sprints'. At the beginning of such a period we outline what we will be working on during the sprint, we do this in delebiration with our PO (Product owner). And at the end we show our progress to the PO and the stakeholders. 

User stories we will be working on are assigned story points at the beginning of each 'Sprint'. These points reperesent an estimate of how much time a story will take. this way we can see how many points we finished at the end of a sprint, so that at the start of the next sprint we better know the workload we can handle. 
After this user stories are broken up into individual tasks wich can then be worked on. 

At the end of every sprint after the review (in wich we show our progress) we have a retrospective. Here we discuss how the sprint went. What went well and what can be improved for next sprint.

Overseeing and the whole scrum process is the scrum master. for our project this was me. 


## CI/CD (IP)

I implemented CI/CD into my project to make sure all my unit tests are ran automatically and my code is automatically deployed to Docker hub. 

### CI
For CI I used Circle CI in the frontend and I used Github workflow in both of the API's more information on how I did this can be found [here](https://github.com/BingoCardGenerator/Documentation/blob/main/Proof/Ci.md)
This has helped me makse sure all my code keeps working in the future. For example on 17/11/2022 I refactored my validation methods in the Challenge API into seprate methods. When I was doing this i implemented the boolean check the wrong way around resulting in the validation failing when it should pass and the other way around. 
It probably would have taken me quite a while to notice this if I wouldn't have had unit tests and CI. But because my CI ran my unit tests when I was trying to merge and the tests failed I figured out that the check was the wrong way around. 

CI helps a development team maintain good code quality as well as safeguard that the code actually works.  

### CD
CD is a process that automatically deploys code to a server when it is merged. This helps save time for development teams when they decide to release a new version of their software. When CD is implemented all they have to do is merge everything into the live branch and then everything is taken care of. 
Without CD teams would have to make a seprate build and update it into the servers manualy. 

## Cultural diffrences and ethics (GP)
TBA

## Requirements and design (IP)
I have created layer 2 of the C4 model (detailing the structure of my overall application) and I created user stories. these can both be found [here](https://github.com/BingoCardGenerator/Documentation/blob/main/Proof/User%20stories%20and%20C4%20model.md)

## Business processes (GP)
TBA

## Profesional (GP)
TBA
