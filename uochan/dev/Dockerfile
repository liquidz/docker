FROM uochan/base
MAINTAINER uochan

## latest vim
RUN cd /tmp && git clone https://github.com/liquidz/playbooks
RUN ansible-playbook --connection=local /tmp/playbooks/vim/latest.yml

## clojure
ENV LEIN_ROOT true
RUN ansible-playbook --connection=local /tmp/playbooks/clojure/leiningen.yml

## golang
ENV GOPATH $HOME
ENV PATH $PATH:/usr/local/go/bin:$HOME/bin
RUN ansible-playbook --connection=local /tmp/playbooks/golang/lib.yml

## dotfiles
RUN curl https://raw.githubusercontent.com/liquidz/dotfiles/master/bin/setup.sh | env MODE=full sh
