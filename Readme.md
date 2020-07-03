## Run locally:
* From command line: `API_KEY=mykey AUTH_TOKEN=mytoken go run main.go`

## Usage:
* Curl endpoint for token:
```
curl http://localhost:8000/token -d "AUTH_TOKEN=mytoken"
```
* Curl endpoint with token
```
curl http://localhost:8000 -H "Authorization: Bearer <token from above>"
```
* All together: 
```
curl http://localhost:8000 -H "Authorization: Bearer $(curl http://localhost:8000/token -d "AUTH_TOKEN=mytoken" | jq -r '.token')" 
```