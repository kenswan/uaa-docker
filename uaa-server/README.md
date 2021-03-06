# UAA-Server

## Build

`docker build -t uaa-docker .`

## Run

`docker run -d -it -p 8080:8080 --name uaa-server uaa-docker`

## Navigate

`docker exec -it uaa-server bash`

## Test

Running below command
```powershell
curl http://localhost:8080/uaa/info
```

Should yield response similar to
```json
{
    "app": {
        "version": "0.0.0"
    },
    "links": {
        "uaa": "http://localhost:8080/uaa",
        "passwd": "/forgot_password",
        "login": "http://localhost:8080/uaa",
        "register": "/create_account"
    },
    "zone_name": "uaa",
    "entityID": "cloudfoundry-saml-login",
    "commit_id": "ecf3734",
    "idpDefinitions": {},
    "prompts": {
        "username": [
            "text",
            "Email"
        ],
        "password": [
            "password",
            "Password"
        ]
    },
    "timestamp": "2021-02-04T19:51:58+0000"
}
```
