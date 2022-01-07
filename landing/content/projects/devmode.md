---
title: "Dev(mode)"
summary: "Dev(mode) is a project management utility for developers."
cover: { image: "images/profile/projects/devmode.png", alt: "Sensei" }
---

```
USAGE:
   dm [SUBCOMMAND]

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

SUBCOMMANDS:
    clone     Clones a utils repository in a specific folder structure.
    config    Sets options for configuration.
    fork      Clone repo and set upstream to your fork
    help      Prints this message or the help of the given subcommand(s)
    open      Opens a project on your selected text editor.
```

## Installation

#### Cargo

```
cargo install devmode
```
#### Arch Linux
```
paru -S devmode-git
```

## Configuration

The `config` or `cf` command will help you configure `dm` to your liking.

### Text Editor

You can set your favorite text editor running:

```
 dm config -e --editor
```

### Git Host

You can set your Git host running:

```
 dm config -h --host
```

### Git User

You can set your Git user running:

```
 dm config -o --owner
```

### Configure everything

You can configure everything running:

```
 dm config -a --all
```

### Show config

You can show your current config running:

```
 dm config -s --show

Current settings:
Host: GitHub
Owner: edfloreshz
Editor: Visual Studio Code
```

## Clone a repo

**Dev(mode)** facilitates repository storage and organization in your filesystem.

### How it works

When you clone a repository it will be stored to your filesystem using a specific folder structure.

You can also use ` dm cl`

```
$HOME
└── Developer
    └── host
        └── owner
            └── repo
```

This makes it easier for you to find repositories and allows `dm` to open them by just specifying the name of the
project.

### Usage

```
USAGE:
    dm clone <args>...

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

ARGS:
    <args>...    Provide either a Git <url> or a Git <host> <owner> <repo>.
```

#### Clone by URL

```bash
 dm clone https://github.com/edfloreshz/devmode
```

#### Clone without URL

```bash
 dm clone <host> <owner> <repository>
```

#### Clone with `config.toml`

Running ` dm config` asks you to specify your Git `host` and `user`, now just type one of your repos.

```bash
 dm clone <repo>
```

You can also clone multiple of your own repositories while using this option.

```bash
 dm clone <repo1> <repo2>
```

#### Just clone

You can clone without specifying the arguments.

```bash
 dm clone
```

You will be presented with the following setup:

```
ᐅ  dm clone

? Choose your Git host: ›
❯ GitHub
  GitLab
? Git username: › user
? Git repo name: › repo

Cloning edfloreshz/blog from GitHub...
```

## Clone and set upstream (fork)

Clone a repo and set upstream, ideal for forks, when you clone a repository it will be stored to your filesystem using a
specific folder structure. Similar to how ` dm cl` works.

### Usage

```
    dm fork --upstream <upstream> [args]...

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

OPTIONS:
    -u, --upstream <upstream>    Set the upstream to your fork <url>

ARGS:
    <args>...    Provide either a Git <url> or a Git <host> <owner> <repo>.

```

### Clone with url

Use the `--upstream` or `-u` to set the upstream repository, then specify the repository that you wish to modify.

```
 dm fork --upstream https://github.com/user/repo https://github.com/your-user/your-repo-fork
```

### Clone with upstream URL and remaining parameters.

```
 dm fk github <provider> <user> <forked-repo> -u <url>
```

### Just clone with the upstream URL

This will launch a clone setup and guide you throught the cloning process.

```
 dm fork -u https://github.com/user/repo
? Choose your Git host: ›
❯ GitHub
  GitLab
? Git username: › your-user
? Git repo name: › your-repo-fork

Cloning your-user/your-repo-fork from GitHub...
Setting https://github.com/user/repo how upstream
```

## Open a project

Opens a project with your selected text editor.

You can also use ` dm o`

```
USAGE:
    dm open <project>

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

ARGS:
    <project>    Provide a project name.
```

You can open a project with the following command:

```bash
 dm open <project>
```

If two or more projects with the same name are found, you will have to choose which one to open.

## Proposals

If you have a proposal for a new feature, open a new [issue](https://github.com/edfloreshz/devmode/issues).
