FROM ubuntu:18.04

RUN apt update \
    && apt install -y libllvm10 llvm-10-dev clang-10 libclang-10-dev liblld-10-dev liblld-10-dev gfortran \
    && apt install -y wget git python3.7 python3-pip \
    && pip3 install conan \
    && wget https://github.com/Kitware/CMake/releases/download/v3.22.4/cmake-3.22.4-linux-x86_64.tar.gz \
    && tar -xzf cmake-3.22.4-linux-x86_64.tar.gz --strip-components=1 -C /usr/local/
