# 下载安装

{% hint style="info" %}
安装前请确保你已经在电脑上安装好了Golang以及Git等最基础的开发工具
{% endhint %}

### 下载项目

首先你需要把项目下载到任何一个对于你舒服的位置

```bash
$ git clone https://github.com/bydmm/singo.git
```

无论你是通过git clone命令，还是直接下载并解压了项目的压缩包，你都可以把项目文件夹改成你需要的项目名称。

下面我会按照项目名为giligili作为例子

```bash
$ mv singo giligili
```

{% hint style="warning" %}
请不要把项目放在Golang安装目录的src子目录中！  
Singo使用了Go Modules，你把项目放进src中会引起各种报错。  
如果你执意这么做，请设置环境变量GO111MODULE=on。  
如何设置环境变量，请参见参考资料中的《如何设置环境变量》这个小节。
{% endhint %}



