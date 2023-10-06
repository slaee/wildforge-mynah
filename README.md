# Pulling the project 
```bash
git clone git@github.com:slaee/wildforge-mynah.git
cd wildforge-mynah
git submodule init
git submodule update --remote
```

# Development 
Update the `wildforge-api/backend/wildforge/settings.py` under Database configuration with this code or just uncomment
```python
DB_NAME = os.getenv('DB_NAME')
DB_USER = os.getenv('DB_USER')
DB_PASSWORD = os.getenv('DB_PASSWORD')
DB_HOST = os.getenv('DB_HOST')
DB_PORT = os.getenv('DB_PORT')

LOCAL_HOST = os.getenv('LOCAL_HOST')

# use environment variables from /backend/env/backend.env
# load_dotenv(dotenv_path=API_REPO_DIR / 'env' / 'backend.env')

# DB_NAME = os.getenv('DB_NAME')
# DB_USER = os.getenv('DB_USER')
# DB_PASSWORD = os.getenv('DB_PASSWORD')
# DB_HOST = '0.0.0.0'
# DB_PORT = os.getenv('DB_PORT')

# LOCAL_HOST = os.getenv('LOCAL_HOST')
```

Running the docker-compose:
```bash
docker-compose up --build -d
```

To stop the docker-compose and cleaning up volumes to save space:
```bash
docker-compose down
docker volume rm $(docker volume ls -q)
```
