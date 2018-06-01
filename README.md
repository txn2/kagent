# kagent

Production Arm:
```bash
sudo docker run -d \
     --restart="always" \
     --privileged \
     --network=host \
     -v /var/run/docker.sock:/var/run/docker.sock \
     --name=kagent \
     txn2/kagent:armhf-latest
```

Development testing mounts the ./configs directory
```bash
docker stop $(docker ps -q) && docker rm $(docker ps -aq)

sudo docker run --rm \
     --privileged \
     --network=host \
     -p 2700:2700 \
     -v /var/run/docker.sock:/var/run/docker.sock \
     -v "$(pwd)/configs":/configs \
     -e AGENT_CFG_URL=file://configs/defs.json \
     -e AGENT_AUTH_URL=file://configs/defs.json \
     --name=kagent \
     txn2/txagent:1.0.4

```