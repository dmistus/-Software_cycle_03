# **«Процессы CI/CD»**

### *Знакомоство с SonarQube*

#### Пропишите в inventory playbook созданные хосты.

![](img/124546.jpg)


#### Проверьте sonar-scanner --version.

![](img/2024-06-27_22-50.jpg)

#### Сделайте скриншот успешного прохождения анализа, приложите к решению ДЗ.

![](img/2024-06-28_00-15.jpg)

### *Знакомство с Nexus*

### В репозиторий maven-public загрузите артефакт с GAV-параметрами.

![](img/133749.jpg)

### В ответе пришлите файл maven-metadata.xml для этого артефекта.

![](img/150949.jpg)

### *Знакомство с Maven*

### Удалите из apache-maven-<version>/conf/settings.xml упоминание о правиле, отвергающем HTTP- соединение — раздел mirrors —> id: my-repository-http-unblocker.

``` <!--<mirror>
   <id>maven-default-http-blocker</id>
   <mirrorOf>external:http:*</mirrorOf>
   <name>Pseudo repository to mirror external repositories initially using HTTP.</name>
   <url>http://0.0.0.0/</url>
   <blocked>true</blocked>
 </mirror> -->
 ```
 
 ### Поменяйте в pom.xml блок с зависимостями под ваш артефакт из первого пункта задания для Nexus (java с версией 8_282).
 
 ```
 <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
 
  <groupId>com.netology.app</groupId>
  <artifactId>simple-app</artifactId>
  <version>1.0-SNAPSHOT</version>
   <repositories>
    <repository>
      <id>my-repo</id>
      <name>maven-public</name>
      <url>http://158.160.123.179:8081/repository/maven-public/</url>
    </repository>
  </repositories>
  <dependencies>
     <dependency>
      <groupId>netology</groupId>
      <artifactId>java</artifactId>
      <version>8_282</version>
      <classifier>distrib</classifier>
      <type>tar.gz</type>
    </dependency>
  </dependencies>
</project>
```

### Запустите команду mvn package в директории с pom.xml, ожидайте успешного окончания.

### В ответе пришлите исправленный файл pom.xml.

```<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
 
  <groupId>com.netology.app</groupId>
  <artifactId>simple-app</artifactId>
  <version>1.0-SNAPSHOT</version>
   <repositories>
    <repository>
      <id>my-repo</id>
      <name>maven-public</name>
      <url>http://158.160.123.179:8081/repository/maven-public/</url>
    </repository>
  </repositories>
  <dependencies>
     <dependency>
      <groupId>netology</groupId>
      <artifactId>java</artifactId>
      <version>8_282</version>
      <classifier>distrib</classifier>
      <type>tar.gz</type>
    </dependency>
  </dependencies>
</project>
```