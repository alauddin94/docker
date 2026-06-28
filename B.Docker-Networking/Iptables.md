## Check iptables Rules

```bash
sudo iptables -t nat -L -n  # Check NAT rules
sudo iptables -L DOCKER -n  # Check Docker chain
```

## iptables Disable

```bash
cat /etc/docker/daemon.json
```

```json
{
  "iptables": false,
  "ipv6": false,
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  }
}
```
