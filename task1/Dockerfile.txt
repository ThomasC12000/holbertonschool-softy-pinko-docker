# Using the latest version of Ubuntu
FROM ubuntu:latest

# Update the package list
RUN apt-get update

# Upgrade the packages
RUN apt-get upgrade -y

#Install Python3 et Phython3-pip
RUN apt-get install -y python3 python3-pip

# Remove the file that indicates that the python installation is managed externally
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

#Install Flask
RUN pip3 install flask

# Define /app as the working directory
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY ./api.py /app/api.py

# Command to run when the container starts
CMD ["python3", "api.py"]