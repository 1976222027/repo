# repo
自己在github上搭建的maven仓库  简便提供依赖使用
```
allprojects {
    repositories {
    //github上的maven仓库
        maven { url 'https://raw.githubusercontent.com/1976222027/repo/master/' }
        maven { url 'https://raw.githubusercontent.com/1976222027/repo/main/' }
        maven { url 'https://github.com/1976222027/repo/raw/maven' }
    //gitee上的maven仓库repository: https://gitee.com/<用户名>/<仓库名>/raw/分支名/路径
        maven { url 'https://gitee.com/mahongyin/repo/raw/main'}
        maven { url 'https://maven.aliyun.com/repository/public' } //阿里云仓库
        google() 
        mavenCentral() 
    }
}
```
~/.gradle/gradle.properties
MAVEN_PRIVATE_URL = https://gitee.com/mahongyin/repo/raw/main/
MAVEN_LOCAL_PATH = D:/repo

// Maven Private Repo
repositories {
    maven { url MAVEN_PRIVATE_URL }
}
// Maven Private Deploy
uploadArchives {
    repositories {
        mavenDeployer {
            repository(url: "file://${MAVEN_LOCAL_PATH}" )
        }
    }
}
发布和上传
# 发布到本地
gradle uploadArchives
# 提交到git仓库
cd ${MAVEN_LOCAL_PATH}
git add . && git commit -m "upload pom" && git push origin master
