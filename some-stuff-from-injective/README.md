# Some stuff from injective

## Install `cosmwasm-check`

Install the latest version of `cosmwasm-check` tool:

```shell
$ cargo +1.88.0 install cosmwasm-check --force
```

Display installed version:

```
$ cosmwasm-check --version
Contract checking 3.0.2
```

Validate the contract:

```shell
$ cosmwasm-check some-stuff.wasm
```

Output:

```text
Available capabilities: {"staking", "stargate", "cosmwasm_2_2", "cosmwasm_1_3", "cosmwasm_2_0", "iterator", "cosmwasm_1_2", "cosmwasm_1_1", "cosmwasm_2_1", "cosmwasm_1_4", "ibc2"}

some-stuff.wasm: failure
Error during static Wasm validation: Wasm contract requires unavailable capabilities: {"injective"}

Passes: 0, failures: 1
```
