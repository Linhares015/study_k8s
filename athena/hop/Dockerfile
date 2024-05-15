# Use the official Apache Hop image as the base
FROM apache/hop:latest

# Switch to root to install packages
USER root

# Install necessary packages using apk (Alpine Package Keeper)
RUN apk update && apk add --no-cache \
    openssh-server \
    && mkdir /var/run/sshd \
    && echo 'root:root' | chpasswd \
    && sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# Expose the SSH port
EXPOSE 22

# Command to run SSH server and Apache Hop
CMD ["/usr/sbin/sshd", "-D"]
