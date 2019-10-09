# litecoin Regtest with Electrum Server and Faucet API

* New blocks are mined automatically every 20 seconds
* Insight API: tls@56002, tcp@56001
* Faucet API: http://localhost:3002/faucet/

# Requirement
* docker & docker-compose

# Usage

Following commands are enabled under the root dir of the project.

* 1. build: `docker-compose build`
* 2. clean: `./clean-electrumx.sh`
* 3. start daemon: `docker-compose up -d`
* 4. test: `./test.sh`

## Other commands
* stop & remove daemon: `docker-compose down`
* list process: `docker-compose ps`
* login to the server: `docker-compose exec litecoind bash`
* run command: `docker-compose exec litecoind [command]`


# Electrum API example

after `$ npm install`, try `$ node rpctest.js`.

# Faucet API example

`curl -d "amount=10"  http://localhost:3001/faucet/mnJQyeDFmGjNoxyxKQC6MMFdpx77rYV3Bo`

# Other examples

```
$ docker exec --user litecoin electrumx-regtest_litecoind_1 litecoin-cli -rpcuser=electrum -rpcpassword=electrum -regtest getmininginfo
```

```
$ docker exec -it --user litecoin electrumx-regtest_litecoind_1 bash
```
