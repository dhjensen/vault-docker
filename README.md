# vault-docker

[HashiCorp Vault](https://www.hashicorp.com/en/products/vault) docker compose and .hcl files example

## .env example

```bash
VAULT_VERSION=version
```

## config/config.hcl example

```hcl
ui                  = true
disable_clustering  = false
cluster_addr        = "https://url"
api_addr            = "http://0.0.0.0:8200"
disable_mlock       = false

storage "raft" {
  path      = "/path/to/vault/raft"
  node_id   = "node1"

  retry_join {
    leader_api_addr = "https://url"
  }
}

listener "tcp" {
  address       = "0.0.0.0:8200"
  tls_disable   = true
}
```
