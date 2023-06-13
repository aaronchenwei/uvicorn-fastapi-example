# uvicorn-fastapi-example <!-- omit in toc -->

## 1. Development Setup

### 1.1. Clone Project

```bash
$ git clone https://github.com/aaronchenwei/uvicorn-fastapi-example.git

# enter directory of cloned project 
$ cd uvicorn-fastapi-example
```

### 1.2. Creating the environment

```sh
$ conda create --name uvicorn-fastapi-example --file conda-linux-64.lock
$ conda activate uvicorn-fastapi-example
$ poetry install
```

### 1.3. Activating the environment

```sh
$ conda activate uvicorn-fastapi-example
```

### 1.4. Updating the environment

```sh
# Re-generate Conda lock file(s) based on environment.yml
$ conda-lock -k explicit --conda mamba
# Update Conda packages based on re-generated lock file
$ mamba update --file conda-linux-64.lock
# Update Poetry packages and re-generate poetry.lock
$ poetry update
```

### 1.5. Run application in project directory

```bash
$ poetry run uvicorn --workers 1 --host 0.0.0.0 --port 80 app.main:app
```

### 1.6. Run pytest

```bash
$ poetry run pytest
```

### Docker image

```bash
# export requirements.txt
$ poetry export --without-hashes --format=requirements.txt > requirements.txt

# Build Docker image
$ docker build -t aaronchenwei/uvicorn-fastapi-example .

# Run Docker container
$ docker run -d --name uvicorn-fastapi-example -p 80:80 aaronchenwei/uvicorn-fastapi-example 
```