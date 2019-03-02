[![npm version](https://badge.fury.io/js/msbot.svg)](https://badge.fury.io/js/cogLint)

# CogTracker 

This library allows reading, validating, indexing, modifying and writing [Bot Framework](https://dev.botframework.com/) .schema, .cog and .lg files utilizing an in-memory cache.  It reads in cog files and captures errors in them so that they can be presented as issues to be fixed.  It also provides indexing to help tools maniuplate the information in the files.  It builds an index of .cog components and how they relate to each other using $type, $role, $id and $copy.  It captures:
* **Missing $type:** A valid component must include a $type.
* **Multiple $id definitions:** There should be only one definition for a $id.
* **Incompatible types between $copy and $id:** 
* **Undefined $id** 
* **Schema validation:** Reports JSON schema validation errors.
* **Malformed JSON:** Reports files which do not contain valid JSON.
* **Multiple definitions of .lg template references:**
References to definitions show up in this format `TYPE[ID](file#/path)`.  

## Using
The main class is the [`CogTracker`](docs/classes/_cogtracker_.cogtracker.html) class which supports reading, updating, writing and indexing cog files with both schema and semantic validation.  The [`CogLint`](../coglint/src/cogLint.ts) tool shows an example of how to use the tracker to read in files and report various kinds of errors.

## Prerequisite

- [Node.js](https://nodejs.org/) version 8.5 or higher

## Installation

To install using npm:

```shell
npm install -g cogLint
```

This will install cogLint into your global path.

To uninstall using npm:

```shell
npm uninstall -g cogLint
```
## Nightly builds

Nightly builds are based on the latest development code which means they may or may not be stable and probably won't be documented. These builds are better suited for more experienced users and developers although everyone is welcome to give them a shot and provide feedback.

You can get the latest nightly build of CogLint from the [BotBuilder MyGet](https://botbuilder.myget.org/gallery) feed. To install the nightly - 

```shell
npm config set registry https://botbuilder.myget.org/F/botbuilder-tools-daily/npm/
```

Install using npm:
```shell
npm i -g msbot
```

To reset registry:
```shell
npm config set registry https://registry.npmjs.org/
```