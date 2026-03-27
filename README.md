# Uetlib Parent

Bill of Materials maven POM for uetlib libraries.

## Using

### As parent

You can use this artifact as parent for your maven project. 
This will set the dependency management, plugin management and set some basic maven properties. 
You can use it as following:

```xml
<parent>
    <groupId>ch.ubique</groupId>
    <artifactId>uetlib-parent</artifactId>
    <version>...</version>
</parent>
```

To set up sonar cloud with coverage reports, add the following to your properties:

```xml
<properties>
    <sonar.projectName>my-project</sonar.projectName>
    <sonar.coverage.module>my-project-coverage</sonar.coverage.module>
</properties>
```

## Changelog

See [CHANGELOG.md](CHANGELOG.md)
