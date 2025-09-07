# Start from the official Jenkins LTS image
FROM jenkins/jenkins:lts

# Switch to root to install packages
USER root

# Install Python3 and pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Switch back to Jenkins user
USER jenkins

# Set working directory inside the container
WORKDIR /var/jenkins_home

# Copy your repo files (optional, if needed)
# COPY . /var/jenkins_home

# Default command (Jenkins already runs its own entrypoint)
