# Sweet ASP.NET Core 3.0 Web Api Implementation

# What is this repo all about ?

   The idea is to present starter asp.net core web api project with best (and not really good) practices implemented.

# How can i play with it ?

   You can run the project either via Visual Studio or via docker (cmd `docker-compose up`), then you need to import the [Postman collection](https://github.com/tchelidze/Locker.Api/blob/master/docs/Locker.Api.postman_collection.json) (`Postman` -> `File` -> `Import`)


# Boring summary of structure/features included

1. Token Based Authentication, supporting `password` and `refresh_token` grant type, implemented [**manually**](https://github.com/tchelidze/Locker.Api/blob/master/src/Locker.Api/Features/Auth/AuthController.cs) 
2. Identity Management implemented **manually** without [Microsoft.AspNetCore.Identity](https://www.nuget.org/packages/Microsoft.AspNetCore.Identity/) and familiar `AspNet..` tables/collections
3. Fine-grained Authorization implemented [manually](https://github.com/tchelidze/Locker.Api/blob/master/src/Locker.Api/Web/Filters/CrudApiFilterAttribute.cs)
4. [Docker](https://github.com/tchelidze/Locker.Api/blob/master/Dockerfile) support
5. [Github Action](https://github.com/tchelidze/Locker.Api/tree/master/.github/workflows) for running the test via docker and publishing image to docker hub
6. [Unit Tests](https://github.com/tchelidze/Locker.Api/tree/master/test/Locker.UnitTests) for all main parts of the App 
7. MongoDb as a persistance mechanism (surprisingly)
8. [Screaming Architecture](https://blog.cleancoder.com/uncle-bob/2011/09/30/Screaming-Architecture.html) for organizing the folder structure
9. [MediatR](https://github.com/jbogard/MediatR) as mediator between API layer and the domain
10. [Route Constraints](https://github.com/tchelidze/Locker.Api/blob/master/src/Locker.Api/Web/RouteConstraints/ObjectIdRouteConstraint.cs) for crosscutting route data validation
11. [Model State Validator](https://github.com/tchelidze/Locker.Api/blob/master/src/Locker.Api/Web/Filters/ValidateModelStateFilterAttribute.cs) Action Filter for crosscutting model state validation (`if(!ModelState.IsValid) { ... })` basically)


# Wait a sec, why should i care ?

--  ![](https://ljdchost.com/038/Q0QD9Jj.gif)
