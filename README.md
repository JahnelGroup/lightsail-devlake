# Lightsail Devlake

The purpose of this repo is to automate the deploy of Devlake to an Amazon Lightsail instance. 

## How do deploy this from AWS Lightsail console

### If you already have an instance up

SSH into the instance, run
```curl -o https://raw.githubusercontent.com/jahnelgroup/lightsail-devlake/main/docker-compose.yml```
to get the docker compose file into the instance.
```docker-compose -f docker-compose.yml up -d```
This runs the docker compose file and sets up the devlake server on port 8080. If you want devlake on a different port, you can specify in the compose file.

### If you do not have an instance already

TODO


## How to start this locally

You can use a .env file to export the environment variables to a local file you don't check into source control.

```docker-compose --env-file .env.dev up -d```
