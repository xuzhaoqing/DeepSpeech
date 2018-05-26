Bootstrap:docker  
From:ubuntu:latest  


%labels
ARTHUR ZhaoqingXu

%post
	apt-get update
	apt-get install -y cmake \
			   python2.7  \
		           python-pip \
			   gcc  \
			   pkg-config  \
		           libflac-dev \ 
			   libogg-dev  \
			   libvorbis-dev \
		           libboost-dev \
                           swig        \
			   git
	pip install paddlepaddle-gpu 
