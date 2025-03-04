# [CVPR 2025] BF-STVSR: B-Splines and Fourier-Best Friends for High Fidelity Spatial-Temporal Video Super-Resolution

Authors : Eunjin Kim*, [Hyeonjin Kim](https://scholar.google.co.kr/citations?user=LV30lG4AAAAJ&hl=ko&oi=ao)*, Kyong Hwan Jin, [Jaejun Yoo](https://scholar.google.co.kr/citations?hl=en&user=7NBlQw4AAAAJ)

(* : equal contribution)

[Paper](https://arxiv.org/abs/2501.11043a)  | [Project Page](https://eunjnnn.github.io/bfstvsr_site/) 
### [News]
* Our **BF-STVSR** is accepted by **CVPR 2025** 🎉!

## Overview of BF-STVSR

<img src = "./asset/overview.png" width="100%" height="100%"/>

## Environmental Setup

The code is tested on:

- Python 3.8
- Cuda 11.3
- [Deformable Convolution v2](https://arxiv.org/abs/1811.11168). Following [Zooming Slowmo](https://github.com/Mukosame/Zooming-Slow-Mo-CVPR-2020), we adopt [CharlesShang's implementation](https://github.com/CharlesShang/DCNv2) in the submodule.
- We build DCNv2 module using [DCNv2_latest repository](https://github.com/lucasjinreal/DCNv2_latest) and alt_cuda_corr module from [RAFT](https://github.com/princeton-vl/RAFT/tree/master/alt_cuda_corr).

```
conda create -y -n bfstvsr python=3.8
conda activate bfstvsr
conda install -y libxcrypt gxx_linux-64=7 cxx-compiler ninja -c conda-forge

conda install -y cudatoolkit=11.3 nvidia/label/cuda-11.3.1::cuda
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 torchaudio==0.12.1 --extra-index-url https://download.pytorch.org/whl/cu113
pip install opencv-python pillow tqdm pyyaml lmdb scipy tensorboard einops

### cupy installation for softsplat ###
pip install --pre cupy-cuda113 

### Go to the DCNv2_latest directory ###
cd models/DCNv2_latest
python setup.py install

### Go to the alt_cuda_corr directory ###
cd ../alt_cuda_corr
python setup.py install
```

## Citation
If you find this repository useful for your research, please cite the following work.
```
@article{kim2025bf,
  title={BF-STVSR: B-Splines and Fourier-Best Friends for High Fidelity Spatial-Temporal Video Super-Resolution},
  author={Kim, Eunjin and Kim, Hyeonjin and Jin, Kyong Hwan and Yoo, Jaejun},
  journal={arXiv preprint arXiv:2501.11043},
  year={2025}
}
```

## Acknowledgement

This repository heavily depends on [DCNv2_latest](https://github.com/lucasjinreal/DCNv2_latest), [RAFT](https://github.com/princeton-vl/RAFT), [VideoINR](https://github.com/Picsart-AI-Research/VideoINR-Continuous-Space-Time-Super-Resolution/tree/main), and [MoTIF](https://github.com/sichun233746/MoTIF). Thank you for sharing their implementations.