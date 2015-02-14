## Global information

### API Versionning

The current API version is the __v1__. All the endpoints are prefixed by `/v1`.

> Example: `curl -X GET https://api.scalingo.com/v1/apps`

### HTTP vs HTTPS

Our API is only available through HTTPS: it's TLS, or nothing.

<!-- Data Format -->

### Parameters

#### GET and DELETE endpoints

Parameters for GET and DELETE requests are known as _query parameters_, they are declared in the resource URL

> Example: `curl -X GET https://api.scalingo.com/v1/apps/name/events?page=2`

#### POST/PUT/PATCH

For these types of request, parameters are not included as query parameters, they should be encoded as JSON with the following header:

* `Content-Type: 'application/json'`

> Example: `curl -X POST -H 'Content-Type: application/json' https://api.scalingo.com/v1/apps -d '{"app": {"name": "a-new-app"}}'`

### HTTP Verbs

The API is not perfectly RESTful, it is more REST-ish. It has been developed to
be easy to use and instinctive, we'll probably normalize in a second version.

* HEAD		Can be issued against any resource to get just the HTTP header info.
* GET		Get resources, nullipotent operation (no matter how many times you call it, there is no side effect).
* POST		Used for creating resources. (creation of a new app, or to create an environment variable)
* PATCH		Update part of resources, as the value of an environment variable.
* PUT		Update complete resources.
* DELETE	Used for deleting items. Nullipotent operation (as GET)

<!-- Errors -->
<!-- Authentication -->
