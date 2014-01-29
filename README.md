appengine-endpoints-backend-java
================================

This application implements a simple backend for a Tic Tac Toe game using
Google Cloud Endpoints, App Engine, and Java.

## Products
- Google App Engine 1.8.8  [1]

## Language
- Java 1.7 [2]

## APIs
- [Google Cloud Endpoints][3]
- [Google App Engine Maven plugin][6]

## Setup Instructions
a. Update the value of `application` in `appengine-web.xml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
b. Update the values in `src/com/google/devrel/samples/ttt/spi/Ids.java` to
   reflect the respective client IDs you have registered in the
   [APIs Console][4].

c. Update the value of `google.devrel.samples.ttt.CLIENT_ID` in
   `war/js/render.js` to reflect the web client ID you have registered in the

   >>Need a separate link to guide the user through the setup process. Non trivial.


d. mvn clean install
e. Run the application with `mvn appengine:devserver`, and ensure it's running
   by visiting your local server's  address (by default [localhost:8080][5].)

   >> And I see a page with a large yellow triangle, with a caption stating "You must sign in to play".
   >> So I press "Sign in" at the top left, then get an error in the next popup page. Is this expected behaviour ?

The error is:

Error: invalid_client
Bad request.
Request Details
cookie_policy_enforce=false
response_type=code token id_token gsession
scope=https://www.googleapis.com/auth/userinfo.email https://www.googleapis.com/auth/plus.login
redirect_uri=postmessage
cookie_policy=single_host_origin
proxy=oauth2relay646919858
include_granted_scopes=true
origin=http://localhost:8080
state=305326422|0.3899307157
client_id=itaxibookperf
request_visible_actions=http://schemas.google.com/AddActivity
authuser=0

e. Get the client library with `mvn appengine:get_client_lib`
f. Deploy your application.


[1]: https://developers.google.com/appengine
[2]: http://java.com/en/
[3]: https://developers.google.com/appengine/docs/java/endpoints/
[4]: https://code.google.com/apis/console
>>>NOT https
>>>[5]: http://localhost:8080/
[6]: https://developers.google.com/appengine/docs/java/tools/maven
