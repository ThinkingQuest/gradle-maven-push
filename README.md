# gradle-maven-push
一个gradle的script。用于发布到maven central。

## Usage
### 配置
在build.gradle最后增加：
```groovy
apply from: 'maven_push_java.gradle'
```
并将maven_push_java.gradle文件复制到项目目录下（与build.gradle同目录）。  
  
在USER_HOME/.gradle/gradle.properties文件中增加：
```groovy
NEXUS_USERNAME=yourusername
NEXUS_PASSWORD=yourpassword
signing.keyId=your key id like ABCDEF12
signing.password=yourpassword
signing.secretKeyRingFile=~/.gnupg/secring.gpg
```
`~`代表USER_HOME，实践中这里需要使用绝对路径。因为脚本中判断~会当作相对路径与工程路径拼接，而不会像/Users/xxxuser这样的路径一样被当作绝对路径。  

将gradle.properties文件复制到或合并到项目目录下，相应修改其配置值。


### 发布
要发布到本地maven仓库，执行：
```
gradle publishToMavenLocal
```

要发布到maven中央仓库，执行：
```
gradle uploadArchives
```