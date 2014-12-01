FROM centos
MAINTAINER uochan

ENV HOME /root

## yum
RUN rpm -Uvh http://ftp-srv2.kddilabs.jp/Linux/distributions/fedora/epel/6/x86_64/epel-release-6-8.noarch.rpm &&\
    yum -y upgrade

RUN yum install -y sudo gcc git which vim wget tar unzip zsh &&\
    yum -y clean all
RUN yum install -y tmux &&\
    yum -y clean all

# Time Zone
#RUN echo 'ZONE="Asia/Tokyo"' > /etc/sysconfig/clock
#RUN yum install -y ntp
#RUN yum clean -y all
#RUN rm -f /etc/localtime
#RUN ln -fs /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
#RUN ntpdate ntp.nict.jp

## git
RUN git config --global user.name "uochan"
RUN git config --global user.email liquidz.uo@gmail.com

### chef
#RUN curl -L https://www.opscode.com/chef/install.sh | bash
#RUN mkdir /etc/chef
#RUN touch /etc/chef/solo.rb
#RUN echo "cookbook_path ["                          >> /etc/chef/solo.rb
#RUN echo "  \"/var/chef/chef-repo/cookbooks\","     >> /etc/chef/solo.rb
#RUN echo "  \"/var/chef/chef-repo/site-cookbooks\"" >> /etc/chef/solo.rb
#RUN echo "]"                                        >> /etc/chef/solo.rb
#RUN echo "log_location \"/var/log/chef-solo.log\""  >> /etc/chef/solo.rb
#RUN echo "log_level :info"                          >> /etc/chef/solo.rb
#RUN mkdir /var/chef

## dotfiles
RUN curl https://raw.githubusercontent.com/liquidz/dotfiles/master/bin/setup.sh | env MODE=full sh

### chef-repo
#RUN git clone https://github.com/liquidz/chef-repo.git /var/chef/chef-repo
#RUN (cd /var/chef/chef-repo && git submodule update --init)

CMD /bin/zsh
