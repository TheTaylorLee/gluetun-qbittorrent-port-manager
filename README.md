# Disclaimer
This is a fork of a fork of [snoringdragon's](https://github.com/SnoringDragon) gluetun qbittorrent port forward update tool. I've updated it to create docker images using an action. If it is ever failing it may or may not get fixed.

# gluetun-qbittorrent Port Manager
Automatically updates the listening port for qbittorrent to the port forwarded by [Gluetun](https://github.com/qdm12/gluetun/).

## Description
[Gluetun](https://github.com/qdm12/gluetun/) has the ability to forward ports for supported VPN providers, but qbittorrent does not have the ability to update its listening port dynamically.

I modified the script by [snoringdragon](https://github.com/SnoringDragon)  to reach out to the [Gluetun](https://github.com/qdm12/gluetun/) control server API and updates the qbittorrent's listening port based on the response.

## Setup
First, ensure you are able to successfully connect qbittorrent to the forwarded port manually (can be seen by a green globe at the bottom of the WebUI).

Second, ensure the [Gluetun](https://github.com/qdm12/gluetun/) control server port (default 8000) is exposed in your compose file.

Finally, insert the template in `docker-compose.yml` into your docker-compose containing gluetun, substituting the default values for your own.
