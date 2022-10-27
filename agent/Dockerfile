FROM jenkins/ssh-agent
RUN apt-get update && apt-get install -y lsb-release git curl
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli
RUN touch /var/run/docker.sock && chown jenkins /var/run/docker.sock
#sudo chmod 666 /var/run/docker.sock
