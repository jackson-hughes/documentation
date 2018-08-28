# OpenSSH

## Configuration

Boilerplate ssh configuration:

    Host example
        Hostname example.jhcloud.io
        User jhughes
        Port 2222
        IdentityFile ~/.ssh/id_rsa
        ForwardAgent yes
        ForwardX11 yes
        ProxyJump jhughes@jumphost.jhcloud.io