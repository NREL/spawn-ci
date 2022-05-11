FROM ubuntu:18.04

ENV PATH="/graalvm-ce-java11-21.3.1/bin:${PATH}"

RUN apt update \
    && apt install -y libllvm10 llvm-10-dev clang-10 libclang-10-dev liblld-10-dev liblld-10-dev gfortran libz-dev  \
    && apt install -y wget git python3.7 python3-pip \
    && pip3 install awscli conan \
    && wget https://github.com/Kitware/CMake/releases/download/v3.22.4/cmake-3.22.4-linux-x86_64.tar.gz \
    && tar -xzf cmake-3.22.4-linux-x86_64.tar.gz --strip-components=1 -C /usr/local/ \
    && rm cmake-3.22.4-linux-x86_64.tar.gz \
    && wget https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-21.3.1/graalvm-ce-java11-linux-amd64-21.3.1.tar.gz \
    && tar -xzf graalvm-ce-java11-linux-amd64-21.3.1.tar.gz \
    && rm graalvm-ce-java11-linux-amd64-21.3.1.tar.gz \
    && gu install native-image \
    ## Do these steps to install the conan dependencies
    && git clone --recurse-submodules --depth 1  https://github.com/nrel/spawn /tmp/spawn \
    && cd /tmp/spawn \
    && cmake . \
    && cd \
    && rm -rf /tmp/spawn
