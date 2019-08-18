# 如何设置环境变量

## Linux系统或者OSX

### 设置临时环境变量

如果你想临时的设置一次环境变量，你可以通过在命令行中使用export命令来完成，下面是为Go mod设置镜阿里云高速镜像代理的方法。

```bash
$ export GOPROXY=https://mirrors.aliyun.com/goproxy/
```

export是指令，代表需要设置环境变量。  
GOPROXY是变量名，值被设置为[https://mirrors.aliyun.com/goproxy/](https://mirrors.aliyun.com/goproxy/)

{% hint style="warning" %}
临时环境变量只能在当前这次你启动的命令行终端中生效。  
只要你退出当前的终端，开启新的终端，这次的设置就会失效
{% endhint %}

### 设置永久的环境变量

我们的攻略主要是针对开发环境，所以我们讲解如何改变你当前用户的环境变量。

```bash
$ echo 'export GOPROXY=https://mirrors.aliyun.com/goproxy/' >> ~/.bashrc 
```

当你每次启动新终端的时候，操作系统都会执行~/.bashrc这个文件内的所有指令。  
所以我们只要把设置临时环境变量的指令写入到这个文件中就可以了。

## Windows系统

### 在Powershell中设置临时的环境变量

和Linux相似，也可以在命令行中暂时的使环境变量生效

```bash
$env:GOPROXY = 'https://mirrors.aliyun.com/goproxy/'
```

### 在CMD中设置临时的环境变量

CMD中使用set命令就可以设置临时环境变量了

```bash
set GOPROXY=https://mirrors.aliyun.com/goproxy/
```

### **设置永久的环境变量**

因为涉及到windows界面的操作，请参见

\*\*\*\*[**https://jingyan.baidu.com/article/47a29f24610740c0142399ea.html**](https://jingyan.baidu.com/article/47a29f24610740c0142399ea.html)\*\*\*\*

