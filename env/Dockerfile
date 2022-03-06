FROM nvidia/cuda:10.0-devel-ubuntu18.04
RUN apt-get update && apt-get install -y \
    python3.6 \
    python3-pip \
    git

RUN pip3 install https://download.pytorch.org/whl/cu100/torch-1.1.0-cp36-cp36m-linux_x86_64.whl && \
    pip3 install numpy tqdm boto3 requests regex pandas scipy sklearn

WORKDIR /usr/src
RUN git clone https://github.com/NVIDIA/apex && cd apex && \
    git checkout 3d01e4a0a188cc8df54bc6e44cf5eb40ff6b4cc5 && \
    pip3 install -v --no-cache-dir --global-option="--cpp_ext" --global-option="--cuda_ext" .