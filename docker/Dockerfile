# Start with NVIDIA CUDA development image
FROM nvidia/cuda:12.8.0-devel-ubuntu22.04

# Install Python and pip
RUN apt-get update && apt-get install -y \
    apt-utils \
    python3 \
    python3-pip \
    git \
    libgl1-mesa-glx \
    libglib2.0-0 \
    libsm6 \
    libxext6 \
    libxrender-dev \
    libgomp1 \
    xvfb \
    && rm -rf /var/lib/apt/lists/*

# Set display for headless rendering
ENV DISPLAY=:99

# Install PyTorch with CUDA 12.1 support
RUN pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121

RUN pip3 install \
    numpy \
    matplotlib \
    jupyter \
    ipykernel \
    mujoco \
    opencv-python \
    imageio[ffmpeg] \
    tensorboard \
    gymnasium \
    stable-baselines3

# Set working directory
WORKDIR /home/workspace

# Keep container running
CMD ["sleep", "infinity"]