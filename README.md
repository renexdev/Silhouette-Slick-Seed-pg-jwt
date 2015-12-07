Adaptation of Silhouette Slick Seed Template: JWTAuthenticator instead of CookieAuthenticator
==========================================
Master branch is and adaptation of Silhouette Slick Seed Template for using pg database instead of H2. The JWTAuthenticator implementations is been codded at the jwtimpl branch...
The core idea:
I'm trying to imlement JWTAuthenticator in an existing template that uses 
CookieAuthenticator:
https://github.com/sbrunk/play-silhouette-slick-seed

I got a route issue when comparing the original ouput (doing simply println) of val result = Redirect(routes.ApplicationController.index()) after the following code line

 env.authenticatorService.init(authenticator).flatMap { v =>

In the original Cookie implementation the output gives 
"GET /", but when I run my JWTAuthenticator version I got a Result(303, Map(Location -> /)) instead!. Therefore, I'm not able to get the user logged koz the result doesnt route to the proper index page.

If someone wants to contribute to clarify the issu and to make this new template working would be very usefull to expand templates of Silhouette project. The idea of implementing a JWTAuthenticator version of Silhouette Slick Seed Template is that you can have both: a web-based logging access and you can also work with the useful json-token for mobile apps.

# License

The code is licensed under [Apache License v2.0](http://www.apache.org/licenses/LICENSE-2.0).
