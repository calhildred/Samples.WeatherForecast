# Samples.WeatherForecast
https://dev.to/newday-technology/api-s-from-dev-to-production-428i 

## Step 1

Followed steps as listed (using commands in cmd/powershell, vscode ui for git), encountered issues below

Issues : 
1. Was unable to update "Swashbuckle.AspNetCore" as it was not located in my offline packages or in the Valocity package set. Had to add nuget as a package source to get the last version to allow a successful 'dotnet restore'
2. Was unable to build the docker file from the root folder. Turns out that docker actually has to be running, so I opened the Docker Desktop app and tried again