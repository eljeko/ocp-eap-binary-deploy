# Build the app

From the project root

```cd web-app```

Build the app:

```mvn clean package -Dappversion=1.0```

Then go back to the project root

# Crate new project (if needed)

Create the project

```oc new-project eap-playground```

```oc project eap-playground```

# Deploy the app

Create new app:

```
oc new-app jboss-eap72-openshift:1.1 --binary --name=helloapp
```

Start the binary build:

```oc start-build helloapp --from-file web-app/target/ROOT.war --follow;```

Expose the service:

```oc expose svc helloapp```

Now from the route created by OpenShift you can reach the application deployed.