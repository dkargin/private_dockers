FROM nvidia/cuda:12.0.0-devel-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y software-properties-common && \
	add-apt-repository ppa:ubuntu-toolchain-r/test \
	&& apt-get install -y \
		python3-pip \
		build-essential \
		git \
		wget \
		unzip \
		yasm \
		ninja-build \
		pkg-config \
		libswscale-dev \
		libtbb-dev \
		libjpeg-dev \
		libpng-dev \
		libtiff-dev \
		libavformat-dev \
		libpq-dev \
		libxine2-dev \
		libglew-dev \
		libtiff5-dev \
		zlib1g-dev \
		libjpeg-dev \
		libpng-dev \
		libavcodec-dev \
		libavformat-dev \
		libavutil-dev \
		libpostproc-dev \
		libswscale-dev \
		libeigen3-dev \
		libgtk2.0-dev \
		cuda-nsight-systems-12-0 \
		pkg-config \
		ninja-build \
		python3-dev \
		gdb gdbserver \
	## Cleanup
	&& rm -rf /var/lib/apt/lists/*

RUN pip3 install --upgrade pip && pip3 install conan pytest psutil

# Setting up default conan profile
RUN conan profile new default --detect && conan profile update settings.compiler.libcxx=libstdc++11 default

ARG CMAKE_VERSION=3.23.1

ENV DEBIAN_FRONTEND="noninteractive"
RUN wget https://github.com/Kitware/CMake/releases/download/v$CMAKE_VERSION/cmake-$CMAKE_VERSION-Linux-x86_64.sh \
      -q -O /tmp/cmake-install.sh \
      && chmod u+x /tmp/cmake-install.sh \
      && mkdir /usr/bin/cmake \
      && /tmp/cmake-install.sh --skip-license --prefix=/usr/bin/cmake \
      && rm /tmp/cmake-install.sh

ENV PATH="/usr/bin/cmake/bin:${PATH}"

