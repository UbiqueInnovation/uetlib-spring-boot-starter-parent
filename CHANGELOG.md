# CHANGELOG

## 4.1.0-2026.07.0

Set `explicit-null-marking-level` to `ERROR` by default. Projects can (but shouldn't) opt-out of this by setting the
`explicit-null-marking-level` property to `WARN` or even `OFF`.

## 4.0.6-2026.06.0

First release.

- Add westemeyer plugin with property to change artifact package name: `westemeyer-version-package-name` (defaults to
  `${project.groupId}.version`)
- Add the `spotless` plugin to enforce code formatting. cann be autofixed with `mvn spotless:apply`
