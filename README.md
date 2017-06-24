### Download Ethereum

  - mkdir /home/gi.gupta/projects/ethereum
  - cd /home/gi.gupta/projects/ethereum  
  - sudo apt-get install software-properties-common
  - sudo add-apt-repository -y ppa:ethereum/ethereum
  - sudo apt-get update
  - sudo apt-get install ethereum

### create new account in
- create new account for private network at /home/gi.gupta/projects/ethereum

- geth --datadir myPrivateNetwork2 account new

- logs:

WARN [06-23|17:59:30] No etherbase set and no accounts found as default

Your new account is locked with a password. Please give a password.

Do not forget this password.

Passphrase:

Repeat passphrase:

Address: {ef0e5806e9242cb41611267a6f1cdb95ea4a313e}

### create genesis json file(customGenesis.json)

```json

{
	"nonce": "0x0000000000000042",
	"timestamp": "0x0",
	"parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
	"extraData": "0x00",
	"gasLimit": "0x8000000",
	"difficulty": "0x400",
	"mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
	"coinbase": "0x3333333333333333333333333333333333333333",
	"config": {
	    "chainId": 15,
	    "homesteadBlock": 0,
	    "eip155Block": 0,
	    "eip158Block": 0
    },
	"alloc":{}
}

```

### geth init
geth --identity "Girish" --fast --cache=1024 --rpc  --rpcport "8013" --rpccorsdomain "*" --datadir "myPrivateNetwork2" --port "30312" --rpcapi "db,eth,net,web3,admin,debug,miner,personal,web3" --networkid 1902 --nat "any" init customGenesis.json console    
* logs

INFO [06-23|18:01:42] Allocated cache and file handles         database=/home/gi.gupta/projects/ethereum/myPrivateNetwork2/geth/chaindata cache=16 handles=16
INFO [06-23|18:01:42] Writing custom genesis block
INFO [06-23|18:01:42] Successfully wrote genesis state         database=chaindata                                                         hash=6650a0…b5c158
INFO [06-23|18:01:42] Allocated cache and file handles         database=/home/gi.gupta/projects/ethereum/myPrivateNetwork2/geth/lightchaindata cache=16 handles=16
INFO [06-23|18:01:42] Writing custom genesis block
INFO [06-23|18:01:42] Successfully wrote genesis state         database=lightchaindata                                                         hash=6650a0…b5c158



### start block chain
geth --identity "Girish" --fast --cache=1024 --rpc  --rpcport "8013" --rpccorsdomain "*" --datadir "myPrivateNetwork2" --port "30312" --rpcapi "db,eth,net,web3,admin,debug,miner,personal,web3" --networkid 1902 --nat "any" -ipcpath "/home/gi.gupta/.ethereum/geth.ipc" console

logs:

INFO [06-23|18:09:06] Starting peer-to-peer node               instance=Geth/Prashant/v1.6.6-stable-10a45cb5/linux-amd64/go1.8.1
INFO [06-23|18:09:06] Allocated cache and file handles         database=/home/gi.gupta/projects/ethereum/myPrivateNetwork2/geth/chaindata cache=1024 handles=1024
INFO [06-23|18:09:06] Initialised chain configuration          config="{ChainID: 15 Homestead: 0 DAO: <nil> DAOSupport: false EIP150: <nil> EIP155: 0 EIP158: 0 Metropolis: <nil> Engine: unknown}"
INFO [06-23|18:09:06] Disk storage enabled for ethash caches   dir=/home/gi.gupta/projects/ethereum/myPrivateNetwork2/geth/ethash count=3
INFO [06-23|18:09:06] Disk storage enabled for ethash DAGs     dir=/home/gi.gupta/.ethash                                         count=2
INFO [06-23|18:09:06] Initialising Ethereum protocol           versions="[63 62]" network=1902
INFO [06-23|18:09:06] Loaded most recent local header          number=0 hash=6650a0…b5c158 td=1024
INFO [06-23|18:09:06] Loaded most recent local full block      number=0 hash=6650a0…b5c158 td=1024
INFO [06-23|18:09:06] Loaded most recent local fast block      number=0 hash=6650a0…b5c158 td=1024
INFO [06-23|18:09:06] Starting P2P networking
INFO [06-23|18:09:08] UDP listener up                          self=enode://7d7fb16fceaab128fd46804ac446d4236c2c53e29430e68a04273cdb9deff8c78e5f5b4ec6d5505c31424ac7cc6d3d3febd803704bcfe7f48775301efb72442f@[::]:30312
INFO [06-23|18:09:08] RLPx listener up                         self=enode://7d7fb16fceaab128fd46804ac446d4236c2c53e29430e68a04273cdb9deff8c78e5f5b4ec6d5505c31424ac7cc6d3d3febd803704bcfe7f48775301efb72442f@[::]:30312
INFO [06-23|18:09:08] IPC endpoint opened: /home/gi.gupta/.ethereum/geth.ipc
INFO [06-23|18:09:08] HTTP endpoint opened: http://127.0.0.1:8013
Welcome to the Geth JavaScript console!

instance: Geth/Prashant/v1.6.6-stable-10a45cb5/linux-amd64/go1.8.1
coinbase: 0xef0e5806e9242cb41611267a6f1cdb95ea4a313e
at block: 0 (Thu, 01 Jan 1970 05:30:00 IST)
 datadir: /home/gi.gupta/projects/ethereum/myPrivateNetwork2
 modules: admin:1.0 debug:1.0 eth:1.0 miner:1.0 net:1.0 personal:1.0 rpc:1.0 txpool:1.0 web3:1.0


### start mining

* geth attach
 > miner.start(4)
null
> eth.accounts
["0xef0e5806e9242cb41611267a6f1cdb95ea4a313e"]
> eth.getBalance("0xef0e5806e9242cb41611267a6f1cdb95ea4a313e")
160000000000000000000
> eth.getBalance("0xef0e5806e9242cb41611267a6f1cdb95ea4a313e")
270000000000000000000
> eth.getBalance("0xef0e5806e9242cb41611267a6f1cdb95ea4a313e")
275000000000000000000


### downlaod etherium wallet to mange accoubt through GUI

Download https://github.com/ethereum/mist/releases
