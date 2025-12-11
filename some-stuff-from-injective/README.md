# Some stuff from injective

## 1.88.0-x86_64-unknown-linux-gnu

### Install `cosmwasm-check`

Install the latest version of `cosmwasm-check` tool:

```shell
cargo +1.88.0 install cosmwasm-check --force
```

Display installed version:

```
$ cosmwasm-check --version
Contract checking 3.0.2
```

### Validate the contract

```shell
cosmwasm-check some-stuff.wasm
```

Output:

```text
Available capabilities: {"staking", "stargate", "cosmwasm_2_2", "cosmwasm_1_3", "cosmwasm_2_0", "iterator", "cosmwasm_1_2", "cosmwasm_1_1", "cosmwasm_2_1", "cosmwasm_1_4", "ibc2"}

some-stuff.wasm: failure
Error during static Wasm validation: Wasm contract requires unavailable capabilities: {"injective"}

Passes: 0, failures: 1
```

### Validate the contract again (with extended capability list)

```shell
cosmwasm-check --available-capabilities "staking,stargate,cosmwasm_2_2,cosmwasm_1_3,cosmwasm_2_0,iterator,cosmwasm_1_2,cosmwasm_1_1,cosmwasm_2_1,cosmwasm_1_4,ibc2,injective" some-stuff.wasm
```

Output:

```text
Available capabilities: {"cosmwasm_1_1", "iterator", "stargate", "cosmwasm_1_2", "cosmwasm_2_2", "injective", "cosmwasm_2_1", "ibc2", "staking", "cosmwasm_1_3", "cosmwasm_1_4", "cosmwasm_2_0"}

some-stuff.wasm: pass

All contracts (1) passed checks!
```

## 1.88.0-aarch64-apple-darwin

### Install `cosmwasm-check`

Install the latest version of `cosmwasm-check` tool:

```shell
cargo +1.88.0 install cosmwasm-check --force
```

Display installed version:

```
$ cosmwasm-check --version
Contract checking 3.0.2
```

### Validate the contract

```shell
cosmwasm-check some-stuff.wasm
```

Output:

```text
Available capabilities: {"staking", "stargate", "cosmwasm_2_2", "cosmwasm_1_3", "cosmwasm_2_0", "iterator", "cosmwasm_1_2", "cosmwasm_1_1", "cosmwasm_2_1", "cosmwasm_1_4", "ibc2"}

some-stuff.wasm: failure
Error during static Wasm validation: Wasm contract requires unavailable capabilities: {"injective"}

Passes: 0, failures: 1
```

### Validate the contract again (with extended capability list)

```shell
cosmwasm-check --available-capabilities "staking,stargate,cosmwasm_2_2,cosmwasm_1_3,cosmwasm_2_0,iterator,cosmwasm_1_2,cosmwasm_1_1,cosmwasm_2_1,cosmwasm_1_4,ibc2,injective" some-stuff.wasm
```

Output:

```text
Available capabilities: {"stargate", "cosmwasm_1_2", "cosmwasm_1_1", "cosmwasm_2_1", "cosmwasm_2_2", "cosmwasm_2_0", "cosmwasm_1_4", "ibc2", "cosmwasm_1_3", "iterator", "staking", "injective"}

some-stuff.wasm: failure
Error compiling Wasm: Could not compile: Compilation error: Assembler failed finalization with: ImpossibleRelocation(Dynamic(DynamicLabel(0)))

Passes: 0, failures: 1
```

So, there is an error during compilation (processor Apple Silicon M4):

```text
Error compiling Wasm: Could not compile: Compilation error: Assembler failed finalization with: ImpossibleRelocation(Dynamic(DynamicLabel(0)))
```
