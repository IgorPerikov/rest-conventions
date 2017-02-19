# CRUD

Resource:

* GET /books - returns list of books (with offset and limit as query params)
* GET /books/1 - returns book
* POST /books - creates a new book
* PUT /books/1 - fully updates book
* PATCH /books/1 - partially updates book
* DELETE /books/1 - deletes book


Subresource:

* GET /repo/1/commits - returns list of commits
* GET /repo/1/commits/835f0a634b9536a15e95 - returns 1 exact commit
* POST /repo/1/commits - creates new commit
* PUT /repo/1/commits/835f0a634b9536a15e95 - fully updates commit (uh, dat examples, dude :confused:)
* PATCH /repo/1/commits/835f0a634b9536a15e95 - partially updates commit
* DELETE /repo/1/commits/835f0a634b9536a15e95 - delete commit (delete resource or relation with it? I guess depends on situation, will look forward to find an answer for it)
