# Add a Gradle settings repository

**org.openrewrite.gradle.plugins.AddSettingsPluginRepository**

_Add a Gradle settings repository to `settings.gradle(.kts)`._

## Source

[Github](https://github.com/openrewrite/rewrite/blob/main/rewrite-gradle/src/main/java/org/openrewrite/gradle/plugins/AddSettingsPluginRepository.java), [Issue Tracker](https://github.com/openrewrite/rewrite/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite/rewrite-gradle/7.41.0-SNAPSHOT/jar)

* groupId: org.openrewrite
* artifactId: rewrite-gradle
* version: 7.41.0-SNAPSHOT

## Contributors
<span style="display: inline-block; width: 50px; height: 50px; border-radius: 50%; background-color: #555; color: #fff; text-align: center; line-height: 50px; font-size: 24px; text-transform: uppercase;" title="Shannon Pamperl(shanman190@gmail.com)">SP</span>
<span style="display: inline-block; width: 50px; height: 50px; border-radius: 50%; background-color: #555; color: #fff; text-align: center; line-height: 50px; font-size: 24px; text-transform: uppercase;" title="Sam Snyder(sam@moderne.io)">SS</span>
## Options

| Type | Name | Description |
| -- | -- | -- |
| `String` | type | The type of the artifact repository |
| `String` | url | The url of the artifact repository |


## Usage

This recipe has required configuration parameters. Recipes with required configuration parameters cannot be activated directly. To activate this recipe you must create a new recipe which fills in the required parameters. In your `rewrite.yml` create a new recipe with a unique name. For example: `com.yourorg.AddSettingsPluginRepositoryExample`.
Here's how you can define and customize such a recipe within your rewrite.yml:

{% code title="rewrite.yml" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: com.yourorg.AddSettingsPluginRepositoryExample
displayName: Add a Gradle settings repository example
recipeList:
  - org.openrewrite.gradle.plugins.AddSettingsPluginRepository:
      type: maven
      url: https://repo.spring.io
```
{% endcode %}


Now that `com.yourorg.AddSettingsPluginRepositoryExample` has been defined activate it in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.40.4")
}

rewrite {
    activeRecipe("com.yourorg.AddSettingsPluginRepositoryExample")
}

repositories {
    mavenCentral()
}

```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.45.0</version>
        <configuration>
          <activeRecipes>
            <recipe>com.yourorg.AddSettingsPluginRepositoryExample</recipe>
          </activeRecipes>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}


## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://public.moderne.io/recipes/org.openrewrite.gradle.plugins.AddSettingsPluginRepository)

The Moderne public SaaS instance enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.