# minitor

Mini-sized Tor client (i.e. SOCKS-proxy) for Docker.
Same as https://hub.docker.com/r/toronsynology/tor-client-minimal (from https://github.com/tor-on-synology/tor-client-minimal) only using alpine:edge as base instead of alpine:latest, to get the current version of Tor instead of an older version of Tor.
Ensuring a current version of Tor can sometimes be critical to ensure the functionalities expected by its users.

Remember to add "--publish 9150:9150" or your chosen equivalent port assignment to your "docker run" in order to be actually able to use the exposed port, if that's what you wanted.
