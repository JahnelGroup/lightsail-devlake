# Lightsail Devlake

The purpose of this repo is to automate the deploy of Devlake to an Amazon Lightsail instance. 

## How do deploy this from AWS Lightsail console

* From the Lightsail console click `Create Instance`.
* Choose whichever region you prefer (us-east-1).
* Under `Select a blueprint` click on `OS Only` and choose Amazon Linux.
* Create an SSH keypair.
* Check `Enable Automatic Snapshots`.
* Choose the instance size. This requires a Sonarqube server and a Postgres, so probably the $10-20/mo version.
* Add your tags.

SSH into the instance, grab the docker compose file:

```curl -o https://raw.githubusercontent.com/jahnelgroup/lightsail-devlake/main/docker-compose.yml```

And then run the docker compose:

```docker-compose -f docker-compose.yml up -d```

This sets up the devlake server on port 8080. If you want devlake on a different port, you can specify in the compose file.
