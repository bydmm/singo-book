# 配置环境变量来连接数据库

{% hint style="info" %}
Singo使用了Mysql和Redis来存储数据，所以把Singo跑起来之前，你得安装好Mysql和Redis这两个服务。很多人会忘记安装Redis，但是看到这里的你当然不会。
{% endhint %}

### 创建.env文件

你需要在项目根目录创建.env文件来配置环境变量。项目中已经放置了.env.example这个文件作为一个例子，你可以把他的内容拷贝过来方便你创建这个文件。

```bash
MYSQL_DSN="db_user:db_passwd@tcp(127.0.0.1:3306)/db_name?charset=utf8&parseTime=True&loc=Local" # Mysql连接配置
REDIS_ADDR="127.0.0.1:6379" # Redis端口和地址
REDIS_PW=""                 # Redis连接密码
REDIS_DB=""                 # Redis库从0到10，不填即为0
SESSION_SECRE=""            # Seesion密钥，必须设置而且不要泄露
GIN_MODE="debug"            # 设置gin的运行模式，有 debug 和 release
```

我们可以特殊关注一下Mysql的连接配置，因为他确实有那么一点点复杂

```text
MYSQL_DSN="db_user:db_passwd@tcp(127.0.0.1:3306)/db_name?charset=utf8&parseTime=True&loc=Local"
```

db\_user是数据库账号  
db\_passwd是数据库密码  
tcp\(127.0.0.1:3306\)是使用tcp协议，在ip为127.0.0.1的3306端口去访问数据库  
db\_name是数据库名  
charset=utf8是设置数据库字符集  
parseTime=True&loc=Local最后是设置时区为服务器时间

{% hint style="info" %}
创建数据库的时候请把数据库的字符集设置为utf8\_general\_ci，这样才能比较好的支持中文。  
否则到时候存进去和取出来的中文会变成乱码。  
如果你还想让你的数据库支持emoji也就是🎂这样的特殊符号，你则需要把字符集设置为utf8mb4\_general\_ci，否则也emoji也是保存不进去的。
{% endhint %}

### 例子

我们在mysql中创建了名为giligili的数据库，并设置为utf8\_general\_ci这个字符集。  
我们还给SESSION\_SECRE这个变量赋值了一个比较复杂的随机字符串，这可以有效的保护我们Session数据。这个值非常机密，你一定不能把他泄露出去。

```text
MYSQL_DSN="root:123456@tcp(127.0.0.1:3306)/giligili?charset=utf8&parseTime=True&loc=Local" # Mysql连接配置
REDIS_ADDR="127.0.0.1:6379" # Redis端口和地址
REDIS_PW=""                 # Redis连接密码
REDIS_DB=""                 # Redis库从0到10，不填即为0
SESSION_SECRE="fRJ%KVZVoq4Du4#*Rx" # Seesion密钥，必须设置而且不要泄露
GIN_MODE="debug"            # 设置gin的运行模式，有 debug 和 release
```

### 总结

.env文件只是一个帮你便捷的设置环境变量的途径而已，你其实可以通过很多方法来设置环境变量。只要环境变量设置的正确，没有这个文件也是可以运行singo的。

{% page-ref page="../can-kao-zi-liao/ru-he-she-zhi-huan-jing-bian-liang.md" %}

特别提一下，.env文件已经在git中被忽略掉了。这样会避免你错误的把这个充满秘密的文件被提交到GitHub。如果你好奇怎么做到的。可以参考godotenv的文档[https://github.com/joho/godotenv](https://github.com/joho/godotenv)，来观察他的实现方式。

生产环境如何设置环境变量，请参考后面的部署章节

