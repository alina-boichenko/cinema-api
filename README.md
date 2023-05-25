# Cinema API
API service for cinema management written on DRF

## Installing using GitHub
Install PostgresSQL

```
git clone https://github.com/alina-boichenko/cinema-api.git
cd cinema-api
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Setting environment variables
- Create an empty file .env in the following path: py-dockerize-cinema/.
- Copy the entire content of the .env.sample file and paste it into the .env file.
- Modify the placeholders in the .env file with the actual environment variables. For example (but don`t use "< >" in your project):
```
POSTGRES_HOST=<your db hostname>
POSTGRES_DB=<your db name>
POSTGRES_USER=<your db username>
POSTGRES_PASSWORD=<your db user password>
DJANGO_SECRET_KEY=<your secret key>
```

### Create db
```
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