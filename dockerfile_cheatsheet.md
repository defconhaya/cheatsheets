A Dockerfile is a script used to create a Docker container image. 

```Dockerfile
# Set the base image
FROM base_image:tag

# Maintainer information
LABEL maintainer="Your Name <your.email@example.com>"

# Set environment variables
ENV ENV_VARIABLE_NAME=value

# Working directory inside the container
WORKDIR /app

# Copy files or directories from the host to the container
COPY source_path/ destination_path/

# Download files from the internet and add them to the container
ADD https://example.com/file.tar.gz /tmp/

# Install packages and dependencies
RUN apt-get update && apt-get install -y package_name

# Expose ports
EXPOSE 80

# Define the command to run when the container starts
CMD ["executable", "arg1", "arg2"]

# Define entry point (overrides CMD) - typically for running a specific script or application
ENTRYPOINT ["executable", "arg1"]

# Define a volume to mount host directories or files inside the container
VOLUME /path/in/container

# Add metadata to an image
LABEL key=value

# Specify the user that runs the container
USER user_name

# Set the default shell
SHELL ["executable", "-option"]

# Execute multiple commands in a single RUN instruction
RUN command1 && command2

# Remove cached package information
RUN apt-get clean

# Set a default argument for ENTRYPOINT or CMD
CMD ["default_arg"]

# Build context (directory where the Dockerfile is located)
# Use .dockerignore to exclude files and directories
# when using the `docker build` command
COPY . .

# Set labels to describe the image
LABEL description="Description of the image"

# Define a build-time argument
ARG build_arg_name=default_value

# Pass build-time arguments to the image
ARG build_arg_name

# Multi-stage build (example: build and copy without unnecessary files)
# Use as many stages as needed
# Example stage for building
FROM builder AS build
RUN build_commands

# Example stage for copying artifacts from the build stage
FROM base_image:tag
COPY --from=build /app/artifact /app/artifact

# Install a package or tool for debugging inside the container
# (Useful for debugging, remove in production)
RUN apt-get update && apt-get install -y package_name
```