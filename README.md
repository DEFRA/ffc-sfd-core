# Single Front Door Core
Local development support for orchestrating all Single Front Door microservices.

## Prerequisites

Ensure you have satisfied the prerequisites of all individual repositories.

## Repositories
### Frontends
- [ffc-sfd-landing-page](https://github.com/defra/ffc-sfd-landing-page)
- [ffc-sfd-proxy](https://github.com/defra/ffc-sfd-proxy)
- [ffc-sfd-ahwp-stub](https://github.com/defra/ffc-sfd-ahwp-stub)
- [ffc-sfd-permissions](https://github.com/defra/ffc-sfd-permissions)
- [ffc-sfd-messages](https://github.com/DEFRA/ffc-sfd-messages)
- [ffc-sfd-queries](https://github.com/DEFRA/ffc-sfd-queries)

### Backends
- [ffc-sfd-auth](https://github.com/defra/ffc-sfd-auth)
- [ffc-sfd-business](https://github.com/defra/ffc-sfd-business)
- [ffc-sfd-ingress](https://github.com/defra/ffc-sfd-ingress)
- [ffc-sfd-gateway](https://github.com/defra/ffc-sfd-gateway)
- [ffc-sfd-permissions-api](https://github.com/defra/ffc-sfd-permissions-api)
- [ffc-sfd-messages-processor](https://github.com/DEFRA/ffc-sfd-messages-processor)

### Customer
- [ffc-sfd-data](https://github.com/defra/ffc-sfd-data)
- [ffc-sfd-customer-receiver-messages](https://github.com/DEFRA/ffc-sfd-customer-receiver-messages)
- [ffc-sfd-customer-receiver-payments](https://github.com/DEFRA/ffc-sfd-customer-receiver-payments)
- [ffc-sfd-customer-receiver-preferences](https://github.com/DEFRA/ffc-sfd-customer-receiver-preferences)
- [ffc-sfd-customer-receiver-queries](https://github.com/DEFRA/ffc-sfd-customer-receiver-queries)

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

#### Resources
`./resources/cosmos-upload`  

Upload multiple items to a local emulator instance of cosmos. Follow the command prompt to provide:
- crn
- sbi
- database name
- container name
- quantity

Currently the items uploaded match the messages and queries database schema only.

### Resource quota

Determine the Kubernetes resource usage for a namespace based on all microservices running at maximum capacity and scaling.

[`./resource-quota`](resource-quota)