---
sidebar_label: "Change XML attribute of a specific resource version"
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Change XML attribute of a specific resource version

**org.openrewrite.xml.ChangeNamespaceValue**

_Alters XML Attribute value within specified element of a specific resource versions._

## Recipe source

[GitHub](https://github.com/openrewrite/rewrite/blob/main/rewrite-xml/src/main/java/org/openrewrite/xml/ChangeNamespaceValue.java), [Issue Tracker](https://github.com/openrewrite/rewrite/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite/rewrite-xml/8.38.0/jar)

* groupId: org.openrewrite
* artifactId: rewrite-xml
* version: 8.38.0

## Options

| Type | Name | Description | Example |
| -- | -- | -- | -- |
| `String` | elementName | *Optional*. The name of the element whose attribute's value is to be changed. Interpreted as an XPath Expression. | `property` |
| `String` | oldValue | *Optional*. Only change the property value if it matches the configured `oldValue`. | `newfoo.bar.attribute.value.string` |
| `String` | newValue | The new value to be used for the namespace. | `newfoo.bar.attribute.value.string` |
| `String` | versionMatcher | *Optional*. The version of resource to change | `1.1` |
| `Boolean` | searchAllNamespaces | *Optional*. Specify whether evaluate all namespaces. Defaults to true | `true` |
| `String` | newVersion | The new version of the resource | `2.0` |
| `String` | newSchemaLocation | *Optional*. The new value to be used for the namespace schema location. | `newfoo.bar.attribute.value.string` |


## Usage

This recipe has required configuration parameters. Recipes with required configuration parameters cannot be activated directly. To activate this recipe you must create a new recipe which fills in the required parameters. In your `rewrite.yml` create a new recipe with a unique name. For example: `com.yourorg.ChangeNamespaceValueExample`.
Here's how you can define and customize such a recipe within your rewrite.yml:
```yaml title="rewrite.yml"
---
type: specs.openrewrite.org/v1beta/recipe
name: com.yourorg.ChangeNamespaceValueExample
displayName: Change XML attribute of a specific resource version example
recipeList:
  - org.openrewrite.xml.ChangeNamespaceValue:
      elementName: property
      oldValue: newfoo.bar.attribute.value.string
      newValue: newfoo.bar.attribute.value.string
      versionMatcher: 1.1
      searchAllNamespaces: true
      newVersion: 2.0
      newSchemaLocation: newfoo.bar.attribute.value.string
```

Now that `com.yourorg.ChangeNamespaceValueExample` has been defined, activate it in your build file:
<Tabs groupId="projectType">
<TabItem value="gradle" label="Gradle">

1. Add the following to your `build.gradle` file:
```groovy title="build.gradle"
plugins {
    id("org.openrewrite.rewrite") version("6.26.0")
}

rewrite {
    activeRecipe("com.yourorg.ChangeNamespaceValueExample")
    exportDatatables = true
}

repositories {
    mavenCentral()
}
```
2. Run `gradle rewriteRun` to run the recipe.
</TabItem>
<TabItem value="maven" label="Maven">

1. Add the following to your `pom.xml` file:

```xml title="pom.xml"
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.43.0</version>
        <configuration>
          <exportDatatables>true</exportDatatables>
          <activeRecipes>
            <recipe>com.yourorg.ChangeNamespaceValueExample</recipe>
          </activeRecipes>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```
2. Run `mvn rewrite:run` to run the recipe.
</TabItem>
<TabItem value="moderne-cli" label="Moderne CLI">

You will need to have configured the [Moderne CLI](https://docs.moderne.io/moderne-cli/cli-intro) on your machine before you can run the following command.

```shell title="shell"
mod run . --recipe ChangeNamespaceValueExample
```
</TabItem>
</Tabs>

## See how this recipe works across multiple open-source repositories

<a href="https://app.moderne.io/recipes/org.openrewrite.xml.ChangeNamespaceValue">
    <img
    src={require("/static/img/ModerneRecipeButton.png").default}
    alt="Moderne Link Image"
    width="50%"
    />
</a>

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.
## Data Tables

### Source files that had results
**org.openrewrite.table.SourcesFileResults**

_Source files that were modified by the recipe run._

| Column Name | Description |
| ----------- | ----------- |
| Source path before the run | The source path of the file before the run. `null` when a source file was created during the run. |
| Source path after the run | A recipe may modify the source path. This is the path after the run. `null` when a source file was deleted during the run. |
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


## Contributors
cjobinabo, Adriano Machado, [Sam Snyder](mailto:sam@moderne.io), [Tim te Beek](mailto:tim@moderne.io), [Jonathan Schnéider](mailto:jkschneider@gmail.com)