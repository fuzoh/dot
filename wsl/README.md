# WSL specific tips

## Launch backgroud process

WSL dosen't use the default distribution init system. So you cannot use systemd
to manage processes.
Instead you can use the service command, below an example with postgresql :

```
# Check the status of a service
$ sudo service postgresql status

# Start a service
$ sudo service postgresql start

# Stop a service
$ sudo service postgresql stop
```
