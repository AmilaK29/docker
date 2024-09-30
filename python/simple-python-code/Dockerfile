# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set environment variable to avoid output buffering
ENV PYTHONUNBUFFERED=1

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the current directory contents into the container
COPY . .

# Run the Python application explicitly
CMD ["python3", "app.py"]
