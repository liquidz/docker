FROM debian:wheezy
MAINTAINER uochan

RUN apt-get update \
    && apt-get install -y curl git vim zsh

RUN apt-get install -y tmux ruby
RUN apt-get install -y make
RUN apt-get install -y gcc

RUN curl -L http://bit.ly/uochan_dotfile | env MODE=full bash

#RUN vim +":NeoBundleInstall" +:q
#RUN vim -u ~/.vimrc -i NONE -c "try | NeoBundleUpdate! | finally | q! | endtry" -e -s -V1

CMD ["/bin/zsh"]
