# Launchpad ENV variables

- `ETH1_NETWORK_NAME`
- `ETH2_NETWORK_NAME`

----

# Eth2 Staker Checklist

## Hardware

### Recommended

- In order to process incoming validator deposits from the eth1 chain, you'll need to run an eth1 client in parallel to your eth2 client. While it is possible to use a third-party service like Infura, we recommend running your own client in order to ensure the network stays as decentralised as possible.
    - For example, you need at least 140 GB SSD to run geth fast sync on *mainnet*.

## Keystore
1. - [ ] I have securely generated and saved my keystore(s).
1. - [ ] I have backed up my mnemonic.
1. - [ ] I have set a strong password for my keystore(s)
1. - [ ] I have backed up my password. 

## Security
1. - [ ] I have secured the root account.
2. - [ ] I have hardened ssh on a random port
3. - [ ] I have set up a firewall.
4. - [ ] I have forwarded the necessary ports from my router to the correct machine(s). Only open the ports that apply to your installation:
        - [ ] Port 30303 TCP/UDP for geth
        - [ ] Port 19000 TCP/UDP for Nimbus
        - [ ] Port 9001 TCP/UDP for Teku
        - [ ] Port 9000 TCP/UDP for Lighthouse
        - [ ] Port 12000 UDP, Port 13000 TCP for Prysm
        
## Configure time sync
1.  - [ ] For Ubuntu 20.04: `sudo timedatectl set-ntp on`

## Eth1 Client

1. - [ ] I have installed and synced my Eth1 node on `ETH1_NETWORK_NAME`.

## Eth2 Beacon Node (BN)

### Required:
1. - [ ] I have installed the **latest stable software release** for my client.
    - **Note**: If you're setting up your client before phase 0 launch, it is your responsibility to check for any new software releases in the run up to launch. There is a good chance you will need to update your software.
1. - [ ] My Eth2 beacon node is able to connect to my Eth1 client via HTTP API(s).
1. - [ ] I have synced my Eth2 beacon node on `ETH2_NETWORK_NAME`.
    - **Note**: Please check that your node has greater than 20 peers.

### Recommended:
1. - [ ] I have joined my client's discord chat.
    - [Lighthouse](https://discord.gg/uC7TuaH) | [Nimbus](https://discord.gg/YbTCNat) | [Prysm](https://discord.gg/KSA7rPr) | [Teku](https://discord.gg/vZPbTfw)
1. - [ ] I have opened the ports on my router.

## Eth2 Validator Client (VC)
1. - [ ] I have imported my keystore(s) into my Eth2 validator client.
1. - [ ] I have started running my validator client.


### Recommended:
1. - [ ] I have set up my validator client on a separate machine and connected it to my Beacon Node via HTTP/gRPC API(s).

## Appendix

### Prometheus + Grafana monitor

The Eth2 clients support Prometheus + Grafana to help you visualise important real-time metrics concerning your validator. You can find client specific instructions here:

- [Lighthouse](https://github.com/sigp/lighthouse-metrics) | [Nimbus](https://status-im.github.io/nimbus-eth2/metrics-pretty-pictures.html) | [Prysm](https://docs.prylabs.network/docs/prysm-usage/monitoring/grafana-dashboard/) | [Teku](https://docs.teku.consensys.net/en/latest/HowTo/Monitor/Metrics/)

1. I have set up my [Prometheus](https://prometheus.io/) service.
1. I have set up my [Grafana](https://grafana.com/) service.
1. I have imported the dashboard config to my Grafana server and double checked that my node is alive.
    
### [POAP](https://beaconcha.in/poap) Graffiti

You can use your validator client's graffiti flag to add a personal touch to your proposed blocks (some text of your choice). You'll be able to see it using the [block explorer](https://beaconcha.in/).

1. I have set my graffiti flag.

### Advanced system architecture

1. To avoid exposing your validator identity to the network, you can use a trustworthy VPN to help reduce the risk of revealing your IP address.
1. Moreover, you can set your Validator Client (VC) and Beacon Node (BN) on separate machines and IPs so that even if your beacon node is vulnerable, your keystore is stored on a different machine.
