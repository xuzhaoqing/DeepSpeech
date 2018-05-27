Bootstrap:docker
From:ubuntu:latest

%labels
        MAINTAINER xuzhaoqing

%environment
        export LANGUAGE=en_US.UTF-8
        export LANG=en_US.UTF-8
        export LC_ALL=en_US.UTF-8

%post
        apt-get update
        apt-get install -y cmake \
                           locales \
                           language-pack-en \
                           git \
                           python2.7 \
                           python-pip \
                           gcc \
                           pkg-config \
                           libogg-dev  \
                           libvorbis-dev \
                           libboost-dev \
                           swig         \
			   wget		\
		           doxygen
        locale-gen en_US.UTF-8 && dpkg-reconfigure locales
	wget http://downloads.xiph.org/releases/flac/flac-1.3.2.tar.xz   
        tar -xvf flac-1.3.2.tar.xz
	cd flac-1.3.2
	./configure --prefix=$HOME/usr --disable-ogg
	make
	make install    
	cd
	git clone https://github.com/01org/mkl-dnn.git
	cd mkl-dnn
	cd scripts && ./prepare_mkl.sh && cd ..
	mkdir -p build && cd build && cmake .. && make && make install
	cp libmkldnn.so.0.9.0 /usr/lib/libmkldnn.so.0.9.0
	cd /usr/lib
	ln -s libmkldnn.so.0.9.0 libmkldnn.so.0
	ln -s libmkldnn.so.0 libmkldnn.so
	ldconfig
	cd 
	pip install paddlepaddle-gpu
	git clone https://github.com/PaddlePaddle/DeepSpeech.git
	cd DeepSpeech
	sh setup.sh
