+++
title = "Installation"
weight = 15
+++

## Server Installation

The server consists of a series of containers, defined as kubernetes resources and packaged in helm.

Before starting, you will need to have an available Kubernetes cluster, with helm setup. 
Minikube is a great way of getting started with this locally.

You will also need to obtain a series of configuration properties. At the time being, these are: 

- GitHub API token for mining information from the GitLAB API. (Large read scope, no write)
- GitHub API token for reading from the package repository.
- GitLab API token for mining information from the GitLab API. (Large read scope, no write)

Place these into a file called `private_values.yml` in the format:

```
gitlab:
  oAuthToken: <YOUR VALUE HERE>
github:
  oAuthToken: <YOUR VALUE HERE>
ghDockerRegistryCredentials:
  registry: docker.pkg.github.com
  username: <YOUR GITHUB USERNAME HERE>
  password: <YOUR VALUE HERE>
```

Clone `https://github.com/dominiccobo-fyp/infrastructure`

and inside run: 

`helm install ./gcs --namespace gcs --values=private_values.yaml --name gcs`


## Client Installation

### Visual Studio Code

For the Visual Studio Code client, please download the most recent release under: 
https://github.com/dominiccobo-fyp/vscode-command-extension/releases/

Please see [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery#_install-from-a-vsix) 
for help installing the file.