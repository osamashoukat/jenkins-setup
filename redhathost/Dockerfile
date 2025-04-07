FROM redhat/ubi9:latest

LABEL maintainer="Osama Shoukat"

# Set timezone (optional)
ENV TZ=Asia/Karachi

# Install base tools without requiring subscription
RUN dnf -y install openssh-server
RUN dnf -y install mysql 
RUN dnf -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm
RUN dnf -y install python3-pip
RUN dnf clean all

# Upgrade pip and install awscli
RUN pip3 install --upgrade pip && \
    pip3 install awscli

# Create remote user with password
RUN useradd remote_user && \
    echo "remote_user:1234" | chpasswd && \
    mkdir -p /home/remote_user/.ssh

# Add public SSH key for remote access
COPY remote-key.pub /home/remote_user/.ssh/authorized_keys

# Set proper permissions
RUN chown -R remote_user:remote_user /home/remote_user && \
    chmod 700 /home/remote_user/.ssh && \
    chmod 400 /home/remote_user/.ssh/authorized_keys

# Generate SSH host keys
RUN ssh-keygen -A

# Expose SSH port
EXPOSE 22

# Run SSH daemon
CMD ["/usr/sbin/sshd", "-D"]

