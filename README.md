<p align="center">
<img
    src="https://repository-images.githubusercontent.com/204357600/6e429f00-c7a2-11e9-8761-a838f0f01e23"
    width="250px">
</p>

<p align="center">      
  <a href="https://travis-ci.org/george-key/geo-node">
    <img src="https://travis-ci.org/george-key/geo-node.svg?branch=master" alt="Current TravisCI build status.">
  </a>
  <a href="https://github.com/george-key/geo-node/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  </a>
  <a href="https://github.com/george-key/geo-node/releases">
    <img src="https://badge.fury.io/gh/george-key%2Fgeo-node.svg" alt="Current geo-node version.">
  </a>    
</p>

## Prerequisites

You will need Window, Linux or macOS. Ubuntu 14 and 16 are supported. Ubuntu 17 is not supported.

Install [.NET Core](https://www.microsoft.com/net/download/core).

On Linux, install the LevelDB and SQLite3 dev packages. E.g. on Ubuntu:

```sh
sudo apt-get install libleveldb-dev sqlite3 libsqlite3-dev libunwind8-dev
```

On macOS, install the LevelDB package. E.g. install via Homebrew:

```
brew install --ignore-dependencies --build-from-source leveldb
```

On Windows, use the [Neo version of LevelDB](https://github.com/neo-project/leveldb).

## Download pre-compiled binaries

See also [official docs](http://docs.neo.org/en-us/node/introduction.html). Download and unzip [latest release](https://github.com/neo-project/neo-cli/releases).

```sh
dotnet neo-cli.dll
```

## Compile from source

Clone the neo-cli repository.

```sh
cd neo-cli
dotnet restore
dotnet publish -c Release
```
In order to run, you need .NET Core. Download the SDK [binary](https://www.microsoft.com/net/download/linux).

Assuming you extracted .NET in the parent folder:

```sh
../dotnet bin/Release/netcoreapp1.0/neo-cli.dll .
```
## Build into Docker

Clone the neo-cli repository.

```sh
cd neo-cli
docker build -t neo-cli .
docker run -p 10332:10332 -p 10333:10333 --name=neo-cli-mainnet neo-cli
```

After start the container successfully, use the following scripts to open geo-node interactive window:

```sh
docker exec -it neo-cli-mainnet /bin/bash
screen -r node
```

## Logging

To enable logs in neo-cli, you need to add the ApplicationLogs plugin. Please check [here](https://github.com/george-key/geo-plugins) for more information.


## Bootstrapping the network.
In order to synchronize the network faster, please check [here](http://docs.neo.org/en-us/network/syncblocks.html).


## Usage

See [documentation](https://docs.neo.org/en-us/node/cli/cli.html). E.g. try `show state` or `create wallet wallet.json`.
