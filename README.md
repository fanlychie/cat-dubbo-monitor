> 对`Dubbo`调用进行拦截，并加入到`CAT`监控。

源码源自[CAT](https://github.com/dianping/cat)的[框架埋点方案集成/dubbo](https://github.com/dianping/cat/tree/master/框架埋点方案集成/dubbo)。源码改动内容有如下：

- [x] 项目名`cat-monitor`更改为`cat-dubbo-monitor`
- [x] 修复`pom.xml`的依赖声明
- [x] 修改源码文件`CatTransaction.java`去掉`commons-lang`的依赖

---

安装到本地仓库命令：

```sh
mvn clean install
```

客户端依赖声明方式：

```xml
<dependency>
    <groupId>net.dubboclub</groupId>
    <artifactId>cat-dubbo-monitor</artifactId>
    <version>0.0.6</version>
</dependency>
```

---

或者使用我托管的仓库`fanlychie-maven-repo`直接声明依赖：

```xml
<repositories>
    <repository>
        <id>fanlychie-maven-repo</id>
        <url>https://raw.github.com/fanlychie/maven-repo/releases</url>
    </repository>
</repositories>
<dependencies>
    <dependency>
        <groupId>net.dubboclub</groupId>
        <artifactId>cat-dubbo-monitor</artifactId>
        <version>0.0.6</version>
    </dependency>
</dependencies>
```

---

接入方式：只需要声明依赖包，不需要做任何配置。接入后，在cat中会出现cross报表，dependency，服务端的matrix以及调用链路的trace信息。

---

效果图：

![cat-dubbo-monitor接入效果图](https://raw.githubusercontent.com/fanlychie/mdimg/master/dubbo-monitor-cat.png)