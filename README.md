# docker-for-layers
How to make an AWS Layer via Docker

# AWS Layer requires software libraries to be compiled for Linux. If you download and zip the libraries locally on a Mac, it will not be compatible with the AWS server which runs Linux. 
# Here are the steps to making an AWS Layer using Docker.

# Start by creating a Docker container running Ubuntu 20.04 and installing python3.8, and pip. 
docker build -t [NAME OF IMAGE] .



