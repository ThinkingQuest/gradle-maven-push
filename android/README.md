# maven-push-android.gradle
一个gradle的script。用于发布到maven central。

## Usage
### 配置
在build.gradle最后增加：
```groovy
apply from: 'maven-push-android.gradle'
```
并将maven-push-android.gradle文件复制到项目目录下（与build.gradle同目录）。  


### 发布
要发布到本地maven仓库，执行：
```
gradle clean build publishToMavenLocal
```

