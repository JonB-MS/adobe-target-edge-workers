# Background
This repository tries to demonstrate how we can leverage Target ODD from an Akamai Edge worker.

# Development
There are a few prerequisites:
- Akamai credentials
- Akamai CLI
- Akamai CLI with Edge Workers plugin enabled
- Akamai contract with Edge Workers enabled

## Akamai Credentials
In order to use Akamai CLI we need credentials, using Akamai IAM we should create a so called "API Client". Once the API Client is created we can dowload the credentials and add them to `.edgerc` file in our user home directory.

To make sure we can use the credentials from `.edgerc` we will have to pass the "section" as a parameter. If we have an `.edgerc` with a section named `[default]`, then when using Akamai CLI we will have to invoke any command using this:
```bash
$ akamai --secion=default ....
```

## Tools setup
We will need to instal Akamai CLI, on Mac OS X this can be done using `Homebrew`, like this:
```bash
$ brew install akamai
```

We will need to add Edge Workers support to Akamai CLI. This can be done by running:
```bash
$ akamai install edgeworkers
```

## Code bundling
All the code can be found in the `src` folder. We will be using NPM scripts to build and package the bundle.