# Changelog

## v.NEXT


## v1.4.1

**Bug fixes**

* Enabled the `networkId` to be passed from the contract loading query through to the loader transform function; reintroduced support for specifying the `networkId` in `truffleTransform` (`@colony/colony-js-contract-loader`)

## v1.4.0

**New features**

* Added new `ContractEvent` events subscription to `ContractClient`, allowing for simple events subscription (`@colony/colony-js-contract-client`)
* Added new task lifecycle events to `ColonyClient`, using new event subscriptions (`@colony/colony-js-contract-client`)
* Added support for sending multisig operations for tasks with one signature alone (when no other signatures are required) (`@colony/colony-js-client`)
* Added support for per-task nonce values for multisig operations; multisig operations can now be run in parallel (for different tasks) (`@colony/colony-js-client`)
* Added `TokenClient`, a means of interacting with a colony's token contract (`@colony/colony-js-client`)
* Added `AuthorityClient`, a means of interacting with a colony's authority contract (`@colony/colony-js-client`)
* Get `token` and `authority` when initializing a `ColonyClient` (`@colony/colony-js-client`)

**Enhancements**
* Refactored contract parameter validation and conversion to allow for events subscriptions (`@colony/colony-js-contract-client`)
* Refactored the contracts interface and `EthersContract` to allow for events subscription with optional transaction hashes (`@colony/colony-js-adapter`, `@colony/colony-js-adapter-ethers`)
* Ignore parameters that aren't in the spec when validating parameters (`@colony/colony-js-contract-client`)

**Documentation**
* Specify which users can call `addGlobalSkill`, `addDomain`, `setTaskRoleUser`, `setTaskDomain` and `setTaskSkill` (`@colony/colony-js-client`)

## v1.3.0

**New features**

Added `colony-js-contract-loader-fs`: load contracts from the local file-system in node.

## v1.2.1

**Documentation**

* Updated 'Getting Started', removed 'Quickstart' and reordered sections

**Enhancements**

* Validation errors in contract methods now contain the method name (`@colony/colony-js-contract-client`)
* Add a `release` command for the project, streamlined prepublish hooks, simplified and improved babel config

**Bug fixes**

* Fixed a bug where methods with default values were not validated properly (`@colony/colony-js-contract-client`)
* Fixed a bug where timestamps were not converted correctly (`@colony/colony-js-contract-client`)

## v1.2.0

**Enhancements**

* New `ipfsHash` parameter type, to more easily store/retrieve IPFS hashes from the contracts (`@colony/colony-js-contract-client`)
* Implement the `ipfsHash` type in `ColonyClient`: `getTask`, `createTask`, `submitTaskDeliverable`, `setTaskBrief` (`@colony/colony-js-client`)
* Add a `date` parameter type and implement it in `ColonyClient`: `getTask`, `getTaskWorkRatings`, `setTaskDueDate` (`@colony/colony-js-client`)
* Add a default value (1) for `ColonyClient.createTask` (`@colony/colony-js-client`)

**Bug fixes**

* Ensure that the returned values in `ColonyClient.getTask` were handled properly (`@colony/colony-js-client`)
* Clean 'empty' hex strings for IPFS hash output validation (`@colony/colony-js-contract-client`)

## v1.1.4

**Documentation**

* Updated the Quickstart and Get Started documentation; these guides now show how to use an `ethers` wallet, use `require` statements over `import`, and provide some additional information about prerequisites.

**Bug fixes**

* Define the `defaultGasLimit` property of Senders as a number as opposed to a `BigNumber` (`@colony/colony-js-contract-client`)

## v1.1.3

**Enhancements**

* The nonce value is now carried through when serializing and restoring MultisigOperations (`@colony/colony-js-contract-client)`

**Maintenance**

* Update `ethers` to `3.0.17` (`@colony/colony-js-adapter-ethers)`
* Use `fixed` mode in `lerna.json` (see [here](https://github.com/lerna/lerna#fixedlocked-mode-default))

**Bug fixes**

* Fix `ROLES` values to reflect contracts (`@colony/colony-js-client`)
* Fixed a bug where `MultisigOperation`s erroneously had required signees reset upon restoring an operation (`@colony/colony-js-contract-client)`

## v1.1.2

* Bumped versions of packages/interdependencies

## v1.1.1

**Bug fixes**

* Fixed the documentation site link in the `README`
* Fixed a bug where string input values were not converted properly (`@colony/colony-js-contract-client`)

## v1.1.0

**Documentation**

* General documentation updates
* Added automatic documentation generation for `@colony/colony-js-client` (`yarn build:docs`, also runs on precommit hook)

**New features**

* Added method `ColonyNetworkClient.getMetaColonyClient`
* Added Caller `ColonyClient.getDomain`
* Added `bignumber` parameter type for contract methods
* Added `role` parameter type for contract methods
* Added declarative parameter type mapping for contract methods, and `addParamType` method

**Enhancements**

* Better handling for empty values from contracts; e.g. addresses reported as '0x000...0' are cleaned as `null`
* Failed validation reasons are now added to error messages
* Updated `ColonyNetworkClient`/`ColonyClient` to match `colonyNetwork`
* Upon starting or restoring a `MultisigOperation`, the operation is refreshed to get the latest values
* Removed separate error/success contract event handling

**Bug fixes**

* Fixed a bug where the isBigNumber utility function didn't look for the correct property in ethers-ified BigNumbers
* Add `babel-runtime dependency`


## v1.0.0

*Released Tue, 22 May 2018 17:19:06 GMT*

* First release.
