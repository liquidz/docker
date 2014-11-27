FROM uochan/dev
MAINTAINER uochan

## yum
RUN yum install -y redis ruby &&\
    yum -y clean all

RUN yum install -y --enablerepo=centosplus npm &&\
    yum -y clean all

RUN npm install -g coffee-script hubot

RUN yum install -y sudo &&\
    sed -i -e 's/Defaults\s*requiretty/# Defaults requiretty/g' /etc/sudoers
RUN wget -qO- https://toolbelt.heroku.com/install.sh | sh

RUN ssh-keygen -t rsa -f ~/.ssh/heroku_rsa_key -C heroku@docker.local
RUN echo "Host heroku.com"                        >  ~/.ssh/config
RUN echo "    HostName heroku.com"                >> ~/.ssh/config
RUN echo "    IdentityFile ~/.ssh/heroku_rsa_key" >> ~/.ssh/config
RUN echo "    User git"                           >> ~/.ssh/config

ADD setup.sh /setup.sh

RUN yum -y clean all
