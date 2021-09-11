# Docker Image for DayZ Standalone Server  
  
> Currently only Experimental Server since linux server is not yet released to stable
  
### Run the image  

The default startup command will update/install the server using the steamcmd (with anonymous login).  
  
Everything steam cmd downloads will be located in the `/dayz/server` directory, so make sure to create a volume for this dir or map it to the host file system.
  
Example:  
```
docker run -d -P \\
    -v "${PWD}:/dayz/server" \\
    --restart unless-stopped \\
    senfo/dayz-sa-server-docker \\
```  
  
### Environment  
  
| Variable | Description | Default |
| --- | --- | --- |
| STEAM_CMD_USER | the username for steam cmd login | anonymous |
| STEAM_CMD_PASSWORD | the password for steam cmd login | |
| UPDATE_EXTRA_ARGS | args passed to the steam cmd update command, i.e. workshop items | |
| START_EXTRA_ARGS | args passed to the server start command i.e. server profile etc | |
| APP_ID | the steam app id for the dayz server | 1042420 (experimental) |
