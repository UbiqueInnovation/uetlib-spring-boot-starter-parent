# Uetlib Spring Boot Starter Parent

This parent has the Spring Boot Starter Parent as its own parent and includes common dependency- and plugin management
for uetlib-using projects.

## Dependency Management

In the given order:

- `ch.ubique.uetlib:uetlib-bom`
- `ch.ubique.uetlib:uetlib-self-bom`
- `org.springframework.cloud:spring-cloud-dependencies`

## Plugin Management

- `org.springframework.boot:spring-boot-maven-plugin` with goal `build-info`
- `com.google.cloud.tools:jib-maven-plugin` with the job spring boot extension
- `org.jacoco:jacoco-maven-plugin` with goal `prepare-agent`

## Usage

- Include as parent
  ```xml
  <parent>
    <groupId>ch.ubique.uetlib</groupId>
    <artifactId>uetlib-spring-boot-starter-parent</artifactId>
    <version>4.1.1-2026.11.0</version>
  </parent>
  ```
- No `spring-cloud-dependencies`/`uetlib-bom`/`uetlib-self-bom` dependency management is necessary
- No plugin management section is necessary
- Set in application modules only:
  ```xml
  <build>
    <plugins>
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
      </plugin>
      <plugin>
        <groupId>com.google.cloud.tools</groupId>
        <artifactId>jib-maven-plugin</artifactId>
      </plugin>
    </plugins>
  </build>
  ```
- Set in `coverage` module only:
  ```xml
  <build>
    <plugins>
      <plugin>
        <groupId>org.jacoco</groupId>
        <artifactId>jacoco-maven-plugin</artifactId>
        <executions>
          <execution>
            <id>report-aggregate</id>
            <phase>verify</phase>
            <goals>
              <goal>report-aggregate</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
  ```

## Versioning

This project does not adhere to semantic versioning, as the SemVer space is occupied by the Spring Boot Version, which
this parent follows. We use:

```
<springBootMajor>.<springBootMinor>.<springBootPath>-<YYYY>.<MM>.<versionOfTheMonth>
```

Hence, starting from `4.1.0-2027.7.4` the next version can be one of three scenarios:

| Next Version                                           | Cause                                                                             |
|--------------------------------------------------------|-----------------------------------------------------------------------------------|
| `5.0.0-2027.7.4` / `4.2.0-2027.7.4` / `4.1.1-2027.7.4` | The Spring Boot version is updated, but the uetlib parent is otherwise unchanged. |
| `4.1.0-2027.1.0` / `4.1.0-2027.8.0` / `4.1.0-2027.7.5` | The Spring Boot version is unchanged, but the uetlib parent is updated.           |
| `5.0.0-2027.8.0` / `4.2.0-2027.8.0` / `4.1.1-2027.8.0` | Both the Spring Boot version and the uetlib parent are updated.                   |

## Changelog

See [CHANGELOG.md](CHANGELOG.md)

## License

Except where otherwise noted, original uetlib code is licensed under the [Apache License 2.0](LICENSE). Third-party files retain their original license terms; see [NOTICE](NOTICE) and any third-party notices in this repository.

## Publishing and license metadata

This parent has no default deployment destination. Consuming projects must configure their own publishing destination, such as an internal registry. Maven Central publishing is invoked explicitly by uetlib release workflows. The parent's Apache-2.0 metadata describes this parent; inheriting it does not license your application. Applications should declare their own project/license metadata rather than relying on inherited library metadata.
