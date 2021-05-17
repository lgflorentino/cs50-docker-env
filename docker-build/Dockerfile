FROM debian:buster-slim

RUN apt-get update -y && apt-get install -y \
    build-essential \
    neovim \
    clang \
    python3 \
    python3-pip \
    curl \
    libssl-dev \
    git \
    zsh

RUN curl https://sh.rustup.rs -sSf | bash -s -- -y

RUN apt-get install -y \
    astyle

ENV PATH="/root/.cargo/bin:${PATH}"

RUN update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1 && \
    update-alternatives --install /usr/bin/python python /usr/bin/python3.7 2 && \
    update-alternatives --install /usr/bin/pip pip /usr/bin/pip3 2

RUN pip install \
    check50 \
    compare50 \
    style50 \
    render50 \
    submit50 

CMD ["zsh"]
