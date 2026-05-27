# CHANGELOG

## 4.0.6-2026.06.0

First release.

- Add westemeyer plugin with proeprty to change artifact package name: `westemeyer-version-package-name` (defaults to
  `${project.groupId}.version`)
- Add the `spotless` plugin to enforce code formatting. cann be autofixed with `mvn spotless:apply`
