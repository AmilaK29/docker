# Use an official GCC image as the base image
FROM gcc:latest

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy the current directory's contents into the container
COPY . .

# Compile the C++ program
RUN g++ -o hello main.cpp

# Run the program
CMD ["./hello"]
