# Getting Started

Our `ez_shopping` application primarily uses:

- Python
- Poetry
- Docker
- ngrok.

Therefore, you must have the listed software installed. We walk through how to do this for each of the items listed.

## Setting up a Poetry Environment

The Python environment manager we use for this project is Poetry 2. For more detailed instructions and usage of poetry, defer to the official [Poetry documentation](https://python-poetry.org/docs/).

!!! info "Unix-based (Mac and Linux)"
    ```bash
    $ curl -sSL https://install.python-poetry.org | python3 -

    $ poetry shell
    $ poetry install
    ```

!!! info "Windows (Powershell)"
    ```powershell
    (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -
    ```

Once installed, cd into the root directory of the project and run:

```bash
poetry shell

# or on newer versions of poetry
python -m venv .venv
source .venv/bin/activate

# next steps
poetry install # install dependencies and editable install of source code.
```

To build a release artifact of the software, run:

```bash
poetry build -f wheel
```

The python artifact then installs to: `<root>/dist/*.whl`

## Setting up Docker

On linux, you can install docker with your package manager:

```bash
sudo dnf install -y docker # fedora

sudo apt install -y docker # debian
```

On mac and linux, it is recommended to install Docker via [Docker Desktop](https://www.docker.com/products/docker-desktop/).

we mostly use the docker-compose cli tool for spawning our databse servers.

## Setting up Ngrok

Ngrok is the gateway technology we use. Create a free account with them to get an API token. Defer to [ngrok documentation](https://ngrok.com/docs/). Detailed instructions on how to install are [given here](https://ngrok.com/downloads/linux).

most package managers support the software:

!!! info "Debian"
    ```sudo apt install ngrok```

!!! info "Fedora"
    ```sudo dnf install ngrok```

!!! info "Mac"
    ```brew install ngrok```

!!! info "Windows"
    ```choco install ngrok```

Once installed, you need to authenticate your ngrok instance by running:

```bash
ngrok config add-authtoken <your-token-here>
```

To spin-up the ngrok client, we provide a shell script at: [./scripts/create_ngrok_tunnel.sh](https://github.com/rarnold97/ceg6110-term-project-group-2/blob/main/scripts/create_ngrok_tunnel.sh).

## Deploy EzShopping.

Once the above dependencies are resolved, you may deploy the suite of services for the EzShopping application as shown below:

**ngrok gateway**


<!-- termynal -->
```
$ poetry install
$ docker compose up mongo mongo-express
$ streamlit run ez_shopping/frontend/app.py
```

!!! note
    The ngrok tunnel needs to be ran in a separate terminal instance

<!-- termynal -->
```
$ ./scripts/create_ngrok_tunnel.sh
```


!!! tip "All Commands"
    ```bash
    cd <parent-dir>/ez_shopping
    poetry config virtualenvs.in-project true
    poetry install
    docker compose up mongo mongo-express
    streamlit run ez_shopping/frontend/app.py

    # in separate terminal
    ./scripts/create_ngrok_tunnel.sh
    ```

Once all commands are executed, you will be redirected to the application's frontend via browser.

!!! warning
    The current version of the software, as of March 2025, runs on local-host only.