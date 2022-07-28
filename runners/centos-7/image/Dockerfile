FROM quay.io/pypa/manylinux2014_x86_64

RUN yum update \
  && yum -y groupinstall "Development Tools" \
  && pipx install conan \
  && curl -LO https://github.com/Kitware/CMake/releases/download/v3.24.0-rc3/cmake-3.24.0-rc3-linux-x86_64.tar.gz \
  && tar -xzf cmake-3.24.0-rc3-linux-x86_64.tar.gz \
  && ln -s /cmake-3.24.0-rc3-linux-x86_64/bin/cmake /bin/ \
  && ln -s /cmake-3.24.0-rc3-linux-x86_64/bin/ccmake /bin/ \
  && yum -y install libXrandr-devel \
  && yum -y install libXinerama-devel \
  && yum -y install libXcursor-devel \
  && yum -y install libXi-devel
