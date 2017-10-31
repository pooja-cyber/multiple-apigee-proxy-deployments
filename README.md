The pom should do the following:
1) Configure the Target Servers or/and any other configurations
2) Update the proxy config to include the deployment suffix
3) Deploy to Apigee

The command to execute

```
mvn clean install -P{profile} \
 -Dapigee.config.dir=resources/edge \
 -Dapigee.config.options=update \
 -Ddeployment.suffix={number} 
```

For example

```
mvn clean install -Ptest \
 -Dapigee.config.dir=resources/edge \
 -Dapigee.config.options=update \
 -Ddeployment.suffix=2

```

If you want to skip the config updates as there will not be frequent changes

```
mvn clean install -Ptest \
 -Dapigee.config.dir=resources/edge \
 -Dapigee.config.options=update \
 -Ddeployment.suffix=2
 -Dskip.config=true

```

**NOTE: The `deployment.suffix` defaults to `1` and `skip.config` defaults to `false`**
