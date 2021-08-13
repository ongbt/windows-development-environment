Initialize
- Install Anaconda3: Anaconda3-2021.05-Windows-x86_64.exe
- Check GPU:
cmd: wmic path win32_VideoController get name
Output:
(base) C:\Windows\system32>wmic path win32_VideoController get name
Name
Intel(R) UHD Graphics
NVIDIA GeForce RTX 2070 Super

- Setup new Anaconda env:
 - Open Anaconda cmd in Admin mode
 - Only tried with python 3.7
 - Create a virtual environment from command prompt by using command:
   -  conda create -n tensor-keras-gpu python=3.7
   - output: 
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
- Install Tensor
  - Switch env: conda activate tensor-keras-gpu 
  - cmd: conda install tensorflow-gpu=2.3 tensorflow=2.3=mkl_py37h936c3e2_0 
  - this cmd installs cudnn and cudatoolkit
- Install Keras
  - cmd: conda install keras-gpu=2.3 keras=2.3
- Verify GPU detected:
- in Anaconda prompt, enter Python:
  - cmd: python
- verify versions:
  - cmd: import tensorflow as tf
tf.__version__
import keras
   - output:
  >>> import tensorflow as tf
2021-07-02 09:58:28.958724: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library cudart64_101.dll
>>> tf.__version__
'2.3.0'
>>> import keras
Using TensorFlow backend.
>>> keras.__version__
'2.3.1'
keras.__version__
 - verify GPU:
 - cmd: from tensorflow.python.client import device_lib
print(device_lib.list_local_devices())
  - output:
2021-07-02 10:00:28.218776: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library nvcuda.dll
2021-07-02 10:00:28.253538: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1716] Found device 0 with properties:
pciBusID: 0000:01:00.0 name: NVIDIA GeForce RTX 2070 Super computeCapability: 7.5
coreClock: 1.38GHz coreCount: 40 deviceMemorySize: 8.00GiB deviceMemoryBandwidth: 417.29GiB/s
2021-07-02 10:00:28.259668: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library cudart64_101.dll
2021-07-02 10:00:28.298492: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library cublas64_10.dll
2021-07-02 10:00:28.305168: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library cufft64_10.dll
2021-07-02 10:00:28.310077: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library curand64_10.dll
2021-07-02 10:00:28.315721: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library cusolver64_10.dll
2021-07-02 10:00:28.320765: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library cusparse64_10.dll
2021-07-02 10:00:28.328451: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library cudnn64_7.dll
2021-07-02 10:00:28.331392: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1858] Adding visible gpu devices: 0
2021-07-02 10:00:28.747435: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1257] Device interconnect StreamExecutor with strength 1 edge matrix:
2021-07-02 10:00:28.752091: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1263]      0
2021-07-02 10:00:28.754157: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1276] 0:   N
2021-07-02 10:00:28.756082: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1402] Created TensorFlow device (/device:GPU:0 with 6205 MB memory) -> physical GPU (device: 0, name: NVIDIA GeForce RTX 2070 Super, pci bus id: 0000:01:00.0, compute capability: 7.5)
2021-07-02 10:00:28.764766: I tensorflow/compiler/xla/service/service.cc:168] XLA service 0x1a215888230 initialized for platform CUDA (this does not guarantee that XLA will be used). Devices:
2021-07-02 10:00:28.768459: I tensorflow/compiler/xla/service/service.cc:176]   StreamExecutor device (0): NVIDIA GeForce RTX 2070 Super, Compute Capability 7.5
[name: "/device:CPU:0"
device_type: "CPU"
memory_limit: 268435456
locality {
}
incarnation: 11511368296045105763
, name: "/device:XLA_CPU:0"
device_type: "XLA_CPU"
memory_limit: 17179869184
locality {
}
incarnation: 16393943357908414243
physical_device_desc: "device: XLA_CPU device"
, name: "/device:GPU:0"
device_type: "GPU"
memory_limit: 6507127385
locality {
  bus_id: 1
  links {
  }
}
incarnation: 2967901338917081273
physical_device_desc: "device: 0, name: NVIDIA GeForce RTX 2070 Super, pci bus id: 0000:01:00.0, compute capability: 7.5"
, name: "/device:XLA_GPU:0"
device_type: "XLA_GPU"
memory_limit: 17179869184
locality {
}
incarnation: 2382546571488675693
physical_device_desc: "device: XLA_GPU device"
]
  - To check whether CUDA is enabled for the TensorFlow
    - cmd:  import tensorflow as tf
print(tf.test.is_built_with_cuda())
   - output: True





Jupyter:
 - Install Jupyter: pip install ipykernel
 - Configure: python -m ipykernel install --user --name tensor-keras-gpu --display-name "tensor-keras-gpu"
 - pip install notebook
 - Open Jupyter Notebook: cmd: jupyter notebook
     

Other Libs:
- conda install matplotlib
- conda install pandas
- conda install scikit-learn







Ref:
https://stackoverflow.com/questions/65273118/why-is-tensorflow-not-recognizing-my-gpu-after-conda-install
https://github.com/ContinuumIO/anaconda-issues/issues/12194#issuecomment-751700156 (refer for tensor install cmd)
https://medium.com/@martin.berger/how-to-setup-gpu-accelerated-tensorflow-keras-on-windows-10-with-anaconda-3-bf844a720aa3 (refer for verification cmd)
https://www.analyticsvidhya.com/blog/2020/11/how-to-download-install-and-use-nvidia-gpu-for-tensorflow-on-windows/ (refer for verification cmd)
