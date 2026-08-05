# CHANGELOG

## 4.1.0-2026.8.0

- Added property `spring-boot.version` that is always the same as the version of the `spring-boot-starter-parent`
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
