## [1.1.1](https://github.com/easytocloud/ssostart/compare/v1.1.0...v1.1.1) (2026-03-30)


### Bug Fixes

* replace mapfile with while loop for bash 3.x compatibility ([488c02a](https://github.com/easytocloud/ssostart/commit/488c02a05cc64a6ee2e3000ec214d890af74b924))

# [1.1.0](https://github.com/easytocloud/ssostart/compare/v1.0.2...v1.1.0) (2026-03-30)


### Features

* auto-select sso-session when exactly one exists in config ([271527a](https://github.com/easytocloud/ssostart/commit/271527ac4eb5d91896b062b5c03a9adac3ef388b))

## [1.0.2](https://github.com/easytocloud/ssostart/compare/v1.0.1...v1.0.2) (2026-03-30)


### Bug Fixes

* simplify completion to avoid state machine issues ([f5b92e3](https://github.com/easytocloud/ssostart/commit/f5b92e3156d3d50816a4173b904d476292bfc2e3))

## [1.0.1](https://github.com/easytocloud/ssostart/compare/v1.0.0...v1.0.1) (2026-03-30)


### Bug Fixes

* correct glob pattern for aws-envs completion ([de70983](https://github.com/easytocloud/ssostart/commit/de70983e6eedeaacd030a5e2c006cca356e46162))

# 1.0.0 (2026-03-30)


### Features

* initial release of ssostart ([2c7b156](https://github.com/easytocloud/ssostart/commit/2c7b156a5fba4a8a600771d0aded8f15fbcfc6eb))

# Changelog

## [1.0.0] - Initial release

### Features

- AWS SSO login helper with intelligent browser/device-code selection
- aws-envs aware: pass an environment name to use its config/credentials
- Default options via `~/.ssostartrc`
- Zsh completion listing available aws-envs
