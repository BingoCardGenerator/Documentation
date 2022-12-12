# How can CORS protect the microservice APIs in the bingocard generator?

## Table of Contents

- [How can CORS protect the microservice APIs in the bingocard generator?](#how-can-cors-protect-the-microservice-apis-in-the-bingocard-generator)
  - [Table of Contents](#table-of-contents)
  - [Subquestions](#subquestions)
    - [What is CORS? (Library research)](#what-is-cors-library-research)
    - [How does CORS work? (Library research)](#how-does-cors-work-library-research)
    - [Why should CORS be used in the bingo card API project?](#why-should-cors-be-used-in-the-bingo-card-api-project)
    - [How to implement CORS in the Bingo card APIs? (Prototype)](#how-to-implement-cors-in-the-bingo-card-apis-prototype)
  - [Conclusion](#conclusion)
  - [Scources](#scources)

## Subquestions

### What is CORS? (Library research)

CORS (Cross Origin Rescourse Sharing) is an HTTP based protocol to control wich origins other then itself have acces to certain recourses. This works by making the origin send a 'preflight' request to the rescourse, and then it check whether an actual request from that origin is allowed.

By default browsers restrict cross origin HTTP requests. This means that a resource (for example an API) only allows requests from the same origin that hosts the API.
By using CORS you can allow specific other origins to acces the rescource while maintaining the restriction on all other origins.

### How does CORS work? (Library research)

CORS works by adding new HTTP headers that let servers describe wich origins are allowed to acces the resources that are hosted on it.
It mandates that browsers 'preflight' the request soliciting supported methods from the server with the HTTP options request method. And upon approval from the server the browser will then send the actual request.

### Why should CORS be used in the bingo card API project?

CORS should be used in situations where requests have to be sent from a diffrent origin then the API server. This is defenitely the case in the bingo card project. As the frontend is hosted on a diffrent origin then both of the APIs.

### How to implement CORS in the Bingo card APIs? (Prototype)

CORS can be added in the startup files of the APIs. In here you can specify what origins are allowed to acces the API. During development this can simply be all localhost posts.
![CORS](CORS.png)

But once the app is being deployed this should be changed to the actual host of the frontend. Once this is done only the frontend can acces the API and no other place.

## Conclusion

CORS can protect the bigno card APIs by allowing only specific other origins (such as the frontend) to make requests to it. This means that a request from any other place (like another website) will be blocked.

## Scources

[used on 21-11-2022](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
