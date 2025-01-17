sfdx-profiles-splitter
==

A plugin for splitting and merging Salesforce profiles.

## Setup

### Install from source

1. Install the SDFX CLI.

2. Clone the repository: `git clone git@github.com:LumioHX/sfdx-profiles-splitter.git`

3. Install npm modules: `npm install`

4. Link the plugin: `sfdx plugins:link .`

## Usage
<!-- commands -->
* [`sfdx metadata:profiles:merge`](#sfdx-metadataprofilesmerge)
* [`sfdx metadata:profiles:split`](#sfdx-metadataprofilessplit)

## `sfdx metadata:profiles:merge`

Merge profiles that were split.

```
USAGE
  $ sfdx metadata:profiles:merge

OPTIONS
  -d, --delete                                    Delete the splitted profiles once merged?

  -i, --input=input                               (required) [default: src-temp/main/default/profiles/decomposed] the input
                                                  directory where the splitted profiles exist.

  -o, --output=output                             (required) [default: src-temp/main/default/profiles] the output
                                                  directory to store the full profiles.

  --json                                          format output as json

  --loglevel=(trace|debug|info|warn|error|fatal)  logging level for this command invocation

EXAMPLE

           sfdx metadata:profiles:merge -i force-app/main/default/profiles -o force-app/main/default/test
           //Merges profiles located in specified input dir and copies them into the output dir.
```

_See code: [src/commands/metadata/profiles/merge.ts](https://github.com/lodossDev/sfdx-profiles-splitter/blob/v0.1.0/src/commands/metadata/profiles/merge.ts)_

## `sfdx metadata:profiles:split`

Split profiles into smaller parts.

```
USAGE
  $ sfdx metadata:profiles:split

OPTIONS
  -d, --delete                                    Delete the existing profiles once converted?

  -i, --input=input                               (required) [default: src-temp/main/default/profiles] the input
                                                  directory where the full profiles exist.

  -o, --output=output                             (required) [default: src-temp/main/default/profiles/decomposed] the output
                                                  directory to store the chunked profiles.

  --json                                          format output as json

  --loglevel=(trace|debug|info|warn|error|fatal)  logging level for this command invocation

EXAMPLE

           sfdx metadata:profiles:split -i force-app/main/default/profiles -o force-app/main/default/test
           //Splits profiles located in specified input dir and copies them into the output dir.
```

_See code: [src/commands/metadata/profiles/split.ts](https://github.com/lodossDev/sfdx-profiles-splitter/blob/v0.1.0/src/commands/metadata/profiles/split.ts)_
<!-- commandsstop -->