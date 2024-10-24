---
sidebar_label: "Remove LaunchDarkly's boolVariation for feature key"
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Remove LaunchDarkly's `boolVariation` for feature key

**org.openrewrite.featureflags.launchdarkly.RemoveStringVariation**

_Replace `boolVariation` invocations for feature key with value, and simplify constant if branch execution._

## Recipe source

[GitHub](https://github.com/openrewrite/rewrite-feature-flags/blob/main/src/main/java/org/openrewrite/featureflags/launchdarkly/RemoveStringVariation.java), [Issue Tracker](https://github.com/openrewrite/rewrite-feature-flags/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-feature-flags/0.9.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-feature-flags
* version: 0.9.0

## Options

| Type | Name | Description | Example |
| -- | -- | -- | -- |
| `String` | featureKey | The key of the feature flag to remove. | `flag-key-123abc` |
| `String` | replacementValue | The value to replace the feature flag check with. | `topic-456` |


## Definition

<Tabs groupId="recipeType">
<TabItem value="recipe-list" label="Recipe List" >
* [Remove a String feature flag for feature key](../../featureflags/removestringflag)
  * methodPattern: `com.launchdarkly.sdk.server.LDClient stringVariation(String, com.launchdarkly.sdk.*, String)`

</TabItem>

<TabItem value="yaml-recipe-list" label="Yaml Recipe List">

```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.featureflags.launchdarkly.RemoveStringVariation
displayName: Remove LaunchDarkly's `boolVariation` for feature key
description: Replace `boolVariation` invocations for feature key with value, and simplify constant if branch execution.


recipeList:
  - org.openrewrite.featureflags.RemoveStringFlag:
      methodPattern: com.launchdarkly.sdk.server.LDClient stringVariation(String, com.launchdarkly.sdk.*, String)

```
</TabItem>
</Tabs>

## Usage

This recipe has required configuration parameters. Recipes with required configuration parameters cannot be activated directly. To activate this recipe you must create a new recipe which fills in the required parameters. In your `rewrite.yml` create a new recipe with a unique name. For example: `com.yourorg.RemoveStringVariationExample`.
Here's how you can define and customize such a recipe within your rewrite.yml:
```yaml title="rewrite.yml"
---
type: specs.openrewrite.org/v1beta/recipe
name: com.yourorg.RemoveStringVariationExample
displayName: Remove LaunchDarkly's `boolVariation` for feature key example
recipeList:
  - org.openrewrite.featureflags.launchdarkly.RemoveStringVariation:
      featureKey: flag-key-123abc
      replacementValue: topic-456
```

Now that `com.yourorg.RemoveStringVariationExample` has been defined, activate it and take a dependency on org.openrewrite.recipe:rewrite-feature-flags:0.9.0 in your build file:
<Tabs groupId="projectType">
<TabItem value="gradle" label="Gradle">

1. Add the following to your `build.gradle` file:

```groovy title="build.gradle"
plugins {
    id("org.openrewrite.rewrite") version("6.26.0")
}

rewrite {
    activeRecipe("com.yourorg.RemoveStringVariationExample")
    exportDatatables = true
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-feature-flags:0.9.0")
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
            <recipe>com.yourorg.RemoveStringVariationExample</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-feature-flags</artifactId>
            <version>0.9.0</version>
          </dependency>
        </dependencies>
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
mod run . --recipe RemoveStringVariationExample
```
</TabItem>
</Tabs>

## See how this recipe works across multiple open-source repositories

<a href="https://app.moderne.io/recipes/org.openrewrite.featureflags.launchdarkly.RemoveStringVariation">
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
[Tim te Beek](mailto:tim@moderne.io)