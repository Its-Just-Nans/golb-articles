# Nix

- <https://search.nixos.org/packages>

## Current channel

```sh
nix-channel --list
```

## Delete package

```sh
nix-env --uninstall <package>
```

## Update all

```sh
nix-channel --update
nix-env -u '*'
```

## Clean store

```sh
nix-store --gc
```

## Check installed packages

```sh
nix-env --query
```
