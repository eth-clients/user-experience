# Launchpad ENV variables

- `ETH1_NETWORK_NAME`
- `ETH2_NETWORK_NAME`

----

# Eth2 Staker Checklist

## Hardware

### Recommended

- We recommend you run the Validator Client (VC) on a separate machine from your Beacon Node (BN). This is to ensure your keystore(s) and password(s) are as secure as possible. Read [here](https://blog.ethereum.org/2019/11/27/validated-staking-on-eth2-0/) to understand more about the architecture.
- In order to process incoming validator deposits from the eth1 chain, you'll need to run an eth1 client in parallel to your eth2 client. While it is possible to use a third-party service like Infura, we recommend running your own client in order to ensure the network stays as decentralised as possible.
    - For example, you need at least 140 GB SSD to run geth fast sync on *mainnet*.

## Keystore
1. - [ ] I have securely generated and saved my keystore(s).
2. - [ ] I have backed up my mnemonic.
3. - [ ] I have set a strong password for my keystore(s)
4. - [ ] I have backed up my password. 

## Security
1. - [ ] I have set up a firewall on my machine(s).

## Eth1 Client

1. - [ ] I have installed and synced my Eth1 node on `ETH1_NETWORK_NAME`.

## Eth2 Beacon Node (BN)

### Required:
1. - [ ] I have installed the **latest stable software release** of my client.
    - **Note**: If you're setting up your client before phase 0 launch, it is your responsibility to check for any new software releases in the run up to launch. There is a good chance you will need to update your software.
1. - [ ] My Eth2 beacon node is able to connect to my Eth1 client via HTTP API(s).
1. - [ ] I have synced my Eth2 beacon node on `ETH2_NETWORK_NAME`.
    - **Note**: Please check that your node has greater than 20 peers.

### Recommended:
1. - [ ] I have joined my client's discord chat.
    - [Lighthouse](https://discord.gg/uC7TuaH) | [Nimbus](https://discord.gg/YbTCNat) | [Prysm](https://discord.gg/KSA7rPr) | [Teku](https://discord.gg/vZPbTfw)
3. - [ ] I have opened the ports on my router.

## Eth2 Validator Client (VC)
1. - [ ] I have imported my keystore(s) into my Eth2 validator client.
1. - [ ] I have started running my validator client.


### Recommended:
1. - [ ] I have set up my validator client on a separate machine and connected it to my Beacon Node via HTTP/gRPC API(s).

## [Optional] Prometheus + Grafana monitor

The Eth2 clients support Prometheus + Grafana to help you visualise important real-time metrics concerning your validator. You can find client specific instructions here:

- [Lighthouse](https://github.com/sigp/lighthouse-metrics) | [Nimbus](https://status-im.github.io/nim-beacon-chain/metrics-pretty-pictures.html) | [Prysm](https://docs.prylabs.network/docs/prysm-usage/monitoring/grafana-dashboard/) | [Teku](https://docs.teku.consensys.net/en/latest/HowTo/Monitor/Metrics/)

1. - [ ] I have set up my [Prometheus](https://prometheus.io/) service.
1. - [ ] I have set up my [Grafana](https://grafana.com/) service.
1. - [ ] I have imported the dashboard config to my Grafana server and double checked that my node is alive.
    
## [Optional] [POAP](https://beaconcha.in/poap) Graffiti

You can use your validator client's graffiti flag to add a personal touch to your proposed blocks (some text of your choice). You'll be able to see it using the [block explorer](https://beaconcha.in/).

1. - [ ] I have set my graffiti flag.
