# Conda转清华镜像

Conda自带的链接下载东西太慢了（当然，如果使用梯子之后也会快到飞起，详见[Linux_Clash.md](Linux_Clash.md))，大多数人都会换成清华的源。但网上方法鱼龙混杂，前几天还因为弄这个差点把服务器搞坏。研究了半天之后，终于搞定了！我的方法如下：

- 命令输入：

```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
```

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

```
conda config --set show_channel_urls yes
```

- 有时候国内镜像源无法连接，需要恢复原来的源：

```
conda config --remove-key channels
```



cf. https://blog.csdn.net/sunmingyang1987/article/details/102851249