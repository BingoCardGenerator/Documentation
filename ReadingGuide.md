# Bingo Card Generator Reading guide

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

The bingo card generator is a .net Core and React JS webapplication where you can make a list of challenges for a video game (or other). And then you can generate a random bingo card with those challenges.

## Web Application

For the learning outcome web application I have created a React Js frontend (TBA) and two .Net core API's. [The challenge api](https://github.com/BingoCardGenerator/ChallengeAPI) and [the card API (TBA)](https://github.com/BingoCardGenerator/CardAPI).

To store the data in the Challenge API I decided to use Entity Framework. Because I had previously never used this framework I did some research first. {add link to research here}.

## Software quality

To ensure the quality of my software I did the followitng:

- I wrote unit test (Wich are automatically run by the CI tooling)
- I documented all my code so that other people working on the project can easily work out what my code does and how to use it.
- I made sure my naming conventions stayed consistent within each project.

## Agile methodology

TBA

## CI/CD

### CI

For CI I used Circle CI in the frontend and I used Github workflow in both of the API's more information on how I did this can be found [here](https://github.com/BingoCardGenerator/Documentation/blob/main/Proof/Ci.md)

### CD

TBA

## Cultural diffrences and ethics

TBA

## Requirements and design

I have created layer 2 of the C4 model (detailing the structure of my overall application) and I created user stories. these can both be found [here](https://github.com/BingoCardGenerator/Documentation/blob/main/Proof/User%20stories%20and%20C4%20model.md)

## Business processes

TBA

## Profesional

TBA
