# Conda转清华镜像

- 命令输入：
- 把 .condarc 里面的东西替换成:

```
- https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
#  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
#  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
#  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
#  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
#  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
#  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud

```

- 命令输入：

conda config --set show_channel_urls yes

- 有时候国内镜像源无法连接，需要恢复原来的源：

conda config --remove-key channels



ref: https://blog.csdn.net/sunmingyang1987/article/details/102851249