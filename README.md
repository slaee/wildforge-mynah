# Pulling the project 
```bash
$ git clone git@github.com:slaee/wildforge-mynah.git
$ cd wildforge-mynah
$ git submodule init
$ git submodule update --remote
```

# Development 
Update the `wildforge-api/backend/wildforge/settings.py` under Database configuration with this code or just uncomment
```python
# Database
# https://docs.djangoproject.com/en/4.2/ref/settings/#databases

DB_NAME = os.environ.get('DB_NAME')
DB_USER = os.environ.get('DB_USER')
DB_PASSWORD = os.environ.get('DB_PASSWORD')
DB_HOST = os.environ.get('DB_HOST')
DB_PORT = os.environ.get('DB_PORT')

# use environment variables from /backend/env/backend.env
# load_dotenv(dotenv_path=API_REPO_DIR / 'env' / 'backend.env')

# DB_NAME = os.getenv('DB_NAME')
# DB_USER = os.getenv('DB_USER')
# DB_PASSWORD = os.getenv('DB_PASSWORD')
# DB_HOST = os.getenv('DB_HOST')
# DB_PORT = os.getenv('DB_PORT')
```

Running the docker-compose:
```bash
$ docker-compose up --build -d
```

To stop the docker-compose and cleaning up volumes to save space:
```bash
$ docker-compose down
$ sudo docker volume rm $(sudo docker volume ls -q)
```
