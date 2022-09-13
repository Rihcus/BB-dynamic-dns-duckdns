# Bluebubbles x Caddy x Duckdns (WIP)
A way to get https when portforwarding bluebubbles using caddy and duckdns

#Steps
1. Download xcaddy with duckns and move it to your home folder with the following command

Intel Macs:

`curl -o ./caddy https://caddyserver.com/api/download?os=darwin&arch=amd64&p=github.com/caddy-dns/duckdns&idempotency=8875705962096`

Apple Silicon:

`curl -o ./caddy https://caddyserver.com/api/download?os=darwin&arch=arm64&p=github.com/caddy-dns/duckdns&idempotency=28552737821716`

2. Make caddy runable with the command `chmod 755  ./caddy`

3. Download the template caddy file with the following command:

`curl -o ./Caddyfile`
