# Cinema API
API service for cinema management written on DRF

## Installing using GitHub
Install PostgresSQL and create db

```
git clone https://github.com/alina-boichenko/cinema-api.git
cd cinema-api
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
set POSTGRES_HOST=<your db hostname>
set POSTGRES_DB=<your db name>
set POSTGRES_USER=<your db username>
set POSTGRES_PASSWORD=<your db user password>
set SECRET_KEY=<your secret key>
python manage.py migrate
python manage.py runserver
```

### Run with docker
Docker should be installed
```
docker-compose build
docker-compose up
```

### Getting access
```
Create user via /api/user/register/
Get access token via /api/user/token/
Install ModHeader extension and create Request header with value: Bearer <Your access token>
```

### Features
- JWT authenticated
- Admin panel /admin/
- Documentation is located at /api/doc/swagger/
- Managing orders and tickets
- Creating movies with genres, actors
- Creating cinema halls
- Adding movie sessions
- Filtering movies and movie sessions

### Creating Admin user
1. Display containers list:
```
docker ps
```
2. Copy container ID
3. Run
```
docker exec -it <container ID> bash
```
4. Create superuser
```
python manage.py createsuperuser
```