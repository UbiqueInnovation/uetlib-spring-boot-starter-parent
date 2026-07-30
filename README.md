# Uetlib Spring Boot Starter Parent

This parent has the Spring Boot Starter Parent as its own parent and includes common dependency- and plugin management
for uetlib-using projects.

## Dependency Management

In the given order:

- `ch.ubique:uetlib-bom`
- `ch.ubique:uetlib-self-bom`
- `org.springframework.cloud:spring-cloud-dependencies`

## Plugin Management

- `org.springframework.boot:spring-boot-maven-plugin` with goal `build-info`
- `com.google.cloud.tools:jib-maven-plugin` with the job spring boot extension
- `org.jacoco:jacoco-maven-plugin` with goal `prepare-agent`

## Usage

- Include as parent
  ```xml
  <parent>
    <groupId>ch.ubique</groupId>
    <artifactId>uetlib-spring-boot-starter-parent</artifactId>
    <version>4.0.5-2027.7.4</version>
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
