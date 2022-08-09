# repo
自己在github上搭建的maven仓库  简便提供依赖使用
```
allprojects {
    repositories {
        maven { url 'https://raw.githubusercontent.com/1976222027/repo/master/' } //自己的仓库
        maven { url 'https://maven.aliyun.com/repository/public' } //阿里云仓库
        google() 
        mavenCentral() 
    }
}
```
