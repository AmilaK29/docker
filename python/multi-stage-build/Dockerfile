# Stage 1: Build environment
FROM python:3.9-slim AS builder

# Set working directory inside the container
WORKDIR /app

# Copy the requirements file to the container
COPY app/requirements.txt .

# Install dependencies in a virtual environment
RUN python -m venv /opt/venv && \
    /opt/venv/bin/pip install --upgrade pip && \
    /opt/venv/bin/pip install -r requirements.txt

# Copy the application code into the container
COPY app/ .

# Stage 2: Minimal runtime environment
FROM python:3.9-alpine

# Set the working directory in the minimal image
WORKDIR /app

# Copy the virtual environment from the builder stage
COPY --from=builder /opt/venv /opt/venv

# Copy application code to the minimal container
COPY --from=builder /app .

# Update PATH to use the virtual environment's binaries
ENV PATH="/opt/venv/bin:$PATH"

# Command to run the application
CMD ["python", "main.py"]
