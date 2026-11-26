# LI-text-formatter

<p align="center">
  <img src=".github/assets/flake-flow.svg" width="100%" alt="Diagram of flake.nix: the nixpkgs (nixos-unstable) and flake-utils inputs feed eachDefaultSystem, which produces an empty mkShell as devShell for x86_64-linux, aarch64-linux, x86_64-darwin and aarch64-darwin, each entered with nix develop.">
</p>

This repository is at its starting point. It contains one file, `flake.nix`,
which defines an empty Nix development shell. No formatter code has been
written yet.

## Get started

You need [Nix](https://nixos.org/download/) with flakes enabled.

```sh
git clone https://github.com/jakob1379/LI-text-formatter
cd LI-text-formatter
nix develop
```

There is no `flake.lock` in the repository, so the first `nix develop` resolves
the inputs and writes one.

## What the flake defines

| Part    | Value                                                                    |
| ------- | ------------------------------------------------------------------------ |
| Inputs  | `nixpkgs` on `nixos-unstable`, `utils` from `numtide/flake-utils`        |
| Systems | `x86_64-linux`, `aarch64-linux`, `x86_64-darwin`, `aarch64-darwin`       |
| Output  | `devShell.<system>`, a `pkgs.mkShell` with empty `buildInputs` and `shellHook` |

## Add tools to the shell

List packages in `buildInputs` inside `flake.nix`, then run `nix develop`
again:

```nix
buildInputs = with pkgs; [
  # packages go here
];
```

## License

The repository does not include a license file yet.
