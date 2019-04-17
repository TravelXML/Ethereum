# Ethereum
1. Install Geth

https://github.com/ethereum/go-ethereum/wiki/Installing-Geth

2. Main Network

Start

geth


Attach
Geth attach <IpcPath>
Stop
Terminate the shell

2.1 Test Network 

geth --testnet

3. RPC

https://github.com/ethereum/wiki/wiki/JSON-RPC

4. Private Network 
    
Create Genesis File

Init
geth -datadir . init genesis.json

Start
 geth -datadir . -rpc -rpcport "8545" -port "30303" -rpccorsdomain "*" -rpcapi eth,web3,personal,net

Attach
Geth attach ipc
Create account
personal.newAccount()
Mine
miner.start()
Stop Mining
miner.stop()
Check accounts
eth.accounts
Check Balance
eth.getBalance(eth.accounts[0])
Send Transaction
personal.unlockAccount(eth.accounts[0])
eth.sendTransaction({from : eth.accounts[0], to :eth.accounts[1], value: 10000})
Check Mempool
eth.getBlock('pending', true)
Mine
Check Transaction
eth.getTransaction("0x7e99b221d5883bbba209905296573d2da7d80d5eb6454d40f43e9f4373b0c561")l
Check Block
eth.getBlock(4, true)


Genesis File

{  
   "config":{  
      "chainId":4842,
      "homesteadBlock":0,
      "eip155Block":0,
      "eip158Block":0      
   },
   "difficulty":"0",
   "gasLimit":"210000000",
"parentHash":"0x0000000000000000000000000000000000000000000000000000000000000000",
   "timestamp":"0x00",
   "alloc":{  

   }
}


4.1 Attach your network

geth -datadir . -rpc -rpcport "8546" -port "3030" -rpccorsdomain "*" -rpcapi eth,web3,personal,net -bootnodes "enode://41a7ef0d0d8520c5d50b2dd15a66c846439ee69868f252f3d1a4a1ccef42f793b2fe2f67b227e220bc271309daa1783b5ee772f265d024a048e6a14854f05687@127.0.0.1:30303"

5. Generate Address with Python Script
6. Transfer some ether to address

6.1 Get Balance using python
6.1 Send Raw Transaction using python

7. Write a sample Smart Contract

pragma solidity ^0.4.25;

contract HelloWorld{
    
    function getHelloWorld() public returns(string){
        return "Hello World";
    }
    
}

8. Deploy contract on Browser with Remix

9. Deploy contract on private Network with Remix
-> Mine
-> eth.getTransactionReceipt(“”) -> get Contract Address

10. Get ABI and Byte Code
11. Interact with smart Contract with python script



