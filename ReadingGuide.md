# Portfolio Reading guide

## Table of contents

- [Portfolio Reading guide](#portfolio-reading-guide)
  - [Table of contents](#table-of-contents)
  - [Intro](#intro)
    - [What is this document?](#what-is-this-document)
    - [What is the bingo card generator?](#what-is-the-bingo-card-generator)
    - [What is the group project?](#what-is-the-group-project)
  - [Web Application](#web-application)
  - [Software quality](#software-quality)
  - [Agile methodology](#agile-methodology)
  - [CI/CD](#cicd)
    - [CI](#ci)
    - [CD](#cd)
  - [Cultural diffrences and ethics](#cultural-diffrences-and-ethics)
  - [Requirements and design](#requirements-and-design)
  - [Business processes](#business-processes)
    - [Customer process](#customer-process)
    - [kitchen staff process](#kitchen-staff-process)
    - [waiter staff process](#waiter-staff-process)
  - [Profesional](#profesional)
    - [Working with our stakeholders](#working-with-our-stakeholders)
    - [Feedback](#feedback)

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

## Web Application

For the learning outcome web application I have created a [React Js frontend](https://github.com/BingoCardGenerator/CardGenFrontend) and two .NET core API's. [The challenge API](https://github.com/BingoCardGenerator/ChallengeAPI) and [the card API](https://github.com/BingoCardGenerator/CardAPI).

The Challenge API is resposible for creating and managing the challenges that appear on the bingo cards.
The BingoCard API is responsible for creating and managing the BingoCards that appear on a users profile. Additionally it randomly assigns challenges to the bingo cards based on a list of selected challenges.

The API's are writen in C# using the ASP.NET core and Entity framework core (Add Research paper) because I already had expierience using these frameworks and because I think they work well given the scope of my project. Entity Framework makes it easy to create and mange a code first database. while ASP.NET makes it easy to create and manage API endpoints.

For the frontend I have chosen to work with Javascript as it is a requirement for school. I am using the React Js framework because this is currently (one of) the most popular frameworks with the most demand in the workfield. As such I wanted to learn how to better use it.

## Software quality

To ensure the quality of my software I did the followitng:

- I wrote unit test for my API's (Wich are automatically run by the CI tooling)
- I documented all my code so that other people working on the project can easily work out what my code does and how to use it.
- I made sure my naming conventions stayed consistent within each project.

## Agile methodology

For the group project we used the Scum methodology as this is one of the most popular ways of working in the work field.
Every day we before we began working we held a 'daily standup' in wich we recap what everybody is going to be working on for the day. if someone finished their task they get assigned a new one.
The tasks are listed on a Scrum board in Jira. here you can find all tasks and their status in the ongoing 'Sprint' and all user stories in the backlog.

We work in 2-3 week 'Sprints'. At the beginning of such a period we outline what we will be working on during the sprint, we do this in delebiration with our PO (Product owner). And at the end we show our progress to the PO and the stakeholders.

User stories we will be working on are assigned story points at the beginning of each 'Sprint'. These points reperesent an estimate of how much time a story will take. this way we can see how many points we finished at the end of a sprint, so that at the start of the next sprint we better know the workload we can handle.
After this user stories are broken up into individual tasks wich can then be worked on.

At the end of every sprint after the review (in wich we show our progress) we have a retrospective. Here we discuss how the sprint went. What went well and what can be improved for next sprint.

Overseeing and the whole scrum process is the scrum master. for our project this was me.

## CI/CD

I implemented CI/CD into my project to make sure all my unit tests are ran automatically and my code is automatically deployed to Docker hub.

### CI

For CI I used Circle CI in the frontend and I used Github workflow in both of the API's more information on how I did this can be found [here](https://github.com/BingoCardGenerator/Documentation/blob/main/Proof/Ci.md)
This has helped me makse sure all my code keeps working in the future. For example on 17/11/2022 I refactored my validation methods in the Challenge API into seprate methods. When I was doing this I implemented the boolean check the wrong way around resulting in the validation failing when it should pass and the other way around.
It probably would have taken me quite a while to notice this if I wouldn't have had unit tests and CI. But because my CI ran my unit tests when I was trying to merge and the tests failed I figured out that the check was the wrong way around.

CI helps a development team maintain good code quality as well as safeguard that the code actually works.

### CD

CD is a process that automatically deploys code to a server when it is merged. This helps save time for development teams when they decide to release a new version of their software. When CD is implemented all they have to do is merge everything into the live branch and then everything is taken care of.
Without CD teams would have to make a seprate build and update it into the servers manualy.

## Cultural diffrences and ethics

To get ahead of potentital issues with the group and colaboration we created [a contract](https://github.com/BingoCardGenerator/Documentation/blob/main/Proof/Groeps%20contract.pdf) outlining the rules of our group and how we work.
This way everyone can be clear on what was expected of them and we do not run into issues of miscomunication on this front.

## Requirements and design

I have created layer 2 of the C4 model (detailing the structure of my overall application) and I created user stories. these can both be found [here](https://github.com/BingoCardGenerator/Documentation/blob/main/Proof/User%20stories%20and%20C4%20model.md)

## Business processes

For the group project we made a digital menu application. This project was given to us by [Mediaan Conclusion](https://www.conclusion.nl/mediaan)
Tot describe the business process of the application. a Business Process Modeling Notation (BPMN) can be used to visualize the flow of the process.
The BPMN of our application can be seen in the diagram below.
![BPMN](proof/modus-bpmn.png)

_This diagram was provided by Calvin Zhen (A memeber of our group). I've been given permission by him to use this here as well._

### Customer process

When a customer sits down they will see a qr code on the table that will lead them to the menu. The first person to scann the qr code will be the session host. They are directed to the menu immidiatly and they are provided a code wich will have to be used on the landing page by each subsequent person scanning the qr code that session.

![landing page](proof/design-landing-page.png)
_landing page_

![menuPage](proof/design-menu-page.png)
_menu page_

Once a customer is on the menu page they can add items to their order. When they are satiesfied with the items in their order they can go to the checkout page using the button in the bottom of the screen. On the checkout page they can add the correct amount of items to their order, delete items from their order and add a note to their order.
Then they can pay after wich their order will be send to the kitchen to be made.

### kitchen staff process

Once an order has been placed it will apear on the kitchen staff screen.

![kitchen staff page](proof/design-staff-kp.png)
_kitchen staff page_

this screen displayes the orders in three difrent categories. New, In progress and Ready.
The staff can tap on the screen to move the orders between these categories.
Once an order reaches ready it will be send to the waiter staff screen.

### waiter staff process

![waiter staff screen](proof/design-staff-wp.png)
_waiter staff screen_

Once an order is ready to be brought to the customer it will appear on the waiter screen under ready.
The waiter can then bring the order to the customer and then mark it as deliverd.

## Profesional

### Working with our stakeholders

The way we worked with our stakeholder within our group project was with the [Agile methodology](#agile-methodology). Each sprint, we defined new user stories and refined existing ones where necessary. We then discussed these with our product owners and set the priorities together with them. The agreed upon user stories were then worked on in our sprints of ~3 weeks. At the end of each sprint, we gave our product owners a sneak preview of what they can expect from us in the coming sprint presentation to manage their expectations.

We have selected one group member to handle all comunication with the product owners (outside of sprint reviews) to avoid confusion over what email adress to use to contact us. Any questions we had for our product owners during the sprint were handled trough this one person.

If a change of plans occured we always made sure to comunicate this to our product owners on time.
An example of one of these changes was the addition of our gateway service wich handles to communication between the frondends and the apis. We had to add this to avoid potential security issues down the line but it was going to take time away from the agreed upon sprint priorities so we had to discuss this with our product owners.

In our second to last sprint review, our product owner told us that we had to finish all the leftover tasks and user stories during the last sprint, despite having been told that we only needed to finish milestone 1 in the past. Given our limited workforce and time this was not a realisic goal. We told our product owners that we could not make this promise. After that they told us this situation was a test to see how we'd react.
Our teacher gave us the tip to use the scrum board as an argument as to why we could meet or not meet certain expectations in the future.

### Feedback

During the semester I made sure to ask for feedback regularly. This way I always knew if I was on the right track and I knew what I could adjust to make things better.
I noted down most of the feedback I recieved on canvas in feedpule.
