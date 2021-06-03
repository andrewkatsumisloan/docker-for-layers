# docker-for-layers
How to make an AWS Layer via Docker

AWS Layer requires software libraries to be compiled for Linux. If you download and zip the libraries locally on a Mac, it will not be compatible with the AWS server which runs Linux. 

Here are the steps to making an AWS Layer using Docker.

Start by creating a Docker container running Ubuntu 20.04 and installing python3.8, and pip. 

This is already specified in the Dockerfile, so just run: 
```
docker build -t [NAME OF IMAGE] .
```
Run the container (replace full path to local-storage with proper path)
```
docker run -v ~/[NAME OF IMAGE]/local-storage:/docker-storage -it pandas-image
```

Then, once the container is running:
```
mkdir -p /docker-storage/site-packages
pip install [PACKAGE] -t /docker-storage/site-packages
```

Then: 
```
ls -l /docker-storage/site-packages
```


Exit, then you will find library and all of its (Ubuntu) dependencies here in your local area:
```
ls -l local-storage/site-packages
```
