
#============================#
# Nicotine+ with Gluetun VPN #
#============================#

# Base image
FROM ghcr.io/fletchto99/nicotine-plus-docker:latest

# Environment variables
ENV TZ="America/Los_Angeles"

# Add Gluetun configuration and scripts
RUN apt-get update && apt-get install -y wireguard && rm -rf /var/lib/apt/lists/*

# Set up directory structure for volumes and configurations
VOLUME /config
VOLUME /data/shares
VOLUME /data/downloads
VOLUME /data/incomplete_downloads

# Copy entrypoint script
COPY rootfs/ /

# Entrypoint
CMD [ "/bin/bash", "/ha_entrypoint.sh" ]
