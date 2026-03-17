# Django App Template

This Django template includes:

- JET admin interface
- Python slugify package
- Django Tailwind (_node.js and npm required_)
- Python dotenv package
- Basic templating structure
- Basic account functionality (login and logout)

## Installation

1. Install dependencies:
   ```
   poetry install
   ```
2. Install tailwind dependencies:
   ```
   poetry run python manage.py tailwind install
   ```
3. Migrate:
   ```
   poetry run python manage.py migrate
   ```

## Dotenv

In order to use the `dotenv` package, you will need to create a _.env_ file in the root of your project. You can change the location of the file by modifying this line in the `settings.py` file:

```python
# Load environment variables from .env
load_dotenv(os.path.join(BASE_DIR, '.env'))
```

By default, the project settings gets `DEBUG` and `SECRET_KEY` values from _.env_ file.

## Development Server

To run the development server, just run these two commands in separate terminals:

```
poetry run python manage.py tailwind start
```

and

```
poetry run python manage.py runserver
```

### Running in Docker

To run the development server in Docker, use the following command:

```
docker-compose -f docker/dev/docker-compose.yaml up
```

This will run 2 services:

- Tailwind compiler
- Django web server
