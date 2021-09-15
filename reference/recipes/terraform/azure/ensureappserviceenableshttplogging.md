# Ensure app service enables HTTP logging

 **org.openrewrite.terraform.azure.EnsureAppServiceEnablesHTTPLogging** _Ensure app service enables HTTP logging._

### Tags

* Azure
* CKV\_AZURE\_63
* terraform

## Source

[Github](https://github.com/openrewrite/rewrite-terraform), [Issue Tracker](https://github.com/openrewrite/rewrite-terraform/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-terraform/0.5.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-terraform
* version: 0.5.0

## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-terraform:0.5.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.9.0")
}

rewrite {
    activeRecipe("org.openrewrite.terraform.azure.EnsureAppServiceEnablesHTTPLogging")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-terraform:0.5.0")
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
        <version>4.11.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.terraform.azure.EnsureAppServiceEnablesHTTPLogging</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-terraform</artifactId>
            <version>0.5.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.terraform.azure.EnsureAppServiceEnablesHTTPLogging`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Terraform configuration](../addconfiguration.md)
  * resourceName: `azurerm_app_service`
  * content: \`logs {

    http\_logs {

    retention\_in\_days = 4

    retention\_in\_mb = 10

    }

    }\`
{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.terraform.azure.EnsureAppServiceEnablesHTTPLogging
displayName: Ensure app service enables HTTP logging
description: Ensure app service enables HTTP logging.
tags:
  - Azure
  - CKV_AZURE_63
  - terraform
recipeList:
  - org.openrewrite.terraform.AddConfiguration:
      resourceName: azurerm_app_service
      content: logs {
  http_logs {
    retention_in_days = 4
    retention_in_mb = 10
  }
}
```
{% endtab %}
{% endtabs %}
