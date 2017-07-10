# awslogs-docker
Docker-compose script to create a container for awslogs (https://github.com/jorgebastida/awslogs)

## Requirements
Please install

1) Docker Toolbox
```
https://www.docker.com/products/docker-toolbox
```
2) Docker-Compose
```
https://docs.docker.com/compose/
```

## Installation

### Clone the repository

Using Kitematic (Docker toolbox), click Docker CLI to open a console which is remoted into your Virtual Box VM with Docker.

### Configure files

Populate the *.aws* credentials file with you api key
```
[default]
aws_access_key_id=[key]
aws_secret_access_key=[secret]
```

In the docker-compose.yml modify the following keys: 

| KEY  | Description  |
|---|---|
|  *AWS_LOGS_STREAM* |  cloudwatch endpoint |
|  *AWS_LOGS_REGION*  |  Region (default: Sydney) |
|  *AWS_LOGS_TIME*  |  is use to query the logs. we're filtering by startdate (default: 1 day of logs) |
| *AWS_LOGS_GREP* | used to filter the resulting dataset (default: find all entries with 'error') |
| *AWS_LOGS_REFRESH* | AWS_LOGS_REFRESH=1m |


### Create Docker Container
In the console, run:
```
  /> docker-compose -f docker-compose.yml up -d
```

### View logs in Kitematic
You should now see live logs appearing in the "Container Logs" window in Kitematic.


## Contributing
1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History
- v1

## License
MIT