+++
title = "Client-Side"
weight = 16
+++

## Areas of Development

### The Daemon

The daemon is developed using Java. [Spring](https://spring.io/projects/spring-boot) is used as the base platform with 
[Axon Framework](https://axoniq.io/) for messaging.

#### Guidelines

- Focuses mainly on backend logic and reusable integration points.

### IDE Extensions

Each IDE has its own approach to plugins. For example, [Electron](https://www.electronjs.org/) based IDEs such a
[Atom](https://atom.io/) and [VSCode](https://code.visualstudio.com/) rely on variations of 
[NodeJS](https://nodejs.org/en/) for extensibility.

#### Guidelines

- Focus on the principles of thin clients.
- If you need to implement large amounts of logic other than formatting, you should look at the Daemon.
