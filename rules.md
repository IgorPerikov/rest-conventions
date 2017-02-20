# Rules

## Resource:

* GET /books - returns list of books (with offset and limit as query params)
* GET /books/1 - returns book
* POST /books - creates a new book
* PUT /books/1 - fully updates book
* PATCH /books/1 - partially updates book
* DELETE /books/1 - deletes book


## Subresource:

* GET /repos/1/commits - returns list of commits
* GET /repos/1/commits/835f0a634b9536a15e95 - returns 1 exact commit
* POST /repos/1/commits - creates new commit
* PUT /repos/1/commits/835f0a634b9536a15e95 - fully updates commit (uh, dat example, dude :confused:)
* PATCH /repos/1/commits/835f0a634b9536a15e95 - partially updates commit
* DELETE /repos/1/commits/835f0a634b9536a15e95 - delete commit


## Non-crud actions:

problem: specify some action which will be easy for consumer and sctricted by our implementation details, which are not preferred to be known by consumer (not some PATCH), for example subscribing on someone's blog

Glossary: 'subscription' is an author, whos notifications you are listening for


### Option 1: rework and handle as subresources: 

* GET /users/1/subscriptions - returns all user subscriptions
* POST /users/1/subscriptions - adds new subscription
* PUT /users/1/subscriptions/2 - updates subscription
* PATCH /users/1/subscriptions/2 - partially updates subscription
* DELETE /users/1/subscriptions/4 - unsubscribe user from resource #4


### Option 2: handle as a standalone resource (this one will contain both subscriber and his target) :
 
* GET /subscriptions/1 - returns subscription by **subscription identifier**
* POST /subscriptions
* PUT /subscriptions/1
* PATCH /subscriptions/1
* DELETE /subscriptions/1


## Filtering:

* GET /users?filed1=value1&field2=value2

## Sorting:

* GET /users?sort=-age,salary
where unary minus means descending order, ascending otherwise.

## Common-known queries:

* GET /users/oldest
* GET /users/poorest-parents

## Pagination:

* GET /users?page=4&size=20

## So-called controller for actions:

Use verb or verb phrase, e.g.:

* POST /server/shutdown
* POST /reminder/123/resend
