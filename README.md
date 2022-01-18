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
        System.out.println(doc.title()); //Title printout

        Elements newsHeadlines = doc.select("body > div.branding-wrapper > div.content-wrapper > div > div.container > table > tbody > tr > td > a"); //Prvek - Element, class name
        for (Element headline : newsHeadlines) {
            System.out.println(headline.text()); //Element printout
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
![image](https://user-images.githubusercontent.com/90755554/149888041-5948d057-e108-4c1f-ae7c-01bdb4033ce9.png)
![image](https://user-images.githubusercontent.com/90755554/149084552-7380c765-fb19-4701-9918-610c390da57a.png)<br>
![image](https://user-images.githubusercontent.com/90755554/149084968-41c57488-a91b-45da-ac77-b276f53af987.png)<br>

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
```

