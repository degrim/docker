FROM ubuntu:14.04

ENV RUBY_VERSION 1.9.2

RUN apt-get -y update \
    && apt-get -y install curl git unzip emacs24-nox \
    && curl -sSL https://rvm.io/mpapis.asc | gpg --import - \
    && curl -L https://get.rvm.io | bash -s stable --ruby=$RUBY_VERSION \
    && /bin/bash -l -c "gem install bundler"
RUN echo "source /usr/local/rvm/scripts/rvm" >> /etc/bash.bashrc
RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
