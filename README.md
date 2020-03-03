# minitor

Mini-sized Tor client (i.e. SOCKS-proxy) for Docker.
Same as https://hub.docker.com/r/toronsynology/tor-client-minimal (from https://github.com/tor-on-synology/tor-client-minimal) only using alpine:edge as base instead of alpine:latest, to get the current version of Tor instead of an older version of Tor.
Ensuring a current version of Tor can sometimes be critical to ensure the functionalities expected by its users.

Could be used as a super-light local proxy on a desktop/laptop to Torify one of your browsers, if you want to use soething else than the modified Firefox provided by the Tor Project as their "Tor Browser Bundle".
For example, you could pass something similar to this to a portable Chromium browser such as through chrlauncher (https://github.com/henrypp/chrlauncher) to Torify Chromium (but it's your own responsibility to anonymize/pseudonymize your browser and behavior):
```
docker run --detach --rm --publish 127.0.0.1:9150:9150 b9ace/minitor
"[path to chrlauncher]\chrlauncher.exe" /forcecheck --proxy-server="socks5://localhost:[your configured port]"
```
That "--proxy-server=" allows for setting proxy only for the session and without affecting any other software, as would normally be the case nowadays when Chrome/Chromium otherwise demands to get the proxy configuration from the system-settings, which would run everything that respects that system setting properly through Tor as well, which may be very undesired.

Remember to add "--publish 9150:9150" or your chosen equivalent port assignment to your "docker run" in order to be actually able to use the exposed port on the host, if that's what you wanted.
