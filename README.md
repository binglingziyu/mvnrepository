# Maven 私有仓库

```gradle
repositories {
    mavenCentral()
    maven {
        url 'https://raw.githubusercontent.com/binglingziyu/mvnrepository/master/'
    }
}
```

```mvn
<repository>
  <id>binglingziyu</id>
  <name>mvnrepository</name>
  <url>https://raw.githubusercontent.com/binglingziyu/mvnrepository/master/</url>
</repository>
```

# 使用方法

新建 Github 仓库：https://github.com/binglingziyu/mvnrepository

假设有一个 Jar: taobao-sdk-java-auto-1479188381469-20190815.jar

操作步骤：

```
$ pwd
/home/staff/Desktop/taobao-sdk

# 安装到本地仓库中
$ mvn install:install-file -DgroupId=com.dingtalk -DartifactId=taobao-sdk-java-auto -Dversion=1479188381469-20190815 -Dpackaging=jar -Dfile=taobao-sdk-java-auto-1479188381469-20190815.jar

# 安装完存放的位置
$ cd ~/.m2/repository/com/dingtalk/taobao-sdk-java-auto/1479188381469-20190815

# 将 com/dingtalk/taobao-sdk-java-auto/1479188381469-20190815 文件夹添加到 Github 仓库
$ pwd
/Users/hubin/Documents/mvnrepository
$ tree .
.
├── README.md
└── com
    └── dingtalk
        └── taobao-sdk-java-auto
            ├── 1479188381469-20190815
            │   ├── _remote.repositories
            │   ├── taobao-sdk-java-auto-1479188381469-20190815.jar
            │   └── taobao-sdk-java-auto-1479188381469-20190815.pom
            └── maven-metadata-local.xml

4 directories, 5 files

# 将 mvnrepository 提交到 Github
```
