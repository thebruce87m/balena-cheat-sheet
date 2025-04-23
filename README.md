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

Ping supervisor
```bash
curl -X GET --header "Content-Type:application/json" \
"$BALENA_SUPERVISOR_ADDRESS/ping"
```

Response
```bash
OK
```
