<div align="center">
<h1>测试 （CVPR 2025）SLAM3R: Real-Time Dense Scene Reconstruction from Monocular RGB Videos</h1>
</div>

## 配置测试
```bash
git clone https://github.com/KwanWaiPang/SLAM3R.git


conda create -n slam3r python=3.11 cmake=3.14.0
conda activate slam3r 
# conda remove --name slam3r --all

# install torch according to your cuda version
# pip install torch==2.5.0 torchvision==0.20.0 torchaudio==2.5.0 --index-url https://download.pytorch.org/whl/cu118

# 实验中采用A100 CUDA 12.2
pip install torch==2.5.0 torchvision==0.20.0 torchaudio==2.5.0 --index-url https://download.pytorch.org/whl/cu121


pip install -r requirements.txt
# optional: install additional packages to support visualization （可视化安装包）
pip install -r requirements_vis.txt

```

* Accelerate SLAM3R with XFormers and custom cuda kernels for RoPE (加速器)由于也是采用跟作者一样的torch==2.5.0，因此应该是一样的下载
```bash
# install XFormers according to your pytorch version, see https://github.com/facebookresearch/xformers
pip install xformers==0.0.28.post2
# compile cuda kernels for RoPE
cd slam3r/pos_embed/curope/
python setup.py build_ext --inplace
cd ../../../
```

接下来下载模型(但似乎运行的时候也会自动下载模型，此处先跳过~)
* [I2P](https://huggingface.co/siyan824/slam3r_i2p) 
* [L2W](https://huggingface.co/siyan824/slam3r_l2w)