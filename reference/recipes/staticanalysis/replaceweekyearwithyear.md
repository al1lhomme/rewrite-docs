# Week Year (YYYY) should not be used for date formatting

**org.openrewrite.staticanalysis.ReplaceWeekYearWithYear**

_For most dates Week Year (YYYY) and Year (yyyy) yield the same results. However, on the last week of December and first week of January Week Year could produce unexpected results._

### Tags

* RSPEC-3986

## Source

[GitHub](https://github.com/openrewrite/rewrite-static-analysis/blob/main/src/main/java/org/openrewrite/staticanalysis/ReplaceWeekYearWithYear.java), [Issue Tracker](https://github.com/openrewrite/rewrite-static-analysis/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-static-analysis/1.0.4/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-static-analysis
* version: 1.0.4

## Example


{% tabs %}
{% tab title="Test.java" %}

###### Before
{% code title="Test.java" %}
```java
import java.text.SimpleDateFormat;
import java.util.Date;

class Test {
  public void formatDate() {
    Date date = new SimpleDateFormat("yyyy/MM/dd").parse("2015/12/31");
    String result = new SimpleDateFormat("YYYY/MM/dd").format(date);
  }
}
```
{% endcode %}

###### After
{% code title="Test.java" %}
```java
import java.text.SimpleDateFormat;
import java.util.Date;

class Test {
  public void formatDate() {
    Date date = new SimpleDateFormat("yyyy/MM/dd").parse("2015/12/31");
    String result = new SimpleDateFormat("yyyy/MM/dd").format(date);
  }
}
```
{% endcode %}

{% endtab %}
{% tab title="Diff" %}
{% code %}
```diff
--- Test.java
+++ Test.java
@@ -7,1 +7,1 @@
  public void formatDate() {
    Date date = new SimpleDateFormat("yyyy/MM/dd").parse("2015/12/31");
-   String result = new SimpleDateFormat("YYYY/MM/dd").format(date);
+   String result = new SimpleDateFormat("yyyy/MM/dd").format(date);
  }
```
{% endcode %}
{% endtab %}
{% endtabs %}


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-static-analysis:1.0.4` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.1.19")
}

rewrite {
    activeRecipe("org.openrewrite.staticanalysis.ReplaceWeekYearWithYear")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-static-analysis:1.0.4")
}
```
{% endcode %}
{% endtab %}
{% tab title="Maven POM" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.3.2</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.staticanalysis.ReplaceWeekYearWithYear</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-static-analysis</artifactId>
            <version>1.0.4</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}

{% tab title="Maven Command Line" %}
{% code title="shell" %}
You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.

```shell
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run \
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-static-analysis:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.staticanalysis.ReplaceWeekYearWithYear
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Contributors
* [Aleksandar A Simpson](mailto:alek@asu.me)


## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.staticanalysis.ReplaceWeekYearWithYear)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.