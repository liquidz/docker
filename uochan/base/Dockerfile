FROM centos
MAINTAINER uochan

ENV HOME /root

## yum
RUN rpm -Uvh http://ftp-srv2.kddilabs.jp/Linux/distributions/fedora/epel/6/x86_64/epel-release-6-8.noarch.rpm &&\
    yum -y upgrade

RUN yum install -y sudo git which vim wget tar unzip zsh &&\
    yum -y clean all
RUN yum install -y tmux &&\
    yum -y clean all

## locale
RUN localedef -f UTF-8 -i ja_JP ja_JP
ENV LANG ja_JP.UTF-8

## git
RUN git config --global user.name "uochan" &&\
    git config --global user.email liquidz.uo@gmail.com

## dotfiles
RUN curl https://raw.githubusercontent.com/liquidz/dotfiles/master/bin/setup.sh | sh

## timezone
RUN ln -fs /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
