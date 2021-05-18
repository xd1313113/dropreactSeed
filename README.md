# drop-react - Example Dropwizard & React application

A simple example application to show how to use dropwizard with a react UI.

## How to start the DropReact application

1. Run `mvn clean package` to build your application
1. Start application with `java -jar target/dropreact-1-SNAPSHOT.jar server config.yml`
1. To check that your application is running enter url `http://localhost:8080`

## Development

1. Run `mvn clean package` to build your application
1. Start application with `java -jar target/dropreact-1-SNAPSHOT.jar server config.yml`
1. Start the development web server with `cd src/web && yarn start`
1. Access your application via `http://localhost:3000`

The react dev webserver will proxy all requests to the dropwizard API server
at `http://localhost:8080`.

## Deploy in Azure
You can prepare your application for Azure Web App easily with one command:

```shell
mvn com.microsoft.azure:azure-webapp-maven-plugin:1.14.0:config
```

This command adds a `azure-webapp-maven-plugin` plugin and related configuration by prompting you to select an existing Azure Web App or create a new one. Then you can deploy your Java app to Azure using the following command:
```shell
mvn package azure-webapp:deploy
```

Then login in azure and find created webapp instance
1. In the Configuration Tab -> General Setting ->  Startup Command, set value "java -jar dropreact-1-SNAPSHOT.jar server config.yml"
1. In the Configuration Tab -> Application settings -> Port, set value "8080"
1. It is better to enable logs "App Service logs".
1. Upload the jar file to FTP /site/wwwroot folder

