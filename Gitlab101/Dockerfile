#Create new Ubuntu from Docker-Hub
FROM ubuntu
#Install Gitlab as guide document
#Step1: Update apt
USER root
RUN apt-get update
RUN apt-get install -y curl openssh-server ca-certificates
#Step2: Install gitlab
RUN cd /tmp
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
RUN chmod 600 script.deb.sh
RUN bash ./script.deb.sh
RUN  EXTERNAL_URL="https://localhost"
RUN apt-get install gitlab-ce -y
#Step3: Adjusting Firewall Rules
RUN ufw status
RUN ufw allow http
RUN ufw allow https
RUN ufw allow OpenSSH
#Step 4 — Editing the GitLab Configuration File

EXPOSE  80
