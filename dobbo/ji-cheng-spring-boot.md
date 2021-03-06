# 使用Spring构建Dubbo服务

由于阿里团队重启对Dubbo项目的维护，相对以往对Spring Boot项目集成Dubbo做出更多的优化

## 资源准备

* 前往Github下查询Dubbo的仓库，并关注dubbo-spring-boot-starter子项目

```
    https://github.com/dubbo/dubbo-spring-boot-project
```

* 新建Spring Boot应用

```
    注意：请选择选择1.3.0.RELEASE
```

* pom.xml如下

```
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.3.0.RELEASE</version>
    </parent>
    
    <dependencies>        
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>    
    
        <dependency>
            <groupId>com.alibaba.boot</groupId>
            <artifactId>dubbo-spring-boot-starter</artifactId>
            <version>1.0.0-SNAPSHOT</version>
        </dependency>    
    </dependencies>
    
    <repositories>
        <repository>
            <id>sonatype-nexus-snapshots</id>
            <url>https://oss.sonatype.org/content/repositories/snapshots</url>
            <releases>
                <enabled>false</enabled>
            </releases>
            <snapshots>
                <enabled>true</enabled>
            </snapshots>
        </repository>
    </repositories>
            
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
```

*  由于项目还正在开发中，因此只能Snapshot库的依赖，如果由此而无法拉取依赖，请参考如下步骤解决

```
a. 使用无mirror的maven的settings.xml
b. 执行 mvn clean install
```

## 创建API

```
public interface DemoService {
    
    String sayHello(String name);
}
```

##  创建服务Provider



  



 

