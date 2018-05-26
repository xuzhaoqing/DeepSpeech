Bootstrap:docker  
From:ubuntu:latest  


%labels
ARTHUR ZhaoqingXu

%post
	apt-get update
	apt-get install -y cmake \
			   python2.7 \
		           python-pip \
			   gcc  \
			   pkg-config \
		          
			   libogg-dev  \
			   libvorbis-dev \
		           libboost-dev \
                           swig        \
			   git
	wget http://downloads.xiph.org/releases/flac/flac-1.3.2.tar.xz   
        tar -xvf flac-1.3.2.tar.xz
	cd flac-1.3.2
	./configure --prefix=$HOME/inst --disable-ogg
	make
	make install
	cd $HOME/inst
	export PATH = $HOME/inst/bin:$PATH
	export LD_LIBRARY_PATH = $HOME/inst/lib:$LD_LIBRARY_PATH
	export PKG CONFIG PATH = $HOME/lib/pkgconfig:$PKG CONFIG PATH	         
 	pip install paddlepaddle-gpu
	git clone https://github.com/PaddlePaddle/DeepSpeech.git
	cd DeepSpeech
	sh setup.sh
