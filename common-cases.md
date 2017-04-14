# Common cases

## Resource:

* GET /books - returns list of books (with page and per_page as pagination parameters)
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

## Collection resource:

* GET /repos/1/labels = returns labels
* POST /repos/1/labels + request body = append labels from body
* PUT /repos/1/labels + request body = replace all labels
* DELETE /repos/1/labels - delete all labels OR delete labels that passed with request body

## Filtering:

* GET /users?field1=value1
* GET /search/users?field1=value1

## Pagination:

* GET /users?page=4&per_page=20
* GET /users?page=4&size=20
