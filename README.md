# WARNING: OpenEthereum has been discontinued.

# Description

This role configures [OpenEthereum](https://github.com/openethereum/openethereum) - an Eth1 client written in Rust.

# Configuration

A bare minimum would include:
```yaml

# OpenEthereum
openethereum_service_name: 'my-openeth'
openethereum_chain: 'foundation'
openethereum_mode: 'active'
openethereum_pruning: 'auto'
openethereum_identity: 'My Nimbus Sync Node'

# Ports and Addresses
openethereum_p2p_port: 30303
openethereum_rpc_port: 8545
openethereum_rpc_addr: '4.3.2.1'
openethereum_websocket_port: 8546
openethereum_websocket_addr: '1.2.3.4'
openethereum_metrics_port: 3000
```

# Management

The node is created and managed using [Docker Compose](https://docs.docker.com/compose/):
```
 > docker-compose up --force-recreate -d
Recreating nimbus-openeth-node ... done

 > docker-compose ps
       Name                      Command               State                                       Ports                                 
-----------------------------------------------------------------------------------------------------------------------------------------
my-openeth-node   /home/openethereum/openeth ...   Up      0.0.0.0:3000->3000/tcp, 0.0.0.0:30303->30303/tcp, 0.0.0.0:30303->30303/udp,   
                                                           8080/tcp, 8180/tcp, 4.3.2.1:8545->8545/tcp, 1.2.3.4:8546->8546/tcp            
```
