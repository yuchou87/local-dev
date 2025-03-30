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

# Access the local development environment using the following URL
https://local-dev

# Access the consul server using the following URL
http://local-dev:8500/ui

# Access the vault server using the following URL
http://local-dev:8200/ui
```
