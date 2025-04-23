# balena-cheat-sheet

Login
```bash
balena login
```

List fleets
```bash
balena fleet list
```

Push and build on their server:
```bash
balena push username/fleet-name
```

# Develop Locally

Find local devices
```bash
sudo balena device detect

# Or:
sudo $(which balena) device detect
```

Push build locally
```bash

# Change name to detected device
balena push 63ec46c.local
```


# API

## Ping supervisor
```bash
curl -X GET --header "Content-Type:application/json" \
"$BALENA_SUPERVISOR_ADDRESS/ping"
```

Response
```bash
OK
```

## Get State

```bash
# Raw output
curl "$BALENA_SUPERVISOR_ADDRESS/v2/state/status?apikey=$BALENA_SUPERVISOR_API_KEY"

# Or use jq to format:
curl "$BALENA_SUPERVISOR_ADDRESS/v2/state/status?apikey=$BALENA_SUPERVISOR_API_KEY" | jq '.'
```

## Stop Service

```bash
curl --header "Content-Type:application/json" \
"$BALENA_SUPERVISOR_ADDRESS/v2/applications/$BALENA_APP_ID/stop-service?apikey=$BALENA_SUPERVISOR_API_KEY" \
-d '{"serviceName": "my-service"}'
```

Response
```bash
OK
```
