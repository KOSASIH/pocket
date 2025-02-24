# Changelog

All notable changes to this module will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.0.0.6] - 2023-01-11

- Updated tests to reflect the updated genesis file

## [0.0.0.5] - 2023-01-10

- Updated modules constructor to accept a `bus` and not a `runtimeMgr` anymore
- Registering modules with the `bus` via `RegisterModule` method
- Providing Dependency Injection functionality via `bus`
- Updated tests and mocks accordingly

## [0.0.0.4] - 2023-01-09

- Added 'is_client_only' to `P2PConfig`

## [0.0.0.3] - 2023-01-03

- Split testing/development configs into separate files
- Centralized `NewDefaultConfig` logic with options used by the config generator
- Refactored Params handling, not hardcoded anymore but sourced from genesis

## [0.0.0.2] - 2022-12-21

- Centralized config handling into a `config` package
- Config protos from the various modules are now in the `config` package
- Removed the `BaseConfig` struct
- Removed overlapping parts in `PersistenceGenesisState` and `ConsensusGenesisState` and consolidated under a single `GenesisState` struct
- Updated tests to use the new config and genesis handling
- Introduced a singleton `keyGenerator` capable of generating keys randomly or deterministically (#414)

## [0.0.0.1] - 2022-12-14

- Added `DefaultP2PMaxMempoolCount`

## [0.0.0.0] - 2022-09-30

### [#235](https://github.com/pokt-network/pocket/pull/235) Config and genesis handling

- Abstracted config and genesis handling
- Mockable runtime
- Refactored all modules to use `RuntimeMgr`
- Updated `RuntimeMgr` to manage clock as well
- Modules now accept `interfaces` instead of paths.
- Unmarshalling is done in a new `runtime` package (runtime because what we do in there affects the runtime of the application)
- We are now able to accept configuration via environment variables (thanks to @okdas for inspiration and [sp13 for Viper]("github.com/spf13/viper"))
