FROM codercom/enterprise-base:ubuntu

# Run everything as root
USER root

# bash .profile so projector can be added to the path
ENV PATH="/home/coder/.local/bin:${PATH}"

# Packages required for JetBrains projector support
RUN DEBIAN_FRONTEND="noninteractive" apt-get update -y && \
    apt-get install -y \
    libxtst6 \
    libxrender1 \
    libfontconfig1 \
    libxi6 \
    libgtk-3-0

# configure script
COPY ["configure", "/coder/configure"]
RUN chmod +x /coder/configure

# Set back to coder user
USER coder

