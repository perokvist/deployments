# deployments
A collection of github action utils

## dapr

> Exprimental compose files for single app use of dapr.

> WiP - see issues for status

### Azure Web Apps for Containers

The docker-compose file in the "dapr" folder could be used with the "azure/webapps-deploy@v2" github action. The ENV variables set in the github action seems to not be in context. The app configuration settings sould be in scope.

#### Options

- Deploy with compose in github action
- Configure compose file in deployment center and use web hook to deploy.

> Since compose support is in preview there is alot of [unsupported features](https://docs.microsoft.com/en-us/azure/app-service/configure-custom-container?pivots=container-linux#configure-multi-container-apps), that dapr might need.


> [Environment variables in the compose file doesn't seem to be supported](https://stackoverflow.com/questions/64760074/azure-web-app-service-for-linux-containers-not-picking-up-environment-variables), and will need to be manually replaced to fit the scenario.

#### Storage
In the compose file, Azure File Storage is used. It might be possible to use the host storage when running web apps.

### Azure Container Instances

The docker-compose file in the "dapr" folder could be use in a github action, but not as straight forward as for web apps.

#### Options
- Deploy with compose in github action
- Configure compose file in deployment center and use web hook to deploy.

### Azure Functions
The support for running functions in a custom container, is basicly running functions in app service, but based on an functions runtime image. The compose support is the same as in app service, but now with access to the [dapr integration](https://cloudblogs.microsoft.com/opensource/2020/07/01/announcing-azure-functions-extension-for-dapr/).

The [dapr functions extension](https://github.com/dapr/azure-functions-extension) adds access to dapr triggers and bindings.

#### Options
- Deploy with compose in github action
- Configure compose file in deployment center and use web hook to deploy.

### Logging
When running on App Service with Linux containers, yoou need to enable logging - 
[Enable logging for linux containers](https://docs.microsoft.com/en-us/azure/app-service/troubleshoot-diagnostic-logs#enable-application-logging-linuxcontainer)

### Logic Apps

Since the new [Logic Apps runtime](https://techcommunity.microsoft.com/t5/azure-developer-community-blog/new-logic-apps-runtime-performance-and-developer-improvements/ba-p/1645335) let you run workflows anywhere containerized, it could run in all mentioned services. With the [dapr workflows](https://cloudblogs.microsoft.com/opensource/2020/05/26/announcing-cloud-native-workflows-dapr-logic-apps/) this allows you to utilize dapr service invocation and binding triggers in [workflows](https://github.com/dapr/workflows).

### Resources

- [Configure a GitHub action to create a container instance](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-github-action)
- [Setting Up Cloud Deployments Using Docker, Azure and Github Actions](https://www.docker.com/blog/setting-up-cloud-deployments-using-docker-azure-and-github-actions/)
- [Dapr Sample - Hello docker compose](https://github.com/dapr/samples/tree/master/hello-docker-compose)
- [Dapr demos](https://github.com/mchmarny/dapr-demos)
- [Dapr Web Push Sample](https://github.com/perokvist/Dapr.WebPush)
- [Dapr docs - self hosted with docker](https://v1-rc3.docs.dapr.io/operations/hosting/self-hosted/self-hosted-with-docker/#run-using-docker-compose)
- [Units of deployment - a brief look into the future, guided by dapr](https://perokvist.github.io/event-driven-architecture/azure_containers.html)

