# CHANGELOG

## 4.1.1-2026.9.5

- Fix Error Prone compilation on Windows by keeping its compiler flags on one line when the compiler is forked.

## 4.1.1-2026.9.4

- `uetlib-bom` updated to
  `2026.9.1`: [Changelog/2026.9.1](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202691) [Diff/2026.9.0-2026.9.1](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.9.0...v2026.9.1)
- `uetlib-self-bom` updated to
  `5.5.0`: [Changelog/5.5.0](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#550) [Diff/5.4.3-5.5.0](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.4.3...v5.5.0)

## 4.1.1-2026.9.3

- add `uetlib-core`'s annotations `NullOrNotBlank` and `NullOrNotEmpty` as custom nullable annotations
- `uetlib-self-bom` updated to
  `5.4.3`: [Changelog/5.4.3](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#543) [Diff/5.4.2-5.4.3](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.4.2...v5.4.3)
- Update `spotless` and `kotlin.version`

## 4.1.1-2026.9.2

- `uetlib-bom` updated to
  `2026.9.2`: [Changelog/2026.9.2](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202692) [Diff/2026.9.0-2026.9.1](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.9.0...v2026.9.1)
- `uetlib-self-bom` updated to
  `5.4.2`: [Changelog/5.4.2](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#542) [Diff/5.4.0-5.4.1](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.4.0...v5.4.1)

## 4.1.1-2026.9.1

- `uetlib-bom` updated to
  `2026.9.1`: [Changelog/2026.9.1](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202691) [Diff/2026.9.0-2026.9.1](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.9.0...v2026.9.1)
- `uetlib-self-bom` updated to
  `5.4.1`: [Changelog/5.4.1](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#541) [Diff/5.4.0-5.4.1](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.4.0...v5.4.1)
- updated `spotless-maven-plugin`

## 4.1.1-2026.9.0

- Fix `sonar.coverage.jacoco.xmlReportPaths` for single-module projects: `sonar.coverage.module` now defaults to `.`
  (the root of the Maven build) instead of `${project.artifactId}`, which resolved to `<root>/<artifactId>/target/...`
  and made Sonar report *"No coverage report can be found"*. Multi-module projects are unaffected: they keep overriding
  `sonar.coverage.module` with their dedicated `{{project}}-coverage` module. Matches `uetlib-parent`
  `2026.8.4`.
- `uetlib-self-bom` updated to
  `5.4.0`: [Changelog/5.4.0](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#540) [Diff/5.3.0-5.4.0](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.3.0...v5.4.0)
- `uetlib-bom` updated to
  `2026.9.0`: [Changelog/2026.9.0](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202690) [Diff/2026.8.4-2026.9.0](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.8.4...v2026.9.0)

## 4.1.1-2026.8.7

- Spring Boot updated to `4.1.1` (`spring-boot-starter-parent` and the `spring-boot.version` property)
- `spring-cloud-dependencies` updated to `2025.1.3`
- Update `de.westemeyer:artifact-version-maven-plugin` to `3.0.0`
- `uetlib-bom` updated to
  `2026.8.4`: [Changelog/2026.8.4](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202684) [Diff/2026.8.2-2026.8.4](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.8.2...v2026.8.4)
- `uetlib-self-bom` updated to
  `5.3.0`: [Changelog/5.3.0](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#530) [Diff/5.2.0-5.3.0](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.2.0...v5.3.0)

## 4.1.0-2026.8.6

- Update `de.westemeyer:artifact-version-maven-plugin` to `2.1.0`, which is fully null-marked. Property
  `westemeyer-version-package-name` is no longer used and can be removed.

## 4.1.0-2026.8.5

- Fix `sonar.coverage.jacoco.xmlReportPaths` again

## 4.1.0-2026.8.4

- Fix `<sonar.coverage.jacoco.xmlReportPaths>` to resolve via
  `${project.basedir}/../${sonar.coverage.module}`, matching `uetlib-parent`. This also fixes the outdated comment that
  suggested setting `sonar.coverage.module` to `.` for single-module projects.
  `sonar.coverage.module` must always be a plain module name, never `.` or a path with `../` in it:
    - For single-module projects, leave it unset to inherit the default (the module's own name):
      ```xml
      <sonar.coverage.module>${project.artifactId}</sonar.coverage.module>
      ```
    - For multi-module projects, override it with the name of the module holding the aggregated jacoco report, e.g.
      ```xml
      <sonar.coverage.module>post-coverage</sonar.coverage.module>
      ```
- `uetlib-bom` updated to
  `2026.8.2`: [Changelog/2026.8.2](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202682) [Diff/2026.8.1-2026.8.2](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.8.1...v2026.8.2)
- `uetlib-self-bom` updated to
  `5.2.0`: [Changelog/5.2.0](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#520) [Diff/5.0.3-5.2.0](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.0.3...v5.2.0)
- Updated plugins

## 4.1.0-2026.8.3

- Fix `spring-boot.version`. Must be duplicated, as `project.parent.version` is always relative to the project
  executing, not the current file it is defined.

## 4.1.0-2026.8.2

- `uetlib-bom` updated to
  `2026.8.1`: [Changelog/2026.8.1](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202681) [Diff/2026.7.6-2026.8.1](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.7.6...v2026.8.1)

## 4.1.0-2026.8.1

- Added property `spring-boot.version` that is always the same as the version of the `spring-boot-starter-parent`
- Added `kapt` compiler plugin to `kotlin-maven-plugin`

## 4.1.0-2026.8.0

- `kotlin-maven-plugin` now in `pluginManagement`
- `uetlib-bom` updated to
  `2026.7.6`: [Changelog/2026.7.6](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202676) [Diff/2026.7.5-2026.7.6](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.7.5...v2026.7.6)

## 4.1.0-2026.7.13

- updated actions to not run tests twice for sonar
- `uetlib-bom` updated to
  `2026.7.5`: [Changelog/2026.7.5](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202675) [Diff/2026.7.4-2026.7.5](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.7.4...v2026.7.5)
- `uetlib-self-bom` updated to
  `5.0.3`: [Changelog/5.0.3](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#503) [Diff/5.0.2-5.0.3](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v5.0.2...v5.0.3)

## 4.1.0-2026.7.12

- Configure `spotless` with `ktfmt` for Kotlin
- `uetlib-bom` updated to
  `2026.7.4`: [Changelog/2026.7.4](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#202674) [Diff/2026.7.3-2026.7.4](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.7.3...v2026.7.4)
- `uetlib-self-bom` updated to
  `5.0.2`: [Changelog/5.0.2](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#502) [Diff/4.5.2-5.0.2](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v4.5.2...v5.0.2)

## 4.1.0-2026.7.11

- Back to SemVer-compatible CalVer. No 0-padded months
- `uetlib-bom` updated to
  `2026.7.3`: [Changelog/2026.7.3](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#241) [Diff/2026.07.1-2026.7.3](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.07.1...v2026.7.3)
- `uetlib-self-bom` updated to
  `4.5.2`: [Changelog/4.5.2](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#452) [Diff/4.5.0-4.5.2](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v4.5.0...v4.5.2)

## 4.1.0-2026.07.10

- Fix `sonar.coverage.jacoco.xmlReportPaths`. Make sure `sonar.coverage.module` is set to the correct value.
    - For a mutli module project it should be the name of the coverage module, e.g. `post-coverage`.
    - For a single module project it should be `.` (The local directory, as it is resolved relative to the project base
      dir).

## 4.1.0-2026.07.9

- Add back sonar properties

## 4.1.0-2026.07.8

- Add `unidata-all` repository
- Add default project sonar properties
- Add more plugins not just as plugin management (default usages of these do not need to be specified in the plugin or
  management section):
    - `com.diffplug.spotless:spotless-maven-plugin`: **USE IN TANDEM WITH
      `uses: UbiqueInnovation/action-systems-mvn-install@v1.2.0` to have spotless fail on formatting errors in CI but
      auto-apply locally.**
    - `de.westemeyer:artifact-version-maven-plugin`
    - `org.jacoco:jacoco-maven-plugin`
- Added to plugin management (see usage in the project below):
    - `org.apache.maven.plugins:maven-source-plugin`
    - `org.apache.maven.plugins:maven-javadoc-plugin`
  ```xml
  <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-source-plugin</artifactId>
  </plugin>
  <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-javadoc-plugin</artifactId>
  </plugin>
  ```

## 4.1.0-2026.07.7

- `uetlib-bom` updated to
  `2026.07.1`: [Changelog](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#2026071) [Diff/2026.07.0-2026.07.1](https://github.com/UbiqueInnovation/uetlib-bom/compare/v2026.07.0...v2026.07.1)
- `uetlib-self-bom` updated to
  `4.5.0`: [Changelog/4.5.0](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#450) [Diff/4.4.0-4.5.0](https://github.com/UbiqueInnovation/uetlib-self-bom/compare/v4.4.0...v4.5.0)

## 4.1.0-2026.07.6

- `uetlib-bom` updated to
  `2026.07.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#2026070)
- Fix import bom order (first import boms take precedence)

## 4.1.0-2026.07.5

- `uetlib-self-bom` updated to
  `4.4.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#440)

## 4.1.0-2026.07.4

- `uetlib-self-bom` updated to
  `4.3.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#430)

## 4.1.0-2026.07.3

- `uetlib-self-bom` updated to
  `4.2.1`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#421)

## 4.1.0-2026.07.2

- `uetlib-self-bom` updated to
  `4.2.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#420)

## 4.1.0-2026.07.1

- `uetlib-bom` updated to
  `2026.06.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#2026060)
- Updated `uetlib-self-bom` tp
  `4.1.3`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#413)
- `spotless-maven-plugin` updated to `3.8.0`

## 4.1.0-2026.07.0

Set `explicit-null-marking-level` to `ERROR` by default. Projects can (but shouldn't) opt-out of this by setting the
`explicit-null-marking-level` property to `WARN` or even `OFF`.

## 4.0.6-2026.06.0

First release.

- Add westemeyer plugin with property to change artifact package name: `westemeyer-version-package-name` (defaults to
  `${project.groupId}.version`)
- Add the `spotless` plugin to enforce code formatting. cann be autofixed with `mvn spotless:apply`
