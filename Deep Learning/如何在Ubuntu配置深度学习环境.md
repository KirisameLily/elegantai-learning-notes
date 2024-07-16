# 如何在Ubuntu配置深度学习环境

大致思路为



首先，更新Ubuntu必要库

```bash
sudo apt-get update
```

安装Miniconda（Python版本为3.12）

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh -b
~/miniconda3/bin/conda init
```

[非必需]安装d2l（"动手学深度学习"代码包，详见https://d2l.ai/）

```bash
conda create --name d2l python=3.12 -y
```

激活d2l环境

```bash
conda activate d2l
```



安装Pytorch+CUDA[需要你的机器具有Nvidia的GPU]（需要比较多的流量）

```bash
sudo pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

如果没有GPU，可以使用CPU

```bash
sudo pip3 install torch torchvision torchaudio
```



[非必需]下载D2L Notebook

```bash
mkdir d2l-zh && cd d2l-zh
curl https://zh-v2.d2l.ai/d2l-zh-2.0.0.zip -o d2l-zh.zip
sudo apt install unzip #若系统没有安装unzip
unzip d2l-zh.zip && rm d2l-zh.zip
cd pytorch
```



安装Jupyter

```bash
sudo pip3 install jupyter
```

激活d2l环境

```bash
conda activate d2l
```

输入

```bash
jupyter notebook
```

在浏览器输入终端给出的链接

![链接](https://github.com/KirisameLily/elegantai-learning-notes/blob/main/resource/%E9%93%BE%E6%8E%A5.png)