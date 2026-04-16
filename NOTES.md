## SSH Config

```
Host *
  RequestTTY yes
  Compression yes
  TCPKeepAlive yes
  SendEnv LANG LC_*
  ServerAliveCountMax 3
  ServerAliveInterval 30
  IPQoS lowdelay throughput

  # Persistent connections
  ControlMaster auto
  ControlPersist 10m
  ControlPath ~/.ssh/cm-%r@%h:%p

  # Faster handshake
  IdentitiesOnly yes
  GSSAPIAuthentication no

Host bandit
  Hostname bandit.labs.overthewire.org
  Port 2220
```
