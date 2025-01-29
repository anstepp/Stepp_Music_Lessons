FROM ubuntu:22.04

RUN apt-get update && \
    apt-get -y install \
        apt-utils \
        autoconf \
        bison \
        build-essential \
        curl \
        git \
        iputils-ping \
        jq \
        libbz2-dev \
        libdb-dev \
        libffi-dev \
        libgdbm6 \
        libgdbm-dev \
        liblzma-dev \
        libncurses5-dev \
        libreadline-dev \
        libsqlite3-dev \
        libssl-dev \
        libyaml-dev \
        sudo \
        wget \
        vim \
        zip \
        zlib1g-dev && \
    rm -rf /var/lib/apt/lists/*

    # libreadline6-dev \

ENV RBENV_ROOT /usr/local/src/rbenv
ENV RUBY_VERSION 3.1.2
ENV PATH ${RBENV_ROOT}/bin:${RBENV_ROOT}/shims:$PATH

# Install rbenv to manage Ruby versions.
RUN git clone https://github.com/rbenv/rbenv.git ${RBENV_ROOT} \
  && git clone https://github.com/rbenv/ruby-build.git \
    ${RBENV_ROOT}/plugins/ruby-build \
  && ${RBENV_ROOT}/plugins/ruby-build/install.sh \
  && echo 'eval "$(rbenv init -)"' >> /etc/profile.d/rbenv.sh

# Install ruby and set the global version.
RUN rbenv install ${RUBY_VERSION} \
  && rbenv global ${RUBY_VERSION}

# Install the version of Jekyll that GitHub Pages supports.
# https://pages.github.com/versions/
RUN gem install jekyll -v '3.10.0'_config.yml