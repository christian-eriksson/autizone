# Autizone

Can update the timezone if it detects an ip change. Consists of a systemd
service that monitors changes in the systems IP addresses and runs the
`autizone` script if an IP address with global scope is obtained.

It will print the new timezone to the units log as
`new timezone: Europe/Stockholm`. You can see this by running this, as root:
`journalctl -fu ip-change-detect.service`

## Install

```sh
cp autizone /usr/local/bin
mkdir -p /usr/local/lib/systemd/system
cp ip-change-detect.service /usr/local/lib/systemd/system
```
