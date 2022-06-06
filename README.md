## Directory Structure

- `/fabric`: Fabric network used as a test environment
- `/chaincode`: chaincode-related files
- `/rest-server`: chaincode REST API project

## Development

Install dependencies: 

In the root folder run ./installPreReqUbuntu.sh

Dependencies for chaincode:

- Go 1.14 or higher

Dependencies for test environment:

- Docker 20.10.5 or higher
- Docker Compose 1.28.5 or higher
- Node v8.17.0
- Node Package Manager (npm) 6.14.11 or higher

Installation:

```bash
$ cd chaincode; go mod vendor; cd ..
$ cd rest-server; ./npmInstall.sh; cd ..
```

After installing, use the script `./startDev2.sh` in the root folder to start the development environment. It will
start all components of the project.

To apply chaincode changes, run `$ ./upgradeCC2.sh <version>` with a version higher than the current one (starts with 0.1).

To apply CC API changes, run `$ ./reloadCCAPI.sh`.

To test transactions after starting all components, run `$ ./tryout.sh`.

NOTES: 

- If Permission is denied to execute files, run in the root folder : 

```bash
$ chmod +X *
```
- The chaincode interface can be accessed by browsing http://localhost:8080/
- the API can be accessed by browsing http://localhost:880/api-docs/, http://localhost:980/api-docs/, or http://localhost:1080/api-docs/. The "880" represents the org.
