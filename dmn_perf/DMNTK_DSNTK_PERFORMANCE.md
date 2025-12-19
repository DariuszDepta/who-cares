# Performance comparison

## Compiling crates

Tested commands:

```shell
cargo install dmntk --force
```

```shell
cargo install dsntk --force
```

Tested versions:

- dmntk: v0.3.7
- dsntk: v0.2.0

### macOS

macOS Tahoe 26.2, M4 Pro (12 cores), 64GB unified memory

|        [dmntk] |        [dsntk] |
|---------------:|---------------:|
|          24.98 |          27.44 |
|          24.66 |          26.60 |
|          25.16 |          26.35 |
|          25.03 |          26.72 |
|          25.14 |          26.63 |
|          25.86 |          27.59 |
|          25.41 |          26.50 |
|          25.92 |          26.71 |
|          24.93 |          26.28 |
|          24.95 |          26.34 |
| avg: **25.20** | avg: **26.72** |


[dmntk]: https://crates.io/crates/dmntk
[dsntk]: https://crates.io/crates/dsntk
             
### Fedora Linux 43

#### Intel Core® i5

Intel Core® i5-8500T CPU@2.1GHz


## Useful commands

Check memory details:

```shell
sudo dmidecode --type memory
```

Check processor details:

```shell
lscpu
```
