# Molecule

[Molecule](https://molecule.readthedocs.io/en/latest/) is a complete test framework for ansible roles.

## Test suite

1.  Lint
2.  Dependency
3.  Syntax
4.  Convergence
5.  Idempotence

## Configuration

Add molecule to existing role:

```
molecule init scenario --scenario-name default --verifier-name testinfra --driver-name docker --role-name $ROLENAME
```

Create new role with molecule framework:

```
molecule init role --role-name $ROLENAME --verifier-name testinfra --driver-name docker
```

To run molecule inside a docker container:

```
docker run --rm -it -v "$(pwd)":/tmp/$(basename "${PWD}"):ro \
-v /var/run/docker.sock:/var/run/docker.sock \
-w /tmp/$(basename "${PWD}") quay.io/ansible/molecule:2.20 \
molecule test
```

To use molecule inside a docker container transparently add the following to your shell rc file (bashrc, zshrc, etc.)

```
alias 'molecule=docker run --rm -it -v "$(pwd)":/tmp/$(basename "${PWD}"):ro -v /var/run/docker.sock:/var/run/docker.sock -w /tmp/$(basename "${PWD}") quay.io/ansible/molecule:2.20 molecule'
```

You can then invoke molecule simply with `molecule`. For example, `molecule test`, abstracting the docker stuff away from usage.