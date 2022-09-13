# Bluebubbles x Caddy x Duckdns
A way to get https when portforwarding bluebubbles using caddy and duckdns
This guide is written with the intention caddy is deployed on the same mac as your bluebubbles server but the config can be tweaked if you have a remote caddy server

Benefits:
- Works nonstandard ports

## Requirements
- A duckdns account with a domain https://www.duckdns.org/domains
- A setup bluebubbles server
- The ability to portforward

## Steps to setup caddy
1. Download xcaddy with duckns and move it to your home folder with the following command

Intel Macs:

`curl -o ./caddy https://caddyserver.com/api/download?os=darwin&arch=amd64&p=github.com/caddy-dns/duckdns&idempotency=8875705962096`

Apple Silicon:

`curl -o ./caddy https://caddyserver.com/api/download?os=darwin&arch=arm64&p=github.com/caddy-dns/duckdns&idempotency=28552737821716`

2. Make caddy runable with the command `chmod 755  ./caddy`

3. Download the template caddy file with the following command:

`curl -o ./Caddyfile https://raw.githubusercontent.com/Rihcus/BB-dynamic-dns-duckdns/main/Caddyfile`

4. Edit the Caddyfile
- replace the example domains with your domains
- replace `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` with your duckdns token
- Optional ajust the https/http or bluebubbles server ports as needed

5. For testing purposes set your duckdns domain to the local ip of your bluebubbles server using the duckdns web portal

https://www.duckdns.org/domains

6. test the config with `./caddy run`
7. if the config works and you can acess your domain via https use `./caddy start` to make it auto run
8. Setup portforwarding (not covered in this guide)
9. Optional install duckdns to your mac server inorder to autoupdate public ip

https://www.duckdns.org/install.jsp
