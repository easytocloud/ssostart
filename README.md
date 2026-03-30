# ssostart

![release workflow](https://github.com/easytocloud/ssostart/actions/workflows/release.yml/badge.svg)

## Overview

`ssostart` is an AWS SSO login helper that intelligently selects the authentication method based on your environment:

- **VS Code** (local or remote): browser-based authentication
- **Local terminal**: browser-based authentication
- **SSH session**: device code authentication (copy/paste)

It is aws-envs aware: if you pass an environment name as the first argument, `ssostart` will point the AWS CLI at that environment's config and credentials files before initiating the SSO login.

## Installation

```bash
brew tap easytocloud/tap
brew install ssostart
```

## Usage

```bash
ssostart [ENV] [OPTIONS]
```

### Arguments

| Argument | Description |
|----------|-------------|
| `ENV` | Optional. Name of an aws-env directory under `~/.aws/aws-envs/`. Sets `AWS_CONFIG_FILE` and `AWS_SHARED_CREDENTIALS_FILE` for that environment. |
| `OPTIONS` | Any options are passed directly to `aws sso login`. |

### Examples

```bash
ssostart                              # Login with default AWS config
ssostart hc                           # Login using ~/.aws/aws-envs/hc/ config
ssostart hc --profile myprofile       # Login to a specific profile in the hc environment
ssostart --region us-east-1           # Login with a specific region
```

### Default options

Create `~/.ssostartrc` to set default options (one per line):

```
--region eu-west-1
```

## Shell completion

The Homebrew formula installs zsh completion. Tab-completing the first argument lists your available aws-envs:

```bash
ssostart <TAB>     # shows directories from ~/.aws/aws-envs/
```

## AWS Environments

`ssostart` integrates with the [aws-envs](https://github.com/easytocloud/aws-envs) concept. Place per-environment AWS config and credentials under `~/.aws/aws-envs/<name>/`:

```
~/.aws/aws-envs/
├── hc/
│   ├── config
│   └── credentials
└── prod/
    ├── config
    └── credentials
```

## Related tools

| Tool | Purpose |
|------|---------|
| [aws-envs](https://github.com/easytocloud/aws-envs) | Set up and manage aws-envs (`uvx aws-envs-setup`) |
| [sso-config-generator](https://github.com/easytocloud/sso-config-generator) | Generate AWS CLI config from SSO (`uvx sso-config-generator`) |
| [oh-my-easytocloud](https://github.com/easytocloud/oh-my-easytocloud) | zsh plugin with `asp`/`ase` for switching environments |
