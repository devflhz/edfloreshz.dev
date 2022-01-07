---
title: "Sensei"
summary: "Sensei is a simple command line tool to open documentation for any crate."
cover: { image: "images/profile/projects/sensei.png", alt: "Sensei" }
---

## Installation

#### Cargo

```shell
cargo install sensei
```

#### Arch Linux

```rust
paru -S sensei
```

## Usage

```rust
sns <crate> [OPTIONS] [FLAGS]
```

### Options

```
-v, --version <version>    Opens documentation for a specific version.
-q, --query <query>      Specifies query to search documentation.
```

### Flags

```
-h, --help      Prints help information
-l, --local    Tries to open local documentation.
-m, --manifest  Looks up the version in Cargo.toml
```

### Examples

##### Opening documentation for a crate.

```rust
sns rand
```

##### Opening local documentation for a crate.

```rust
sns rand -l
sns rand --local
```

##### Specifying a version.

```rust
sns rand -v 0.7.2
sns rand --version 0.7.2
```

##### Getting version from Cargo.toml

```rust
sns rand --manifest
sns rand -m
```

##### Sending a query.

```rust
sns rand -q Rng
sns rand --query Rng
```
