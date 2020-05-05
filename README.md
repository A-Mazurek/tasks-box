# tasks-box

## Setup

To build this app locally use:
```bash
docker-compose build
```

Then you can start it with:
```bash
docker-compose up
```

Also you can run pytests
Then you can start it with:
```bash
docker-compose run web pytest
```

## Usage

### A Swagger API
For a first overview of all available endpoints, see Swagger:
```url
http://localhost:5000/apidocs/
```

#### Endpoints:

#### 1. 'POST' Endpoint for creating new "tasks"
To create a new task, use the terminal and enter the curl command as below:
```bash
curl -i -H "Content-Type: application/json" -X POST -d '{"content":"Read a book"}' http://localhost:5000/todo/
```

#### 2. 'GET' Endpoint for reading individual task.
To see individual task use browser and enter the url:
```url
http://localhost:5000/task/1
```

#### 3. 'PUT' Endpoint for updating individual tasks
To update task, use the terminal and enter the curl command as below:
```bash
curl -i -H "Content-Type: application/json" -X PUT -d '{"done":true}' http://localhost:5000/task/1
```

#### 4. 'GET' Endpoint for reading all tasks.
To see all tasks use browser and enter the url:
```url
http://localhost:5000/tasks/
```

### Dependencies

```bash
Flask==1.1.2
Flask-Caching==1.8.0
flask-marshmallow==0.12.0
Flask-RESTful==0.3.8
geopy==1.21.0
requests==2.23.0
pytest-flask==1.0.0
pip-tools==5.1.1
flasgger==0.9.4
```

### Updating dependencies

Modify `requirements.in` file and run the command below, to pin down the dependecies versions.
```bash
docker-compose run --rm web pip-compile --generate-hashes requirements.in --output-file requirements.txt
```