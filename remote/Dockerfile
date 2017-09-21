# Use an official Ubuntu runtime as a base image
FROM ubuntu:16.04

# Set labels
LABEL "Author"="Arvin.Cudanin" "Email"="arvin.cudanin@gmail.com"

# Copy the current directory contents into the container at /app
ADD . /app

# Set the working directory to /app
WORKDIR /app

# Add proxy settings
RUN touch /etc/apt/apt.conf \
    && echo "Acquire::http::proxy \"$http_proxy\";" >> /etc/apt/apt.conf \
    && echo "Acquire::https::proxy \"$https_proxy\";" >> /etc/apt/apt.conf

# Install ansible
RUN apt-get update \
    && apt-get install -y \
        ansible \
        ssh
