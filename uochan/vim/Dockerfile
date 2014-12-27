FROM debian:wheezy
MAINTAINER uochan

RUN apt-get update \
    && apt-get install -y git vim

ENV HOME /root
RUN mkdir -p $HOME/.vim/bundle/
RUN git clone https://github.com/Shougo/neobundle.vim.git $HOME/.vim/bundle/neobundle.vim
RUN apt-get clean &&\
    rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*

RUN echo "updated 2014-12-27 09:06"
ADD vimrc $HOME/.vimrc

CMD ["/bin/bash"]
