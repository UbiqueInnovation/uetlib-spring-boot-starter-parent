# CHANGELOG

## 4.1.0-2026.07.4

- Updated `uetlib-self-bom` to
  `4.3.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#430)

## 4.1.0-2026.07.3

- Updated `uetlib-self-bom` to
  `4.2.1`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#421)

## 4.1.0-2026.07.2

- Updated `uetlib-self-bom` to
  `4.2.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#420)

## 4.1.0-2026.07.1

- Updated `uetlib-bom` to
  `2026.06.0`: [Changelog](https://github.com/UbiqueInnovation/uetlib-bom/blob/main/CHANGELOG.md#2026060)
- Updated `uetlib-self-bom` tp
  `4.1.3`: [Changelog](https://github.com/UbiqueInnovation/uetlib-self-bom/blob/main/CHANGELOG.md#413)
- Updated `spotless-maven-plugin` to `3.8.0`

## 4.1.0-2026.07.0

Set `explicit-null-marking-level` to `ERROR` by default. Projects can (but shouldn't) opt-out of this by setting the
`explicit-null-marking-level` property to `WARN` or even `OFF`.

## 4.0.6-2026.06.0

First release.

- Add westemeyer plugin with property to change artifact package name: `westemeyer-version-package-name` (defaults to
  `${project.groupId}.version`)
- Add the `spotless` plugin to enforce code formatting. cann be autofixed with `mvn spotless:apply`
