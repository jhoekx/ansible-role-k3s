# ansible-role-k3s

An Ansible role to set up [k3s](https://github.com/rancher/k3s).

k3s can be installed on a single node or in a cluster.

## Configuration

The `k3s_role=(server|agent)` inventory variable defines the role of the host.

Example inventory:

```
[k3s]
jh-kube01 k3s_role=server
jh-kube[02:03] k3s_role=agent`

```

In case no `k3s_role` is defined, the host will be a k3s server.

## Role Variables

The k3s version can be defined as a role variable:

```
k3s_version: 1.17.3+k3s1
k3s_binary_sha256: fcc9621a62f232f0f865dbd1ef1449315cde65052e3a71ab9ada3edab865b34f
```

Extra arguments to the [k3s server](https://rancher.com/docs/k3s/latest/en/installation/install-options/) can also be defined:

```
k3s_server_args: "--no-deploy traefik"
```
