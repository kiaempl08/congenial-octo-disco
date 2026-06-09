FROM ubuntu:latest

# Prevent systemd from asking about interactive services
ENV DEBIAN_FRONTEND=noninteractive

# Install systemd and required packages
RUN apt-get update && apt-get install -y \
    systemd \
    systemd-sysv \
    dbus \
    iproute2 \
    ssh \
    sudo \
    && rm -rf /var/lib/apt/lists/*

# Enable necessary services (e.g., ssh)
RUN systemctl enable ssh

# Set systemd as the entrypoint (PID 1)
ENTRYPOINT ["/lib/systemd/systemd"]
CMD ["/bin/bash"]
