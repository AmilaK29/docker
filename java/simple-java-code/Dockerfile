# Use an official OpenJDK runtime (with JDK for compilation) as a parent image
FROM openjdk:11-slim

# Set the working directory in the container
WORKDIR /usr/src/myapp

# Copy the current directory contents into the container
COPY . .

# Compile the Java program
RUN javac HelloWorld.java

# Run the Java program
CMD ["java", "HelloWorld"]
