FROM ubuntu:latest

# Instalação de dependências
RUN apt-get update && apt-get install -y \
    build-essential \
    chrpath \
    cpio \
    diffstat \
    gawk \
    git \
    wget \
    texinfo \
    python3 \
    python3-pip \
    locales \
    && rm -rf /var/lib/apt/lists/*

# Configuração do ambiente do Yocto
RUN locale-gen en_US.UTF-8
ENV LANG=en_US.UTF-8 LANGUAGE=en_US:en LC_ALL=en_US.UTF-8
RUN update-locale

# Clone do repositório do Yocto
RUN git clone -b dunfell git://git.yoctoproject.org/poky.git /poky

# Configuração do ambiente
WORKDIR /poky
RUN ./oe-init-build-env

# Comando padrão para iniciar o shell do Yocto
CMD ["bitbake", "-k", "core-image-minimal"]
