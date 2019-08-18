# 运行项目

### 把项目跑起来

在项目了使用go run main.go就可以把项目跑起来了。  
然后go modoules会自动把你缺失的包安装好。

```bash
$ go run main.go   
finding github.com/gin-contrib/sessions latest
finding github.com/gin-contrib/sessions/cookie latest
finding golang.org/x/crypto/bcrypt latest
finding github.com/jinzhu/gorm/dialects/mysql latest
finding golang.org/x/crypto latest
finding github.com/jinzhu/gorm/dialects latest
```

{% hint style="info" %}
如果你项目没有成功启动，绝大部分情况下是环境变量配置不成功，导致你要么连不上mysql，要么连不上redis
{% endhint %}

