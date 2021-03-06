# Final DApp
This is the final DApp you are going to develop in the Etheruem Class.

## Scope
The scope of the DApp is to show the usage of Truffle, 

* demonstrate how to work with the Ethereum Blockchain 
* Web3 
* Listen and react to specific events
* Write Test Cases
* Deploy the DApp using MetaMask or Truffle
* Work with Ganache, Go-Etheruem and other Blockchain Nodes
* Understand where Private Keys are located at
* Integrate Angular into Truffle

## Install Instructions

Developing for Ethereum is sometimes frustrating, because things change at fast pace. If something does not work as described here, please:

1. try a google search as you are 100% not alone with your problem
2. inform the instructors of the course so they can correct the problem
3. if you have the time, it would be awesome if you'd make a pull-request here

### Windows

1. Install NodeJS and the Node Package Manager (NPM)
 https://nodejs.org/en/download/

2. Install the windows-build-tools
`npm install -g windows-build-tools`

### Ubuntu

1. Install NodeJS and NPM
```
 curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
 sudo apt-get install -y nodejs
 sudo npm install -g express
```


### Other Necessary Files

Download the Genesis File either from [here](genesis.json) or directly from the [go-ethereum github page](https://github.com/ethereum/go-ethereum#operating-a-private-network). It is advised to take it directly from the official github page, as it is probably more up to date.

## Run the Project

On any OS you need Truffle 5, which is at the time of writing in Beta. The Project is optimized for Solidity 0.5.0

```
npm install -g truffle@beta
```

and then **clone this repository**
```
git clone https://github.com/tomw1808/truffle_eth_class1.git
```
and run

```
npm install
```

which installs the node components.

Additionally you need to have a geth/ganache node running (or the ethereumjs-testrpc):

```
npm install ganache-cli
```

and then start ganache-cli:

```
ganache-cli -b 3
```

then you can simply:

```
truffle migrate
```

and

```
npm start
```

which opens an HTTP Server on http://localhost:4200/

## Known Issues


### Error when installing truffle

Something like

 `... receive errors including "MSBUILD : error MSB3428: Could not load the Visual C++ component "VCBuild.exe".`

or

`... node_modules\truffle\node_modules\sha3\build\sha3.vcxproj(20,3): error MSB4019: The imported project "C:\Microsoft.Cpp.Default.props" was not found. Confirm that the path in the <Import> declaration is correct, and that the file exists on disk.".  `


Then try `npm config set msvs_version 2015 --global` and in addition you can try to install the ms-build tools:
```
npm install --global --production windows-build-tools
```

### Geth Attach

https://www.udemy.com/ethereum-developer/learn/v4/questions/1846724

On Windows its simply possible to do a `geth attach`, but on MacOS it seems that you need to provide the actual ipc file. `geth --datadir /media/user/sdcard/chaindata --ipcpath $HOME/.ethereum/geth.ipc console` which is a problem posed here: http://ethereum.stackexchange.com/questions/4472/port-30303-error-in-mist-when-i-run-geth-with-a-different-datadir


### Private Network
The way the private network is initialized changed in the past months and seems to keep changing. For better information on it, it is advised to directly see the correct instructions on:
https://github.com/ethereum/go-ethereum

_Usually_ it should work with:
```
geth init path/to/genesis.json --datadir=/path/to/some/folder
```


### Solidity Compilation Errors/Warnings
Solidity is in active maintenance and things change _all the time_! 

Any Solidity Program can be "made" to use another compiler version (older one) by defining it in the  _first line in your program_
`pragma solidity ^0.4.0;` for version 0.4.0, change it to whatever version you might need.

The code here is updated to work with solidity 0.5.0.


## Contact
If you run into any problems, don't hesitate to contact us on the course-forum at any time. If you use the forum-search function, there is a high chance that you find the answer to your problem already.
