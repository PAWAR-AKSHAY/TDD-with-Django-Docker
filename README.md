# TDD-with-Django-Docker
Recipe API Project

### Using Docker Compose
* Run all commands through Docker Compose
`docker-compose run --rm app sh -c "python manage.py collectstatic"`
* `docker-compose` runs a Docker Compose command
* run will start a specific container defined in config
* `--rm` removes the container, this is optional. It tells Docker compose to remove the container, once it’s finished running. It’s recommended that you add this any time you’re running a single command beacause that means you don’t have a build up of lingering containers on your system
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
  * Highlights errorsm typos, formatting issues
  * Handle Linting
    * Install `flake8` package
    * Run it through Docker Compose
    * `docker-compose run --rm app sh -c "flake8"`
    * It is recommend to solve linting error from bottom to top
* Testing
    * Django test suite
    * Setup test per Django app
    * Run tests through Docker Compose
    * `docker-compose run --rm app sh -c "python manage.py test"`


### Create Django Project using Docker-Compose

* `docker-compose run --rm app sh -c "django-admin startproject app ."`
* `docker-compose up`