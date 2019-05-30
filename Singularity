Bootstrap:docker  
From:paddlepaddle/deep_speech:latest-gpu

%labels
ARTHUR ZhaoqingXu

%environment
	export LANG='C.UTF-8'
        export HOME="/mnt/rds/redhen/gallina/Singularity"

%post
  apt-get update && apt-get -y install ffmpeg sox
  pip install webrtcvad

