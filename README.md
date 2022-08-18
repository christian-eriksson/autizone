# Autizone

Can update the timezone if it detects an ip change. Consists of a systemd
service that monitors changes in the systems IP addresses and runs the
`autizone` script if an IP address with global scope is obtained.

It will print the new timezone to the units log as
`new timezone: Europe/Stockholm`. You can see this by running this, as root:
`journalctl -fu ip-change-detect.service`

**NOTE:** we use [ipapi.co](https://ipapi.co/) to fetch the location of the
device. Make sure that you are within the free tier or [signup for a plan](https://ipapi.co/#pricing).

## Install

```sh
cp autizone /usr/local/bin
mkdir -p /usr/local/lib/systemd/system
cp ip-change-detect.service /usr/local/lib/systemd/system
```
