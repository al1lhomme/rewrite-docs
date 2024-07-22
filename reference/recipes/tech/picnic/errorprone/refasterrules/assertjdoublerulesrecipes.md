# `AssertJDoubleRules` Refaster recipes

**tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes**

_Refaster template recipes for `tech.picnic.errorprone.refasterrules.AssertJDoubleRules`. [Source](https://error-prone.picnic.tech/refasterrules/AssertJDoubleRules)._

## Recipe source

[GitHub](https://github.com/search?type=code&q=tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes), [Issue Tracker](https://github.com/openrewrite/rewrite-third-party/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-third-party/0.5.3/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-third-party
* version: 0.5.3

{% hint style="info" %}
This recipe is composed of more than one recipe. If you want to customize the set of recipes this is composed of, you can find and copy the GitHub source for the recipe from the link above.
{% endhint %}
## Data Tables

### Source files that had results
**org.openrewrite.table.SourcesFileResults**

_Source files that were modified by the recipe run._

| Column Name | Description |
| ----------- | ----------- |
| Source path before the run | The source path of the file before the run. |
| Source path after the run | A recipe may modify the source path. This is the path after the run. |
| Parent of the recipe that made changes | In a hierarchical recipe, the parent of the recipe that made a change. Empty if this is the root of a hierarchy or if the recipe is not hierarchical at all. |
| Recipe that made changes | The specific recipe that made a change. |
| Estimated time saving | An estimated effort that a developer to fix manually instead of using this recipe, in unit of seconds. |
| Cycle | The recipe cycle in which the change was made. |

### Source files that errored on a recipe
**org.openrewrite.table.SourcesFileErrors**

_The details of all errors produced by a recipe run._

| Column Name | Description |
| ----------- | ----------- |
| Source path | The file that failed to parse. |
| Recipe that made changes | The specific recipe that made a change. |
| Stack trace | The stack trace of the failure. |

### Recipe performance
**org.openrewrite.table.RecipeRunStats**

_Statistics used in analyzing the performance of recipes._

| Column Name | Description |
| ----------- | ----------- |
| The recipe | The recipe whose stats are being measured both individually and cumulatively. |
| Source file count | The number of source files the recipe ran over. |
| Source file changed count | The number of source files which were changed in the recipe run. Includes files created, deleted, and edited. |
| Cumulative scanning time | The total time spent across the scanning phase of this recipe. |
| 99th percentile scanning time | 99 out of 100 scans completed in this amount of time. |
| Max scanning time | The max time scanning any one source file. |
| Cumulative edit time | The total time spent across the editing phase of this recipe. |
| 99th percentile edit time | 99 out of 100 edits completed in this amount of time. |
| Max edit time | The max time editing any one source file. |


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-third-party:0.5.3` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
1. Add the following to your `build.gradle` file:
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.16.4")
}

rewrite {
    activeRecipe("tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-third-party:0.5.3")
}
```
{% endcode %}
2. Run `gradle rewriteRun` to run the recipe.
{% endtab %}

{% tab title="Gradle init script" %}
1. Create a file named `init.gradle` in the root of your project.
{% code title="init.gradle" %}
```groovy
initscript {
    repositories {
        maven { url "https://plugins.gradle.org/m2" }
    }
    dependencies { classpath("org.openrewrite:plugin:6.16.4") }
}
rootProject {
    plugins.apply(org.openrewrite.gradle.RewritePlugin)
    dependencies {
        rewrite("org.openrewrite.recipe:rewrite-third-party:0.5.3")
    }
    rewrite {
        activeRecipe("tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes")
    }
    afterEvaluate {
        if (repositories.isEmpty()) {
            repositories {
                mavenCentral()
            }
        }
    }
}
```
{% endcode %}
2. Run `gradle --init-script init.gradle rewriteRun` to run the recipe.
{% endtab %}
{% tab title="Maven POM" %}
1. Add the following to your `pom.xml` file:
{% code title="pom.xml" %}
```xml
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.36.0</version>
        <configuration>
          <exportDatatables>true</exportDatatables>
          <activeRecipes>
            <recipe>tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-third-party</artifactId>
            <version>0.5.3</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
2. Run `mvn rewrite:run` to run the recipe.
{% endtab %}

{% tab title="Maven Command Line" %}

You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.

{% code title="shell" overflow="wrap" %}
```shell
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-third-party:RELEASE -Drewrite.activeRecipes=tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes -Drewrite.exportDatatables=true
```
{% endcode %}
{% endtab %}
{% tab title="Moderne CLI" %}
You will need to have configured the [Moderne CLI](https://docs.moderne.io/moderne-cli/cli-intro) on your machine before you can run the following command.

{% code title="shell" %}
```shell
mod run . --recipe AssertJDoubleRulesRecipes
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Refaster template `AssertJDoubleRules.AbstractDoubleAssertIsCloseToWithOffset`](../../../../tech/picnic/errorprone/refasterrules/assertjdoublerulesrecipes$abstractdoubleassertisclosetowithoffsetrecipe.md)
* [Refaster template `AssertJDoubleRules.AbstractDoubleAssertIsEqualTo`](../../../../tech/picnic/errorprone/refasterrules/assertjdoublerulesrecipes$abstractdoubleassertisequaltorecipe.md)
* [Refaster template `AssertJDoubleRules.AbstractDoubleAssertIsNotEqualTo`](../../../../tech/picnic/errorprone/refasterrules/assertjdoublerulesrecipes$abstractdoubleassertisnotequaltorecipe.md)
* [Refaster template `AssertJDoubleRules.AbstractDoubleAssertIsZero`](../../../../tech/picnic/errorprone/refasterrules/assertjdoublerulesrecipes$abstractdoubleassertiszerorecipe.md)
* [Refaster template `AssertJDoubleRules.AbstractDoubleAssertIsNotZero`](../../../../tech/picnic/errorprone/refasterrules/assertjdoublerulesrecipes$abstractdoubleassertisnotzerorecipe.md)
* [Refaster template `AssertJDoubleRules.AbstractDoubleAssertIsOne`](../../../../tech/picnic/errorprone/refasterrules/assertjdoublerulesrecipes$abstractdoubleassertisonerecipe.md)

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes
displayName: `AssertJDoubleRules` Refaster recipes
description: Refaster template recipes for `tech.picnic.errorprone.refasterrules.AssertJDoubleRules`. [Source](https://error-prone.picnic.tech/refasterrules/AssertJDoubleRules).
recipeList:
  - tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes$AbstractDoubleAssertIsCloseToWithOffsetRecipe
  - tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes$AbstractDoubleAssertIsEqualToRecipe
  - tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes$AbstractDoubleAssertIsNotEqualToRecipe
  - tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes$AbstractDoubleAssertIsZeroRecipe
  - tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes$AbstractDoubleAssertIsNotZeroRecipe
  - tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes$AbstractDoubleAssertIsOneRecipe

```
{% endtab %}
{% endtabs %}

## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/tech.picnic.errorprone.refasterrules.AssertJDoubleRulesRecipes)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.