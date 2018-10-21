# OpenSSH

## Configuration

Boilerplate ssh configuration:

`~/.ssh/id_rsa`

```bash
Host example
    Hostname example.jhcloud.io
    User jhughes
    Port 2222
    IdentityFile ~/.ssh/id_rsa
    ForwardAgent yes
    ForwardX11 yes
    ProxyJump jhughes@jumphost.jhcloud.io
```

### Further reading

[OpenSSH Cookbook](https://en.wikibooks.org/wiki/OpenSSH/Cookbook/Proxies_and_Jump_Hosts)