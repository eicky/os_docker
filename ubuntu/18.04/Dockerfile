FROM ubuntu:18.04

LABEL AUTHOR="Eicky" \
	  VERSION=18.04

RUN apt-get -y update \
	&& apt-get upgrade \
	&& apt-get -y install sudo openssh-server vim curl wget \
	&& echo root:123456 | sudo chpasswd root \
	&& sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config \
	&& sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config \
	&& sudo service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
