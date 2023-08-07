# Migrates to ApacheHttpClient 4.5.x

**org.openrewrite.java.apache.httpclient4.UpgradeApacheHttpClient\_4\_5**

_Migrate applications to the latest Apache HttpClient 4.5.x release. This recipe modifies  application's build files, make changes to deprecated/preferred APIs, and migrates configuration settings that have changes between versions._

### Tags

* apache
* httpclient

## Source

[GitHub](https://github.com/openrewrite/rewrite-spring/blob/main/src/main/resources/META-INF/rewrite/apache-httpclient-4-5.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-spring/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-spring/5.0.7/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-spring
* version: 5.0.7


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-spring:5.0.7` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.1.22")
}

rewrite {
    activeRecipe("org.openrewrite.java.apache.httpclient4.UpgradeApacheHttpClient_4_5")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-spring:5.0.7")
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
        <version>5.4.1</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.apache.httpclient4.UpgradeApacheHttpClient_4_5</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-spring</artifactId>
            <version>5.0.7</version>
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
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-spring:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.java.apache.httpclient4.UpgradeApacheHttpClient_4_5
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Upgrade Gradle or Maven dependency versions](../../../java/dependencies/upgradedependencyversion.md)
  * groupId: `org.apache.httpcomponents`
  * artifactId: `httpclient`
  * newVersion: `4.5.x`
* [Maps deprecated classes from Apache HttpClient 4.5.x to suggested replacements](../../../java/apache/httpclient4/mappingdeprecatedclasses.md)

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.apache.httpclient4.UpgradeApacheHttpClient_4_5
displayName: Migrates to ApacheHttpClient 4.5.x
description: Migrate applications to the latest Apache HttpClient 4.5.x release. This recipe modifies  application's build files, make changes to deprecated/preferred APIs, and migrates configuration settings that have changes between versions.

tags:
  - apache
  - httpclient
recipeList:
  - org.openrewrite.java.dependencies.UpgradeDependencyVersion:
      groupId: org.apache.httpcomponents
      artifactId: httpclient
      newVersion: 4.5.x
  - org.openrewrite.java.apache.httpclient4.MappingDeprecatedClasses

```
{% endtab %}
{% endtabs %}

## Contributors
* [Joan Viladrosa](mailto:joan@moderne.io)


## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.java.apache.httpclient4.UpgradeApacheHttpClient_4_5)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.