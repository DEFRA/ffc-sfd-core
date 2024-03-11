# Single Front Door Core
Local development support for orchestrating all Single Front Door microservices.

## Prerequisites

Ensure you have satisfied the prerequisites of all individual repositories.

## Repositories
- [ffc-sfd-gateway](https://github.com/defra/ffc-sfd-gateway)
- [ffc-sfd-landing-page](https://github.com/defra/ffc-sfd-landing-page)
- [ffc-sfd-business](https://github.com/defra/ffc-sfd-business)
- [ffc-sfd-auth](https://github.com/defra/ffc-sfd-auth)
- [ffc-sfd-proxy](https://github.com/defra/ffc-sfd-proxy)
- [ffc-sfd-ingress](https://github.com/defra/ffc-sfd-ingress)
- [ffc-sfd-data](https://github.com/defra/ffc-sfd-data)
- [ffc-sfd-permissions](https://github.com/defra/ffc-sfd-permissions)
- [ffc-sfd-permissions-api](https://github.com/defra/ffc-sfd-permissions-api)
- [ffc-sfd-ahwp-stub](https://github.com/defra/ffc-sfd-ahwp-stub)

## Scripts

### Clone

Clone all repositories from GitHub.  Repositories will cloned in the parent directory of this repository.

[`./clone`](clone)

### Update

Switch to `main` branch in every repository and pull latest changes with `git pull`.

[`./update`](update)

### Build

Build/rebuild Docker container for all microservices.

[`./build`](build)

### Start

Run all services.

Runs `Seed` script if `ffc-sfd-scripts` repository is cloned.

[`./start`](start)

#### Optional arguments
- `-f` - include Azure Functions
- `-s` - include Statement services
- `-S` - only statement services

### Stop

Run all services.

[`./stop`](stop)

#### Optional arguments

Any valid `docker-compose down` argument.

### Seed

Seed customer mapping data from private repository to `ffc-sfd-business` if `ffc-sfd-scripts` repository is cloned.

[`./seed`](seed)

### Open

Open all services in Visual Studio Code.

[`./open`](open)

#### Optional arguments
- `-f` - include Azure Functions
- `-s` - include Statement services
- `-S` - only statement services

### Latest versions

List latest GitHub release version for each microservice.

[`./latest-versions`](latest-versions)

### Environment versions

List current environment version for each microservice hosted in Kubernetes.

[`./environment-versions`](environment-versions)

#### Options
- `-c | --cluster` - Kubernetes cluster context name
- `-n | --namespace` - Kubernetes namespace

### Resource quota

Determine the Kubernetes resource usage for a namespace based on all microservices running at maximum capacity and scaling.

[`./resource-quota`](resource-quota)
