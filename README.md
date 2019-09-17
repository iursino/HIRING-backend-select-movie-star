# SELECT MOVIE * Service
Mason America hiring challenge for backend engineering positions

## Problem Statement

You are joining a crack team of engineers at FaveFlix, a service that wants to allow users to search
for movie information in a variety of ways. You're in charge of building the first version of this
budding service, and you've been handed the following "specification" for the backend: 

### Customer API
The service is expected to support the following operations:

1. MOVSRCH: Search for movies by up to three different criteria and return all matching results
2. ACTSRCH: Search for actors by up to three different criteria and return all matching results
3. MAGICSRCH: One "interesting" search that is going to be your secret sauce. This is an 
   opportunity for you to design a specific query that you personally find interesting. 
   Examples: _"Search for the movie that has the most actors"_, or 
   _"How many moves rated PG-13 has a specific actor"._

### Admin API
The service also is expected to support the following "administrative" APIs:

1. NEWMOV: create a new movie entry
2. NEWACT: create a new actor entry

## Your Mission
You are to start with this early version of a rudimentary specification with various details
left out, fill in the blanks (such as parameters, return values, etc.), and build out the
first cut of the service. 

You primary tasks are:

* Define and document the APIs for the operations
* Document the schema for the actor and movie entities. You may use the provided SQL files to 
  populate your database
* Implement a web service that supports the APIs mentioned above (_customer_ and _admin_)

Also note:

* Your database must persist even if your service is cycled
* Your service must accessible via a RESTful interface and testable using `cURL`
* You may ignore authentication. Requests from a customer `C` should always include an
  `X-Identifier` header with a value set to `C`. Requests from the admin should always include
  an `X-Identifier` header with a value set to `"ADMIN"`
* Responses are expected in JSON

You are to use the provided bootstrap data containing movie and actor information to load up
you backing database which you are to then expose to customers via APIs. In this repository you'll
find two files, `actors.sql` and `movies.sql`. They comprise titles and actors from Internet Movie
Database (IMDB). For simplicity's sake, it is not fully normalized.

### Database Choice

For this exercise, you may use any database of your choice. Please ensure that the installation
instructions for the database component are included (if it is a link to documentation elsewhere
that is also acceptable). We recommend either sqlite or PostreSQL for their simplicity.

Note that the SQL files included have been tested with SQLite.

## Examples

You are to define the APIs for the various operation. Here are some examples of how some of the operations
might be implemented. Note that paths and parameters below are only suggestions.

### MOVSRCH Operation

> GET /movsrch?name=Toy%20Story

_Headers_:
* X-Identifier: "CUST"

Result status: `200`

```json
{
  "results": [
    {
      "id": "tt0114709",
      "name": "Toy Story",
      :
      :
    }
  ]
}
```

## Submission Notes

### DOs
* Fork this repo to your own user space, make it private, add @scorpiodawg, @trevorhalvorson 
  and @grimkey as outside collaborators. Click "Use this template" button above for this purpose.
* Push all changes to the `master` branch of your fork, and let us know when you're ready
  to officially submit. We will fork your repo and review your code. Changes made after that
  will likely be ignored, so please do submit only after you are ready
* Do use any popular, modern language and technology stack of your choice. 
* Do ensure your final submission includes everything so that the project can be 
  **built, deployed, and run either locally or on a public cloud**.
* Do write self-documenting code
* Do include a `SOLUTION.md` with the following:
  * what major design decisions did you have to make
  * why did you choose any frameworks used
  * why did you pick the database used
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
We expect this project to take approximately 3-6 hours of an experienced engineer's time.
However, everyone is different so please treat these numbers as suggestions. If you find
yourself blocked, or stuck spending inordinate amounts of time in a specific area, it might
be best to reach out to us -- we want to be respectful of your time and it is our job to 
ensure you have a pleasant experience.

## Feedback

We are always looking for feedback on the question itself. If, after reading through the
problem, you have questions on its clarity or suggestions on how to improve it, we're all
ears! You may leave a file named `FEEDBACK.md` when you submit your code.

## Credits
Thanks to the original authors of [this](https://github.com/slackhq/backend-interview-prep-questions)
repository which inspired this exercise.

**We look forward to seeing your work!**
