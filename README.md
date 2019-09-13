# SELECT MOVIE * Service
Mason America hiring challenge for backend engineering positions

## Problem Statement

You are attempting to build FaveFlix, a service that allows users to search for movie information
in a variety of ways, with a future vision of allowing users to design their own queries and
pinpoint info they are specifically interested in.

### Customer API
The service is expected to support the following operations:

1. MOVSRCH: Search for movies by three different criteria and return all matching results
2. ACTSRCH: Search for actors by three different criteria and return all matching results
3. MAGICSRCH: One "interesting" search that is going to be your secret sauce. This is an 
   opportunity for you to design a specific query that you personally find interesting. 
   Examples: _"Search for the movie that has the most actors"_, or 
   _"How many moves rated PG-13 has a specific actor"._

### Admin API
The service also is expected to support the following "administrative" APIs:

* create a new movie entry
* create a new actor entry

## Your Mission

You are to use the provided bootstrap data containing movie and actor information to load up
you backing database which you are to then expose via APIs. 

In this repository you'll find two files, `actors.sql` and `movies.sql`. They comprise titles
and actors from Internet Movie Database (IMDB). For simplicity's sake, it is not fully normalized.

* Write a simple service that supports the APIs mentioned above (_customer_ and _admin_)
* Define the APIs for the operations
* Document the schema for the actor and movie entities. You may use the provided SQL files to 
  populate your database.
* Your database must persist even if your service is cycled
* Your service must accessible via a RESTful interface and testable using `cURL`
* You may ignore authentication. Requests from a customer `C` should always include an
  `X-Identifier` header with a value set to `C`. Requests from the admin should always include
  an `X-Identifier` header with a value set to `"ADMIN"`
* Responses are expected in JSON


## Examples

You are to define the APIs for the various operation. Here are some examples of how some of the operations
might be implemented.

### Customer Operations

**FIND**

> GET /smashes?q=seattle-warehouse-1

_Headers_:
* X-Identifier: "CUST"

Result status: `200`

```json
{
  "results": [
    {
      "id": "123",
      "customer": "CUST",
      "name": "seattle-warehouse-1",
      "type": "v1",
      "presses": 4
    }
  ]
}
```

### Admin Operations

**GOLIVE**

> POST /admin

_Headers_:
* X-Identifier: "ADMIN"

Post DATA:
```json
  {
    "customer": "CUST",
    "id": "123",
    "name": "seattle-warehouse-2",
    "live": true
  }
```

Response:

Result status: `200`

```
  {
    "id": "123",
    "customer": "CUST",
    "name": "seattle-warehouse-2",
    "type": "v1",
    "live": true,
    "presses": 0
  }
```

## Submission Notes

### DOs
* Fork this repo to your own user space, make it private (now possible with free accounts
  as well), and add @scorpiodawg and/or @trevorhalvorson as an outside collaborator
* Push all changes to the `master` branch of your fork, and let us know when you're ready
  to officially submit. We will fork your repo and review your code. Changes made after that
  will likely be ignored, so please do submit only after you are ready
* Do use any popular, modern language and technology stack of your choice. 
* Do ensure your final submission includes everything so that the project can be 
  **built, deployed, runnable and accessible locally**.
  As a completely optional stretch goal, it can be accessible on a public cloud (using
  their free tier for instance). Absence of this will not adversely affect your candidacy
* Do write self-documenting code
* Do include a `SOLUTION.md` with the following:
  * what major design decisions did you have to make
  * why did you choose any frameworks used
  * working [cURL](https://curl.haxx.se) command example(s) to hit your service
  * a references section listing any _significant_ resources used during development
    (significant StackOverflow questions, articles, books, etc. You do not need to
    include links to questions about language syntax, for e.g.)
* Do implement your solution as though you intend to productionize it eventually
* Do consider scale during your design

### DONTs
- Don't jump right in if you have any doubts as to whether your choice of language/
  framework might not be suitable for our review (e.g. less common ones such as 
  Clojure, Fortran, Elixir, etc.). Please contact us ahead of time to clarify.


### Timing
We expect this project to take approximately 2-6 hours of an experienced engineer's time.
However, everyone is different so please treat these numbers as suggestions. If you find
yourself blocked, or stuck spending inordinate amounts of time in a specific area, it might
be best to reach out to us -- we want to be respectful of your time and it is our job to 
ensure you have a pleasant experience.

## Feedback

We are always looking for feedback on the question itself. If, after reading through the
problem, you have questions on its clarity or suggestions on how to improve it, we're all
ears! You may leave a file named `FEEDBACK.md` when you submit your code.

**We look forward to seeing your work!**
