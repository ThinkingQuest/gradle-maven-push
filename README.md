# gradle-maven-push
在软件开发的世界里，任何造成大量的工程师为了同一个问题而各自浪费时间和精力的事情，都是罪大恶极的。Gradle就做了一件这样的事：搞定gradle的发布任务是非常困难的。  
Gradle中与发布到maven相关的插件有两个：'maven'和'maven-publish'。
maven-publish为新的插件，目标是替代前者。
但maven-publish不支持为pom签名，也就是说无法实现发布到maven中央仓库。
maven提供了install命令，可以发布到本地maven cache，但只对apply了java plugin的工程有效，并且这一点并未在官方文档中说明。  
总之，两个插件各有各的问题，没有一个好用，能干脆利落的解决问题。

## 目标
* 支持java library（packaging为jar），支持android library（packaging为aar）
* 支持发布到本地maven cache（即~/.m2/repository）相当于maven install
* 支持通过sonatype发布到maven中央仓库。实现指定的规范，包括gpg签名等。

## 使用
两个gradle插件。详见`android`和`java`目录。