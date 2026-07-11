# Use Ubuntu as the base image
FROM ubuntu:22.04

# Prevent interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Install required packages
RUN apt-get update && \
    apt-get install -y \
    bash \
    fortune-mod \
    cowsay \
    netcat-openbsd && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Add cowsay and fortune to PATH
ENV PATH="/usr/games:${PATH}"

# Set working directory
WORKDIR /app

# Copy application
COPY wisecow.sh .

# Make script executable
RUN chmod +x wisecow.sh

# Expose application port
EXPOSE 4499

# Start the application
CMD ["./wisecow.sh"]
