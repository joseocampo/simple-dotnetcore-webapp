# simple-dotnetcore-webapp 

This webapplication simply outputs a background color and a text from the configuration file *appsettings.json*, and also the value of custom environment variables *ENVIRONMENT* and *APP_NAME*

To be used in docker exercises

# Requirements
```
.NET Core v2.2.0-preview2
```

# dotnet CLI commands
```dotnet restore ```
Downloads package dependencies referenced in *.csproj* file

```dotnet publish -c Release -o out ```
Packages the application and its dependencies with Release configuration and outputs to "/out" directory

# Docker commands
To run this web app:  
1. Build the image with  
`docker build -t website .`  
0. Start a container based on the image with  
```docker run -e APP_NAME='.net web app' -e ENVIRONMENT='linux docker container' -d -p 80:80 --name swa website```  
(website:latest is automatically used if not specified)

Useful commands:
1. Check status of running containers  
`docker ps`
0. Check usage of cpu, memory etc  
`docker stats`
0. Check what's happening in docker  
`docker events`
0. Check log for failed container  
`docker logs [name or hash]`
0. Get rid of all that shit docker leaves behind  
`docker image prune`
0. Stop a container  
`docker stop swa` 
0. Delete container  
`docker rm swa` 
0. Delete image  
`docker rmi [hash]`
0. See files in container  
`docker exec -it [container ID] bash`

# Health Check
Available on endpoint */healthz*
