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