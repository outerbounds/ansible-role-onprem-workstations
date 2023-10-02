# Onprem Workstations

This role:
* installs and starts docker
* downloads an Outerbounds PAM file and configures ssh to use
* Creates a new user named `outerbounds` and provisions with access to docker

## Requirements

This role is created to be run on Ubuntu 18.04

## Installing

```
$ ansible-galaxy role install git+https://github.com/outerbounds/ansible-role-onprem-workstations.git,<release-version>
```

## Role variables


| Variable                            | Default value                   | Description                                                                                                           |
|-------------------------------------|---------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| `outerbounds_issuer`       | `"https://issuer.example.com"`                     | The URL on which the jwks public key is hosted. The PAM will make a request on `/.well-known/jwks`|
| `outerbounds_audience`     | `"https://foo.outerbounds.com/origin"`                            | The expected audience claim on the JWT that will be enforced when users try authenticate via SSH password. |
