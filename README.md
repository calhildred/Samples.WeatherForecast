# Samples.WeatherForecast
https://dev.to/newday-technology/api-s-from-dev-to-production-428i 

## Step 1

Followed steps as listed (using commands in cmd/powershell, vscode ui for git), encountered issues below

Issues : 
1. Was unable to update "Swashbuckle.AspNetCore" as it was not located in my offline packages or in the Valocity package set. Had to add nuget as a package source to get the last version to allow a successful 'dotnet restore'
2. Was unable to build the docker file from the root folder. Turns out that docker actually has to be running, so I opened the Docker Desktop app and tried again
3. Was unable to successfully send a postman get request. Make sure to send it to http instead of https (I guess there is some set up required for https to work, porbably authentication?)

## Steps 2

Followed steps as listed and encounter no issues until I tried to send a postman request. Definitely more reading and thinking (and googling) than writing in this section

Issues :
1. Was unable to successfully send a postman get request: As covered in the read-me's of https://github.com/johannesprinz/Samples.WeatherForecast and https://github.com/henrymrrtt67/Sample.WeatherForecast, it seems like we were exposing the 8080 port in the dockerfile but that was not not the actual port we were sitting in (which was 80, as it seems that is the default). By adding ENV ASPNETCORE_URLS=http://+:8080 to the docker file we are able to make sure the exposed port is the same as the url the api is listening on
Before:
![](2021-06-05-20-42-48.png)

After:
![](2021-06-05-20-43-12.png)