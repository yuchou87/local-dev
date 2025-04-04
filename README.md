# local-dev

This is a repository for local development environment setup.

## Usage

```bash
# Clone the repository
git clone https://github.com/yuchou87/local-dev.git
cd local-dev
# Run the docker compose command with all profiles
docker compose --profile "*" up -d
# Run the docker compose command with base profile
docker compose --profile=base up -d

# ssl certs
docker compose --profile=web exec caddy caddy trust
# format caddyfile
docker compose --profile=web exec -w /etc/caddy caddy caddy fmt --overwrite
# reload caddy
docker compose --profile=web restart caddy

# Save the root CA certificate to a file, and double click the certificate file to install it
docker compose --profile='*' exec caddy cat /data/caddy/pki/authorities/local/root.crt

# Access the local development environment using the following URL
https://local-dev.com

# Access the consul server using the following URL
http://local-dev.com:8500/ui

# Access the vault server using the following URL
http://local-dev.com:8200/ui
```
