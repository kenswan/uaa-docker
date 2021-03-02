# UAA-CLI

## Build

`docker build -t uaa-cli .`

## Run

`docker run --rm -it uaa-cli bash`

<i>If uaa is in another local docker container, you can link by following steps below:</i>

- Add `--link=<your containername>` to above run command
- Run `env` to list environment variables
- Find ip address in variable `<your container name>_PORT_8080` 
- Use this ip address in `uaac target` command below

## Commands
<i>Check UAAC version</i>

`uaac -v`

<i>Connecting to UAA Server</i>

`uaac target http://<domain>/uaa`

<i>Set context for subsequent commands (add users, groups, etc.)</i>

`uaac token client get admin -s adminsecret`

## Resources
- [cf-uaac repo](https://github.com/cloudfoundry/cf-uaac)
- [cf-uaac workflow](https://www.baeldung.com/cloud-foundry-uaa#6-installing-the-uaa-command-line-client)
