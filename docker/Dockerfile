FROM debian:bookworm

RUN apt-get update && apt-get install -y openssh-server python3 python3-apt
RUN mkdir /var/run/sshd
RUN echo 'root:your_password' | chpasswd
RUN sed -i 's/^.*PermitRootLogin.*$/PermitRootLogin yes/' /etc/ssh/sshd_config
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]