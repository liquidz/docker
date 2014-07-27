FROM uochan/base
MAINTAINER uochan

## yum
RUN yum install -y gcc &&\
    yum -y clean all

## java
RUN yum install -y java-1.7.0-openjdk.x86_64

## leiningen
ENV LEIN_ROOT true
RUN mkdir ~/bin
RUN wget https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein -O ~/bin/lein
RUN chmod +x ~/bin/lein
RUN ~/bin/lein self-install

## go

## dotfiles
RUN curl https://raw.githubusercontent.com/liquidz/dotfiles/master/bin/setup.sh | env MODE=full sh

