# Node.js docker build for Bitbucket Pipelines

This is the simplest example of a Node.js whose Docker image is built within BB pipelines and pushed to a private docker registry.

## Requirements

- You need a private Docker registry and you need the username and password to access it.

## Important files

- bitbucket-pipelines.yml - Bitbucket Pipelines configuration file that defines the build process for this repo.
- Dockerfile - The Docker configuration file.
- index.js - Simplest possible Node.js program.
- package.json - Node.js package configuration file.

## Setup instructions

- Create a repo in Bitbucket.
- Enable Pipelines throught the Bitbucket settings for the repo.
- You can view/modified the configuration for Pipelines in the file bitbucket-pipelines.yml.
- You need to set the following [environment variables in Bitbucket](https://confluence.atlassian.com/bitbucket/variables-in-pipelines-794502608.html)
    - $DOCKER_REGISTRY - the URL to access your private Docker registry.
    - $DOCKER_UN - The username for your private Docker registry.
    - $DOCKER_PW - The password for your private Docker registry.
- Commit this code to your repo and push it to Bitbucket. 

After pushing to Bitbucket your build should execute.
You can check recent builds in Bitbucket under the Pipelines section. Here you can see if the build succeeded or failed
If it failed you can check the console to find out why.

After a successful build you can check your private Docker registry to ensure that the expected image has been pushed to it.

## Resources

- https://www.atlassian.com/continuous-delivery/using-docker-with-pipelines
- https://bitbucket.org/blog/bitbucket-pipelines-supports-building-docker-images-and-service-containers
- https://confluence.atlassian.com/bitbucket/use-docker-images-as-build-environments-792298897.html
- https://confluence.atlassian.com/bitbucket/run-docker-commands-in-bitbucket-pipelines-879254331.html