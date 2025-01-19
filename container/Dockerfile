# Use the NVIDIA PyTorch base image
FROM nvcr.io/nvidia/pytorch:24.06-py3

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONUNBUFFERED=1

# Install build tools and dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    wget \
    curl \
    build-essential \
    ninja-build \
    cmake \
    python3-dev \
    pybind11-dev \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies for Triton build
RUN pip install --upgrade pip setuptools wheel \
    && pip install ninja cmake pybind11

# Clone Triton source
RUN git clone https://github.com/openai/triton.git /triton-source

# Build and install Triton
WORKDIR /triton-source
RUN pip install -e python

# Set default working directory
WORKDIR /workspace

# Default command
CMD ["bash"]
