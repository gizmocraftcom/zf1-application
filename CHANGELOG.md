# Changelog

## 2.0.0

Fork of `diablomedia/zendframework1-application`, published as `gizmocraft/zendframework1-application`.

### Breaking changes

- Requires PHP `>=8.5`. Tested on PHP 8.5 and 8.6.
- Package renamed from `diablomedia/zendframework1-application` to `gizmocraft/zendframework1-application`. It now requires the `gizmocraft/zendframework1-*` packages `exception`, `loader`, `registry`, `cache`, `controller`, `http`, `layout`, `locale`, `log`, `mail`, `navigation`, `translate`, `view` and `view-helper-navigation` (each `^2.0.0`), `config` (`^3.0.0`) and `session` (`^3.0.0`).

### Other changes

- No library code changes were needed and no public signatures changed. The bootstrap resources (Cachemanager, Frontcontroller, Layout, Locale, Log, Mail, Modules, Navigation, Router, Session, Translate, UserAgent, View) were checked on PHP 8.5 and 8.6 with `error_reporting=-1`; none raised a deprecation. This package has no Db, Dojo or Multidb resource.
- Dev dependencies upgraded (PHPUnit 13, PHPStan 2.3, php-cs-fixer 3.95, GrumPHP 2.27). Dropped `composer-require-checker`, which has no release for PHP 8.6.
- Tests migrated to PHPUnit 13 attributes. The session resource tests use a small real save handler (`tests/Zend/Application/Resource/TestAsset/SaveHandler.php`) instead of an interface mock, because PHP 8.6 warns about session handlers that lack `create_sid()` and `validateId()`.
- CI runs PHP 8.5 and 8.6.
