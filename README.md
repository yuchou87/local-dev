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
```
