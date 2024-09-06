# Build stage
FROM python:3.10-slim-buster AS build

# Set the working directory
WORKDIR /app

# Copy the application files
COPY . .

# Install the dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Runtime stage
FROM python:3.8-slim-buster

# Set the working directory
WORKDIR /app

# Copy the application files from the build stage
COPY --from=build /app .

# Expose the SSH port
EXPOSE 22

# Run the application
CMD ["python", "run_ui.py"]

