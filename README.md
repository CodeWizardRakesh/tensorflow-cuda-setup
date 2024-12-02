# CUDA Installation Guide for TensorFlow (Windows)
This guide will help you install CUDA and TensorFlow on a Windows machine. If you're struggling with setting up TensorFlow to use your GPU, this step-by-step guide will make the process easier.

## Prerequisites
- **Windows OS**: Ensure your system has a compatible NVIDIA GPU.
- **Anaconda**: Recommended for managing Python environments

## 1. Install Anaconda (If not installed)
Anaconda is a package manager that helps you manage your Python environments and dependencies. If you don't have Anaconda installed, [download it here](https://www.anaconda.com/download). Provide email to download Distribution.

## 2. Set Up a Conda Environment
### a. Create a Conda environment
``` bash
conda create -n your_env_name python=3.10
```
### b. Activate the Conda environment:
``` bash
conda activate your_env_name
```
### c. Install CUDA and cuDNN:
``` bash
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
```
### d. Install TensorFlow:
``` bash
python -m pip install "tensorflow<2.11"
```
## 3. Check GPU Availability
After installation, you can check if TensorFlow can access your GPU. Run the following code in your Conda environment:
```bash
python
```
``` python
import tensorflow as tf
print("Available GPUs:", tf.config.list_physical_devices('GPU'))
print("Is GPU Available:", tf.test.is_gpu_available())
```

