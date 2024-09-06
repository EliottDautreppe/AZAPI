# Use the Ubuntu 20.04 base image
FROM ubuntu:20.04

# Update the package index and install Python and pip
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip

# Copy the requirements.txt file to the Docker image
COPY requirements.txt /app/requirements.txt

# Install the packages listed in the requirements.txt file
RUN pip3 install -r /app/requirements.txt

# Copy the application files to the Docker image
COPY . /app

# Set the working directory to the /app directory
WORKDIR /app

# Run the application
CMD ["python3", "app.py"]

