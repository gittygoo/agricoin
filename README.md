What is Agricoin?
-------------

Agricoin is a decentralized blockchain project built on Bitcoin's UTXO model, with support for Ethereum Virtual Machine based smart contracts, and secured by a proof of stake consensus model cloned from Agricoin. It achieves this through the revolutionary Account Abstraction Layer which allows the EVM to communicate with Agricoin's Bitcoin-like UTXO blockchain. 

Welcome to the Agricoin Ignition Main Network. This is the main network where the tokens hold value and should be guarded very carefully. If you are testing the network, or developing unstable software on Agricoin, we highly recommend using either testnet or regtest mode. 

The major features of the Agricoin network include:

1. Compatibility with the Ethereum Virtual Machine, which allows for compatibility with most existing Solidity based smart contracts. No special solidity compiler is required to deploy your smart contract to Agricoin. 
2. A Proof of Stake consensus system which is optimized for Agricoin's contract model. Any user can stake and help to secure the network. There is no voting, master nodes, or minimum amount required. There have been transactions as small as 2 Agricoin that have created blocks in the past. 
3. The Decentralized Governance Protocol is completely implemented and functional, which allows certain network parameters to be modified without a fork or other network disruption. This currently controls parameters like block size, gas prices, etc. 
4. Uses the UTXO transaction model and is compatible with Bitcoin, allowing for existing tooling and workflows to be used with Agricoin. This allows for the infamous SPV protocol to be used which is ideal for light wallets on mobile phones and IoT devices.

Note: Agricoin Core is considered beta software. We make no warranties or guarantees of its security or stability.

Agricoin Documentation and Usage Resources (TODO)
---------------
##
These are some resources that might be helpful in understanding Agricoin. Note that the unofficial documents are not created by the Agricoin team.

