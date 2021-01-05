# Homebrew

## Services

```
# Start a service and register de service in launch agent deamon
$ brew services start caddy

# Stop the service
$ brew services stop caddy

# Stop all launched services
$ brew services stop --all

# Just start a service without registering it in macos launch agent
$ brew services run php

# Restart a service
$ brew services restart caddy

# Clean unused services
$ brew services cleanup
```
