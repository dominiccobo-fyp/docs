+++
title = "Server-Side"
weight = 16
+++

## Messaging

The messaging technology used currently is [Axon Server](https://docs.axoniq.io/reference-guide/axon-server).

## Deployment and Packaging

 
#### Kubernetes

Used to orchestrate the server side containers.

[Product Website](https://kubernetes.io/)

#### Helm

Used for simplification of the packaging and deployment of the server-side components.

[Product Website](https://helm.sh/)

### Creating a resolver

Below is an example of the requirements to implement a resolver

```Java
@SpringBootApplication
public class App {
    public static void main(String[] args){
        SpringApplication.run(App.class, args); 
    }
}


@Component
public class ExpertsProvider implements ExpertsQueryListener {
	@QueryHandler
	@Override
	public List<Expert> on(AssociatedExpertsQuery query) {
		// TODO: compute values that need returning
		return new ArrayList<>();
	}
}
```

Using the following dependencies:

```Groovy
implementation 'org.axonframework:axon-spring-boot-starter:{axon-version}'
implementation 'com.dominiccobo.fyp:context-lsp-api:{api-version}'
implementation 'org.springframework.boot:spring-boot-starter-web:{spring-version}'
```

```properties
axon.axonserver.servers=${AXON_SERVER_HOSTNAME}
```

See [GitHub WorkItems](https://github.com/dominiccobo-fyp/github-workitems-resolver) for examples.
