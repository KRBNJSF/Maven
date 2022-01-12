# Maven

https://jsoup.org/<br>
https://jsoup.org/apidocs/org/jsoup/nodes/Document.html<br>
https://mvnrepository.com/artifact/org.jsoup/jsoup/1.14.3<br><br>

<b>Java</b>
```
import org.jsoup.Jsoup;
import org.jsoup.nodes.Document;
import org.jsoup.nodes.Element;
import org.jsoup.select.Elements;

import java.io.IOException;

public class Main {
    public static void main(String[] args) throws IOException {
        Document doc = Jsoup.connect("https://hokej.cz/tipsport-extraliga/stats-center?season=2021&competition=6705&stranger=0&stats-all=1&stats-order=ga&stats-direction=desc").get();
        System.out.println(doc.title());

        Elements newsHeadlines = doc.select("td");
        for (Element headline : newsHeadlines) {
            System.out.println(headline.text());
        }
    }
}


```
<b>Maven</b>
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>mavenProject</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>17</maven.compiler.source>
        <maven.compiler.target>17</maven.compiler.target>
    </properties>

    <dependencies>
    <!-- https://mvnrepository.com/artifact/org.jsoup/jsoup -->
    <dependency>
        <groupId>org.jsoup</groupId>
        <artifactId>jsoup</artifactId>
        <version>1.14.3</version>
    </dependency>
</dependencies>

</project>
```