Basic usage resources (TODO):
<!---  
* [Official Agricoin Usage Guide](https://github.com/agricoinproject/agricoin/wiki/Agricoin-Wallet-Tutorial)
* [Unofficial Agricoin staking tutorial](https://steemit.com/agricoin/@cryptominder/agricoin-staking-tutorial-using-agricoin-qt)
* [Unofficial Agricoin staking tutorial on Raspberry Pi](https://steemit.com/agricoin/@cryptominder/agricoin-staking-tutorial-using-agricoind-on-a-raspberry-pi-3)
* [Unofficial guide for keeping your wallet safe](https://steemit.com/agricoin/@cryptominder/encrypting-backing-up-and-restoring-your-agricoin-wallet)
* [Block explorer](https://explorer.agricoin.org)
* [Unofficial block explorer](https://agricoinexplorer.io/)
* [Unofficial Raspberry Pi Web UI](https://github.com/rpiwalletui/agricoin-ui)

Development resources:

* [Deploying a custom token to Agricoin](https://blog.agricoin.org/agricoin-custom-token-walkthrough-467d725fa27d)
* [Early example faucet contract](http://earlz.net/view/2017/06/30/2144/the-agricoin-sparknet-faucet)
* [Unofficial Agricoin Hello World tutorial](https://steemit.com/agricoin/@cryptominder/quantum-agricoin-blockchain-developer-tutorial-hello-world)
* [Agricoin Book - A Developer's Guide To AGRICOIN](https://github.com/agricoinproject/agricoinbook)

General Info about Agricoin:

* [Mainnet event AMA](https://www.reddit.com/r/Agricoin/comments/6zs8t0/official_agricoin_ama_thread_starts_at_10pm_beijing/)
* [Agricoin's PoS vs CASPER](https://www.reddit.com/r/Agricoin/comments/788oa5/agricoins_pos_vs_casper_and_the_nothingatstake_problem/)
* [Technical article explaining Agricoin's PoS model in depth](http://earlz.net/view/2017/07/27/1904/the-missing-explanation-of-proof-of-stake-version)
* [Unofficial What is Agricoin article](https://storeofvalue.github.io/posts/what-is-agricoin-without-the-bullshit/)
---> 

Developer's Tools
-----------------
<!--- 
* Smart contract deployment tool
  * https://github.com/agricoinproject/solar
* DApp JavaScript Library
  * https://github.com/agricoinproject/agricoinjs
* A toolkit for building agricoin light wallets
  * https://github.com/agricoinproject/agricoinjs-wallet
* CORS agricoind RPC proxy for DApp
  * https://github.com/agricoinproject/agricoinportal
* Docker images for running agricoin services
  * https://github.com/agricoinproject/agricoin-docker
* HTTP API that powers the block explorer and the AGRICOIN web wallet
  * https://github.com/agricoinproject/insight-api
---> 

What is Agricoin Core?
------------------

Agricoin Core is our primary mainnet wallet. It implements a full node and is capable of storing, validating, and distributing all history of the Agricoin network. Agricoin Core is considered the reference implementation for the Agricoin network. 

Agricoin Core currently implements the following:

* Sending/Receiving Agricoin
* Sending/Receiving QRC20 tokens on the Agricoin network
* Staking and creating blocks for the Agricoin network
* Creating and interacting with smart contracts
* Running a full node for distributing the blockchain to other users
* "Prune" mode, which minimizes disk usage
* Regtest mode, which enables developers to very quickly build their own private Agricoin network for Dapp testing
* Compatibility with the Bitcoin Core set of RPC commands and APIs

Alternative Wallets
-------------------

Agricoin Core uses a full node model, and thus requires downloading the entire blockchain. If you do not need the entire blockchain, and do not intend on developing smart contracts, it may be more ideal to use an alternative wallet such as one of our light wallets that can be synchronized in a matter of seconds. 

### Agricoin Electrum

A light wallet that supports the Ledger hardware wallet and is based on the well known Electrum wallet software. 
<!--- 
Download: https://github.com/agricoinproject/agricoin-electrum/releases
---> 

### iOS and Android Wallets

These wallets run on mobile devices and synchronize quickly. 
<!--- 
Android Download: https://play.google.com/store/apps/details?id=org.agricoin.wallet

iOS Download: https://github.com/agricoinproject/agricoin-ios (open source, we are still working with Apple to get approval for their app store)
---> 

### Ledger Chrome Wallet

This light wallet runs in your Chrome browser as a browser extension. This wallet requires a Ledger device to use.
<!--- 
How to install: https://ledger.zendesk.com/hc/en-us/articles/115003776913-How-to-install-and-use-Agricoin-with-Ledger
---> 

Building Agricoin Core
----------

### Build on Ubuntu

    This is a quick start script for compiling Agricoin on  Ubuntu


    sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev
    sudo apt-get install software-properties-common
    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

    # If you want to build the Qt GUI:
    sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler qrencode

    git clone https://github.com/agricoinproject/agricoin --recursive
    cd agricoin

    # Note autogen will prompt to install some more dependencies if needed
    ./autogen.sh
    ./configure 
    make -j2
    
### Build on CentOS

Here is a brief description for compiling Agricoin on CentOS, for more details please refer to [the specific document](https://github.com/agricoinproject/agricoin/blob/master/doc/build-unix.md)

    # Compiling boost manually
    sudo yum install python-devel bzip2-devel
    git clone https://github.com/boostorg/boost.git
    cd boost
    git checkout boost-1.66.0
    git submodule update --init --recursive
    ./bootstrap.sh --prefix=/usr --libdir=/usr/lib64
    ./b2 headers
    sudo ./b2 -j4 install
    
    # Installing Dependencies for Agricoin
    sudo yum install epel-release
    sudo yum install libtool libdb4-cxx-devel openssl-devel libevent-devel
    
    # If you want to build the Qt GUI:
    sudo yum install qt5-qttools-devel protobuf-devel qrencode-devel
    
    # Building Agricoin
    git clone --recursive https://github.com/agricoinproject/agricoin.git
    cd agricoin
    ./autogen.sh
    ./configure
    make -j4

### Build on OSX

The commands in this guide should be executed in a Terminal application.
The built-in one is located in `/Applications/Utilities/Terminal.app`.

#### Preparation

Install the OS X command line tools:

`xcode-select --install`

When the popup appears, click `Install`.

Then install [Homebrew](https://brew.sh).

#### Dependencies

    brew install cmake automake berkeley-db4 libtool boost --c++11 --without-single --without-static miniupnpc openssl pkg-config protobuf qt5 libevent imagemagick --with-librsvg qrencode

NOTE: Building with Qt4 is still supported, however, could result in a broken UI. Building with Qt5 is recommended.

#### Build Agricoin Core

1. Clone the agricoin source code and cd into `agricoin`

        git clone --recursive https://github.com/Agricoin/agricoin.git
        cd agricoin

2.  Build agricoin-core:

    Configure and build the headless agricoin binaries as well as the GUI (if Qt is found).

    You can disable the GUI build by passing `--without-gui` to configure.

        ./autogen.sh
        ./configure
        make

3.  It is recommended to build and run the unit tests:

        make check

### Run

Then you can either run the command-line daemon using `src/agricoind` and `src/agricoin-cli`, or you can run the Qt GUI using `src/qt/agricoin-qt`

For in-depth description of Sparknet and how to use Agricoin for interacting with contracts, please see [sparknet-guide](doc/sparknet-guide.md).

License
-------

Agricoin is GPLv3 licensed.

Development Process
-------------------

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/agricoinproject/agricoin/tags) are created
regularly to indicate new official, stable release versions of Agricoin.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md).

Developer IRC can be found on Freenode at #agricoin-dev.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write [unit tests](src/test/README.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled in configure) with: `make check`. Further details on running
and extending unit tests can be found in [/src/test/README.md](/src/test/README.md).

There are also [regression and integration tests](/qa) of the RPC interface, written
in Python, that are run automatically on the build server.
These tests can be run (if the [test dependencies](/qa) are installed) with: `qa/pull-tester/rpc-tests.py`

### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.

