# Advanced cases

## Non-crud actions:

problem: specify some action which will be easy for consumer and sctricted by our implementation details, which are not preferred to be known by consumer (not some PATCH), for example subscribing on someone's blog

tip: return 202 to indicate that long async action was started

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

### Option 3: if u cant convert to a noun, use verb or verb phrase:

* POST /server/shutdown
* POST /reminder/123/resend

* GET /resource/id/action - get status of action

#### POST or PUT?

* POST /broadcast/1/postpone - general case
* PUT /postponed/1 - in case if you internally/externally handle this as sub-collection (in other parts of api or common-known queries)

## Tips on passing parameters:

If you usually treat some parameter as resource (e.g. user or article), then always use it as path variable, not query param:

use `/organizations/1/blocks/{userId}` instead of `/organizations/1/blocks?id={userId}`

use request body for passing resource content


## Common-known queries:

* GET /users/oldest
* GET /users/poorest-parents

## Multi-field sorting:

* GET /users?sort=-age,salary
where unary minus means descending order, ascending otherwise.

## Search:

* GET /search/plural_resource_name?q=query&sort=my_field&order=desc|asc

## Batch deletings:

* DELETE /user/1/subresourcres?id=1&id=2&id=3&id=4
