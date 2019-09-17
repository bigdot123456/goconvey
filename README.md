# goconvey
测试方法：
```bash
go test -v
```
里面的核心是利用go testing包进行各种测试  

## goconvey的环境搭建 
下是搭建好了环境以后，使用的过程和开发的时候-遇到的一些坑。

安装golang测试框架
```bash
go get github.com/smartystreets/goconvey
```

下载后，在`github.com/smartystreets/goconvey` 目录下运行`goconvey.exe`文件。  

出来的cmd命令页面不要关闭，否则会中断测试。  

注意修改端口。默认是8080端口。可能会与开发的端口产生冲突。  

测试用例必须带_test后缀，否则系统无法检测到你的测试用例。  

半自动化书写测试用例 通过生成测试所用的单元测试  
[链接地址: http://localhost:8080/composer.html](http://localhost:8080/composer.html)

```golang
    Convey("API ", t, func() {
        Convey("/v1/user/login发送post请求得到状态code And http请求 And 账号登录 测试用例", func() {
            So(PostRequest(urlUserLogin), ShouldEqual, true)
        })
    })
```

Convey可无限嵌套，用于表示子测试下的关系  
