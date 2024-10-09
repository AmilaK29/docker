# Use the official Golang image to create a build environment
FROM golang:1.20 as builder

# Set the current working directory inside the container
WORKDIR /app

# Copy go.mod and go.sum to the workspace
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy the rest of the application files
COPY . .

# Build the Go app
RUN go build -o main .

# Use a minimal base image for the runtime
FROM alpine:latest

# Set working directory
WORKDIR /root/

# Copy the compiled binary from the builder stage
COPY --from=builder /app/main .

# Expose port 8080 to the outside world
EXPOSE 8080

# Command to run the application
CMD ["./main"]
