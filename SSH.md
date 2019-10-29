### Env variables forwarding

client part
```
grep SendEnv .ssh/config
SendEnv AWS_ACCESS_KEY_ID
SendEnv AWS_SECRET_ACCESS_KEY
SendEnv AWS_SESSION_TOKEN
SendEnv AWS_DEFAULT_REGION

```

server part
```
grep AcceptEnv /etc/ssh/sshd_config
AcceptEnv AWS_ACCESS_KEY_ID AWS_SECRET_ACCESS_KEY AWS_SESSION_TOKEN AWS_DEFAULT_REGION
```


### Secure knownhosts
HashKnownHosts yes в ssh/config
SSH
https://habr.com/en/post/122445/
https://habr.com/en/post/435546


### Proxy
proxycommand vs proxyjump ProxyCommand ssh host_here -W %h:%p
https://en.wikibooks.org/wiki/OpenSSH/Cookbook/Proxies_and_Jump_Hosts

### Prevent key auth

```
ssh -o "PubkeyAuthentication no" username@hostname
```

### How to debug ssh forwarding

```
ssh-add -l
```

### How to avoid host key checking

```
ssh -o StrictHostKeyChecking=no cloud-user@188.42.225.33
```

### Others people wisdom

http://tom.scogland.com/blog/2012/07/04/ssh-tricks/
https://blog.tjll.net/ssh-kung-fu/
http://matt.might.net/articles/ssh-hacks/
