# Using the latest version of Ubuntu
FROM ubuntu:latest

# Update the package list
RUN apt-get update

# Upgrade the packages
RUN apt-get upgrade -y

# Command to run when the container starts
CMD echo "Hello, World!"