# SSV
Based on eth-nodes el/cl dockers running on same machine

## How to use

###
change ssvnode3 in directory name of ssv node you want to run
```bash
  sudo git clone https://github.com/smartnodecapital/ssv-node.git ssvnode3
  sudo cp docker-compose.override.example.yml docker-compose.override.yml
```

* change ports ending with required number
* ! important that ports and enviroment port are same for udp/tcp
* change container_name: ssv_node3
```docker-compose.override.yml
    ports:
      - 13003:13003/tcp
      - 12003:12003/udp
      - 15003:15000
    environment:
      - TCP_PORT=13003
      - UDP_PORT=12003

    container_name: ssv_node3
```

* make sure the right files are there
- password
- encrypted_private_key.json

```bash
  sudo docker compose up -d && sudo docker compose logs -f
```