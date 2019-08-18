# 修改包名

### 修改go.mod文件

包名在项目的go.mod文件中

```go
module singo

go 1.12

require (
	github.com/gin-contrib/cors v1.3.0
	github.com/gin-contrib/sessions v0.0.0-20190512062852-3cb4c4f2d615
	github.com/gin-gonic/gin v1.4.0
	github.com/go-redis/redis v6.15.3+incompatible
	github.com/jinzhu/gorm v1.9.10
	github.com/joho/godotenv v1.3.0
	golang.org/x/crypto v0.0.0-20190701094942-4def268fd1a4
	gopkg.in/go-playground/validator.v8 v8.18.2
	gopkg.in/yaml.v2 v2.2.2
)
```

你需要把第一行的

```go
module singo
```

修改为

```go
module giligili
```

这样你的包名就修改完成了

