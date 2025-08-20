# CUDA Setup for Jetson Platform

## **Installation Guide:**

1. **Navigate to the NVIDIA documentation:**
    [https://docs.nvidia.com/deeplearning/frameworks/install-pytorch-jetson-platform/index.html](https://docs.nvidia.com/deeplearning/frameworks/install-pytorch-jetson-platform/index.html)

2. **Follow the steps** up to the PyTorch installation export command. You will see a command similar to this:
    ```bash
    export TORCH_INSTALL=https://developer.download.nvidia.cn/compute/redist/jp/v511/pytorch/torch-2.0.0+nv23.05-cp38-cp38-linux_aarch64.whl
    ```

3. **Find the correct wheel (`.whl`) file for your JetPack version:**
    * Go to: [https://developer.download.nvidia.cn/compute/redist/jp/](https://developer.download.nvidia.cn/compute/redist/jp/)
    * Select your JetPack version.
    * Navigate to the `pytorch` directory.
    * Copy the URL of the appropriate `.whl` file.
    * Update the `TORCH_INSTALL` path with the URL you just copied.

    > **Note:** If you cannot find your exact JetPack version, using the nearest one should work. (For example, a JetPack v6.1 PyTorch wheel was tested on JetPack v6.2).

4. **Install PyTorch:**
    You can proceed with either a system-wide installation or a virtual environment installation as described in the documentation. Use the environment variable you just set:
    ```bash
    python3 -m pip install --no-cache $TORCH_INSTALL
    ```

5. **Test the installation:**
    Run the following Python snippet to verify that CUDA is available:

    ```python
    import torch
    print(torch.cuda.is_available())
    ```

    The expected output is `True`. If the output is `False`, the installation was not successful.
