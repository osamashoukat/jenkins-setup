FROM redhat/ubi9:latest

MAINTAINER "Osama Shoukat"
# Openssh-server or client
RUN dnf -y install openssh-server

# new user create and set proper password for user
# create user home directory with proper permissions
RUN useradd remote_user && \
    echo "1234" | passwd remote_user --stdin && \
    mkdir /home/remote_user/.ssh
 
# copy remote key from host machine to this container
COPY remote-key.pub /home/remote_user/.ssh/authorized_keys
RUN chown -R remote_user:remote_user /home/remote_user && \
    chmod 400 /home/remote_user/.ssh/authorized_keys

RUN ssh-keygen -A

EXPOSE 22

CMD /usr/sbin/sshd -D


