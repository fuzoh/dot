# Caddy web server

[Caddy](https://caddyserver.com/v2) is a light web server, with default http2 and https.

## Installation

```
$ brew install caddy
```

## Custom configuration

Add a `Caddyfile` in `/usr/local/etc`.

```
# Caddyfile

# Declare a site on localhost vhost
localhost {

  # Path to the site base folder
  root * /path/to/my/incredible/website

  # Declare a file server for this site
  file_server

  # Declare a php fastcgi pass
  php_fastcgi 127.0.0.1:9000

}
```

## Launch the service

```
$ brew services start caddy

$ brew services restart caddy

$ brew services stop caddy
```
