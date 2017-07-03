## JSPC Maven Plugin

[![Maven Central](https://img.shields.io/maven-central/v/io.leonard.maven.plugins/jspc-maven-plugin.svg)](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22io.leonard.maven.plugins%22%20AND%20a%3A%22jspc-maven-plugin%22)

This plugin precompiles JSPs. It is a fork of jetty-jspc-maven-plugin and configured as follows:

```xml
<build>
....
<plugin>
 <groupId>io.leonard.maven.plugins</groupId>
  <artifactId>jspc-maven-plugin</artifactId>
  <version>${ENTER_VERSION_HERE}</version>
   <executions>
    <execution>
     <id>jspc</id>
     <goals>
     <goal>compile</goal>
    </goals>
    <configuration>
    </configuration>
  </execution>
 </executions>
</plugin>
...
</build>
```

It has the following improvements compared to jetty-jspc-maven-plugin:

* Faster: on my test project I was able to cut down the compilation time by about 40%
* More descriptive error messages: Under Maven 3 this plugin shows a clear indication of what caused the error and which file it is in
* Indication of the progress of the compilation by showing which JSP is currently being compiled

The compiler used in this plugin is [Apache Jasper 8.5.8](http://search.maven.org/#artifactdetails%7Corg.apache.tomcat%7Cjasper%7C8.5.8%7Cjar).

Full documentation of the goal is available at http://leonardehrenfried.github.com/jspc-maven-plugin/compile-mojo.html

## Release process

1. Set version in `pom.xml`
1. `mvn clean deploy`
1. `make commit-site`
