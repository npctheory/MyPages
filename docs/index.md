
- [ ] Blank Solution 
* /src
* /src/PublicApi
* /src/Domain 
* /src/Application 
* /src/Infrastructure 
* /src/Contracts/ 
* Shared project: requests

- [ ] /requests/Authentication/Register.http 
* /requests/Authentication/Login.http 

- [ ] Удалить везде Class1.cs 


- [ ] Добавить везде референсы

| PublicApi | Infrastructure | Application |
|-----------|----------------|-------------|
|Contracts| Application | Domain|
|Infrastructure|||
|Application|||


- [ ] Добавить пакеты

| PublicApi | Infrastructure | Application |
|-----------|----------------|-------------|
|System.Configuration.ConfigurationManager | Application | Domain|
|Swashbuckle.AspNetCore ||MediatR |
|||MediatR.Extensions.Microsoft.DependencyInjection |
|||Microsoft.Extensions.DependencyInjection.Abstractions |


* PublicApi: 
DependencyInjection.cs 
Controllers/V1/AuthenticationController.cs 
Controllers/V1/ErrorController.cs 
Controllers/V1/PostsController.cs 
Controllers/V1/TagsController.cs 
Options/ApiSwaggerOptions.cs 
 
* Contracts: 
V1/ApiRoutes.cs 
V1/Authentication/Requests/RegisterRequest.cs 
V1/Authentication/Requests/LoginRequest.cs 
V1/Authentication/Responses/SuccessResponse.cs 
V1/Authentication/Responses/FailedResponse.cs 
Application: 
DependencyInjection.cs 
/Authentication/Common/AuthenticationResult.cs 
/Authentication/Commands/Register/RegisterCommand.cs 
/Authentication/Commands/Register/RegisterCommandHandler.cs 
/Authentication/Queries/Login/LoginQuery.cs 
/Authentication/Queries/Login/LoginQueryHandler.cs 
/Common/Interfaces/Authentication/IJwtTokenGenerator.cs 
/Common/Services/IDateTimeProvider.cs 
/Persistence/IUserRepository.cs 
Infrastructure: 
DependencyInjection.cs 
/Services/DateTimeProvider.cs 
/Persistence/UserRepository.cs 
/Authentication/JwtSettings.cs 
/Authentication/JwtTokenGenerator.cs 
Domain: 
/Aggregates/User.cs 

 * В корне создать dockerfile
`FROM httpd:alpine
COPY ./html/ /usr/local/apache2/htdocs/`

git-bash:

`docker images`

`docker build -t hello-docker:1.0.0 .`