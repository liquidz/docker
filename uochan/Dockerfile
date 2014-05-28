FROM centos
MAINTAINER uochan

ENV HOME /root

## yum
RUN yum install -y sudo git which vim wget tar unzip
RUN rpm -ivh http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.3-1.el6.rf.x86_64.rpm
RUN yum install --enablerepo=rpmforge tmux -y

## fish
RUM yum install -y bc man
RUN http://fishshell.com/files/2.1.0/linux/RedHat_RHEL-5/fish-2.1.0-2.1.x86_64.rpm
RUN chsh -s /usr/bin/fish
ENV SHELL /usr/bin/fish

## git
RUN git config --global user.name "uochan"
RUN git config --global user.email liquidz.uo@gmail.com

## chef
RUN curl -L https://www.opscode.com/chef/install.sh | bash
RUN mkdir /etc/chef
RUN touch /etc/chef/solo.rb
RUN echo "cookbook_path ["                          >> /etc/chef/solo.rb
RUN echo "  \"/var/chef/chef-repo/cookbooks\","     >> /etc/chef/solo.rb
RUN echo "  \"/var/chef/chef-repo/site-cookbooks\"" >> /etc/chef/solo.rb
RUN echo "]"                                        >> /etc/chef/solo.rb
RUN echo "log_location \"/var/log/chef-solo.log\""  >> /etc/chef/solo.rb
RUN echo "log_level :info"                          >> /etc/chef/solo.rb
RUN mkdir /var/chef

## dotfiles
RUN git clone https://github.com/liquidz/dotfiles.git $HOME/dotfiles
RUN (cd $HOME/dotfiles && git submodule update --init)

## chef-repo
RUN git clone https://github.com/liquidz/chef-repo.git /var/chef/chef-repo
RUN (cd /var/chef/chef-repo && git submodule update --init)

## tmux
RUN ln -sf $HOME/dotfiles/.tmux.conf $HOME/.tmux.conf
