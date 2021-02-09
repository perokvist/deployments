# deployments
A collection of github action utils

## dapr

> Exprimental compose files for single app use of dapr.

### Azure Web Apps for Containers

The docker-compose file in the "dapr" folder could be used with the "azure/webapps-deploy@v2" github action. The ENV variables set in the github action seems to not be in context. The app configuration settings sould be in scope.

#### Options

- Deploy with compose in github action
- Configure compose file in deployment center and use web hook to deploy.

> Since compose support is in preview there is alot of [unsupported features](https://docs.microsoft.com/en-us/azure/app-service/configure-custom-container?pivots=container-linux#configure-multi-container-apps), that dapr might need.


> [Environment variables in the compose file doesn't seem to be supported](https://stackoverflow.com/questions/64760074/azure-web-app-service-for-linux-containers-not-picking-up-environment-variables), and will need to be manually replaced to fit the scenario.

### Azure Container Instances

The docker-compose file in the "dapr" folder could be use in a github action, but not as straight forward as for web apps.

#### Options
- Deploy with compose in github action
- Configure compose file in deployment center and use web hook to deploy.