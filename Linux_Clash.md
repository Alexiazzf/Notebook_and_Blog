# Linux环境使用clash实现梯子

之前给conda的虚拟环境装包的时候，由于有些地方需要用国外的源，慢到哭泣，所以准备给服务器搭一个梯子！！步骤如下

- 给服务器安装 proxychains

```
sudo apt install proxychains
```

- 下载一个 clash-linux-amd64-v1.1.0.gz（版本很重要！！）

- 创建你想要的存放文件的目录，解压gz包，我存放的路径是/root/clash，可以将解压文件重命名为clash便于阅读

```
gunzip /clash-linux-amd64-v1.1.0.gz
```

- 赋予文件执行权限

```
chmod+x clash
```

- 启动文件

```
./clash
```

第一次启动会在*/home/<user>/.config/clash/*目录下生成Config.yaml和Country.mmdb两个文件。生成的Config.yaml文件为空，需要后续填写自己的代理信息。

- 配置文件

编辑该目录下的config.yaml文件，内容为自己的服务器及规则等信息(有些商家会提供相应的yml文件，复制进当前目录即可)。一定要注意，proxychains的使用端口，要跟clash对上！！！（proxychains的使用端口一般在proxychains.conf 里面 最底下会有 例如`socks5 127.0.0.1 7891 http 127.0.0.1 7890`等，要和Config.yaml 最开始的port 7890 和socks-port: 7891 相对应）

保存更改后复制该文件至先前创建的/root/clash/文件夹(by:这两个文件夹不要弄混，一个是手动建立的，一个是自动创建的，都需要.yml文件)

- 启动clash

配置完成后重新执行命令启动clash，以加载修改的配置文件

- 开心上网

重新打开一个terminal（旧的也不要关掉），输入`proxychains curl www.google.com`

如果terminal里出现网站的html文件，则说明成功了！之后每一条命令之前输入`proxychains`，就会自动走梯子的通道！网速起飞！

- 绕过的弯路

不要多开clash，terminal输入`ps aux | grep clash`查看，如果多开了clash，记得kill掉！



cf. https://www.cnblogs.com/sueyyyy/p/12424178.html

有问题可以给我发邮件，190839405@qq.com，共同进步！
