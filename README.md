# TDD-with-Django-Docker
Recipe API Project

### Using Docker Compose
* Run all commands through Docker Compose
`docker-compose run --rm app sh -c "python manage.py collectstatic"`
* `docker-compose` runs a Docker Compose command
* run will start a specific container defined in config
* `--rm` removes the container, this is optional. It tells Docker compose to remove the container, once it’s finished running. It’s recommended that you add this any time you’re running a single command because that means you don’t have a build up of lingering containers on your system
* `app` is the name of service: you specify the name of the app that you defined inside your Docker compose configuration
* `sh -c` passes in a shell command: this is the command that is going to be passed into the container when it runs. This command basically says we want to run a single command on our container
* Command to run inside container
  * `python manage.py collectstatic`

### Build Docker Image
* `docker build .`
* `docker-compose build`

### Linting and Testing
* Linting
  * Tool to check code formatting
  * Highlights errors typos, formatting issues
  * Handle Linting
    * Install `flake8` package
    * Run it through Docker Compose
    * `docker-compose run --rm app sh -c "flake8"`
    * It is recommended to solve linting error from bottom to top
* Testing
    * Django test suite
    * Setup test per Django app
    * Run tests through Docker Compose
    * `docker-compose run --rm app sh -c "python manage.py test"`


### Create Django Project using Docker-Compose

* `docker-compose run --rm app sh -c "django-admin startproject app ."`
* `docker-compose up`

### Create App inside Project using Docker-Compose
* `docker-compose run --rm app sh -c "python manage.py startapp core"`

### Custom Wait for db command
* `docker-compose run --rm app sh -c "python manage.py wait_for_db"`
* `docker-compose run --rm app sh -c "python manage.py wait_for_db && flake8"`

### Docker Volumes on our system
* `docker volume ls`
* `docker volume rm <volume-name>`
* Use `docker-compose down` if you get the error while removing volume