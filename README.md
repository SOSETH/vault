# Vault

Tested on: Debian 11

This sets up Hashicorp's vault in server mode. Due to the nature of how vault is set up,
there are unfortunately some manual steps involved.

## Note
This role assumes that TLS certificates will be provisioned at:
* `/etc/vault.d/server-priv.pem` (certificate to use for vault server, including chain)
* `/etc/vault.d/server-priv.key`
* `/etc/vault.d/consul-ca.pem`
* `/etc/vault.d/consul.pem` (client cert to use for connecting to Consul)
* `/etc/vault.d/consul.key`

Bootstrap can be done by connecting to the UI after this role has been applied

## Configuration
|Var|Default value|Description|
|---|-------------|-----------|
|vault_consul_token|`undefined`|Token to use when connecting to consul|
|vault_consul_addr|`127.0.0.1:8501`|Address to use when connecting to consul|
|vault_bind_address|`0.0.0.0:8443`|Where to bind to for accepting client requests|